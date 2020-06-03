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
ms.openlocfilehash: dfd8967d21005d83b38eeae36cfc147051d7beaf
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168528"
---
# <a name="ca2aex-class"></a>CA2AEX クラス

このクラスは、文字列変換マクロ CA2TEX と CT2AEX、および typedef CA2A によって使用されます。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```cpp
template <int t_nBufferLength = 128>
class CA2AEX
```

### <a name="parameters"></a>パラメーター

*t_nBufferLength*<br/>
変換プロセスで使用されるバッファーのサイズ。 既定の長さは128バイトです。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CA2AEX::CA2AEX](#ca2aex)|コンストラクターです。|
|[CA2AEX:: ~ CA2AEX](#dtor)|デストラクターです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CA2AEX:: operator LPSTR](#operator_lpstr)|変換演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CA2AEX:: m_psz](#m_psz)|ソース文字列を格納するデータメンバー。|
|[CA2AEX:: m_szBuffer](#m_szbuffer)|変換された文字列を格納するために使用する静的バッファー。|

## <a name="remarks"></a>解説

追加機能が必要な場合を除き、独自のコードで CA2TEX、CT2AEX、または CA2A を使用してください。

このクラスには、変換の結果を格納するために使用される固定サイズの静的バッファーが含まれています。 結果が大きすぎて静的バッファーに格納できない場合、クラスは**malloc**を使用してメモリを割り当て、オブジェクトがスコープ外に出るとメモリを解放します。 これにより、以前のバージョンの ATL で使用されていたテキスト変換マクロとは異なり、このクラスはループ内で安全に使用でき、スタックをオーバーフローすることはありません。

クラスがヒープにメモリを割り当てようとして失敗した場合は`AtlThrow` 、E_OUTOFMEMORY の引数を指定してを呼び出します。

既定では、ATL の変換クラスとマクロは、現在のスレッドの ANSI コードページを使用して変換を行います。

次のマクロは、このクラスに基づいています。

- CA2TEX

- CT2AEX

次の typedef は、このクラスに基づいています。

- CA2A

これらのテキスト変換マクロの詳細については、「 [ATL および MFC の文字列変換マクロ](string-conversion-macros.md)」を参照してください。

## <a name="example"></a>例

これらの文字列変換マクロの使用例については、「 [ATL および MFC の文字列変換マクロ](string-conversion-macros.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlconv. h

## <a name="ca2aexca2aex"></a><a name="ca2aex"></a>CA2AEX::CA2AEX

コンストラクターです。

```cpp
CA2AEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2AEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>パラメーター

*psz*<br/>
変換されるテキスト文字列。

*nCodePage*<br/>
このクラスでは使用されません。

### <a name="remarks"></a>解説

変換に必要なバッファーを作成します。

## <a name="ca2aexca2aex"></a><a name="dtor"></a>CA2AEX:: ~ CA2AEX

デストラクターです。

```cpp
~CA2AEX() throw();
```

### <a name="remarks"></a>解説

割り当てられたバッファーを解放します。

## <a name="ca2aexm_psz"></a><a name="m_psz"></a>CA2AEX:: m_psz

ソース文字列を格納するデータメンバー。

```cpp
LPSTR m_psz;
```

## <a name="ca2aexm_szbuffer"></a><a name="m_szbuffer"></a>CA2AEX:: m_szBuffer

変換された文字列を格納するために使用する静的バッファー。

```cpp
char m_szBuffer[ t_nBufferLength];
```

## <a name="ca2aexoperator-lpstr"></a><a name="operator_lpstr"></a>CA2AEX:: operator LPSTR

変換演算子。

```cpp
operator LPSTR() const throw();
```

### <a name="return-value"></a>戻り値

テキスト文字列を型 LPSTR として返します。

## <a name="see-also"></a>関連項目

[CA2CAEX クラス](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX クラス](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX クラス](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEX クラス](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEX クラス](../../atl/reference/cw2wex-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
