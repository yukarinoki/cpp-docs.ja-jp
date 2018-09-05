---
title: CW2AEX クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CW2AEX
- ATLCONV/ATL::CW2AEX
- ATLCONV/ATL::CW2AEX::CW2AEX
- ATLCONV/ATL::CW2AEX::m_psz
- ATLCONV/ATL::CW2AEX::m_szBuffer
dev_langs:
- C++
helpviewer_keywords:
- CW2AEX class
ms.assetid: 44dc2cf5-dd30-440b-a9b9-b21b43f49843
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2cd88555ee28b7bdddef51371ba2774047464678
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43759484"
---
# <a name="cw2aex-class"></a>CW2AEX クラス

このクラスは、文字列変換マクロ CT2AEX、CW2TEX、CW2CTEX、および CT2CAEX、および typedef CW2A によって使用されます。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<int t_nBufferLength = 128>  
class CW2AEX
```

#### <a name="parameters"></a>パラメーター

*t_nBufferLength*  
変換プロセスで使用されるバッファーのサイズ。 既定の長さは 128 バイトです。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CW2AEX::CW2AEX](#cw2aex)|コンストラクターです。|
|[CW2AEX:: ~ CW2AEX](#dtor)|デストラクターです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CW2AEX::operator LPSTR](#operator_lpstr)|変換演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CW2AEX::m_psz](#m_psz)|ソース文字列が格納されるデータ メンバー。|
|[CW2AEX::m_szBuffer](#m_szbuffer)|変換後の文字列の格納に使用される静的バッファー。|

## <a name="remarks"></a>Remarks

追加の機能が必要でない限り、コードで CT2AEX、CW2TEX、CW2CTEX、CT2CAEX、または CW2A を使用します。

このクラスには、固定サイズの静的バッファー変換の結果を格納するために使用が含まれています。 クラスでは、メモリを使用して割り当てます、結果が大きすぎて静的バッファーに収まるように場合、 **malloc**オブジェクトがスコープ外になるときに、メモリを解放します。 これにより、テキストとは異なり、ATL のこのクラスを安全にループ内で使用して、スタックがオーバーフローするしませんの以前のバージョンで使用できる変換マクロ。

クラスは、失敗をヒープにメモリの割り当てを試みると、それが呼び出す`AtlThrow`E_OUTOFMEMORY の引数を指定しています。

既定では、ATL 変換クラスとマクロは、変換の現在のスレッドの ANSI コード ページを使用します。 特定の変換の動作をオーバーライドする場合は、クラスのコンス トラクターの 2 番目のパラメーターとしてコード ページを指定します。

次のマクロは、このクラスに基づいています。

- CT2AEX

- CW2TEX

- CW2CTEX

- CT2CAEX

次の typedef は、このクラスに基づいています。

- CW2A

これらのテキスト変換マクロの詳細については、次を参照してください。 [ATL と MFC 文字列変換マクロ](string-conversion-macros.md)します。

## <a name="example"></a>例

参照してください[ATL と MFC 文字列変換マクロ](string-conversion-macros.md)のこれらの文字列変換マクロの使用例についてはします。

## <a name="requirements"></a>要件

**ヘッダー:** atlconv.h

##  <a name="cw2aex"></a>  CW2AEX::CW2AEX

コンストラクターです。

```
CW2AEX(LPCWSTR psz, UINT nCodePage) throw(...);  
CW2AEX(LPCWSTR psz) throw(...);
```

### <a name="parameters"></a>パラメーター

*2 つ*  
変換するテキスト文字列。

*nCodePage*  
コード ページ変換を実行するために使用します。 Windows SDK 関数のコード ページ パラメーターの説明を参照してください。 [MultiByteToWideChar](/windows/desktop/api/stringapiset/nf-stringapiset-multibytetowidechar)の詳細。

### <a name="remarks"></a>Remarks

変換プロセスで使用されるバッファーを割り当てます。

##  <a name="dtor"></a>  CW2AEX:: ~ CW2AEX

デストラクターです。

```
~CW2AEX() throw();
```

### <a name="remarks"></a>Remarks

割り当てられたバッファーを解放します。

##  <a name="m_psz"></a>  CW2AEX::m_psz

ソース文字列が格納されるデータ メンバー。

```
LPSTR m_psz;
```

##  <a name="m_szbuffer"></a>  CW2AEX::m_szBuffer

変換後の文字列の格納に使用される静的バッファー。

```
char m_szBuffer[t_nBufferLength];
```

##  <a name="operator_lpstr"></a>  CW2AEX::operator LPSTR

変換演算子。

```  
operator LPSTR() const throw();
```

### <a name="return-value"></a>戻り値

型 LPSTR としてテキスト文字列を返します。

## <a name="see-also"></a>関連項目

[CA2AEX クラス](../../atl/reference/ca2aex-class.md)   
[CA2CAEX クラス](../../atl/reference/ca2caex-class.md)   
[CA2WEX クラス](../../atl/reference/ca2wex-class.md)   
[CW2CWEX クラス](../../atl/reference/cw2cwex-class.md)   
[CW2WEX クラス](../../atl/reference/cw2wex-class.md)   
[クラスの概要](../../atl/atl-class-overview.md)
