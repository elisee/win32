---
Description: 'The streaming audio renderer (SAR) is a media sink that renders audio.'
ms.assetid: '5884a128-597d-432b-a706-e10c894d7965'
title: Streaming Audio Renderer
---

# Streaming Audio Renderer

The streaming audio renderer (SAR) is a media sink that renders audio. Each instance of the SAR renders a single audio stream. To render multiple streams, use multiple instances of the SAR.

To create the SAR, call either of the following functions:

-   [**MFCreateAudioRenderer**](mfcreateaudiorenderer.md). Returns a pointer to the SAR.
-   [**MFCreateAudioRendererActivate**](mfcreateaudiorendereractivate.md). Returns a pointer to an activation object, which can be used to create the SAR.

The second function, which returns an activation object, is required if you are playing protected content, because the activation object must be serialized to the protected process. For clear content, you can use either function.

The SAR can receive uncompressed audio in either PCM or IEEE floating-point format. If the playback rate is faster or slower than 1×, the SAR automatically adjusts the pitch.

## Configuring the Audio Renderer

The SAR supports several configuration attributes. The mechanism for setting these attributes depends on which function you call to create the SAR. If you use the [**MFCreateAudioRenderer**](mfcreateaudiorenderer.md) function, do the following:

1.  Create a new attribute store by calling [**MFCreateAttributes**](mfcreateattributes.md).
2.  Add the attributes to the attribute store.
3.  Pass the attribute store to the [**MFCreateAudioRenderer**](mfcreateaudiorenderer.md) function in the *pAudioAttributes* parameter.

If you use the [**MFCreateAudioRendererActivate**](mfcreateaudiorendereractivate.md) function, the function returns a pointer to the [**IMFAttributes**](imfattributes.md) interface in the *ppActivate* parameter. Use this pointer to add the attributes.

For a list of configuration attributes, see [Audio Renderer Attributes](audio-renderer-attributes.md).

## Selecting the Audio Endpoint Device

An *audio endpoint device* is a hardware device that either renders or captures audio. Examples include speakers, headphones, microphones, and CD players. The SAR always uses an audio rendering device. There are two ways to select the device.

The first approach is to enumerate the audio rendering devices on the system, using the [**IMMDeviceEnumerator**](coreaudio.immdeviceenumerator) interface. This interface is documented in the core audio API documentation.

1.  Create the device enumerator object.
2.  Use the device enumerator to enumerate audio rendering devices. Each device is represented by a pointer to the [**IMMDevice**](coreaudio.immdevice) interface.
3.  Select a device, based on the device properties or the user's selection.
4.  Call [**IMMDevice::GetId**](coreaudio.immdevice_getid) to get the device identifier.
5.  Set the device identifier as the value of the [**MF\_AUDIO\_RENDERER\_ATTRIBUTE\_ENDPOINT\_ID**](mf-audio-renderer-attribute-endpoint-id-attribute.md) attribute.

Rather than enumerate devices, you can specify the audio device by its *role*. An audio role identifies a general category of usage. For example, the *console* role is defined for games and system notifications, while the *multimedia* role is defined for music and movies. Each role has one audio rendering device assigned to it, and the user can change these assignments. If you specify a device role, the SAR uses whatever audio device has been assigned for that role. To specify the device role, set the [**MF\_AUDIO\_RENDERER\_ATTRIBUTE\_ENDPOINT\_ROLE**](mf-audio-renderer-attribute-endpoint-role-attribute.md) attribute.

The two attributes listed in this section are mutually exclusive. If you do not set either of them, the SAR uses the audio device that is assigned to the **eConsole** role.

The following code enumerates the audio rendering devices and assigns the first device in the list to the SAR. This example uses the [**MFCreateAudioRenderer**](mfcreateaudiorenderer.md) function to create the SAR.


