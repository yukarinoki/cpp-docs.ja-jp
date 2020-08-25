---
title: レジストリデータ交換マクロ
ms.date: 11/04/2016
f1_keywords:
- atlplus/ATL::BEGIN_RDX_MAP
- atlplus/ATL::END_RDX_MAP
- atlplus/ATL::RDX_BINARY
- atlplus/ATL::RDX_CSTRING_TEXT
- atlplus/ATL::RDX_DWORD
- atlplus/ATL::RDX_TEXT
helpviewer_keywords:
- RegistryDataExchange function, macros
ms.assetid: c1bc5e79-2307-43d2-9d10-3a62ffadf473
ms.openlocfilehash: 507db77b525c526fe1cd47c7d75c34e15a6a0628
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834545"
---
# <a name="registry-data-exchange-macros"></a>レジストリデータ交換マクロ

これらのマクロは、レジストリデータ交換操作を実行します。

|名前|説明|
|-|-|
|[BEGIN_RDX_MAP](#begin_rdx_map)|レジストリデータ交換マップの開始をマークします。|
|[END_RDX_MAP](#end_rdx_map)|レジストリデータ交換マップの終了をマークします。|
|[RDX_BINARY](#rdx_binary)|指定されたレジストリエントリを BYTE 型の指定されたメンバー変数に関連付けます。|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|指定されたレジストリエントリを、CString 型の指定されたメンバー変数に関連付けます。|
|[RDX_DWORD](#rdx_dword)|指定されたレジストリエントリを DWORD 型の指定されたメンバー変数に関連付けます。|
|[RDX_TEXT](#rdx_text)|指定されたレジストリエントリを、TCHAR 型の指定されたメンバー変数に関連付けます。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlplus. h

## <a name="begin_rdx_map"></a><a name="begin_rdx_map"></a> BEGIN_RDX_MAP

レジストリデータ交換マップの開始をマークします。

```
BEGIN_RDX_MAP
```

### <a name="remarks"></a>解説

レジストリデータ交換マップ内では、次のマクロを使用して、システムレジストリのエントリの読み取りと書き込みを行います。

|マクロ|説明|
|-----------|-----------------|
|[RDX_BINARY](#rdx_binary)|指定されたレジストリエントリを BYTE 型の指定されたメンバー変数に関連付けます。|
|[RDX_DWORD](#rdx_dword)|指定されたレジストリエントリを DWORD 型の指定されたメンバー変数に関連付けます。|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|指定されたレジストリエントリを、CString 型の指定されたメンバー変数に関連付けます。|
|[RDX_TEXT](#rdx_text)|指定されたレジストリエントリを、TCHAR 型の指定されたメンバー変数に関連付けます。|

グローバル関数 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)、または BEGIN_RDX_MAP と END_RDX_MAP マクロによって作成された同じ名前のメンバー関数は、コードがシステムレジストリと RDX マップで指定された変数の間でデータを交換する必要がある場合に常に使用する必要があります。

## <a name="end_rdx_map"></a><a name="end_rdx_map"></a> END_RDX_MAP

レジストリデータ交換マップの終了をマークします。

```
END_RDX_MAP
```

## <a name="rdx_binary"></a><a name="rdx_binary"></a> RDX_BINARY

指定されたレジストリエントリを BYTE 型の指定されたメンバー変数に関連付けます。

```
RDX_BINARY(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>パラメーター

*rootkey*<br/>
レジストリキーのルート。

*サブキー*<br/>
レジストリサブキー。

*valuename*<br/>
レジストリキー。

*レプリカ*<br/>
指定したレジストリエントリに関連付けるメンバー変数。

*member_size*<br/>
メンバー変数のサイズ (バイト単位)。

### <a name="remarks"></a>解説

このマクロは、BEGIN_RDX_MAP および END_RDX_MAP マクロと組み合わせて使用し、メンバー変数を特定のレジストリエントリに関連付けます。 グローバル関数 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)、または BEGIN_RDX_MAP と END_RDX_MAP マクロによって作成された同じ名前のメンバー関数は、システムレジストリと RDX MAP 内のメンバー変数との間でデータ交換を実行するために使用する必要があります。

## <a name="rdx_cstring_text"></a><a name="rdx_cstring_text"></a> RDX_CSTRING_TEXT

指定されたレジストリエントリを、CString 型の指定されたメンバー変数に関連付けます。

```
RDX_CSTRING_TEXT(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>パラメーター

*rootkey*<br/>
レジストリキーのルート。

*サブキー*<br/>
レジストリサブキー。

*valuename*<br/>
レジストリキー。

*レプリカ*<br/>
指定したレジストリエントリに関連付けるメンバー変数。

*member_size*<br/>
メンバー変数のサイズ (バイト単位)。

### <a name="remarks"></a>解説

このマクロは、BEGIN_RDX_MAP および END_RDX_MAP マクロと組み合わせて使用し、メンバー変数を特定のレジストリエントリに関連付けます。 グローバル関数 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)、または BEGIN_RDX_MAP と END_RDX_MAP マクロによって作成された同じ名前のメンバー関数は、システムレジストリと RDX MAP 内のメンバー変数との間でデータ交換を実行するために使用する必要があります。

## <a name="rdx_dword"></a><a name="rdx_dword"></a> RDX_DWORD

指定されたレジストリエントリを DWORD 型の指定されたメンバー変数に関連付けます。

```
RDX_DWORD(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>パラメーター

*rootkey*<br/>
レジストリキーのルート。

*サブキー*<br/>
レジストリサブキー。

*valuename*<br/>
レジストリキー。

*レプリカ*<br/>
指定したレジストリエントリに関連付けるメンバー変数。

*member_size*<br/>
メンバー変数のサイズ (バイト単位)。

### <a name="remarks"></a>解説

このマクロは、BEGIN_RDX_MAP および END_RDX_MAP マクロと組み合わせて使用し、メンバー変数を特定のレジストリエントリに関連付けます。 グローバル関数 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)、または BEGIN_RDX_MAP と END_RDX_MAP マクロによって作成された同じ名前のメンバー関数は、システムレジストリと RDX MAP 内のメンバー変数との間でデータ交換を実行するために使用する必要があります。

## <a name="rdx_text"></a><a name="rdx_text"></a> RDX_TEXT

指定されたレジストリエントリを、TCHAR 型の指定されたメンバー変数に関連付けます。

```
RDX_TEXT(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>パラメーター

*rootkey*<br/>
レジストリキーのルート。

*サブキー*<br/>
レジストリサブキー。

*valuename*<br/>
レジストリキー。

*レプリカ*<br/>
指定したレジストリエントリに関連付けるメンバー変数。

*member_size*<br/>
メンバー変数のサイズ (バイト単位)。

### <a name="remarks"></a>解説

このマクロは、BEGIN_RDX_MAP および END_RDX_MAP マクロと組み合わせて使用し、メンバー変数を特定のレジストリエントリに関連付けます。 グローバル関数 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)、または BEGIN_RDX_MAP と END_RDX_MAP マクロによって作成された同じ名前のメンバー関数は、システムレジストリと RDX MAP 内のメンバー変数との間でデータ交換を実行するために使用する必要があります。

## <a name="see-also"></a>関連項目

[[マクロ]](../../atl/reference/atl-macros.md)<br/>
[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)
