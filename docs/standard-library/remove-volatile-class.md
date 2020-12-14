---
description: '詳細情報: remove_volatile クラス'
title: remove_volatile クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::remove_volatile
helpviewer_keywords:
- remove_volatile class
- remove_volatile
ms.assetid: 8b87e2c2-a581-4eb3-8691-c5603910d61d
ms.openlocfilehash: 45f0ba9ba4685a471f13d0d36ae5080eb667a9f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344875"
---
# <a name="remove_volatile-class"></a>remove_volatile クラス

型から非 volatile 型を作成します。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct remove_volatile;

template <class T>
using remove_volatile_t = typename remove_volatile<T>::type;
```

### <a name="parameters"></a>パラメーター

*\T*\
変更する型。

## <a name="remarks"></a>解説

`remove_volatile<T>`T の形式がである場合、のインスタンスは変更された型を保持 `T1`  `volatile T1` します。それ以外の場合は *t* です。

## <a name="example"></a>例

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_volatile_t<volatile int> *)0;

    p = p;  // to quiet "unused" warning
    std::cout << " remove_volatile_t<volatile int> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_volatile_t<volatile int> == int
```

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)\
[add_volatile クラス](../standard-library/add-volatile-class.md)
