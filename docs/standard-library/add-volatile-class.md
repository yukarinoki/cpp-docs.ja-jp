---
description: '詳細情報: add_volatile クラス'
title: add_volatile クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_volatile
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
ms.openlocfilehash: 6f138c9009d127efe2d640124d9af1e114eb0732
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319870"
---
# <a name="add_volatile-class"></a>add_volatile クラス

**`volatile`** 指定された型から型を作成します。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct add_volatile;

template <class T>
using add_volatile_t = typename add_volatile<T>::type;
```

### <a name="parameters"></a>パラメーター

*\T*\
変更する型。

## <a name="remarks"></a>解説

のインスタンスには、t が `add_volatile<T>` **`typedef`** `type` 参照、関数 、または volatile で修飾された型である場合は *t* 、それ以外の場合は t となるメンバーがあり **`volatile`** ます。エイリアス `add_volatile_t` は、メンバーにアクセスするためのショートカットです **`typedef`** `type` 。

## <a name="example"></a>例

```cpp
#include <type_traits>
#include <iostream>

int main()
{
    std::add_volatile_t<int> *p = (volatile int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_volatile<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_volatile<int> == int
```

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](type-traits.md)\
[remove_volatile クラス](remove-volatile-class.md)
