---
title: allocator&lt;void&gt; クラス
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: 7ac7fbaa8c50eb13457271cf96ddc3412733c833
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245881"
---
# <a name="allocatorltvoidgt-class"></a>allocator&lt;void&gt; クラス

入力するテンプレート クラス アロケーターの特殊化**void**、このコンテキストで意味のある型を定義します。

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

クラスは、テンプレート クラスを明示的に特殊化[アロケーター](../standard-library/allocator-class.md)型**void**します。 コンストラクターと代入演算子の動作は、同じテンプレート クラスの動作と同じですが、次の型のみを定義します。

- [const_pointer](../standard-library/allocator-class.md#const_pointer)

- [pointer](../standard-library/allocator-class.md#pointer)

- [value_type](../standard-library/allocator-class.md#value_type)

- [rebind](../standard-library/allocator-class.md#rebind)、入れ子になったテンプレート クラス