```C++
#include <mmdeviceapi.h>

HRESULT hr = S_OK;

IMMDeviceEnumerator *pEnum = NULL;      // Audio device enumerator.
IMMDeviceCollection *pDevices = NULL;   // Audio device collection.
IMMDevice *pDevice = NULL;              // An audio device.
IMFAttributes *pAttributes = NULL;      // Attribute store.
IMFMediaSink *pSink = NULL;             // Streaming audio renderer (SAR)

LPWSTR wstrID = NULL;                   // Device ID.

// Create the device enumerator.
hr = CoCreateInstance(
    __uuidof(MMDeviceEnumerator), 
    NULL,
    CLSCTX_ALL, 
    __uuidof(IMMDeviceEnumerator), 
    (void**)&amp;pEnum
    );

// Enumerate the rendering devices.
if (SUCCEEDED(hr))
{
    hr = pEnum->EnumAudioEndpoints(eRender, DEVICE_STATE_ACTIVE, &amp;pDevices);
}

// Get ID of the first device in the list.
if (SUCCEEDED(hr))
{
    hr = pDevices->Item(0, &amp;pDevice);
}

if (SUCCEEDED(hr))
{
    hr = pDevice->GetId(&amp;wstrID);
}

// Create an attribute store and set the device ID attribute.
if (SUCCEEDED(hr))
{
    hr = MFCreateAttributes(&amp;pAttributes, 2);
}

if (SUCCEEDED(hr))
{
    hr = pAttributes->SetString(
        MF_AUDIO_RENDERER_ATTRIBUTE_ENDPOINT_ID, 
        wstrID
        );
}

// Create the audio renderer.
if (SUCCEEDED(hr))
{
    hr = MFCreateAudioRenderer(pAttributes, &amp;pSink);    
}

SAFE_RELEASE(pEnum);
SAFE_RELEASE(pDevices);
SAFE_RELEASE(pDevice); 
SAFE_RELEASE(pAttributes);
CoTaskMemFree(wstrID);
```



To create the activation object for the SAR, change the code that appears after the call to [**IMMDevice::GetId**](coreaudio.immdevice_getid) to the following:


```C++
IMFActivate *pActivate = NULL;          // Activation object.

if (SUCCEEDED(hr))
{
    hr = MFCreateAudioRendererActivate(&amp;pActivate);    
}

if (SUCCEEDED(hr))
{
    hr = pActivate->SetString(
        MF_AUDIO_RENDERER_ATTRIBUTE_ENDPOINT_ID, 
        wstrID
        );
}

SAFE_RELEASE(pActivate);
```



## Selecting the Audio Session

An audio session is a group of related audio streams that an application can manage collectively. The application can control the volume level and mute state of each session. Sessions are identified by GUID. To specify the audio session for the SAR, use the [MF\_AUDIO\_RENDERER\_ATTRIBUTE\_SESSION\_ID](mf-audio-renderer-attribute-session-id-attribute.md) attribute. If you do not set this attribute, the SAR joins the default session for that process, identified by **GUID\_NULL**.

By default, an audio session is process-specific, meaning it contains only streams from the calling process. To join a cross-process session, set the [MF\_AUDIO\_RENDERER\_ATTRIBUTE\_FLAGS](mf-audio-renderer-attribute-flags-attribute.md) attribute with the value **MF\_AUDIO\_RENDERER\_ATTRIBUTE\_FLAGS\_CROSSPROCESS**.

After you create the SAR, you use the [**IMFAudioPolicy**](imfaudiopolicy.md) interface to join the session to a group of sessions, all of which are controlled by the same volume control in the control panel. You can also use this interface to set the display name and the icon that appear in the volume control.

## Controlling Volume Levels

To control the master volume level of all the streams in the SAR's audio session, use the [**IMFSimpleAudioVolume**](imfsimpleaudiovolume.md) interface. To control the volume of an individual stream, or to control the volume of individual channels within a stream, use the [**IMFAudioStreamVolume**](imfaudiostreamvolume.md) interface. Both interfaces are obtained by calling [**IMFGetService::GetService**](imfgetservice-getservice.md). You can call **GetService** directly on the SAR, or call it on the Media Session. Volume levels are expressed as attenuation values. For each channel, the attenuation level is the product of the master volume and the channel volume.

## Related topics

<dl> <dt>

[Audio/Video Playback](audio-video-playback.md)
</dt> </dl>

 

 


