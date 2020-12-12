---
description: '詳細情報: CSimpleMapEqualHelper クラス'
title: CSimpleMapEqualHelper クラス
ms.date: 11/04/2016
f1_keywords:
- CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualValue
helpviewer_keywords:
- CSimpleMapEqualHelper class
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
ms.openlocfilehash: 2b8ff742bf24b6c6c4354cef652e3fc697ffb1d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140609"
---
# <a name="csimplemapequalhelper-class"></a>CSimpleMapEqualHelper クラス

このクラスは、 [CSimpleMap](../../atl/reference/csimplemap-class.md) クラスのヘルパーです。

## <a name="syntax"></a>構文

```
template <class TKey, class TVal>
class CSimpleMapEqualHelper
```

#### <a name="parameters"></a>パラメーター

*TKey*<br/>
キー要素。

*TVal*<br/>
Value 要素。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSimpleMapEqualHelper::IsEqualKey](#isequalkey)|雑音2つのキーが等しいかどうかをテストします。|
|[CSimpleMapEqualHelper::IsEqualValue](#isequalvalue)|雑音2つの値が等しいかどうかをテストします。|

## <a name="remarks"></a>解説

この特徴クラスは、クラスを補完するものです `CSimpleMap` 。 2つの `CSimpleMap` オブジェクト要素 (具体的にはキーと値のコンポーネント) を比較して等しいかどうかを比較するメソッドを提供します。 既定では、キーと値は **operator = = ()** を使用して比較されますが、独自の等値演算子を持たない複合データ型がマップに含まれている場合は、このクラスをオーバーライドして追加の必要な機能を提供することができます。

## <a name="requirements"></a>要件

**ヘッダー:** atl. h

## <a name="csimplemapequalhelperisequalkey"></a><a name="isequalkey"></a> CSimpleMapEqualHelper::IsEqualKey

2つのキーが等しいかどうかをテストします。

```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```

### <a name="parameters"></a>パラメーター

*k1*<br/>
最初のキー。

*k2*<br/>
2番目のキー。

### <a name="return-value"></a>戻り値

キーが等しい場合は true、それ以外の場合は false を返します。

## <a name="csimplemapequalhelperisequalvalue"></a><a name="isequalvalue"></a> CSimpleMapEqualHelper::IsEqualValue

2つの値が等しいかどうかをテストします。

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

[CSimpleMapEqualHelperFalse クラス](../../atl/reference/csimplemapequalhelperfalse-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
