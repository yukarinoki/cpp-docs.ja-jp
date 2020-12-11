---
description: '詳細情報: remove_cv クラス'
title: remove_cv クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::remove_cv
helpviewer_keywords:
- remove_cv class
- remove_cv
ms.assetid: 8502602a-1c80-479c-84e0-33bd1d6496d6
ms.openlocfilehash: 2842c250ef46bf4fe1d36e6159bfaaf09b872034
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159688"
---
# <a name="remove_cv-class"></a>remove_cv クラス

型から非 const/volatile 型を作成します。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct remove_cv;

template <class T>
using remove_cv_t = typename remove_cv<T>::type;
```

### <a name="parameters"></a>パラメーター

*\T*\
変更する型。

## <a name="remarks"></a>解説

T の形式が、 `remove_cv<T>` 、またはの場合、のインスタンスは変更された型を保持し `T1`  `const T1` `volatile T1` `const volatile T1` ます。それ以外の場合は *t* です。

## <a name="example"></a>例

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_cv_t<const volatile int> *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "remove_cv_t<const volatile int> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_cv_t<const volatile int> == int
```

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)\
[remove_const クラス](../standard-library/remove-const-class.md)\
[remove_volatile クラス](../standard-library/remove-volatile-class.md)
