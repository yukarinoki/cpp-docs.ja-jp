---
title: CA2AEX クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CA2AEX
- ATLCONV/ATL::CA2AEX
- ATLCONV/ATL::CA2AEX::CA2AEX
- ATLCONV/ATL::CA2AEX::m_psz
- ATLCONV/ATL::CA2AEX::m_szBuffer
dev_langs:
- C++
helpviewer_keywords:
- CA2AEX class
ms.assetid: 57dc65df-d9cf-4a84-99d3-6e031dde3664
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2b0b63f4054459b7d8b3c8aae45cf583f635cd95
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751894"
---
# <a name="ca2aex-class"></a>CA2AEX クラス

このクラスは、文字列変換マクロ CA2TEX と CT2AEX、typedef CA2A によって使用されます。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <int t_nBufferLength = 128>
class CA2AEX
```

#### <a name="parameters"></a>パラメーター

*t_nBufferLength*  
変換プロセスで使用されるバッファーのサイズ。 既定の長さは 128 バイトです。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CA2AEX::CA2AEX](#ca2aex)|コンストラクターです。|
|[CA2AEX:: ~ CA2AEX](#dtor)|デストラクターです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CA2AEX::operator LPSTR](#operator_lpstr)|変換演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CA2AEX::m_psz](#m_psz)|ソース文字列が格納されるデータ メンバー。|
|[CA2AEX::m_szBuffer](#m_szbuffer)|変換後の文字列の格納に使用される静的バッファー。|

## <a name="remarks"></a>Remarks

追加の機能が必要でない限り、独自のコードで CA2TEX、CT2AEX、または CA2A を使用します。

このクラスには、固定サイズの静的バッファー変換の結果を格納するために使用が含まれています。 クラスでは、メモリを使用して割り当てます、結果が大きすぎて静的バッファーに収まるように場合、 **malloc**オブジェクトがスコープ外になるときに、メモリを解放します。 これにより、テキストとは異なり、ATL のこのクラスを安全にループ内で使用して、スタックがオーバーフローするしませんの以前のバージョンで使用できる変換マクロ。

クラスは、失敗をヒープにメモリの割り当てを試みると、それが呼び出す`AtlThrow`E_OUTOFMEMORY の引数を指定しています。

既定では、ATL 変換クラスとマクロは、変換の現在のスレッドの ANSI コード ページを使用します。

次のマクロは、このクラスに基づいています。

- CA2TEX

- CT2AEX

次の typedef は、このクラスに基づいています。

- CA2A

これらのテキスト変換マクロの詳細については、次を参照してください。 [ATL と MFC 文字列変換マクロ](string-conversion-macros.md)します。

## <a name="example"></a>例

参照してください[ATL と MFC 文字列変換マクロ](string-conversion-macros.md)のこれらの文字列変換マクロの使用例についてはします。

## <a name="requirements"></a>要件

**ヘッダー:** atlconv.h

##  <a name="ca2aex"></a>  CA2AEX::CA2AEX

コンストラクターです。

```
CA2AEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2AEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>パラメーター

*2 つ*  
変換するテキスト文字列。

*nCodePage*  
このクラスで使用されていません。

### <a name="remarks"></a>Remarks

翻訳のために必要なバッファーを作成します。

##  <a name="dtor"></a>  CA2AEX:: ~ CA2AEX

デストラクターです。

```
~CA2AEX() throw();
```

### <a name="remarks"></a>Remarks

割り当てられたバッファーを解放します。

##  <a name="m_psz"></a>  CA2AEX::m_psz

ソース文字列が格納されるデータ メンバー。

```
LPSTR m_psz;
```

##  <a name="m_szbuffer"></a>  CA2AEX::m_szBuffer

変換後の文字列の格納に使用される静的バッファー。

```
char m_szBuffer[ t_nBufferLength];
```

##  <a name="operator_lpstr"></a>  CA2AEX::operator LPSTR

変換演算子。

```
operator LPSTR() const throw();
```

### <a name="return-value"></a>戻り値

型 LPSTR としてテキスト文字列を返します。

## <a name="see-also"></a>関連項目

[CA2CAEX クラス](../../atl/reference/ca2caex-class.md)   
[CA2WEX クラス](../../atl/reference/ca2wex-class.md)   
[CW2AEX クラス](../../atl/reference/cw2aex-class.md)   
[CW2CWEX クラス](../../atl/reference/cw2cwex-class.md)   
[CW2WEX クラス](../../atl/reference/cw2wex-class.md)   
[クラスの概要](../../atl/atl-class-overview.md)