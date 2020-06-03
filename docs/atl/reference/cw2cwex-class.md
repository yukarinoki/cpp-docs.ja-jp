---
title: CW2CWEXクラス
ms.date: 11/04/2016
f1_keywords:
- CW2CWEX
- ATLCONV/ATL::CW2CWEX
- ATLCONV/ATL::CW2CWEX::CW2CWEX
- ATLCONV/ATL::CW2CWEX::m_psz
helpviewer_keywords:
- CW2CWEX class
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
ms.openlocfilehash: 07dd0319586054403d8ed0c8efc813b4061e355a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330434"
---
# <a name="cw2cwex-class"></a>CW2CWEXクラス

このクラスは、文字列変換マクロ CW2CTEX と CT2CWEX、およびタイプ定義 CW2W で使用されます。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<int t_nBufferLength = 128>
class CW2CWEX
```

#### <a name="parameters"></a>パラメーター

*t_nBufferLength*<br/>
変換プロセスで使用されるバッファーのサイズ。 デフォルトの長さは 128 バイトです。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CW2CWEX::CW2CWEX](#cw2cwex)|コンストラクターです。|
|[CW2CWEX::~CW2CWEX](#dtor)|デストラクターです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CW2CWEX::オペレーター LPCWSTR](#operator_lpcwstr)|変換演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CW2CWEX::m_psz](#m_psz)|ソース文字列を格納するデータ メンバー。|

## <a name="remarks"></a>解説

追加の機能が必要な場合を除き、コード内で CW2CTEX、CT2CWEX、または CW2W を使用してください。

このクラスはループで安全に使用でき、スタックをオーバーフローしません。 既定では、ATL 変換クラスとマクロは、変換に現在のスレッドの ANSI コード ページを使用します。

このクラスに基づくマクロは次のとおりです。

- CW2CTEX

- CT2CWEX

このクラスに基づく型定義の例を次に示します。

- CW2W

これらのテキスト変換マクロの詳細については、「 [ATL および MFC 文字列変換マクロ](string-conversion-macros.md)」を参照してください。

## <a name="example"></a>例

これらの[文字列変換マクロの使用例については、「ATL および MFC 文字列](string-conversion-macros.md)変換マクロ」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** アトルコンフ.h

## <a name="cw2cwexcw2cwex"></a><a name="cw2cwex"></a>CW2CWEX::CW2CWEX

コンストラクターです。

```
CW2CWEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2CWEX(LPCWSTR psz) throw(...);
```

### <a name="parameters"></a>パラメーター

*psz*<br/>
変換するテキスト文字列。

*nコードページ*<br/>
コード ページです。 このクラスでは使用されません。

### <a name="remarks"></a>解説

変換プロセスで使用されるバッファーを割り当てます。

## <a name="cw2cwexcw2cwex"></a><a name="dtor"></a>CW2CWEX::~CW2CWEX

デストラクターです。

```
~CW2CWEX() throw();
```

### <a name="remarks"></a>解説

割り当てられたバッファを解放します。

## <a name="cw2cwexm_psz"></a><a name="m_psz"></a>CW2CWEX::m_psz

ソース文字列を格納するデータ メンバー。

```
LPCWSTR m_psz;
```

## <a name="cw2cwexoperator-lpcwstr"></a><a name="operator_lpcwstr"></a>CW2CWEX::オペレーター LPCWSTR

変換演算子。

```
operator LPCWSTR() const throw();
```

### <a name="return-value"></a>戻り値

テキスト文字列を LPCWSTR 型として返します。

## <a name="see-also"></a>関連項目

[CA2AEX クラス](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX クラス](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEXクラス](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX クラス](../../atl/reference/cw2aex-class.md)<br/>
[CW2WEXクラス](../../atl/reference/cw2wex-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
