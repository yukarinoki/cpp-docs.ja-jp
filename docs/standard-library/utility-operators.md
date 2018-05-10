---
title: '&lt;utility&gt; 演算子 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- utility/std::operator!=
- utility/std::operator&gt;
- utility/std::operator&gt;=
- utility/std::operator&lt;
- utility/std::operator&lt;=
- utility/std::operator==
dev_langs:
- C++
ms.assetid: a6617109-2cec-4a69-948f-6c87116eda5f
helpviewer_keywords:
- std::operator!= (utility)
- std::operator&gt; (utility)
- std::operator&gt;= (utility)
- std::operator&lt; (utility)
- std::operator&lt;= (utility)
- std::operator== (utility)
ms.openlocfilehash: e5ed9d81e4b63dd57ebaf5f41ecc8422eaf166dd
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="ltutilitygt-operators"></a>&lt;utility&gt; 演算子

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  operator!=

演算子の左辺のペア オブジェクトが右辺のペア オブジェクトと等しくないかどうかを調べます。

```cpp
template <class Type>
constexpr bool operator!=(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator!=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>パラメーター

`left` 型のオブジェクト**ペア。**

`right` 型のオブジェクト`pair`です。

### <a name="return-value"></a>戻り値

ペアが等しくない場合には **true**。等しい場合は **false**。

### <a name="remarks"></a>コメント

ペアのそれぞれの要素が等しい場合に、ペアが等しくなります。 片方のペアの最初または 2 番目の要素のいずれかがもう一方のペアの対応する要素と等しくない場合には、2 つのペアは等しくありません。

### <a name="example"></a>例

```cpp
// utility_op_ne.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3;

   p1 = make_pair ( 10, 1.11e-1 );
   p2 = make_pair ( 1000, 1.11e-3 );
   p3 = make_pair ( 10, 1.11e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl << endl;

   if ( p1 != p2 )
      cout << "The pairs p1 and p2 are not equal." << endl;
   else
      cout << "The pairs p1 and p2 are equal." << endl;

   if ( p1 != p3 )
      cout << "The pairs p1 and p3 are not equal." << endl;
   else
      cout << "The pairs p1 and p3 are equal." << endl;
}
```

```Output
The pair p1 is: ( 10, 0.111 ).
The pair p2 is: ( 1000, 0.00111 ).
The pair p3 is: ( 10, 0.111 ).

