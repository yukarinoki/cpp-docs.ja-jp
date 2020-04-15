---
title: レジストリ データエクスチェンジ マクロ
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
ms.openlocfilehash: a7d580e4907cec40f97c0cead616665fff7b8a01
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326071"
---
# <a name="registry-data-exchange-macros"></a>レジストリ データエクスチェンジ マクロ

これらのマクロは、レジストリ データ交換操作を実行します。

|||
|-|-|
|[BEGIN_RDX_MAP](#begin_rdx_map)|レジストリ データ エクスチェンジ マップの先頭を示します。|
|[END_RDX_MAP](#end_rdx_map)|レジストリ データ エクスチェンジ マップの末尾をマークします。|
|[RDX_BINARY](#rdx_binary)|指定したレジストリ エントリを BYTE 型の指定されたメンバ変数に関連付けます。|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|指定したレジストリ エントリを、CString 型の指定されたメンバー変数に関連付けます。|
|[RDX_DWORD](#rdx_dword)|指定したレジストリ エントリを DWORD 型の指定されたメンバー変数に関連付けます。|
|[RDX_TEXT](#rdx_text)|指定したレジストリ エントリを、TCHAR 型の指定されたメンバー変数に関連付けます。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlplus.h

## <a name="begin_rdx_map"></a><a name="begin_rdx_map"></a>BEGIN_RDX_MAP

レジストリ データ エクスチェンジ マップの先頭を示します。

```
BEGIN_RDX_MAP
```

### <a name="remarks"></a>解説

レジストリ データ エクスチェンジ マップ内で、次のマクロを使用して、レジストリ内のエントリの読み取りと書き込みを行います。

|マクロ|説明|
|-----------|-----------------|
|[RDX_BINARY](#rdx_binary)|指定したレジストリ エントリを BYTE 型の指定されたメンバ変数に関連付けます。|
|[RDX_DWORD](#rdx_dword)|指定したレジストリ エントリを DWORD 型の指定されたメンバー変数に関連付けます。|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|指定したレジストリ エントリを、CString 型の指定されたメンバー変数に関連付けます。|
|[RDX_TEXT](#rdx_text)|指定したレジストリ エントリを、TCHAR 型の指定されたメンバー変数に関連付けます。|

BEGIN_RDX_MAP マクロとEND_RDX_MAP マクロによって作成された同じ名前のグローバル関数[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)またはメンバー関数は、システム レジストリと RDX マップで指定された変数との間でデータを交換する必要がある場合に必ず使用する必要があります。

## <a name="end_rdx_map"></a><a name="end_rdx_map"></a>END_RDX_MAP

レジストリ データ エクスチェンジ マップの末尾をマークします。

```
END_RDX_MAP
```

## <a name="rdx_binary"></a><a name="rdx_binary"></a>RDX_BINARY

指定したレジストリ エントリを BYTE 型の指定されたメンバ変数に関連付けます。

```
RDX_BINARY(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>パラメーター

*ルートキー*<br/>
レジストリ キーのルート。

*サブキー*<br/>
レジストリ サブキー。

*Valuename*<br/>
レジストリ キー。

*メンバー*<br/>
指定したレジストリ エントリに関連付けるメンバー変数。

*member_size*<br/>
メンバー変数のサイズ (バイト単位)。

### <a name="remarks"></a>解説

このマクロは、BEGIN_RDX_MAPマクロおよびEND_RDX_MAP マクロと組み合わせて使用され、メンバー変数を指定のレジストリ エントリに関連付けます。 BEGIN_RDX_MAPとEND_RDX_MAPマクロによって作成された同じ名前のグローバル関数[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)またはメンバー関数は、システム レジストリと RDX マップ内のメンバー変数との間でデータ交換を実行するために使用する必要があります。

## <a name="rdx_cstring_text"></a><a name="rdx_cstring_text"></a>RDX_CSTRING_TEXT

指定したレジストリ エントリを、CString 型の指定されたメンバー変数に関連付けます。

```
RDX_CSTRING_TEXT(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>パラメーター

*ルートキー*<br/>
レジストリ キーのルート。

*サブキー*<br/>
レジストリ サブキー。

*Valuename*<br/>
レジストリ キー。

*メンバー*<br/>
指定したレジストリ エントリに関連付けるメンバー変数。

*member_size*<br/>
メンバー変数のサイズ (バイト単位)。

### <a name="remarks"></a>解説

このマクロは、BEGIN_RDX_MAPマクロおよびEND_RDX_MAP マクロと組み合わせて使用され、メンバー変数を指定のレジストリ エントリに関連付けます。 BEGIN_RDX_MAPとEND_RDX_MAPマクロによって作成された同じ名前のグローバル関数[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)またはメンバー関数は、システム レジストリと RDX マップ内のメンバー変数との間でデータ交換を実行するために使用する必要があります。

## <a name="rdx_dword"></a><a name="rdx_dword"></a>RDX_DWORD

指定したレジストリ エントリを DWORD 型の指定されたメンバー変数に関連付けます。

```
RDX_DWORD(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>パラメーター

*ルートキー*<br/>
レジストリ キーのルート。

*サブキー*<br/>
レジストリ サブキー。

*Valuename*<br/>
レジストリ キー。

*メンバー*<br/>
指定したレジストリ エントリに関連付けるメンバー変数。

*member_size*<br/>
メンバー変数のサイズ (バイト単位)。

### <a name="remarks"></a>解説

このマクロは、BEGIN_RDX_MAPマクロおよびEND_RDX_MAP マクロと組み合わせて使用され、メンバー変数を指定のレジストリ エントリに関連付けます。 BEGIN_RDX_MAPとEND_RDX_MAPマクロによって作成された同じ名前のグローバル関数[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)またはメンバー関数は、システム レジストリと RDX マップ内のメンバー変数との間でデータ交換を実行するために使用する必要があります。

## <a name="rdx_text"></a><a name="rdx_text"></a>RDX_TEXT

指定したレジストリ エントリを、TCHAR 型の指定されたメンバー変数に関連付けます。

```
RDX_TEXT(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>パラメーター

*ルートキー*<br/>
レジストリ キーのルート。

*サブキー*<br/>
レジストリ サブキー。

*Valuename*<br/>
レジストリ キー。

*メンバー*<br/>
指定したレジストリ エントリに関連付けるメンバー変数。

*member_size*<br/>
メンバー変数のサイズ (バイト単位)。

### <a name="remarks"></a>解説

このマクロは、BEGIN_RDX_MAPマクロおよびEND_RDX_MAP マクロと組み合わせて使用され、メンバー変数を指定のレジストリ エントリに関連付けます。 BEGIN_RDX_MAPとEND_RDX_MAPマクロによって作成された同じ名前のグローバル関数[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)またはメンバー関数は、システム レジストリと RDX マップ内のメンバー変数との間でデータ交換を実行するために使用する必要があります。

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)<br/>
[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)
