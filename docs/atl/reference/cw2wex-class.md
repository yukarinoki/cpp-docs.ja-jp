---
title: CW2WEXクラス
ms.date: 11/04/2016
f1_keywords:
- CW2WEX
- ATLCONV/ATL::CW2WEX
- ATLCONV/ATL::CW2WEX::CW2WEX
- ATLCONV/ATL::CW2WEX::m_psz
- ATLCONV/ATL::CW2WEX::m_szBuffer
helpviewer_keywords:
- CW2WEX class
ms.assetid: 46262e56-e0d2-41fe-855b-0b67ecc8fcd7
ms.openlocfilehash: b116775a595f9fb3612d46e19526cf1396f85002
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330348"
---
# <a name="cw2wex-class"></a>CW2WEXクラス

このクラスは、文字列変換マクロ CW2TEX と CT2WEX、および型定義 CW2W で使用されます。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <int t_nBufferLength = 128>
class CW2WEX
```

#### <a name="parameters"></a>パラメーター

*t_nBufferLength*<br/>
変換プロセスで使用されるバッファーのサイズ。 デフォルトの長さは 128 バイトです。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CW2WEX::CW2WEX](#cw2wex)|コンストラクターです。|
|[CW2WEX::~CW2WEX](#dtor)|デストラクターです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CW2WEX::オペレーター LPWSTR](#operator_lpwstr)|変換演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CW2WEX::m_psz](#m_psz)|ソース文字列を格納するデータ メンバー。|
|[CW2WEX::m_szBuffer](#m_szbuffer)|変換された文字列を格納するために使用される静的バッファー。|

## <a name="remarks"></a>解説

追加の機能が必要な場合を除き、コード内で CW2TEX、CT2WEX、または CW2W を使用してください。

このクラスには、変換の結果を格納するために使用される固定サイズの静的バッファーが含まれています。 結果が大きすぎて静的バッファに収まらない場合、クラスは**malloc**を使用してメモリを割り当て、オブジェクトがスコープ外に出たときにメモリを解放します。 これにより、以前のバージョンの ATL で使用できるテキスト変換マクロとは異なり、このクラスはループで安全に使用でき、スタックがオーバーフローしません。

クラスがヒープにメモリを割り当てようとしても失敗した場合、E_OUTOFMEMORYの引数を指定して呼び出`AtlThrow`します。

既定では、ATL 変換クラスとマクロは、変換に現在のスレッドの ANSI コード ページを使用します。

このクラスに基づくマクロは次のとおりです。

- CW2TEX

- CT2WEX

このクラスに基づく型定義の例を次に示します。

- CW2W

これらのテキスト変換マクロの詳細については、「 [ATL および MFC 文字列変換マクロ](string-conversion-macros.md)」を参照してください。

## <a name="example"></a>例

これらの[文字列変換マクロの使用例については、「ATL および MFC 文字列](string-conversion-macros.md)変換マクロ」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** アトルコンフ.h

## <a name="cw2wexcw2wex"></a><a name="cw2wex"></a>CW2WEX::CW2WEX

コンストラクターです。

```
CW2WEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2WEX( LPCWSTR  psz) throw(...);
```

### <a name="parameters"></a>パラメーター

*psz*<br/>
変換するテキスト文字列。

*nコードページ*<br/>
コード ページです。 このクラスでは使用されません。

### <a name="remarks"></a>解説

変換に必要なバッファーを作成します。

## <a name="cw2wexcw2wex"></a><a name="dtor"></a>CW2WEX::~CW2WEX

デストラクタ。

```
~CW2WEX() throw();
```

### <a name="remarks"></a>解説

割り当てられたバッファを解放します。

## <a name="cw2wexm_psz"></a><a name="m_psz"></a>CW2WEX::m_psz

ソース文字列を格納するデータ メンバー。

```
LPWSTR m_psz;
```

## <a name="cw2wexm_szbuffer"></a><a name="m_szbuffer"></a>CW2WEX::m_szBuffer

変換された文字列を格納するために使用される静的バッファー。

```
wchar_t m_szBuffer[t_nBufferLength];
```

## <a name="cw2wexoperator-lpwstr"></a><a name="operator_lpwstr"></a>CW2WEX::オペレーター LPWSTR

キャスト演算子。

```
operator LPWSTR() const throw();
```

### <a name="return-value"></a>戻り値

テキスト文字列を LPWSTR 型として返します。

## <a name="see-also"></a>関連項目

[CA2AEX クラス](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX クラス](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEXクラス](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX クラス](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEXクラス](../../atl/reference/cw2cwex-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
