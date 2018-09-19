---
title: CSimpleMapEqualHelper クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualValue
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelper class
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 654b801c61d00f179d6d7ef88763b323d6503873
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050581"
---
# <a name="csimplemapequalhelper-class"></a>CSimpleMapEqualHelper クラス

このクラスのヘルパーは、 [CSimpleMap](../../atl/reference/csimplemap-class.md)クラス。

## <a name="syntax"></a>構文

```
template <class TKey, class TVal>
class CSimpleMapEqualHelper
```

#### <a name="parameters"></a>パラメーター

*TKey*<br/>
重要な要素です。

*TVal*<br/>
値の要素。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSimpleMapEqualHelper::IsEqualKey](#isequalkey)|(静的)2 つのキーの等価性をテストします。|
|[CSimpleMapEqualHelper::IsEqualValue](#isequalvalue)|(静的)2 つの値が等しいかどうかをテストします。|

## <a name="remarks"></a>Remarks

この特性クラスを補足するため、`CSimpleMap`クラス。 2 つを比較するためのメソッドを提供`CSimpleMap`object 要素 (具体的には、キーと値コンポーネント) の等価性。 既定では、キーと値が比較されます**operator==()** が必要な追加機能を提供するこのクラスをオーバーライドできますが、マップに独自の等値演算子の複合データ型が含まれている場合。

## <a name="requirements"></a>要件

**ヘッダー:** atlsimpcoll.h

##  <a name="isequalkey"></a>  CSimpleMapEqualHelper::IsEqualKey

2 つのキーの等価性をテストします。

```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```

### <a name="parameters"></a>パラメーター

*k1*<br/>
最初のキー。

*k2*<br/>
2 番目のキー。

### <a name="return-value"></a>戻り値

キーが false でそれ以外の場合、等しい場合は true を返します。

##  <a name="isequalvalue"></a>  CSimpleMapEqualHelper::IsEqualValue

2 つの値が等しいかどうかをテストします。

```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```

### <a name="parameters"></a>パラメーター

*v1*<br/>
最初の値。

*v2*<br/>
2 番目の値。

### <a name="return-value"></a>戻り値

値が false でそれ以外の場合、等しい場合は true を返します。

## <a name="see-also"></a>関連項目

[CSimpleMapEqualHelperFalse クラス](../../atl/reference/csimplemapequalhelperfalse-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