The pairs p1 and p2 are not equal.
The pairs p1 and p3 are equal.
```

## <a name="op_eq_eq"></a>  operator==

演算子の左辺のペア オブジェクトが右辺のペア オブジェクトと等しいかどうかを調べます。

```cpp
template <class T, class U>
constexpr bool operator==(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>パラメーター

`left` 型のオブジェクト**ペア。**

`right` 型のオブジェクト`pair`です。

### <a name="return-value"></a>戻り値

ペアが等しい場合には **true**。`pair` が等しくないときには **false**。

### <a name="remarks"></a>コメント

ペアのそれぞれの要素が等しい場合に、ペアが等しくなります。 `left` が返されます。 **first** == `right`。 **first** && `left`。 **second** == `right`。 **second**。 片方のペアの最初または 2 番目の要素のいずれかがもう一方のペアの対応する要素と等しくない場合には、2 つのペアは等しくありません。

### <a name="example"></a>例

```cpp
// utility_op_eq.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3;

   p1 = make_pair ( 10, 1.11e-1 );
   p2 = make_pair ( 1000, 1.11e-3 );
   p3 = make_pair ( 10, 1.11e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl << endl;

   if ( p1 == p2 )
      cout << "The pairs p1 and p2 are equal." << endl;
   else
      cout << "The pairs p1 and p2 are not equal." << endl;

   if ( p1 == p3 )
      cout << "The pairs p1 and p3 are equal." << endl;
   else
      cout << "The pairs p1 and p3 are not equal." << endl;
}
```

## <a name="op_lt"></a>  operator&lt;

演算子の左辺のペア オブジェクトが右辺のペア オブジェクトより小さいかどうかを調べます。

```cpp
template <class T, class U>
constexpr bool operator<(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>パラメーター

`left` 型のオブジェクト`pair`演算子の左側にあります。

`right` 型のオブジェクト`pair`演算子の右側にあります。

### <a name="return-value"></a>戻り値

演算子の左辺の `pair` が演算子の右辺の `pair` より厳密に小さい場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>コメント

`left` `pair`オブジェクトの厳密にすると表現はより小さい`right``pair`オブジェクトの場合`left`が等しくないと、それよりも小さい`right`です。

ペアを比較する場合、2 つのペアの最初の要素の値が、最も優先度が高くなります。 最初の要素の値が異なる場合、その比較の結果がペアの比較の結果として扱われます。 最初の要素の値が同じである場合、2 番目の要素の値が比較され、その比較の結果がペアの比較の結果として扱われます。

### <a name="example"></a>例

```cpp
// utility_op_lt.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3;

   p1 = make_pair ( 10, 2.22e-1 );
   p2 = make_pair ( 100, 1.11e-1 );
   p3 = make_pair ( 10, 1.11e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl << endl;

   if ( p1 < p2 )
      cout << "The pair p1 is less than the pair p2." << endl;
   else
      cout << "The pair p1 is not less than the pair p2." << endl;

   if ( p1 < p3 )
      cout << "The pair p1 is less than the pair p3." << endl;
   else
      cout << "The pair p1 is not less than the pair p3." << endl;
}
```

```Output
The pair p1 is: ( 10, 0.222 ).
The pair p2 is: ( 100, 0.111 ).
The pair p3 is: ( 10, 0.111 ).

The pair p1 is less than the pair p2.
The pair p1 is not less than the pair p3.
```

## <a name="op_lt_eq"></a>  演算子&lt;=

演算子の左辺のペア オブジェクトが右辺のペア オブジェクト以下かどうかを調べます。

```cpp
template <class Type>
constexpr bool operator<=(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator<=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>パラメーター

`left` 型のオブジェクト`pair`演算子の左側にあります。

`right` 型のオブジェクト`pair`演算子の右側にあります。

### <a name="return-value"></a>戻り値

演算子の左辺の `pair` が演算子の右辺の `pair` 以下である場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>コメント

ペアを比較する場合、2 つのペアの最初の要素の値が、最も優先度が高くなります。 最初の要素の値が異なる場合、その比較の結果がペアの比較の結果として扱われます。 最初の要素の値が同じである場合、2 番目の要素の値が比較され、その比較の結果がペアの比較の結果として扱われます。

### <a name="example"></a>例

```cpp
// utility_op_le.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3, p4;

   p1 = make_pair ( 10, 2.22e-1 );
   p2 = make_pair ( 100, 1.11e-1 );
   p3 = make_pair ( 10, 1.11e-1 );
   p4 = make_pair ( 10, 2.22e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl;
   cout << "The pair p4 is: ( " << p4.first << ", "
        << p4.second << " )." << endl << endl;

   if ( p1 <= p2 )
      cout << "The pair p1 is less than or equal to the pair p2." << endl;
   else
      cout << "The pair p1 is greater than the pair p2." << endl;

   if ( p1 <= p3 )
      cout << "The pair p1 is less than or equal to the pair p3." << endl;
   else
      cout << "The pair p1 is greater than the pair p3." << endl;

   if ( p1 <= p4 )
      cout << "The pair p1 is less than or equal to the pair p4." << endl;
   else
      cout << "The pair p1 is greater than the pair p4." << endl;
}
```

```Output
The pair p1 is: ( 10, 0.222 ).
The pair p2 is: ( 100, 0.111 ).
The pair p3 is: ( 10, 0.111 ).
The pair p4 is: ( 10, 0.222 ).

The pair p1 is less than or equal to the pair p2.
The pair p1 is greater than the pair p3.
The pair p1 is less than or equal to the pair p4.
```

## <a name="op_gt"></a>  operator&gt;

演算子の左辺のペア オブジェクトが右辺のペア オブジェクトより大きいかどうかを調べます。

```cpp
template <class Type>
constexpr bool operator>(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator>(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>パラメーター

`left` 型のオブジェクト`pair`演算子の左側にあります。

`right` 型のオブジェクト`pair`演算子の右側にあります。

### <a name="return-value"></a>戻り値

演算子の左辺にある `pair` が演算子の右辺の `pair` より厳密に大きい場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>コメント

`left` `pair`オブジェクトと呼ばれますより厳密に大きく、 `right` `pair`オブジェクトの場合`left`はより大きいと等しくない`right`です。

ペアを比較する場合、2 つのペアの最初の要素の値が、最も優先度が高くなります。 最初の要素の値が異なる場合、その比較の結果がペアの比較の結果として扱われます。 最初の要素の値が同じである場合、2 番目の要素の値が比較され、その比較の結果がペアの比較の結果として扱われます。

### <a name="example"></a>例

```cpp
// utility_op_gt.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3, p4;

   p1 = make_pair ( 10, 2.22e-1 );
   p2 = make_pair ( 100, 1.11e-1 );
   p3 = make_pair ( 10, 1.11e-1 );
   p4 = make_pair ( 10, 2.22e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl;
   cout << "The pair p4 is: ( " << p4.first << ", "
        << p4.second << " )." << endl << endl;

   if ( p1 > p2 )
      cout << "The pair p1 is greater than the pair p2." << endl;
   else
      cout << "The pair p1 is not greater than the pair p2." << endl;

   if ( p1 > p3 )
      cout << "The pair p1 is greater than the pair p3." << endl;
   else
      cout << "The pair p1 is not greater than the pair p3." << endl;

   if ( p1 > p4 )
      cout << "The pair p1 is greater than the pair p4." << endl;
   else
      cout << "The pair p1 is not greater than the pair p4." << endl;
}
```

```Output
The pair p1 is: ( 10, 0.222 ).
The pair p2 is: ( 100, 0.111 ).
The pair p3 is: ( 10, 0.111 ).
The pair p4 is: ( 10, 0.222 ).

The pair p1 is not greater than the pair p2.
The pair p1 is greater than the pair p3.
The pair p1 is not greater than the pair p4.
```

## <a name="op_gt_eq"></a>  演算子&gt;=

演算子の左辺のペア オブジェクトが右辺のペア オブジェクト以上かどうかを調べます。

```cpp
template <class Type>
constexpr bool operator>=(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator>=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>パラメーター

`left` 型のオブジェクト`pair`演算子の左側にあります。

`right` 型のオブジェクト`pair`演算子の右側にあります。

### <a name="return-value"></a>戻り値

演算子の左辺の `pair` が演算子の右辺の `pair` 以上である場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>コメント

ペアを比較する場合、2 つのペアの最初の要素の値が、最も優先度が高くなります。 最初の要素の値が異なる場合、その比較の結果がペアの比較の結果として扱われます。 最初の要素の値が同じである場合、2 番目の要素の値が比較され、その比較の結果がペアの比較の結果として扱われます。

### <a name="example"></a>例

```cpp
// utility_op_ge.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3, p4;

   p1 = make_pair ( 10, 2.22e-1 );
   p2 = make_pair ( 100, 1.11e-1 );
   p3 = make_pair ( 10, 1.11e-1 );
   p4 = make_pair ( 10, 2.22e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl;
   cout << "The pair p4 is: ( " << p4.first << ", "
        << p4.second << " )." << endl << endl;

   if ( p1 >= p2 )
      cout << "Pair p1 is greater than or equal to pair p2." << endl;
   else
      cout << "The pair p1 is less than the pair p2." << endl;

   if ( p1 >= p3 )
      cout << "Pair p1 is greater than or equal to pair p3." << endl;
   else
      cout << "The pair p1 is less than the pair p3." << endl;

   if ( p1 >= p4 )
      cout << "Pair p1 is greater than or equal to pair p4." << endl;
   else
      cout << "The pair p1 is less than the pair p4." << endl;
}
```

```Output
The pair p1 is: ( 10, 0.222 ).
The pair p2 is: ( 100, 0.111 ).
The pair p3 is: ( 10, 0.111 ).
The pair p4 is: ( 10, 0.222 ).

The pair p1 is less than the pair p2.
Pair p1 is greater than or equal to pair p3.
Pair p1 is greater than or equal to pair p4.
```

## <a name="see-also"></a>関連項目

[\<utility>](../standard-library/utility.md)<br/>
