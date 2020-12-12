---
description: '詳細情報: アロケーター &lt; void &gt; クラス'
title: allocator&lt;void&gt; クラス
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: a6468c35f4660736cd297ffd7ae3d0738bbf0756
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163510"
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

クラスは、型に対してクラステンプレート [アロケーター](allocator-class.md) を明示的に特殊化し **`void`** ます。 コンストラクターと代入演算子は、クラステンプレートと同じように動作しますが、次の型のみを定義します。

- [const_pointer](allocator-class.md#const_pointer)

- [ポインター](allocator-class.md#pointer)。

- [value_type](allocator-class.md#value_type)。

- 入れ子になったクラステンプレートを再[バインド](allocator-class.md#rebind)します。
