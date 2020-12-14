---
description: 詳細については、「 &lt; memory_resource 演算子」を参照してください。 &gt;
title: '&lt;memory_resource &gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- memory_resource/std::operator!=
- memory_resource/std::operator==
helpviewer_keywords:
- std::operator!= (memory_resource)
- std::operator== (memory_resource)
ms.openlocfilehash: 28c1dee4e2f022cdba14b7f71e7b9a2e40bc1162
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183842"
---
# <a name="ltmemory_resourcegt-operators"></a>&lt;memory_resource &gt; 演算子

## <a name="operator"></a><a name="op_neq"></a> operator! =

演算子の左側の memory_resource オブジェクトが右側の memory_resource オブジェクトと等しくないかどうかを調べます。

```cpp
template <class T1, class T2>
    bool operator!=(const polymorphic_allocator<T1>& a, const polymorphic_allocator<T2>& b) noexcept;
```

## <a name="operator"></a><a name="op_eq_eq"></a> operator = =

演算子の左側の memory_resource オブジェクトが右側の memory_resource オブジェクトと等しいかどうかを調べます。

```cpp
template <class T1, class T2>
    bool operator==(const polymorphic_allocator<T1>& a, const polymorphic_allocator<T2>& b) noexcept;
```
