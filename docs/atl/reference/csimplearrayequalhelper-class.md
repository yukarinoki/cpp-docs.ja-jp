---
title: クラスを配列します。
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
ms.openlocfilehash: 386b005777b3e31dd74916a41bc5af2ab82df210
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330880"
---
# <a name="csimplearrayequalhelper-class"></a>クラスを配列します。

このクラスは、クラスのヘルパー[です](../../atl/reference/csimplearray-class.md)。

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
|[を指定します。](#isequal)|(静的)2`CSimpleArray`つのオブジェクト要素が等しいかテストします。|

## <a name="remarks"></a>解説

この特徴クラスはクラスの`CSimpleArray`補足です。 オブジェクトに格納されている 2 つの要素を比較`CSimpleArray`するメソッドを提供します。 デフォルトでは、要素は**operator=()** を使用して比較されますが、配列に独自の等価演算子を持たない複合データ型が含まれている場合は、このクラスをオーバーライドする必要があります。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsimpcoll.h

## <a name="csimplearrayequalhelperisequal"></a><a name="isequal"></a>を指定します。

2`CSimpleArray`つのオブジェクト要素が等しいかテストします。

```
static bool IsEqual(
    const T& t1,
    const T& t2);
```

### <a name="parameters"></a>パラメーター

*T1*<br/>
T 型のオブジェクト。

*t2*<br/>
T 型のオブジェクト。

### <a name="return-value"></a>戻り値

要素が等しい場合は true、そうでない場合は false を返します。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/csimplearray-class.md)<br/>
[クラスを返します。](../../atl/reference/csimplearrayequalhelperfalse-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
