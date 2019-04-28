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
ms.openlocfilehash: bb5e75a897029ded2e00e491d93d2df41a3e115b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62336232"
---
# <a name="isinvocable-isinvocabler-isnothrowinvocable-isnothrowinvocabler-classes"></a>is_invocable、is_invocable_r、is_nothrow_invocable、is_nothrow_invocable_r クラス

これらのテンプレートは、指定した引数型と型を呼び出すことができるかどうかを決定します。 `is_invocable_r` `is_nothrow_invocable_r`も呼び出しの結果が特定の型に変換できるかを判断します。 `is_nothrow_invocable` `is_nothrow_invocable_r`呼び出しが例外をスローしていない既知のかどうかを決定することもできます。 C++ 17 で追加されます。

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

*呼び出し可能*<br/>
照会する呼び出し可能型。

*Args*<br/>
クエリを実行する引数の型。

*変換可能*<br/>
結果の種類の*Callable*に変換できる必要があります。

## <a name="remarks"></a>Remarks

`is_invocable`場合型の述語は true を保持呼び出し可能型*Callable*引数を使用して呼び出すことができます*Args*未評価のコンテキストでします。

`is_invocable_r`場合型の述語は true を保持呼び出し可能型*Callable*引数を使用して呼び出すことができます*Args*を結果に変換できる型を生成するために、評価されないコンテキストで*変換できる*します。

`is_nothrow_invocable`場合型の述語は true を保持呼び出し可能型*Callable*引数を使用して呼び出すことができます*Args*未評価のコンテキストでは、このような呼び出しは例外をスローしないとする呼ばれます。

`is_nothrow_invocable_r`場合型の述語は true を保持呼び出し可能型*Callable*引数を使用して呼び出すことができます*Args*を結果に変換できる型を生成するために、評価されないコンテキストで*変換できる*、このような呼び出しが例外をスローしていない既知であるとします。

各種類*コンバーチブル*、 *Callable*、パラメーター パック内の型と*Args*は完全な型、不明なバインドは、の配列または cv で修飾された可能性があるにする必要があります**void**します。 それ以外の場合、述語の動作は定義されません。

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

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[invoke](functional-functions.md#invoke)<br/>
