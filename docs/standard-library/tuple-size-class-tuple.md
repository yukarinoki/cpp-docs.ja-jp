---
title: tuple_size クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- tuple_size
- std::tuple_size
- utility/std::tuple_size
dev_langs:
- C++
helpviewer_keywords:
- std::tuple_size
ms.assetid: 73852fc5-eb68-41f1-8379-465cedc2314a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7249aad5e130e805aae73bdbfba7f9c4f78ad4fe
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853984"
---
# <a name="tuplesize-class"></a>tuple_size クラス

`tuple` を含む要素の数を報告します。

## <a name="syntax"></a>構文

```cpp
// TEMPLATE STRUCT tuple_size
template <class Tuple>
   struct tuple_size;

// number of elements in array
template <class Elem, size_t Size>
   struct tuple_size<array<Elem, Size>>
      : integral_constant<size_t, Size>;

// size of pair
template <class T1, class T2>
   struct tuple_size<pair<T1, T2>>
      : integral_constant<size_t, 2>

// size of tuple
template <class... Types>
   struct tuple_size<tuple<Types...>>
      : integral_constant<size_t, sizeof...(Types)>;

// size of const tuple
template <class Tuple>
   struct tuple_size<const Tuple>;

// size of volatile tuple
template <class Tuple>
   struct tuple_size<volatile Tuple>;

// size of const volatile tuple
template <class Tuple>
   struct tuple_size<const volatile Tuple>;
```

### <a name="parameters"></a>パラメーター

*タプル*タプルの型。

*Elem*配列の要素の型。

*サイズ*配列のサイズ。

*T1*ペアの最初のメンバーの種類。

*T2*ペアの 2 番目のメンバーの種類。

*型*タプル要素の型。

## <a name="remarks"></a>コメント

テンプレート クラスは、組型 `value` の範囲を値として持つ整数定数式であるメンバー `Tuple`を持ちます。

配列のテンプレート特殊化には、配列のサイズである `Size` を値として持つ整数定数式であるメンバー `value` が含まれます。

ペアのテンプレート特殊化には、2 を値として持つ整数定数式であるメンバー `value` が含まれます。

## <a name="example"></a>例

```cpp
#include <tuple>
#include <iostream>

using namespace std;

typedef tuple<int, double, int, double> MyTuple;
int main()
{
    MyTuple c0(0, 1.5, 2, 3.7);

    // display contents " 0 1 2 3"
    cout << " " << get<0>(c0);
    cout << " " << get<1>(c0);
    cout << " " << get<2>(c0);
    cout << " " << get<3>(c0) << endl;

    // display size " 4"
    cout << " " << tuple_size<MyTuple>::value << endl;
}
```

```Output
 0 1.5 2 3.7
```

## <a name="requirements"></a>要件

**ヘッダー:** \<組 >**ヘッダー:** \<配列 > (配列の特殊化) の**ヘッダー** \<ユーティリティ > のペアの特殊化)。

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<tuple>](../standard-library/tuple.md)<br/>
[tuple](../standard-library/tuple-class.md)<br/>
[tuple_element クラス](../standard-library/tuple-element-class-tuple.md)<br/>
