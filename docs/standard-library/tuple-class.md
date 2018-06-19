---
title: tuple クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- tuple/std::tuple
- tuple/std::tuple::operator=
dev_langs:
- C++
helpviewer_keywords:
- tuple class
ms.assetid: c38749be-ae4d-41f3-98ea-6aa3250de9a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5d265938eb024a41d8b90f3b9891c35ec1ec251
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858800"
---
# <a name="tuple-class"></a>タプル クラス

要素の固定長シーケンスをラップします。

## <a name="syntax"></a>構文

```
class tuple {
public:
   tuple();
   explicit tuple(P1, P2, ..., PN); // 0 < N
   tuple(const tuple&);
   template <class U1, class U2, ..., class UN>
      tuple(const tuple<U1, U2, ..., UN>&);
   template <class U1, class U2>
      tuple(const pair<U1, U2>&); // N == 2

   void swap(tuple& right);
   tuple& operator=(const tuple&);
   template <class U1, class U2, ..., class UN>
      tuple& operator=(const tuple<U1, U2, ..., UN>&);
   template <class U1, class U2>
      tuple& operator=(const pair<U1, U2>&); // N == 2
   };

### Parameters

`TN`
 The type of the Nth tuple element.

## Remarks

The template class describes an object that stores N objects of types `T1`, `T2`, ..., `TN`, respectively, where where `0 <= N <= Nmax`. The extent of a tuple instance `tuple<T1, T2, ..., TN>` is the number `N` of its template arguments. The index of the template argument `Ti` and of the corresponding stored value of that type is `i - 1`. Thus, while we number the types from 1 to N in this documentation, the corresponding index values range from 0 to N - 1.

## Example

```cpp
// tuple.cpp
// compile with: /EHsc

#include <vector>
#include <iomanip>
#include <iostream>
#include <tuple>
#include <string>

using namespace std;

typedef tuple <int, double, string> ids;

void print_ids(const ids& i)
{
   cout << "( "
        << get<0>(i) << ", "
        << get<1>(i) << ", "
        << get<2>(i) << " )." << endl;
}

int main( )
{
   // Using the constructor to declare and initialize a tuple
   ids p1(10, 1.1e-2, "one");

   // Compare using the helper function to declare and initialize a tuple
   ids p2;
   p2 = make_tuple(10, 2.22e-1, "two");

   // Making a copy of a tuple
   ids p3(p1);

   cout.precision(3);
   cout << "The tuple p1 is: ( ";
   print_ids(p1);
   cout << "The tuple p2 is: ( ";
   print_ids(p2);
   cout << "The tuple p3 is: ( ";
   print_ids(p3);

   vector<ids> v;

   v.push_back(p1);
   v.push_back(p2);
   v.push_back(make_tuple(3, 3.3e-2, "three"));

   cout << "The tuples in the vector are" << endl;
   for(vector<ids>::const_iterator i = v.begin(); i != v.end(); ++i)
   {
      print_ids(*i);
   }
}
```

```Output
The tuple p1 is: ( 10, 0.011, one ).
The tuple p2 is: ( 10, 0.222, two ).
The tuple p3 is: ( 10, 0.011, one ).
The tuples in the vector are
( 10, 0.011, one ).
( 10, 0.222, two ).
( 3, 0.033, three ).
```

## <a name="requirements"></a>要件

**ヘッダー:** \<tuple>

**名前空間:** std

## <a name="op_eq"></a>  tuple::operator=

`tuple` オブジェクトを割り当てます。

```cpp
tuple& operator=(const tuple& right);

template <class U1, class U2, ..., class UN>
   tuple& operator=(const tuple<U1, U2, ..., UN>& right);

template <class U1, class U2>
   tuple& operator=(const pair<U1, U2>& right); // N == 2

tuple& operator=(tuple&& right);

template <class U1, class U2>
   tuple& operator=(pair<U1, U2>&& right);
```

### <a name="parameters"></a>パラメーター

`UN` N 番目の型は、タプル要素をコピーします。

`right` コピーされるタプル。

### <a name="remarks"></a>コメント

最初の 2 つのメンバー演算子は、`right` の要素を `*this` の対応する要素に割り当てます。 3 番目のメンバー演算子は、`*this` のインデックス 0 位置の要素に `right.first` を割り当て、インデックス 1 の要素に `right.second` を割り当てます。 これらの 3 つすべてのメンバー演算子は、`*this` を返します。

残りのメンバー演算子はそれ以前のコンストラクターと似ていますが、[Rvalue 参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md) を使用します。

### <a name="example"></a>例

```cpp
// std__tuple__tuple_operator_as.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>
#include <utility>

