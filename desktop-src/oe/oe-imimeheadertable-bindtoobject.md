---
title: IMimeHeaderTable BindToObject method
description: Obtains an IMimeAddressTable or IMimePropertySet interface from the current object.
ms.assetid: '7dbd5e2f-1b84-4bdb-9a26-879c7c5dd93f'
keywords: ["BindToObject method Windows Mail (formerly Outlook Express)", "BindToObject method Windows Mail (formerly Outlook Express) , IMimeHeaderTable interface", "IMimeHeaderTable interface Windows Mail (formerly Outlook Express) , BindToObject method"]
topic_type:
- apiref
api_name:
- IMimeHeaderTable.BindToObject
api_location:
- Inetcomm.dll
api_type:
- COM
---

# IMimeHeaderTable::BindToObject method

Obtains an [**IMimeAddressTable**](oe-imimeaddresstable.md) or [**IMimePropertySet**](oe-imimepropertyset.md) interface from the current object.

## Syntax


```C++
HRESULT BindToObject(
  [in]��REFIID riid,
  [out]�void ��**ppvObject
);
```



## Parameters

<dl> <dt>

*riid* \[in\]
</dt> <dd>

Type: **REFIID**

Specifies the requested interface ID. Valid values for this parameter include: IID\_IMimeAddressTable and IID\_IMimePropertySet.

</dd> <dt>

*ppvObject* \[out\]
</dt> <dd>

Type: **void\*\***

Receives the address of a pointer to the specified interface. The client is responsible for releasing this interface.

</dd> </dl>

## Return value

Type: **HRESULT**

Returns one of the following values.



| Return code                                                                                   | Description                                                                  |
|-----------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| <dl> <dt>**S\_OK**</dt> </dl>          | Indicates success. <br/>                                               |
| <dl> <dt>**E\_NOINTERFACE**</dt> </dl> | Indicates that the interface ID specified by *riid* is not valid.<br/> |
| <dl> <dt>**E\_INVALIDARG**</dt> </dl>  | Indicates that *ppvObject* is **NULL**.<br/>                           |



�

## Requirements



|                                     |                                                                                                                |
|-------------------------------------|----------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�XP \[desktop apps only\]<br/>                                                                    |
| Minimum supported server<br/> | Windows Server�2003 \[desktop apps only\]<br/>                                                           |
| Product<br/>                  | Outlook Express 6.0<br/>                                                                                 |
| Header<br/>                   | <dl> <dt>Mimeole.h</dt> </dl>                           |
| IDL<br/>                      | <dl> <dt>Mimeole.idl</dt> </dl>                         |
| DLL<br/>                      | <dl> <dt>Inetcomm.dll (version 6.0 or later)</dt> </dl> |



�

�




