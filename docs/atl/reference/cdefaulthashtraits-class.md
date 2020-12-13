---
description: '詳細情報: CDefaultHashTraits クラス'
title: CDefaultHashTraits クラス
ms.date: 11/04/2016
f1_keywords:
- CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits::Hash
helpviewer_keywords:
- CDefaultHashTraits class
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
ms.openlocfilehash: 85cc881466be03931d435d91a48548456d74305b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141883"
---
# <a name="cdefaulthashtraits-class"></a>CDefaultHashTraits クラス

このクラスは、ハッシュ値を計算するための静的関数を提供します。

## <a name="syntax"></a>構文

```
template<typename T>
class CDefaultHashTraits
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクションに格納するデータの型。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDefaultHashTraits:: Hash](#hash)|雑音指定された要素のハッシュ値を計算するには、この関数を呼び出します。|

## <a name="remarks"></a>解説

このクラスには、特定の要素のハッシュ値を返す単一の静的関数が含まれています。 このクラスは、 [CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)によって使用されます。

詳細については、「 [ATL コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll. h

## <a name="cdefaulthashtraitshash"></a><a name="hash"></a> CDefaultHashTraits:: Hash

指定された要素のハッシュ値を計算するには、この関数を呼び出します。

```
static ULONG Hash(const T& element) throw();
```

### <a name="parameters"></a>パラメーター

*element*<br/>
要素。

### <a name="return-value"></a>戻り値

ハッシュ値を返します。

### <a name="remarks"></a>解説

既定のハッシュアルゴリズムは非常に単純です。戻り値は要素番号です。 より複雑なアルゴリズムが必要な場合は、この関数をオーバーライドします。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
