---
description: 詳細については、「 &lt; scoped_allocator 演算子」を参照してください。 &gt;
title: '&lt;scoped_allocator&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- scoped_allocator/std::operator!=
- scoped_allocator/std::operator==
ms.assetid: 4dfe0805-cc6e-479f-887f-a1c164f73837
ms.openlocfilehash: 2f32a42ded9c73cbc2608f3e39f3566deee20e83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197140"
---
# <a name="ltscoped_allocatorgt-operators"></a>&lt;scoped_allocator&gt; 演算子

[operator! =](#op_neq)\
[operator = =](#op_eq_eq)

## <a name="operator"></a><a name="op_neq"></a> operator! =

2 つの `scoped_allocator_adaptor` オブジェクトが等しくないかどうかをテストします。

```cpp
template <class Outer, class... Inner>
bool operator!=(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>パラメーター

*左側*\
左側の `scoped_allocator_adaptor` オブジェクト。

*そうです*\
右側の `scoped_allocator_adaptor` オブジェクト。

### <a name="return-value"></a>戻り値

`!(left == right)`

## <a name="operator"></a><a name="op_eq_eq"></a> operator = =

2 つの `scoped_allocator_adaptor` オブジェクトが等しいかどうかをテストします。

```cpp
template <class Outer, class... Inner>
bool operator==(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>パラメーター

*左側*\
左側の `scoped_allocator_adaptor` オブジェクト。

*そうです*\
右側の `scoped_allocator_adaptor` オブジェクト。

### <a name="return-value"></a>戻り値

`left.outer_allocator() == right.outer_allocator() && left.inner_allocator() == right.inner_allocator()`

## <a name="see-also"></a>関連項目

[<scoped_allocator>](../standard-library/scoped-allocator.md)
