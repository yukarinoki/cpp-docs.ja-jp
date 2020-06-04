---
title: クラスを指定します。
ms.date: 11/04/2016
f1_keywords:
- CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualValue
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
ms.openlocfilehash: b6bf1d4e3be849004e13e593fb5f4b5cb87f8123
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330737"
---
# <a name="csimplemapequalhelperfalse-class"></a>クラスを指定します。

このクラスは[、CSimpleMap](../../atl/reference/csimplemap-class.md)クラスのヘルパーです。

## <a name="syntax"></a>構文

```
template <class TKey, class TVal>
class CSimpleMapEqualHelperFalse
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を指定します。](#isequalkey)|(静的)2 つのキーが等しいかテストします。|
|[値が等しい](#isequalvalue)|(静的)false を返します。|

## <a name="remarks"></a>解説

この特徴クラスはクラスの`CSimpleMap`補足です。 オブジェクトに含まれる 2 つの要素、特`CSimpleMap`に 2 つの値要素または 2 つのキー要素を比較するメソッドを提供します。

値比較は常に false を返し、さらに、`ATLASSERT`参照される場合は false の引数を指定して呼び出します。 等値テストが十分に定義されていない状況では、このクラスは、ほとんどのメソッドでキー/値ペアを含むマップが正しく動作しますが[、CSimpleMap::FindVal](../../atl/reference/csimplemap-class.md#findval)などの比較に依存するメソッドに対して明確に定義された方法で失敗します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsimpcoll.h

## <a name="csimplemapequalhelperfalseisequalkey"></a><a name="isequalkey"></a>を指定します。

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

### <a name="remarks"></a>解説

このメソッドは[、を](../../atl/reference/csimplearrayequalhelper-class.md)呼び出します。

## <a name="csimplemapequalhelperfalseisequalvalue"></a><a name="isequalvalue"></a>値が等しい

false を返します。

```
static bool IsEqualValue(const TVal&, const TVal&);
```

### <a name="return-value"></a>戻り値

false を返します。

### <a name="remarks"></a>解説

このメソッドは常に false を`ATLASSERT`返し、参照が行われる場合は false の引数を指定して呼び出します。 等価性テスト`CSimpleMapEqualHelperFalse::IsEqualValue`が適切に定義されていない場合に、比較を使用するメソッドが明確に定義された方法で失敗するように強制することを目的とします。

## <a name="see-also"></a>関連項目

[クラスを指定します。](../../atl/reference/csimplemapequalhelper-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
