---
title: CA2CAEX クラス
ms.date: 11/04/2016
f1_keywords:
- CA2CAEX
- ATLCONV/ATL::CA2CAEX
- ATLCONV/ATL::CA2CAEX::CA2CAEX
- ATLCONV/ATL::CA2CAEX::m_psz
helpviewer_keywords:
- CA2CAEX class
ms.assetid: 388e7c1d-a144-474c-a182-b15f69a74bd8
ms.openlocfilehash: 505c1e369bc5949fea291a2172c16d5e52c75567
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168515"
---
# <a name="ca2caex-class"></a>CA2CAEX クラス

このクラスは、文字列変換マクロ CA2CTEX と CT2CAEX、および typedef CA2CA によって使用されます。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```cpp
template<int t_nBufferLength = 128>
class CA2CAEX
```

### <a name="parameters"></a>パラメーター

*t_nBufferLength*<br/>
変換プロセスで使用されるバッファーのサイズ。 既定の長さは128バイトです。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CA2CAEX::CA2CAEX](#ca2caex)|コンストラクターです。|
|[CA2CAEX:: ~ CA2CAEX](#dtor)|デストラクターです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CA2CAEX:: operator LPCSTR](#operator_lpcstr)|変換演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CA2CAEX:: m_psz](#m_psz)|ソース文字列を格納するデータメンバー。|

## <a name="remarks"></a>解説

追加機能が必要な場合を除き、独自のコードで CA2CTEX、CT2CAEX、または CA2CA を使用してください。

このクラスは、ループで使用するのが安全であり、スタックをオーバーフローすることはありません。 既定では、ATL 変換クラスとマクロは、現在のスレッドの ANSI コード ページを変換に使用します。

次のマクロは、このクラスに基づいています。

- CA2CTEX

- CT2CAEX

次の typedef は、このクラスに基づいています。

- CA2CA

これらのテキスト変換マクロの詳細については、「 [ATL および MFC の文字列変換マクロ](string-conversion-macros.md)」を参照してください。

## <a name="example"></a>例

これらの文字列変換マクロの使用例については、「 [ATL および MFC の文字列変換マクロ](string-conversion-macros.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlconv. h

## <a name="ca2caexca2caex"></a><a name="ca2caex"></a>CA2CAEX::CA2CAEX

コンストラクターです。

```cpp
CA2CAEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2CAEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>パラメーター

*psz*<br/>
変換されるテキスト文字列。

*nCodePage*<br/>
このクラスでは使用されません。

### <a name="remarks"></a>解説

変換に必要なバッファーを作成します。

## <a name="ca2caexca2caex"></a><a name="dtor"></a>CA2CAEX:: ~ CA2CAEX

デストラクターです。

```cpp
~CA2CAEX() throw();
```

### <a name="remarks"></a>解説

割り当てられたバッファーを解放します。

## <a name="ca2caexm_psz"></a><a name="m_psz"></a>CA2CAEX:: m_psz

ソース文字列を格納するデータメンバー。

```cpp
LPCSTR m_psz;
```

## <a name="ca2caexoperator-lpcstr"></a><a name="operator_lpcstr"></a>CA2CAEX:: operator LPCSTR

変換演算子。

```cpp
operator LPCSTR() const throw();
```

### <a name="return-value"></a>戻り値

LPCSTR 型のテキスト文字列を返します。

## <a name="see-also"></a>関連項目

[CA2AEX クラス](../../atl/reference/ca2aex-class.md)<br/>
[CA2WEX クラス](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX クラス](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEX クラス](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEX クラス](../../atl/reference/cw2wex-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
