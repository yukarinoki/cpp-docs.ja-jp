---
description: '詳細情報: CSimpleArrayEqualHelper クラス'
title: CSimpleArrayEqualHelper クラス
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
ms.openlocfilehash: e1a5fd3eea5fd6ef7563febc662c5a7a1bc639c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140765"
---
# <a name="csimplearrayequalhelper-class"></a>CSimpleArrayEqualHelper クラス

このクラスは、 [CSimpleArray](../../atl/reference/csimplearray-class.md) クラスのヘルパーです。

## <a name="syntax"></a>構文

```
template <class T>
class CSimpleArrayEqualHelper
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
派生クラス。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSimpleArrayEqualHelper:: IsEqual](#isequal)|雑音2つ `CSimpleArray` のオブジェクト要素が等しいかどうかをテストします。|

## <a name="remarks"></a>解説

この特徴クラスは、クラスを補完するものです `CSimpleArray` 。 オブジェクトに格納されている2つの要素を比較するためのメソッドを提供 `CSimpleArray` します。 既定では、要素は **operator = ()** を使用して比較されますが、独自の等値演算子を持たない複合データ型が配列に含まれている場合は、このクラスをオーバーライドする必要があります。

## <a name="requirements"></a>要件

**ヘッダー:** atl. h

## <a name="csimplearrayequalhelperisequal"></a><a name="isequal"></a> CSimpleArrayEqualHelper:: IsEqual

2つ `CSimpleArray` のオブジェクト要素が等しいかどうかをテストします。

```
static bool IsEqual(
    const T& t1,
    const T& t2);
```

### <a name="parameters"></a>パラメーター

*t1*<br/>
T 型のオブジェクト。

*t2*<br/>
T 型のオブジェクト。

### <a name="return-value"></a>戻り値

要素が等しい場合は true、それ以外の場合は false を返します。

## <a name="see-also"></a>関連項目

[CSimpleArray クラス](../../atl/reference/csimplearray-class.md)<br/>
[CSimpleArrayEqualHelperFalse クラス](../../atl/reference/csimplearrayequalhelperfalse-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
