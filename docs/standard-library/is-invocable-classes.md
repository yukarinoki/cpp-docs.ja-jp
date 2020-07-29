---
title: is_invocable、is_invocable_r、is_nothrow_invocable、is_nothrow_invocable_r クラス
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::is_invocable
- type_traits/std::is_invocable_r
- type_traits/std::is_nothrow_invocable
- type_traits/std::is_nothrow_invocable_r
helpviewer_keywords:
- is_invocable class
- is_invocable
- is_invocable_r class
- is_invocable_r
- is_nothrow_invocable class
- is_nothrow_invocable
- is_nothrow_invocable_r class
- is_nothrow_invocable_r
ms.openlocfilehash: 47801eff0ea0c41c7b69dfb7a1aa5190a43f1b75
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233107"
---
# <a name="is_invocable-is_invocable_r-is_nothrow_invocable-is_nothrow_invocable_r-classes"></a>is_invocable、is_invocable_r、is_nothrow_invocable、is_nothrow_invocable_r クラス

これらのテンプレートは、指定された引数の型を使用して型を呼び出すことができるかどうかを判断します。 `is_invocable_r``is_nothrow_invocable_r`また、呼び出しの結果が特定の型に変換可能かどうかを判断します。 `is_nothrow_invocable``is_nothrow_invocable_r`また、呼び出しが例外をスローしないことがわかっているかどうかを判断します。 C++ 17 で追加されました。

## <a name="syntax"></a>構文

```cpp
template <class Callable, class... Args>
struct is_invocable;

template <class Convertible, class Callable, class... Args>
struct is_invocable_r;

template <class Callable, class... Args>
struct is_nothrow_invocable;

template <class Convertible, class Callable, class... Args>
struct is_nothrow_invocable_r;

// Helper templates
template <class Callable, class... Args>
inline constexpr bool is_invocable_v =
    std::is_invocable<Callable, Args...>::value;

template <class Convertible, class Callable, class... Args>
inline constexpr bool is_invocable_r_v =
    std::is_invocable_r<Convertible, Callable, Args...>::value;

template <class Callable, class... Args>
inline constexpr bool is_nothrow_invocable_v =
    std::is_nothrow_invocable<Callable, Args...>::value;

template <class Convertible, class Callable, class... Args>
inline constexpr bool is_nothrow_invocable_r_v =
    std::is_nothrow_invocable_r<Convertible, Callable, Args...>::value;
```

### <a name="parameters"></a>パラメーター

*呼び出し可能*\
照会する呼び出し可能型。

*Value*\
照会する引数の型。

*コンバーチブル*\
*呼び出し*可能の結果を変換できる型である必要があります。

## <a name="remarks"></a>解説

型の述語は、 `is_invocable` 未評価のコンテキストで引数引数を使用して呼び出し*Args*可能な型を呼び出すことができる場合に true*を*保持します。

`is_invocable_r`型述語は、未評価のコンテキストで引数*Callable*引数を使用して呼び出し可能*Args*な型を呼び出すことができる場合に True を保持し、*変換*可能に変換可能な結果型を生成します。

型の述語は、評価され `is_nothrow_invocable` ないコンテキストで引数引数を使用して呼び出し可能な型を呼び出すことができ、そのような呼び出しが例外をスローしない*ことが*わかっている場合*に、* true を保持します。

型の述語は、 `is_nothrow_invocable_r` 未評価のコンテキストで*Callable*引数*Args*を使用して呼び出し可能な型を呼び出すことができる場合に True を保持し、*変換*可能なに変換可能な結果型を生成します。このような呼び出しは例外をスローしないことがわかっています。

型*変換*可能、*呼び出し*可能、およびパラメーターパック*引数*の型はそれぞれ、完全な型、不明なバインドの配列、または cv で修飾された型である必要があり **`void`** ます。 それ以外の場合、述語の動作は未定義です。

## <a name="example"></a>例

```cpp
// std__type_traits__is_invocable.cpp
// compile using: cl /EHsc /std:c++17 std__type_traits__is_invocable.cpp
#include <type_traits>

auto test1(int) noexcept -> int (*)()
{
    return nullptr;
}

auto test2(int) -> int (*)()
{
    return nullptr;
}

int main()
{
    static_assert( std::is_invocable<decltype(test1), short>::value );

    static_assert( std::is_invocable_r<int(*)(), decltype(test1), int>::value );
    static_assert( std::is_invocable_r<long(*)(), decltype(test1), int>::value ); // fails

    static_assert( std::is_nothrow_invocable<decltype(test1), int>::value );
    static_assert( std::is_nothrow_invocable<decltype(test2), int>::value ); // fails

    static_assert( std::is_nothrow_invocable_r<int(*)(), decltype(test1), int>::value );
    static_assert( std::is_nothrow_invocable_r<int(*)(), decltype(test2), int>::value ); // fails
}
```

## <a name="requirements"></a>必要条件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)\
[invoke](functional-functions.md#invoke)
