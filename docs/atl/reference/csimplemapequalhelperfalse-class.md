---
description: '詳細情報: CSimpleMapEqualHelperFalse クラス'
title: CSimpleMapEqualHelperFalse クラス
ms.date: 11/04/2016
f1_keywords:
- CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualValue
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
ms.openlocfilehash: 5bad8232dc1a96fc743a3526acdb86b839601d9a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140583"
---
# <a name="csimplemapequalhelperfalse-class"></a>CSimpleMapEqualHelperFalse クラス

このクラスは、 [CSimpleMap](../../atl/reference/csimplemap-class.md) クラスのヘルパーです。

## <a name="syntax"></a>構文

```
template <class TKey, class TVal>
class CSimpleMapEqualHelperFalse
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)|雑音2つのキーが等しいかどうかをテストします。|
|[CSimpleMapEqualHelperFalse::IsEqualValue](#isequalvalue)|雑音False を返します。|

## <a name="remarks"></a>解説

この特徴クラスは、クラスを補完するものです `CSimpleMap` 。 オブジェクトに含まれる2つの要素 `CSimpleMap` (具体的には、2つの値要素または2つのキー要素) を比較するためのメソッドを提供します。

値の比較では常に false が返され、さらに、が `ATLASSERT` 参照されている場合は、引数が false の引数を指定してが呼び出されます。 等値テストが十分に定義されていない場合、このクラスを使用すると、キーと値のペアを含むマップをほとんどのメソッドで正しく動作させることができますが、 [CSimpleMap:: FindVal](../../atl/reference/csimplemap-class.md#findval)などの比較に依存するメソッドに対しては、適切に定義された方法では失敗します。

## <a name="requirements"></a>要件

**ヘッダー:** atl. h

## <a name="csimplemapequalhelperfalseisequalkey"></a><a name="isequalkey"></a> CSimpleMapEqualHelperFalse::IsEqualKey

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

### <a name="remarks"></a>解説

このメソッドは、 [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)を呼び出します。

## <a name="csimplemapequalhelperfalseisequalvalue"></a><a name="isequalvalue"></a> CSimpleMapEqualHelperFalse::IsEqualValue

false を返します。

```
static bool IsEqualValue(const TVal&, const TVal&);
```

### <a name="return-value"></a>戻り値

false を返します。

### <a name="remarks"></a>解説

このメソッドは常に false を返し、 `ATLASSERT` 参照されている場合は false の引数を指定してを呼び出します。 の目的は、 `CSimpleMapEqualHelperFalse::IsEqualValue` 等値テストが適切に定義されていない場合に、比較を使用してメソッドを明確に定義された方法で失敗させることです。

## <a name="see-also"></a>関連項目

[CSimpleMapEqualHelper クラス](../../atl/reference/csimplemapequalhelper-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
