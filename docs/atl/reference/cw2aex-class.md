---
title: CW2AEX クラス
ms.date: 11/04/2016
f1_keywords:
- CW2AEX
- ATLCONV/ATL::CW2AEX
- ATLCONV/ATL::CW2AEX::CW2AEX
- ATLCONV/ATL::CW2AEX::m_psz
- ATLCONV/ATL::CW2AEX::m_szBuffer
helpviewer_keywords:
- CW2AEX class
ms.assetid: 44dc2cf5-dd30-440b-a9b9-b21b43f49843
ms.openlocfilehash: 849cbe5c26d7c7af7a8925a26057b5777554471d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330448"
---
# <a name="cw2aex-class"></a>CW2AEX クラス

このクラスは、文字列変換マクロ CT2AEX、CW2TEX、CW2CTEX、および CT2CAEX、およびタイプ定義 CW2A で使用されます。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<int t_nBufferLength = 128>
class CW2AEX
```

#### <a name="parameters"></a>パラメーター

*t_nBufferLength*<br/>
変換プロセスで使用されるバッファーのサイズ。 デフォルトの長さは 128 バイトです。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CW2AEX::CW2AEX](#cw2aex)|コンストラクターです。|
|[CW2AEX::~CW2AEX](#dtor)|デストラクターです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CW2AEX::オペレーター LPSTR](#operator_lpstr)|変換演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CW2AEX::m_psz](#m_psz)|ソース文字列を格納するデータ メンバー。|
|[CW2AEX::m_szBuffer](#m_szbuffer)|変換された文字列を格納するために使用される静的バッファー。|

## <a name="remarks"></a>解説

追加の機能が必要な場合を除き、コード内で CT2AEX、CW2TEX、CW2CTEX、CT2CAEX、または CW2A を使用してください。

このクラスには、変換の結果を格納するために使用される固定サイズの静的バッファーが含まれています。 結果が大きすぎて静的バッファに収まらない場合、クラスは**malloc**を使用してメモリを割り当て、オブジェクトがスコープ外に出たときにメモリを解放します。 これにより、以前のバージョンの ATL で使用できるテキスト変換マクロとは異なり、このクラスはループで安全に使用でき、スタックがオーバーフローしません。

クラスがヒープにメモリを割り当てようとしても失敗した場合、E_OUTOFMEMORYの引数を指定して呼び出`AtlThrow`します。

既定では、ATL 変換クラスとマクロは、変換に現在のスレッドの ANSI コード ページを使用します。 特定の変換に対する動作をオーバーライドする場合は、クラスのコンストラクターの 2 番目のパラメーターとしてコード ページを指定します。

このクラスに基づくマクロは次のとおりです。

- CT2AEX

- CW2TEX

- CW2CTEX

- CT2CAEX

このクラスに基づく型定義の例を次に示します。

- CW2A

これらのテキスト変換マクロの詳細については、「 [ATL および MFC 文字列変換マクロ](string-conversion-macros.md)」を参照してください。

## <a name="example"></a>例

これらの[文字列変換マクロの使用例については、「ATL および MFC 文字列](string-conversion-macros.md)変換マクロ」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** アトルコンフ.h

## <a name="cw2aexcw2aex"></a><a name="cw2aex"></a>CW2AEX::CW2AEX

コンストラクターです。

```
CW2AEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2AEX(LPCWSTR psz) throw(...);
```

### <a name="parameters"></a>パラメーター

*psz*<br/>
変換するテキスト文字列。

*nコードページ*<br/>
変換を実行するために使用するコード ページ。 詳細については、Windows SDK 関数[のコード](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)ページ パラメーターの説明を参照してください。

### <a name="remarks"></a>解説

変換プロセスで使用されるバッファーを割り当てます。

## <a name="cw2aexcw2aex"></a><a name="dtor"></a>CW2AEX::~CW2AEX

デストラクターです。

```
~CW2AEX() throw();
```

### <a name="remarks"></a>解説

割り当てられたバッファを解放します。

## <a name="cw2aexm_psz"></a><a name="m_psz"></a>CW2AEX::m_psz

ソース文字列を格納するデータ メンバー。

```
LPSTR m_psz;
```

## <a name="cw2aexm_szbuffer"></a><a name="m_szbuffer"></a>CW2AEX::m_szBuffer

変換された文字列を格納するために使用される静的バッファー。

```
char m_szBuffer[t_nBufferLength];
```

## <a name="cw2aexoperator-lpstr"></a><a name="operator_lpstr"></a>CW2AEX::オペレーター LPSTR

変換演算子。

```
operator LPSTR() const throw();
```

### <a name="return-value"></a>戻り値

テキスト文字列を LPSTR 型として返します。

## <a name="see-also"></a>関連項目

[CA2AEX クラス](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX クラス](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEXクラス](../../atl/reference/ca2wex-class.md)<br/>
[CW2CWEXクラス](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEXクラス](../../atl/reference/cw2wex-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
