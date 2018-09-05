---
title: CSimpleMapEqualHelperFalse クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualValue
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7bfa615af00535d899533f21abf933f35bcd5bbf
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43767996"
---
# <a name="csimplemapequalhelperfalse-class"></a>CSimpleMapEqualHelperFalse クラス

このクラスのヘルパーは、 [CSimpleMap](../../atl/reference/csimplemap-class.md)クラス。

## <a name="syntax"></a>構文

```
template <class TKey, class TVal>  
class CSimpleMapEqualHelperFalse
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)|(静的)2 つのキーの等価性をテストします。|
|[CSimpleMapEqualHelperFalse::IsEqualValue](#isequalvalue)|(静的)False を返します。|

## <a name="remarks"></a>Remarks

この特性クラスを補足するため、`CSimpleMap`クラス。 含まれる 2 つの要素を比較するためのメソッドを提供します、`CSimpleMap`オブジェクト、具体的には 2 つの値の要素またはキーの 2 つの要素。

値の比較は、常に false を返すし、さらが呼び出されます`ATLASSERT`引数が参照されている場合は false。 等しいかどうかテストが十分に定義されていない場合、このクラスは、ほとんどのメソッドに対して正常に動作しなどの比較に依存する方法を明確に定義された方法で失敗する可能性がキー/値ペアを含むマップを[CSimpleMap:。FindVal](../../atl/reference/csimplemap-class.md#findval)します。

## <a name="requirements"></a>要件

**ヘッダー:** atlsimpcoll.h

##  <a name="isequalkey"></a>  CSimpleMapEqualHelperFalse::IsEqualKey

2 つのキーの等価性をテストします。

```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```

### <a name="parameters"></a>パラメーター

*k1*  
最初のキー。

*k2*  
2 番目のキー。

### <a name="return-value"></a>戻り値

キーが false でそれ以外の場合、等しい場合は true を返します。

### <a name="remarks"></a>Remarks

このメソッドを呼び出す[CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)します。

##  <a name="isequalvalue"></a>  CSimpleMapEqualHelperFalse::IsEqualValue

false を返します。

```
static bool IsEqualValue(const TVal&, const TVal&);
```

### <a name="return-value"></a>戻り値

false を返します。

### <a name="remarks"></a>Remarks

このメソッドは常に false を返し、呼び出されます`ATLASSERT`引数が参照されている場合は false。 目的は、`CSimpleMapEqualHelperFalse::IsEqualValue`を強制的に比較を使用して、等しいかどうかテストが適切に定義されていないときに、明確に定義された方法で失敗するメソッド。

## <a name="see-also"></a>関連項目

[CSimpleMapEqualHelper クラス](../../atl/reference/csimplemapequalhelper-class.md)   
[クラスの概要](../../atl/atl-class-overview.md)
