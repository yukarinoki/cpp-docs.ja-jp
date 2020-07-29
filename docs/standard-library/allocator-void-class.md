---
title: allocator&lt;void&gt; クラス
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: b6ca3f8b994756a21d85860fd8aff429ee38e58b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87204931"
---
# <a name="allocatorltvoidgt-class"></a>allocator&lt;void&gt; クラス

**`void`** このコンテキストで意味を持つ型を定義する、クラステンプレートアロケーターを型に特殊化したもの。

## <a name="syntax"></a>構文

```cpp
template <>
class allocator<void> {
    typedef void *pointer;
    typedef const void *const_pointer;
    typedef void value_type;
    template <class Other>
    struct rebind;
    allocator();
    allocator(const allocator<void>&);

    template <class Other>
    allocator(const allocator<Other>&);

    template <class Other>
    allocator<void>& operator=(const allocator<Other>&);
};
```

## <a name="remarks"></a>解説

クラスは、型に対してクラステンプレート[アロケーター](allocator-class.md)を明示的に特殊化し **`void`** ます。 コンストラクターと代入演算子は、クラステンプレートと同じように動作しますが、次の型のみを定義します。

- [const_pointer](allocator-class.md#const_pointer)

- [ポインター](allocator-class.md#pointer)。

- [value_type](allocator-class.md#value_type)。

- 入れ子になったクラステンプレートを再[バインド](allocator-class.md#rebind)します。
