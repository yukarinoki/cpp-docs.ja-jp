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
ms.openlocfilehash: c85da1f3be7821f8d82cd2b19dab2a5864426a5a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452042"
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

*\T*\
定数の型。

*画像*\
定数の値。

## <a name="remarks"></a>Remarks

`integral_constant` テンプレート クラスは、整数型 *T* とその型の値 *v* で特殊化されると、指定された値の整数型の定数を保持するオブジェクトを表します。 `type` という名前のメンバーは、生成済みテンプレートの特殊化型のエイリアスです。`value` メンバーは、特殊化を作成するために使用された値 *v* を保持します。

このテンプレートクラスは、 **bool**を*T*引数`integral_constant`として使用する、の明示的な部分的特殊化です。 `bool_constant`

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

[<type_traits>](../standard-library/type-traits.md)\
[false_type](../standard-library/type-traits-typedefs.md#false_type)\
[true_type](../standard-library/type-traits-typedefs.md#true_type)
