---
Description: 'The Active method notifies the pin that the filter is now active.'
ms.assetid: 'c2b8eb54-1bae-4f52-8324-dc70e3cac577'
title: 'CDynamicOutputPin.Active method'
---

# CDynamicOutputPin.Active method

The `Active` method notifies the pin that the filter is now active.

## Syntax


```C++
HRESULT Active();
```



## Parameters

This method has no parameters.

## Return value

Returns an **HRESULT** value. Possible values include those shown in the following table.



| Return code                                                                            | Description                                                                                                     |
|----------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|
| <dl> <dt>**S\_OK**</dt> </dl>   | Success.<br/>                                                                                             |
| <dl> <dt>**E\_FAIL**</dt> </dl> | Failure. [**CDynamicOutputPin::SetConfigInfo**](cdynamicoutputpin-setconfiginfo.md) was not called.<br/> |



�

## Remarks

This method overrides the [**CBaseOutputPin::Active**](cbaseoutputpin-active.md) method. It resets the [**CDynamicOutputPin::m\_hStopEvent**](cdynamicoutputpin-m-hstopevent.md) event. If the owning filter has not called **SetConfigInfo**, this method returns E\_FAIL.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Amfilter.h (include Streams.h)</dt> </dl>                                                                                  |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CDynamicOutputPin Class**](cdynamicoutputpin.md)
</dt> </dl>

�

�



