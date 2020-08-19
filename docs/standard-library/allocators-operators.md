---
title: '&lt;allocators&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: 2d2f928ab3773ed8e0b0afdc0113db2ef5b2a3dd
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561219"
---
# <a name="ltallocatorsgt-operators"></a>&lt;allocators&gt; 演算子

これらは、アロケーターで定義されているグローバルテンプレート演算子関数です &lt; &gt; 。 クラスメンバー演算子関数については、クラスのドキュメントを参照してください。

|||
|-|-|
|[operator! =](#op_neq)|[operator = =](#op_eq_eq)|

## <a name="operator"></a><a name="op_neq"></a> operator! =

指定したクラスのアロケーター オブジェクト間の非等値をテストします。

```cpp
template <class Type, class Sync>
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
不等性をテストする一方のアロケーター オブジェクト。

*そうです*\
不等性をテストする一方のアロケーター オブジェクト。

### <a name="return-value"></a>戻り値

**`true`** アロケーターオブジェクトが等しくない場合は、 **`false`** アロケーターオブジェクトが等しい場合は。

### <a name="remarks"></a>解説

このテンプレート演算子は `!(left == right)` を返します。

## <a name="operator"></a><a name="op_eq_eq"></a> operator = =

指定したクラスのアロケーター オブジェクト間の等値をテストします。

```cpp
template <class Type, class Sync>
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
等しいかどうかをテストする一方のアロケーター オブジェクト。

*そうです*\
等しいかどうかをテストする一方のアロケーター オブジェクト。

### <a name="return-value"></a>戻り値

**`true`** アロケーターオブジェクトが等しい場合は。 **`false`** アロケーターオブジェクトが等しくない場合。

### <a name="remarks"></a>解説

このテンプレート演算子は `left.equals(right)` を返します。

## <a name="see-also"></a>関連項目

[\<allocators>](allocators-header.md)
