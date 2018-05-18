﻿---
Description: 'Gets an integer.'
ms.assetid: '8074758a-f650-4698-8a75-aa0ffb14cb21'
title: 'ID3DXBaseEffect::GetInt method'
---

# ID3DXBaseEffect::GetInt method

Gets an integer.

## Syntax


```C++
HRESULT GetInt(
  [in]  D3DXHANDLE hParameter,
  [out] INT        *pn
);
```



## Parameters

<dl> <dt>

*hParameter* \[in\]
</dt> <dd>

Type: **[D3DXHANDLE](dx9-graphics-reference-effects-constants.md)**

Unique identifier. See [Handles (Direct3D 9)](handles.md).

</dd> <dt>

*pn* \[out\]
</dt> <dd>

Type: **[**INT**](winprog.windows_data_types)\***

Returns an integer.

</dd> </dl>

## Return value

Type: **[**HRESULT**](455d07e9-52c3-4efb-a9dc-2955cbfd38cc)**

If the method succeeds, the return value is D3D\_OK. If the method fails, the return value can be D3DERR\_INVALIDCALL.

## Requirements



|                    |                                                                                          |
|--------------------|------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX9Shader.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3dx9.lib</dt> </dl>     |



## See also

<dl> <dt>

[ID3DXBaseEffect](id3dxbaseeffect.md)
</dt> <dt>

[**SetInt**](id3dxbaseeffect--setint.md)
</dt> </dl>

 

 