typedef std::tuple<int, double, int, double> Mytuple;
int main()
    {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

    Mytuple c1;
    c1 = c0;

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c1);
    std::cout << " " << std::get<1>(c1);
    std::cout << " " << std::get<2>(c1);
    std::cout << " " << std::get<3>(c1);
    std::cout << std::endl;

    std::tuple<char, int> c2;
    c2 = std::make_pair('x', 4);

// display contents " x 4"
    std::cout << " " << std::get<0>(c2);
    std::cout << " " << std::get<1>(c2);
    std::cout << std::endl;

    return (0);
    }

```

```Output
0 1 2 3
0 1 2 3
x 4
```

## <a name="tuple_swap"></a>  tuple:swap

2 つのタプルの要素を交換します。

```cpp
template <class... Types>
   void swap(tuple<Types...&> left, tuple<Types...&> right);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`left`|要素がタプル `right` の要素と交換されるタプル。|
|`right`|要素がタプル `left` の要素と交換されるタプル。|

### <a name="remarks"></a>コメント

この関数は、`left.swap(right)` を実行します。

## <a name="tuple"></a>  tuple::tuple

`tuple` オブジェクトを構築します。

```cpp
constexpr tuple();
explicit constexpr tuple(const Types&...);
template <class... UTypes>
   explicit constexpr tuple(UTypes&&...);

tuple(const tuple&) = default;
tuple(tuple&&) = default;

template <class... UTypes>
   constexpr tuple(const tuple<UTypes...>&);
template <class... UTypes>
   constexpr tuple(tuple<UTypes...>&&);

// only if sizeof...(Types) == 2
template <class U1, class U2>
   constexpr tuple(const pair<U1, U2>&);
template <class U1, class U2>
   constexpr tuple(pair<U1, U2>&&);
```

### <a name="parameters"></a>パラメーター

`UN` N 番目の型は、タプル要素をコピーします。

`right` コピーされるタプル。

### <a name="remarks"></a>コメント

1 つ目のコンストラクターは、要素が既定で構築されるオブジェクトを構築します。

2 番目のコンス トラクターは、引数 `P1`、`P2`...`PN` に基づいて構築されるコピーを要素とするオブジェクトを構築します。これらの `Pi` は、インデックス `i - 1` で要素を初期化します。

3 番目と 4 番目のコンストラクターは、`right` の対応する要素から構築されたコピーを要素として含むオブジェクトを構築します。

5 番目のコンストラクターは、インデックス 0 の要素が `right.first` から構築されたコピーで、インデックス 1 の要素が `right.second` から構築されたコピーであるオブジェクトを構築します。

残りのコンストラクターはそれ以前のコンストラクターと似ていますが、[Rvalue 参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md) を使用します。

### <a name="example"></a>例

```cpp
// std__tuple__tuple_tuple.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>
#include <utility>

typedef std::tuple<int, double, int, double> Mytuple;
int main()
    {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

    Mytuple c1;
    c1 = c0;

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c1);
    std::cout << " " << std::get<1>(c1);
    std::cout << " " << std::get<2>(c1);
    std::cout << " " << std::get<3>(c1);
    std::cout << std::endl;

    std::tuple<char, int> c2(std::make_pair('x', 4));

// display contents " x 4"
    std::cout << " " << std::get<0>(c2);
    std::cout << " " << std::get<1>(c2);
    std::cout << std::endl;

    Mytuple c3(c0);

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c3);
    std::cout << " " << std::get<1>(c3);
    std::cout << " " << std::get<2>(c3);
    std::cout << " " << std::get<3>(c3);
    std::cout << std::endl;

    typedef std::tuple<int, float, int, float> Mytuple2;
    Mytuple c4(Mytuple2(4, 5, 6, 7));

// display contents " 4 5 6 7"
    std::cout << " " << std::get<0>(c4);
    std::cout << " " << std::get<1>(c4);
    std::cout << " " << std::get<2>(c4);
    std::cout << " " << std::get<3>(c4);
    std::cout << std::endl;

    return (0);
    }
```

```Output
 0 1 2 3
 0 1 2 3
 x 4
 0 1 2 3
 4 5 6 7
```

## <a name="see-also"></a>関連項目

[\<tuple>](../standard-library/tuple.md)<br/>
[make_tuple](../standard-library/tuple-functions.md#make_tuple)<br/>
