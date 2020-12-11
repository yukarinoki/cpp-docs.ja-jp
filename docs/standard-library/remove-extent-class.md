---
description: '詳細情報: remove_extent クラス'
title: remove_extent クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::remove_extent
helpviewer_keywords:
- remove_extent class
- remove_extent
ms.assetid: b9320862-3891-49fc-80bc-571eb2c035cf
ms.openlocfilehash: 6f088d58cafdafd9c6ebe4c1fcbbbd8db4dff69c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159675"
---
# <a name="remove_extent-class"></a>remove_extent クラス

配列型から要素型を作成します。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct remove_extent;

template <class T>
using remove_extent_t = typename remove_extent<T>::type;
```

### <a name="parameters"></a>パラメーター

*\T*\
変更する型。

## <a name="remarks"></a>解説

`remove_extent<T>`T の形式がである場合、のインスタンスは変更された型を保持 `T1`  `T1[N]` します。それ以外の場合は *t* です。

## <a name="example"></a>例

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    std::cout << "remove_extent_t<int> == "
        << typeid(std::remove_extent_t<int>).name()
        << std::endl;T
    std::cout << "remove_extent_t<int[5]> == "
        << typeid(std::remove_extent_t<int[5]>).name()
        << std::endl;T
    std::cout << "remove_extent_t<int[5][10]> == "
        << typeid(std::remove_extent_t<int[5][10]>).name()
        << std::endl;
    return (0);
    }
```

```Output
remove_extent_t<int> == int
remove_extent_t<int[5]> == int
remove_extent_t<int[5][10]> == int [10]
```

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)\
[remove_all_extents クラス](../standard-library/remove-all-extents-class.md)
