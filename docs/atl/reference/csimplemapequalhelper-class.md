---
title: クラスを指定します。
ms.date: 11/04/2016
f1_keywords:
- CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualValue
helpviewer_keywords:
- CSimpleMapEqualHelper class
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
ms.openlocfilehash: d137a35a517ea93139f036f6e9a7a8de06d518a7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330750"
---
# <a name="csimplemapequalhelper-class"></a>クラスを指定します。

このクラスは[、CSimpleMap](../../atl/reference/csimplemap-class.md)クラスのヘルパーです。

## <a name="syntax"></a>構文

```
template <class TKey, class TVal>
class CSimpleMapEqualHelper
```

#### <a name="parameters"></a>パラメーター

*Tkey*<br/>
キー要素。

*TVal*<br/>
値要素。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を指定します。](#isequalkey)|(静的)2 つのキーが等しいかテストします。|
|[を指定します。](#isequalvalue)|(静的)2 つの値が等しいかテストします。|

## <a name="remarks"></a>解説

この特徴クラスはクラスの`CSimpleMap`補足です。 2 つの`CSimpleMap`オブジェクト要素 (具体的にはキーコンポーネントと値コンポーネント) を比較して等しい値を比較するメソッドを提供します。 デフォルトでは、キーと値は**operator==()** を使用して比較されますが、マップに独自の等価演算子を持たない複合データ型が含まれている場合、このクラスをオーバーライドして追加の必要な機能を提供できます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsimpcoll.h

## <a name="csimplemapequalhelperisequalkey"></a><a name="isequalkey"></a>を指定します。

2 つのキーが等しいかテストします。

```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```

### <a name="parameters"></a>パラメーター

*k1*<br/>
最初のキー。

*k2*<br/>
2 番目のキー。

### <a name="return-value"></a>戻り値

キーが等しい場合は true、それ以外の場合は false を返します。

## <a name="csimplemapequalhelperisequalvalue"></a><a name="isequalvalue"></a>を指定します。

2 つの値が等しいかテストします。

```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```

### <a name="parameters"></a>パラメーター

*v1*<br/>
最初の値。

*v2*<br/>
2 番目の値。

### <a name="return-value"></a>戻り値

値が等しい場合は true、それ以外の場合は false を返します。

## <a name="see-also"></a>関連項目

[クラスを指定します。](../../atl/reference/csimplemapequalhelperfalse-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
