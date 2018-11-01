---
title: CA2WEX クラス
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
ms.openlocfilehash: 96769c0012b1271263d2217fe9b5ea1a36ec8446
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629945"
---
# <a name="ca2wex-class"></a>CA2WEX クラス

このクラスは、文字列変換マクロ CA2TEX、CA2CTEX、CT2WEX、および CT2CWEX、および typedef CA2W によって使用されます。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <int t_nBufferLength = 128>
class CA2WEX
```

#### <a name="parameters"></a>パラメーター

*t_nBufferLength*<br/>
変換プロセスで使用されるバッファーのサイズ。 既定の長さは 128 バイトです。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CA2WEX::CA2WEX](#ca2wex)|コンストラクターです。|
|[CA2WEX:: ~ CA2WEX](#dtor)|デストラクターです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CA2WEX::operator LPWSTR](#operator_lpwstr)|変換演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CA2WEX::m_psz](#m_psz)|ソース文字列が格納されるデータ メンバー。|
|[CA2WEX::m_szBuffer](#m_szbuffer)|変換後の文字列の格納に使用される静的バッファー。|

## <a name="remarks"></a>Remarks

追加の機能が必要でない限り、コードで CA2TEX、CA2CTEX、CT2WEX、CT2CWEX、または CA2W を使用します。

このクラスには、固定サイズの静的バッファー変換の結果を格納するために使用が含まれています。 クラスでは、メモリを使用して割り当てます、結果が大きすぎて静的バッファーに収まるように場合、 **malloc**オブジェクトがスコープ外になるときに、メモリを解放します。 これにより、テキストとは異なり、ATL のこのクラスを安全にループ内で使用して、スタックがオーバーフローするしませんの以前のバージョンで使用できる変換マクロ。

クラスは、失敗をヒープにメモリの割り当てを試みると、それが呼び出す`AtlThrow`E_OUTOFMEMORY の引数を指定しています。

既定では、ATL 変換クラスとマクロは、変換の現在のスレッドの ANSI コード ページを使用します。 特定の変換の動作をオーバーライドする場合は、クラスのコンス トラクターの 2 番目のパラメーターとしてコード ページを指定します。

次のマクロは、このクラスに基づいています。

- CA2TEX

- CA2CTEX

- CT2WEX

- CT2CWEX

次の typedef は、このクラスに基づいています。

- CA2W

これらのテキスト変換マクロの詳細については、次を参照してください。 [ATL と MFC 文字列変換マクロ](string-conversion-macros.md)します。

## <a name="example"></a>例

参照してください[ATL と MFC 文字列変換マクロ](string-conversion-macros.md)のこれらの文字列変換マクロの使用例についてはします。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlconv.h

##  <a name="ca2wex"></a>  CA2WEX::CA2WEX

コンストラクターです。

```
CA2WEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2WEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>パラメーター

*2 つ*<br/>
変換するテキスト文字列。

*nCodePage*<br/>
コード ページ変換を実行するために使用します。 Windows SDK 関数のコード ページ パラメーターの説明を参照してください。 [MultiByteToWideChar](/windows/desktop/api/stringapiset/nf-stringapiset-multibytetowidechar)の詳細。

### <a name="remarks"></a>Remarks

変換プロセスで使用されるバッファーを割り当てます。

##  <a name="dtor"></a>  CA2WEX:: ~ CA2WEX

デストラクターです。

```
~CA2WEX() throw();
```

### <a name="remarks"></a>Remarks

割り当てられたバッファーを解放します。

##  <a name="m_psz"></a>  CA2WEX::m_psz

ソース文字列が格納されるデータ メンバー。

```
LPWSTR m_psz;
```

##  <a name="m_szbuffer"></a>  CA2WEX::m_szBuffer

変換後の文字列の格納に使用される静的バッファー。

```
wchar_t m_szBuffer[t_nBufferLength];
```

##  <a name="operator_lpwstr"></a>  CA2WEX::operator LPWSTR

変換演算子。

```
operator LPWSTR() const throw();
```

### <a name="return-value"></a>戻り値

LPWSTR を入力すると、テキスト文字列を返します。

## <a name="see-also"></a>関連項目

[CA2AEX クラス](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX クラス](../../atl/reference/ca2caex-class.md)<br/>
[CW2AEX クラス](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEX クラス](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEX クラス](../../atl/reference/cw2wex-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
