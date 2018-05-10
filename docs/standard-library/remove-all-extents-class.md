---
title: remove_all_extents クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::remove_all_extents
dev_langs:
- C++
helpviewer_keywords:
- remove_all_extents class
- remove_all_extents
ms.assetid: 548dc536-82e7-423a-b8c1-443d66d9632e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d027f2c1e9d8f5d4172fd3deff179d9ec8336baf
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="removeallextents-class"></a>remove_all_extents クラス

配列型から非配列型を作成します。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct remove_all_extents;

template <class T>
using remove_all_extents_t = typename remove_all_extents<T>::type;
```

### <a name="parameters"></a>パラメーター

`T` 変更する型。

## <a name="remarks"></a>コメント

`remove_all_extents<T>` のインスタンスは、配列型 `T` の要素の型から、すべての配列次元を取り除いた修飾型を保持します。`T` が配列型でない場合は、`T` を保持します。

## <a name="example"></a>例

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    std::cout << "remove_all_extents<int> == "
        << typeid(std::remove_all_extents_t<int>).name()
        << std::endl;
    std::cout << "remove_all_extents_t<int[5]> == "
        << typeid(std::remove_all_extents_t<int[5]>).name()
        << std::endl;
    std::cout << "remove_all_extents_t<int[5][10]> == "
        << typeid(std::remove_all_extents_t<int[5][10]>).name()
        << std::endl;

    return (0);
    }
```

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_extent クラス](../standard-library/remove-extent-class.md)<br/>
