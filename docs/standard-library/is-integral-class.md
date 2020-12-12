---
description: '詳細情報: is_integral クラス'
title: is_integral クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_integral
helpviewer_keywords:
- is_integral class
- is_integral
ms.assetid: fe9279d0-4495-4e88-bf23-153cc6602397
ms.openlocfilehash: db586054614b9a5ef49ffe9fe8b643b35c65a217
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323702"
---
# <a name="is_integral-class"></a>is_integral クラス

型が整数かどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_integral;
```

### <a name="parameters"></a>パラメーター

*~*\
照会する型。

## <a name="remarks"></a>解説

型 *Ty* が整数型の1つ、または整数型の1つの形式である場合、型述語のインスタンスは true を保持し `cv-qualified` ます。それ以外の場合は、false を保持します。

整数型は、、、、、、、、、、、およびのいずれかです **`bool`** **`char`** **`unsigned char`** **`signed char`** **`wchar_t`** **`short`** **`unsigned short`** **`int`** **`unsigned int`** **`long`** **`unsigned long`** 。 また、それらを提供するコンパイラでは、整数型は、、、 **`long long`** **`unsigned long long`** **`__int64`** および **符号なしの __int64** のいずれかになります。

## <a name="example"></a>例

```cpp
// std__type_traits__is_integral.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_integral<trivial> == " << std::boolalpha
        << std::is_integral<trivial>::value << std::endl;
    std::cout << "is_integral<int> == " << std::boolalpha
        << std::is_integral<int>::value << std::endl;
    std::cout << "is_integral<float> == " << std::boolalpha
        << std::is_integral<float>::value << std::endl;

    return (0);
    }
```

```Output
is_integral<trivial> == false
is_integral<int> == true
is_integral<float> == false
```

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)\
[is_enum クラス](../standard-library/is-enum-class.md)\
[is_floating_point クラス](../standard-library/is-floating-point-class.md)
