---
title: integral_constant クラス、bool_constant クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::integral_constant
- XTR1COMMON/std::integral_constant
- type_traits/std::bool_constant
- XTR1COMMON/std::bool_constant
helpviewer_keywords:
- std::integral_constant [C++]
- std::bool_constant [C++]
ms.assetid: 11c002c6-4d31-4042-9341-f2543f43e108
ms.openlocfilehash: f7b9217560bc94c536a7c819276266fd16fa4b07
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51520336"
---
# <a name="integralconstant-class-boolconstant-class"></a>integral_constant クラス、bool_constant クラス

型および値から整数定数を作成します。

## <a name="syntax"></a>構文

```cpp
template<class T, T v>
struct integral_constant {
   static constexpr T value = v;
   typedef T value_type;
   typedef integral_constant<T, v> type;
   constexpr operator value_type() const noexcept;
   constexpr value_type operator()() const noexcept;
   };
```

### <a name="parameters"></a>パラメーター

*T*<br/>
定数の型。

*v*<br/>
定数の値。

## <a name="remarks"></a>Remarks

`integral_constant` テンプレート クラスは、整数型 *T* とその型の値 *v* で特殊化されると、指定された値の整数型の定数を保持するオブジェクトを表します。 `type` という名前のメンバーは、生成済みテンプレートの特殊化型のエイリアスです。`value` メンバーは、特殊化を作成するために使用された値 *v* を保持します。

`bool_constant`テンプレート クラスの明示的な部分的特殊化は、`integral_constant`を使用して**bool**として、 *T*引数。

## <a name="example"></a>例

```cpp
// std__type_traits__integral_constant.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
    {
    std::cout << "integral_constant<int, 5> == "
        << std::integral_constant<int, 5>::value << std::endl;
    std::cout << "integral_constant<bool, false> == " << std::boolalpha
        << std::integral_constant<bool, false>::value << std::endl;

    return (0);
    }
```

```Output
integral_constant<int, 5> == 5
integral_constant<bool, false> == false
```

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[false_type](../standard-library/type-traits-typedefs.md#false_type)<br/>
[true_type](../standard-library/type-traits-typedefs.md#true_type)<br/>
