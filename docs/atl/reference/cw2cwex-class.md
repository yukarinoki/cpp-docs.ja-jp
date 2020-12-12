---
description: '詳細情報: CW2CWEX クラス'
title: CW2CWEX クラス
ms.date: 11/04/2016
f1_keywords:
- CW2CWEX
- ATLCONV/ATL::CW2CWEX
- ATLCONV/ATL::CW2CWEX::CW2CWEX
- ATLCONV/ATL::CW2CWEX::m_psz
helpviewer_keywords:
- CW2CWEX class
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
ms.openlocfilehash: 769dcedf1a9dc15129b09e3305330de33242562e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140232"
---
# <a name="cw2cwex-class"></a>CW2CWEX クラス

このクラスは、文字列変換マクロ CW2CTEX と CT2CWEX、および typedef CW2W によって使用されます。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<int t_nBufferLength = 128>
class CW2CWEX
```

#### <a name="parameters"></a>パラメーター

*t_nBufferLength*<br/>
変換プロセスで使用されるバッファーのサイズ。 既定の長さは128バイトです。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CW2CWEX::CW2CWEX](#cw2cwex)|コンストラクターです。|
|[CW2CWEX:: ~ CW2CWEX](#dtor)|デストラクターです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CW2CWEX:: operator LPCWSTR](#operator_lpcwstr)|変換演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CW2CWEX:: m_psz](#m_psz)|ソース文字列を格納するデータメンバー。|

## <a name="remarks"></a>解説

追加機能が必要な場合を除き、コードで CW2CTEX、CT2CWEX、または CW2W を使用してください。

このクラスは、ループで使用するのが安全であり、スタックをオーバーフローすることはありません。 既定では、ATL の変換クラスとマクロは、現在のスレッドの ANSI コードページを使用して変換を行います。

次のマクロは、このクラスに基づいています。

- CW2CTEX

- CT2CWEX

次の typedef は、このクラスに基づいています。

- CW2W

これらのテキスト変換マクロの詳細については、「 [ATL および MFC の文字列変換マクロ](string-conversion-macros.md)」を参照してください。

## <a name="example"></a>例

これらの文字列変換マクロの使用例については、「 [ATL および MFC の文字列変換マクロ](string-conversion-macros.md) 」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** atlconv. h

## <a name="cw2cwexcw2cwex"></a><a name="cw2cwex"></a> CW2CWEX::CW2CWEX

コンストラクターです。

```
CW2CWEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2CWEX(LPCWSTR psz) throw(...);
```

### <a name="parameters"></a>パラメーター

*psz*<br/>
変換されるテキスト文字列。

*nCodePage*<br/>
コード ページです。 このクラスでは使用されません。

### <a name="remarks"></a>解説

変換プロセスで使用されるバッファーを割り当てます。

## <a name="cw2cwexcw2cwex"></a><a name="dtor"></a> CW2CWEX:: ~ CW2CWEX

デストラクターです。

```
~CW2CWEX() throw();
```

### <a name="remarks"></a>解説

割り当てられたバッファーを解放します。

## <a name="cw2cwexm_psz"></a><a name="m_psz"></a> CW2CWEX:: m_psz

ソース文字列を格納するデータメンバー。

```
LPCWSTR m_psz;
```

## <a name="cw2cwexoperator-lpcwstr"></a><a name="operator_lpcwstr"></a> CW2CWEX:: operator LPCWSTR

変換演算子。

```
operator LPCWSTR() const throw();
```

### <a name="return-value"></a>戻り値

LPCWSTR 型のテキスト文字列を返します。

## <a name="see-also"></a>関連項目

[CA2AEX クラス](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX クラス](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX クラス](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX クラス](../../atl/reference/cw2aex-class.md)<br/>
[CW2WEX クラス](../../atl/reference/cw2wex-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
