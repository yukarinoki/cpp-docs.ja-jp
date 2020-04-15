---
title: CA2AEX クラス
ms.date: 11/04/2016
f1_keywords:
- CA2AEX
- ATLCONV/ATL::CA2AEX
- ATLCONV/ATL::CA2AEX::CA2AEX
- ATLCONV/ATL::CA2AEX::m_psz
- ATLCONV/ATL::CA2AEX::m_szBuffer
helpviewer_keywords:
- CA2AEX class
ms.assetid: 57dc65df-d9cf-4a84-99d3-6e031dde3664
ms.openlocfilehash: 4f8b9f91e9bc499523fe3484bc76325e2efb8140
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319178"
---
# <a name="ca2aex-class"></a>CA2AEX クラス

このクラスは、文字列変換マクロ CA2TEX と CT2AEX、および型定義 CA2A で使用されます。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <int t_nBufferLength = 128>
class CA2AEX
```

#### <a name="parameters"></a>パラメーター

*t_nBufferLength*<br/>
変換プロセスで使用されるバッファーのサイズ。 デフォルトの長さは 128 バイトです。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CA2AEX::CA2AEX](#ca2aex)|コンストラクターです。|
|[CA2AEX::~CA2AEX](#dtor)|デストラクターです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CA2AEX::オペレーターLPSTR](#operator_lpstr)|変換演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CA2AEX::m_psz](#m_psz)|ソース文字列を格納するデータ メンバー。|
|[CA2AEX::m_szBuffer](#m_szbuffer)|変換された文字列を格納するために使用される静的バッファー。|

## <a name="remarks"></a>解説

追加の機能が必要な場合を除き、独自のコードで CA2TEX、CT2AEX、または CA2A を使用してください。

このクラスには、変換の結果を格納するために使用される固定サイズの静的バッファーが含まれています。 結果が大きすぎて静的バッファに収まらない場合、クラスは**malloc**を使用してメモリを割り当て、オブジェクトがスコープ外に出たときにメモリを解放します。 これにより、以前のバージョンの ATL で使用できるテキスト変換マクロとは異なり、このクラスはループで安全に使用でき、スタックがオーバーフローしません。

クラスがヒープにメモリを割り当てようとしても失敗した場合、E_OUTOFMEMORYの引数を指定して呼び出`AtlThrow`します。

既定では、ATL 変換クラスとマクロは、変換に現在のスレッドの ANSI コード ページを使用します。

このクラスに基づくマクロは次のとおりです。

- CA2TEX

- CT2AEX

このクラスに基づく型定義の例を次に示します。

- CA2A

これらのテキスト変換マクロの詳細については、「 [ATL および MFC 文字列変換マクロ](string-conversion-macros.md)」を参照してください。

## <a name="example"></a>例

これらの[文字列変換マクロの使用例については、「ATL および MFC 文字列](string-conversion-macros.md)変換マクロ」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** アトルコンフ.h

## <a name="ca2aexca2aex"></a><a name="ca2aex"></a>CA2AEX::CA2AEX

コンストラクターです。

```
CA2AEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2AEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>パラメーター

*psz*<br/>
変換するテキスト文字列。

*nコードページ*<br/>
このクラスでは使用されていません。

### <a name="remarks"></a>解説

変換に必要なバッファーを作成します。

## <a name="ca2aexca2aex"></a><a name="dtor"></a>CA2AEX::~CA2AEX

デストラクターです。

```
~CA2AEX() throw();
```

### <a name="remarks"></a>解説

割り当てられたバッファを解放します。

## <a name="ca2aexm_psz"></a><a name="m_psz"></a>CA2AEX::m_psz

ソース文字列を格納するデータ メンバー。

```
LPSTR m_psz;
```

## <a name="ca2aexm_szbuffer"></a><a name="m_szbuffer"></a>CA2AEX::m_szBuffer

変換された文字列を格納するために使用される静的バッファー。

```
char m_szBuffer[ t_nBufferLength];
```

## <a name="ca2aexoperator-lpstr"></a><a name="operator_lpstr"></a>CA2AEX::オペレーターLPSTR

変換演算子。

```
operator LPSTR() const throw();
```

### <a name="return-value"></a>戻り値

テキスト文字列を LPSTR 型として返します。

## <a name="see-also"></a>関連項目

[CA2CAEX クラス](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEXクラス](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX クラス](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEXクラス](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEXクラス](../../atl/reference/cw2wex-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
