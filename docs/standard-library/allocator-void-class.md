---
title: allocator&lt;void&gt; クラス
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: af29c70dca56b1e68eef3614357269c587a77ec9
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623674"
---
# <a name="allocatorltvoidgt-class"></a>allocator&lt;void&gt; クラス

**Void**型へのクラステンプレートアロケーターの特殊化。このコンテキストで意味を持つ型を定義します。

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

## <a name="remarks"></a>Remarks

クラスは、 **void**型に対してクラステンプレート[アロケーター](allocator-class.md)を明示的に特殊化します。 コンストラクターと代入演算子は、クラステンプレートと同じように動作しますが、次の型のみを定義します。

- [const_pointer](allocator-class.md#const_pointer)

- [ポインター](allocator-class.md#pointer)。

- [value_type](allocator-class.md#value_type)。

- 入れ子になったクラステンプレートを再[バインド](allocator-class.md#rebind)します。
