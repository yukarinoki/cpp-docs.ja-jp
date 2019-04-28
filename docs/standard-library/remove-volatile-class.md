---
title: remove_volatile クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::remove_volatile
helpviewer_keywords:
- remove_volatile class
- remove_volatile
ms.assetid: 8b87e2c2-a581-4eb3-8691-c5603910d61d
ms.openlocfilehash: b327bb8362e1f6523d22950974012747e0de99f8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62185933"
---
# <a name="removevolatile-class"></a>remove_volatile クラス

型から非 volatile 型を作成します。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct remove_volatile;

template <class T>
using remove_volatile_t = typename remove_volatile<T>::type;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
変更する型。

## <a name="remarks"></a>Remarks

インスタンス`remove_volatile<T>`、修飾型であるを保持`T1`とき*T*の形式は`volatile T1`それ以外の場合、 *T*します。

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

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[add_volatile クラス](../standard-library/add-volatile-class.md)<br/>
