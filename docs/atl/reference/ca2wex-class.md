---
title: CA2WEXクラス
ms.date: 11/04/2016
f1_keywords:
- CA2WEX
- ATLCONV/ATL::CA2WEX
- ATLCONV/ATL::CA2WEX::CA2WEX
- ATLCONV/ATL::CA2WEX::m_psz
- ATLCONV/ATL::CA2WEX::m_szBuffer
helpviewer_keywords:
- CA2WEX class
ms.assetid: 317d9ffb-e84f-47e8-beda-57e28fb19124
ms.openlocfilehash: c9123e163ca828fa71fe217e46537ceb18e6f549
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319126"
---
# <a name="ca2wex-class"></a>CA2WEXクラス

このクラスは、文字列変換マクロ CA2TEX、CA2CTEX、CT2WEX、および CT2CWEX、およびタイプ定義 CA2W で使用されます。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <int t_nBufferLength = 128>
class CA2WEX
```

#### <a name="parameters"></a>パラメーター

*t_nBufferLength*<br/>
変換プロセスで使用されるバッファーのサイズ。 デフォルトの長さは 128 バイトです。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CA2ウェックス::CA2WEX](#ca2wex)|コンストラクターです。|
|[CA2WEX::~CA2WEX](#dtor)|デストラクターです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CA2WEX::オペレーター LPWSTR](#operator_lpwstr)|変換演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CA2WEX::m_psz](#m_psz)|ソース文字列を格納するデータ メンバー。|
|[CA2WEX::m_szBuffer](#m_szbuffer)|変換された文字列を格納するために使用される静的バッファー。|

## <a name="remarks"></a>解説

追加機能が必要な場合を除き、コード内で CA2TEX、CA2CTEX、CT2WEX、CT2CWEX、または CA2W を使用してください。

このクラスには、変換の結果を格納するために使用される固定サイズの静的バッファーが含まれています。 結果が大きすぎて静的バッファに収まらない場合、クラスは**malloc**を使用してメモリを割り当て、オブジェクトがスコープ外に出たときにメモリを解放します。 これにより、以前のバージョンの ATL で使用できるテキスト変換マクロとは異なり、このクラスはループで安全に使用でき、スタックがオーバーフローしません。

クラスがヒープにメモリを割り当てようとしても失敗した場合、E_OUTOFMEMORYの引数を指定して呼び出`AtlThrow`します。

既定では、ATL 変換クラスとマクロは、変換に現在のスレッドの ANSI コード ページを使用します。 特定の変換に対する動作をオーバーライドする場合は、クラスのコンストラクターの 2 番目のパラメーターとしてコード ページを指定します。

このクラスに基づくマクロは次のとおりです。

- CA2TEX

- CA2CTEX

- CT2WEX

- CT2CWEX

このクラスに基づく型定義の例を次に示します。

- CA2W

これらのテキスト変換マクロの詳細については、「 [ATL および MFC 文字列変換マクロ](string-conversion-macros.md)」を参照してください。

## <a name="example"></a>例

これらの[文字列変換マクロの使用例については、「ATL および MFC 文字列](string-conversion-macros.md)変換マクロ」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** アトルコンフ.h

## <a name="ca2wexca2wex"></a><a name="ca2wex"></a>CA2ウェックス::CA2WEX

コンストラクターです。

```
CA2WEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2WEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>パラメーター

*psz*<br/>
変換するテキスト文字列。

*nコードページ*<br/>
変換を実行するために使用するコード ページ。 詳細については、Windows SDK 関数[のコード](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)ページ パラメーターの説明を参照してください。

### <a name="remarks"></a>解説

変換プロセスで使用されるバッファーを割り当てます。

## <a name="ca2wexca2wex"></a><a name="dtor"></a>CA2WEX::~CA2WEX

デストラクターです。

```
~CA2WEX() throw();
```

### <a name="remarks"></a>解説

割り当てられたバッファを解放します。

## <a name="ca2wexm_psz"></a><a name="m_psz"></a>CA2WEX::m_psz

ソース文字列を格納するデータ メンバー。

```
LPWSTR m_psz;
```

## <a name="ca2wexm_szbuffer"></a><a name="m_szbuffer"></a>CA2WEX::m_szBuffer

変換された文字列を格納するために使用される静的バッファー。

```
wchar_t m_szBuffer[t_nBufferLength];
```

## <a name="ca2wexoperator-lpwstr"></a><a name="operator_lpwstr"></a>CA2WEX::オペレーター LPWSTR

変換演算子。

```
operator LPWSTR() const throw();
```

### <a name="return-value"></a>戻り値

テキスト文字列を LPWSTR 型として返します。

## <a name="see-also"></a>関連項目

[CA2AEX クラス](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX クラス](../../atl/reference/ca2caex-class.md)<br/>
[CW2AEX クラス](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEXクラス](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEXクラス](../../atl/reference/cw2wex-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
