---
description: '詳細情報: CW2WEX クラス'
title: CW2WEX クラス
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
ms.openlocfilehash: 87dbcefe37a54270b021ee1446ba5ccba2ef8313
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140245"
---
# <a name="cw2wex-class"></a>CW2WEX クラス

このクラスは、文字列変換マクロ CW2TEX と CT2WEX、および typedef CW2W によって使用されます。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <int t_nBufferLength = 128>
class CW2WEX
```

#### <a name="parameters"></a>パラメーター

*t_nBufferLength*<br/>
変換プロセスで使用されるバッファーのサイズ。 既定の長さは128バイトです。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CW2WEX::CW2WEX](#cw2wex)|コンストラクターです。|
|[CW2WEX:: ~ CW2WEX](#dtor)|デストラクターです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CW2WEX:: operator LPWSTR](#operator_lpwstr)|変換演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CW2WEX:: m_psz](#m_psz)|ソース文字列を格納するデータメンバー。|
|[CW2WEX:: m_szBuffer](#m_szbuffer)|変換された文字列を格納するために使用する静的バッファー。|

## <a name="remarks"></a>解説

追加機能が必要な場合を除き、コードで CW2TEX、CT2WEX、または CW2W を使用してください。

このクラスには、変換の結果を格納するために使用される固定サイズの静的バッファーが含まれています。 結果が大きすぎて静的バッファーに格納できない場合、クラスは **malloc** を使用してメモリを割り当て、オブジェクトがスコープ外に出るとメモリを解放します。 これにより、以前のバージョンの ATL で使用されていたテキスト変換マクロとは異なり、このクラスはループ内で安全に使用でき、スタックをオーバーフローすることはありません。

クラスがヒープにメモリを割り当てようとして失敗した場合は、 `AtlThrow` E_OUTOFMEMORY の引数を指定してを呼び出します。

既定では、ATL の変換クラスとマクロは、現在のスレッドの ANSI コードページを使用して変換を行います。

次のマクロは、このクラスに基づいています。

- CW2TEX

- CT2WEX

次の typedef は、このクラスに基づいています。

- CW2W

これらのテキスト変換マクロの詳細については、「 [ATL および MFC の文字列変換マクロ](string-conversion-macros.md)」を参照してください。

## <a name="example"></a>例

これらの文字列変換マクロの使用例については、「 [ATL および MFC の文字列変換マクロ](string-conversion-macros.md) 」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** atlconv. h

## <a name="cw2wexcw2wex"></a><a name="cw2wex"></a> CW2WEX::CW2WEX

コンストラクターです。

```
CW2WEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2WEX( LPCWSTR  psz) throw(...);
```

### <a name="parameters"></a>パラメーター

*psz*<br/>
変換されるテキスト文字列。

*nCodePage*<br/>
コード ページです。 このクラスでは使用されません。

### <a name="remarks"></a>解説

変換に必要なバッファーを作成します。

## <a name="cw2wexcw2wex"></a><a name="dtor"></a> CW2WEX:: ~ CW2WEX

デストラクターです。

```
~CW2WEX() throw();
```

### <a name="remarks"></a>解説

割り当てられたバッファーを解放します。

## <a name="cw2wexm_psz"></a><a name="m_psz"></a> CW2WEX:: m_psz

ソース文字列を格納するデータメンバー。

```
LPWSTR m_psz;
```

## <a name="cw2wexm_szbuffer"></a><a name="m_szbuffer"></a> CW2WEX:: m_szBuffer

変換された文字列を格納するために使用する静的バッファー。

```
wchar_t m_szBuffer[t_nBufferLength];
```

## <a name="cw2wexoperator-lpwstr"></a><a name="operator_lpwstr"></a> CW2WEX:: operator LPWSTR

Cast 演算子。

```
operator LPWSTR() const throw();
```

### <a name="return-value"></a>戻り値

LPWSTR 型のテキスト文字列を返します。

## <a name="see-also"></a>関連項目

[CA2AEX クラス](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX クラス](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX クラス](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX クラス](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEX クラス](../../atl/reference/cw2cwex-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
