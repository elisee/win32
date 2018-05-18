﻿---
Description: 'Specifies access control permissions for a directory on a smart card.'
ms.assetid: '361d9fa0-286e-4d2c-8452-3b5f48e77779'
title: 'CARD\_DIRECTORY\_ACCESS\_CONDITION enumeration'
---

# CARD\_DIRECTORY\_ACCESS\_CONDITION enumeration

The **CARD\_DIRECTORY\_ACCESS\_CONDITION** enumeration specifies access control permissions for a directory on a [*smart card*](security.s_gly#-security-smart-card-gly).

## Syntax


```C++
typedef enum  { 
  InvalidAc               = 0,
  UserCreateDeleteDirAc   = 1,
  AdminCreateDeleteDirAc  = 2
} CARD_DIRECTORY_ACCESS_CONDITION;
```



## Constants

<dl> <dt>

<span id="InvalidAc"></span><span id="invalidac"></span><span id="INVALIDAC"></span>**InvalidAc**
</dt> <dd>

This value is not valid.

</dd> <dt>

<span id="UserCreateDeleteDirAc"></span><span id="usercreatedeletedirac"></span><span id="USERCREATEDELETEDIRAC"></span>**UserCreateDeleteDirAc**
</dt> <dd>

Specific users can read, write, and delete the directory.

</dd> <dt>

<span id="AdminCreateDeleteDirAc"></span><span id="admincreatedeletedirac"></span><span id="ADMINCREATEDELETEDIRAC"></span>**AdminCreateDeleteDirAc**
</dt> <dd>

Administrators can read, write, and delete the directory.

</dd> </dl>

## Requirements



|                                     |                                                                                      |
|-------------------------------------|--------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP, Windows XP \[desktop apps only\]<br/>                              |
| Minimum supported server<br/> | Windows Server 2003, Windows Server 2003 \[desktop apps only\]<br/>            |
| Header<br/>                   | <dl> <dt>Cardmod.h</dt> </dl> |



## See also

<dl> <dt>

[Microsoft Base Smart Card Cryptographic Service Provider](secsmart.microsoft_base_smart_card_cryptographic_service_provider)
</dt> <dt>

[**CardCreateDirectory**](secsmart.cardcreatedirectory)
</dt> <dt>

[**CardDeleteDirectory**](secsmart.carddeletedirectory)
</dt> </dl>

 

 



