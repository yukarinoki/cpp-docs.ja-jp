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
ms.openlocfilehash: e6c727993b2907aaa551421a5d2d23e372b68917
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319142"
---
# <a name="ca2caex-class"></a>CA2CAEX クラス

このクラスは、文字列変換マクロ CA2CTEX および CT2CAEX、およびタイプ定義 CA2CA で使用されます。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<int t_nBufferLength = 128>
class CA2CAEX
```

#### <a name="parameters"></a>パラメーター

*t_nBufferLength*<br/>
変換プロセスで使用されるバッファーのサイズ。 デフォルトの長さは 128 バイトです。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CA2CAEX::CA2CAEX](#ca2caex)|コンストラクターです。|
|[CA2CAEX::~CA2CAEX](#dtor)|デストラクターです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CA2CAEX::オペレーターLPCSTR](#operator_lpcstr)|変換演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CA2CAEX::m_psz](#m_psz)|ソース文字列を格納するデータ メンバー。|

## <a name="remarks"></a>解説

追加の機能が必要な場合を除き、独自のコードで CA2CTEX、CT2CAEX、または CA2CA を使用してください。

このクラスはループで安全に使用でき、スタックをオーバーフローしません。 既定では、ATL 変換クラスとマクロは、現在のスレッドの ANSI コード ページを変換に使用します。

このクラスに基づくマクロは次のとおりです。

- CA2CTEX

- CT2CAEX

このクラスに基づく型定義の例を次に示します。

- CA2CA

これらのテキスト変換マクロの詳細については、「 [ATL および MFC 文字列変換マクロ](string-conversion-macros.md)」を参照してください。

## <a name="example"></a>例

これらの[文字列変換マクロの使用例については、「ATL および MFC 文字列](string-conversion-macros.md)変換マクロ」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** アトルコンフ.h

## <a name="ca2caexca2caex"></a><a name="ca2caex"></a>CA2CAEX::CA2CAEX

コンストラクターです。

```
CA2CAEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2CAEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>パラメーター

*psz*<br/>
変換するテキスト文字列。

*nコードページ*<br/>
このクラスでは使用されていません。

### <a name="remarks"></a>解説

変換に必要なバッファーを作成します。

## <a name="ca2caexca2caex"></a><a name="dtor"></a>CA2CAEX::~CA2CAEX

デストラクターです。

```
~CA2CAEX() throw();
```

### <a name="remarks"></a>解説

割り当てられたバッファを解放します。

## <a name="ca2caexm_psz"></a><a name="m_psz"></a>CA2CAEX::m_psz

ソース文字列を格納するデータ メンバー。

```
LPCSTR m_psz;
```

## <a name="ca2caexoperator-lpcstr"></a><a name="operator_lpcstr"></a>CA2CAEX::オペレーターLPCSTR

変換演算子。

```
operator LPCSTR() const throw();
```

### <a name="return-value"></a>戻り値

テキスト文字列を LPCSTR 型として返します。

## <a name="see-also"></a>関連項目

[CA2AEX クラス](../../atl/reference/ca2aex-class.md)<br/>
[CA2WEXクラス](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX クラス](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEXクラス](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEXクラス](../../atl/reference/cw2wex-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
