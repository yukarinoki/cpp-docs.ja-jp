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
ms.openlocfilehash: 53394a10464e2688953cd1b5703530e2719b7593
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076451"
---
# <a name="is_invocable-is_invocable_r-is_nothrow_invocable-is_nothrow_invocable_r-classes"></a>is_invocable、is_invocable_r、is_nothrow_invocable、is_nothrow_invocable_r クラス

これらのテンプレートは、指定された引数の型を使用して型を呼び出すことができるかどうかを判断します。 `is_invocable_r` と `is_nothrow_invocable_r` では、呼び出しの結果が特定の型に変換可能かどうかも判断されます。 `is_nothrow_invocable` と `is_nothrow_invocable_r` では、呼び出しが例外をスローしないことがわかっているかどうかも判断されます。 C++ 17 で追加されました。

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

*呼び出し*可能\
照会する呼び出し可能型。

*Args*\
照会する引数の型。

*変換*可能\
*呼び出し*可能の結果を変換できる型である必要があります。

## <a name="remarks"></a>解説

`is_invocable` 型の述語は、未評価の*コンテキストで引数*引数を使用して呼び出し可能な型を呼び出すことができる場合に*true を保持*します。

`is_invocable_r` 型の述語は、未評価のコンテキストで引数*Args*を使用し*て呼び出し可能*な型を呼び出すことができる場合に true を保持し、*変換*可能に変換可能な結果型を生成します。

`is_nothrow_invocable` 型の述語は、評価されないコンテキストで引数引数を使用して呼び出し可能な型を呼び出すこと*ができ、* そのような呼び出しが例外をスローしないことがわかっている*場合に true*を保持します。

`is_nothrow_invocable_r` 型の述語は、未評価のコンテキストの引数*Args*を使用し*て呼び出し可能*な型を呼び出すことができる場合に true を保持し、*変換*可能に変換可能な結果型を生成します。このような呼び出しは例外をスローしないことがわかっています。

型*変換*可能、*呼び出し*可能、およびパラメーターパック*引数*の型はそれぞれ、完全な型、不明な型の配列、または cv で修飾された**void**型である必要があります。 それ以外の場合、述語の動作は未定義です。

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

**ヘッダー:** \<type_traits >

**名前空間:** std

## <a name="see-also"></a>参照

[<type_traits>](../standard-library/type-traits.md)\
[invoke](functional-functions.md#invoke)
