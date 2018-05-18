﻿---
Description: 'The Refresh method refreshes FaxActivityLogging object information from the fax server.'
ms.assetid: '318b9900-544a-46e1-bd0d-af161df660bd'
title: 'FaxActivityLogging.Refresh method'
---

# FaxActivityLogging.Refresh method

The **Refresh** method refreshes [**FaxActivityLogging**](-mfax-faxactivitylogging.md) object information from the fax server.

## Syntax


```VB
FaxActivityLogging.Refresh() As Long
```



## Parameters

This method has no parameters.

## Remarks

When the **Refresh** method is called, any configuration changes made after the last [**Save**](-mfax-faxactivitylogging-save-vb.md) method call are lost.

To use this method, a user must have the [****farQUERY\_CONFIG****](-mfax-fax-access-rights-enum.md) access right.

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP \[desktop apps only\]<br/>                                             |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                    |
| Header<br/>                   | <dl> <dt>FaxComex.h</dt> </dl>   |
| DLL<br/>                      | <dl> <dt>Fxscomex.dll</dt> </dl> |



## See also

<dl> <dt>

[Visual Basic Example](-mfax-setting-logging-options.md)
</dt> <dt>

[**FaxActivityLogging**](-mfax-faxactivitylogging.md)
</dt> <dt>

[**IFaxActivityLogging**](-mfax-faxactivitylogging-cpp.md)
</dt> </dl>

 

 



