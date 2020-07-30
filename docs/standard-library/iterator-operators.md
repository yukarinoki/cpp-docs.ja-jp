---
title: '&lt;iterator&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- xutility/std::operator!=
- xutility/std::operator&gt;
- xutility/std::operator&gt;=
- xutility/std::operator&lt;
- xutility/std::operator&lt;=
- xutility/std::operator+
- xutility/std::operator-
- xutility/std::operator==
ms.assetid: b7c664f0-49d4-4993-b5d1-9ac4859fdddc
helpviewer_keywords:
- std::operator!= (iterator)
- std::operator&gt; (iterator)
- std::operator&gt;= (iterator)
- std::operator&lt; (iterator)
- std::operator&lt;= (iterator), std::operator== (iterator)
ms.openlocfilehash: 36851eab86a32fab9294129cf1918e0add528eb3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215661"
---
# <a name="ltiteratorgt-operators"></a>&lt;iterator&gt; 演算子

## <a name="operator"></a><a name="op_neq"></a>operator! =

演算子の左側の反復子オブジェクトが右側の反復子オブジェクトと等しくないかどうかを調べます。

```cpp
template <class RandomIterator>
bool operator!=(const reverse_iterator<RandomIterator>& left, const reverse_iterator<RandomIterator>& right);

template <class Type, class CharType, class Traits, class Distance>
bool operator!=(const istream_iterator<Type, CharType, Traits, Distance>& left, const istream_iterator<Type, CharType, Traits, Distance>& right);

template <class CharType, class Tr>
bool operator!=(const istreambuf_iterator<CharType, Traits>& left, const istreambuf_iterator<CharType, Traits>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`iterator` 型オブジェクト。

*そうです*\
`iterator` 型オブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 反復子オブジェクトが等しくない場合は。**`false`** 反復子オブジェクトが等しい場合は。

### <a name="remarks"></a>解説

コンテナー内の同じ要素に対応する場合は、1 つの反復子オブジェクトが別の反復子オブジェクトと等しくなります。 2 つの反復子がコンテナー内の異なる要素を指す場合、これらの反復子は等しくありません。

### <a name="example"></a>例

```cpp
// iterator_op_ne.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for ( i = 1 ; i < 9 ; ++i )
   {
      vec.push_back ( i );
   }

   vector <int>::iterator vIter;

   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the last element
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
           rVPOS2 = vec.rbegin ( );

   cout << "The iterator rVPOS1 initially points to the first "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   if ( rVPOS1 != rVPOS2 )
      cout << "The iterators are not equal." << endl;
   else
      cout << "The iterators are equal." << endl;

   rVPOS1++;
   cout << "The iterator rVPOS1 now points to the second "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   if ( rVPOS1 != rVPOS2 )
      cout << "The iterators are not equal." << endl;
   else
      cout << "The iterators are equal." << endl;
}
```

```Output
The vector vec is: ( 1 2 3 4 5 6 7 8 ).
The iterator rVPOS1 initially points to the first element
in the reversed sequence: 8.
The iterators are equal.
The iterator rVPOS1 now points to the second element
in the reversed sequence: 7.
The iterators are not equal.
```

## <a name="operator"></a><a name="op_eq_eq"></a>operator = =

演算子の左側の反復子オブジェクトが右側の反復子オブジェクトと等しいかどうかを調べます。

```cpp
template <class RandomIterator1, class RandomIterator2>
bool operator==(
    const move_iterator<RandomIterator1>& left,
    const move_iterator<RandomIterator2>& right);

template <class RandomIterator1, class RandomIterator2>
bool operator==(
    const reverse_iterator<RandomIterator1>& left,
    const reverse_iterator<RandomIterator2>& right);

template <class Type, class CharType, class Traits, class Distance>
bool operator==(
    const istream_iterator<Type, CharType, Traits, Distance>& left,
    const istream_iterator<Type, CharType, Traits, Distance>& right);

template <class CharType, class Tr>
bool operator==(
    const istreambuf_iterator<CharType, Traits>& left,
    const istreambuf_iterator<CharType, Traits>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
iterator 型のオブジェクト。

*そうです*\
iterator 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 反復子オブジェクトが等しい場合は。**`false`** 反復子オブジェクトが等しくない場合は。

### <a name="remarks"></a>解説

コンテナー内の同じ要素に対応する場合は、1 つの反復子オブジェクトが別の反復子オブジェクトと等しくなります。 2 つの反復子がコンテナー内の異なる要素を指す場合、これらの反復子は等しくありません。

最初の2つのテンプレート演算子は、 *left*と*right*の両方が同じ反復子を格納している場合にのみ true を返します。 3番目のテンプレート演算子は、 *left*と*right*の両方に同じストリームポインターが格納されている場合にのみ、true を返します。 4 番目のテンプレート演算子は `left.equal (right)` を返します。

### <a name="example"></a>例

```cpp
// iterator_op_eq.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for ( i = 1 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;

   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the last element
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
           rVPOS2 = vec.rbegin ( );

   cout << "The iterator rVPOS1 initially points to the first "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   if ( rVPOS1 == rVPOS2 )
      cout << "The iterators are equal." << endl;
   else
      cout << "The iterators are not equal." << endl;

   rVPOS1++;
   cout << "The iterator rVPOS1 now points to the second "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   if ( rVPOS1 == rVPOS2 )
      cout << "The iterators are equal." << endl;
   else
      cout << "The iterators are not equal." << endl;
}
```

```Output
The vector vec is: ( 2 4 6 8 10 ).
The iterator rVPOS1 initially points to the first element
in the reversed sequence: 10.
The iterators are equal.
The iterator rVPOS1 now points to the second element
in the reversed sequence: 8.
The iterators are not equal.
```

## <a name="operatorlt"></a><a name="op_lt"></a>operator&lt;

演算子の左側の反復子オブジェクトが右側の反復子オブジェクトより小さいかどうかを調べます。

```cpp
template <class RandomIterator>
bool operator<(const reverse_iterator<RandomIterator>& left, const reverse_iterator<RandomIterator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`iterator` 型オブジェクト。

*そうです*\
`iterator` 型オブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 式の左側の反復子が式の右側の反復子より小さい場合は。**`false`** 右側の反復子以上の場合は。

### <a name="remarks"></a>解説

1 つの反復子オブジェクトが、別の反復子オブジェクトが対応する要素よりも前にコンテナーで発生する要素に対応する場合、その反復子オブジェクトは別の反復子オブジェクト未満となります。 1 つの反復子オブジェクトが、別の反復子オブジェクトが対応する要素と同じ要素またはその要素よりも後にコンテナーで発生する要素に対応する場合、その反復子オブジェクトは別の反復子オブジェクト以上となります。

### <a name="example"></a>例

```cpp
// iterator_op_lt.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for ( i = 0 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the last element
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
           rVPOS2 = vec.rbegin ( );

   cout << "The iterators rVPOS1& rVPOS2 initially point to the "
           << "first element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   if ( rVPOS1 < rVPOS2 )
      cout << "The iterator rVPOS1 is less than"
              << " the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is not less than"
              << " the iterator rVPOS2." << endl;

   rVPOS2++;
   cout << "The iterator rVPOS2 now points to the second "
           << "element\n in the reversed sequence: "
           << *rVPOS2 << "." << endl;

   if ( rVPOS1 < rVPOS2 )
      cout << "The iterator rVPOS1 is less than"
              << " the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is not less than"
              << " the iterator rVPOS2." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterators rVPOS1& rVPOS2 initially point to the first element
in the reversed sequence: 10.
The iterator rVPOS1 is not less than the iterator rVPOS2.
The iterator rVPOS2 now points to the second element
in the reversed sequence: 8.
The iterator rVPOS1 is less than the iterator rVPOS2.
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a>operator&lt;=

演算子の左側の反復子オブジェクトが右側の反復子オブジェクト以下かどうかを調べます。

```cpp
template <class RandomIterator>
bool operator<=(const reverse_iterator<RandomIterator>& left, const reverse_iterator<RandomIterator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
iterator 型のオブジェクト。

*そうです*\
iterator 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 式の左側の反復子が式の右側の反復子以下である場合は、です。**`false`** 右側の反復子より大きい場合は。

### <a name="remarks"></a>解説

1 つの反復子オブジェクトが、別の反復子オブジェクトが対応する要素と同じ要素またはその要素よりも前にコンテナーで発生する要素に対応する場合、その反復子オブジェクトは別の反復子オブジェクト以下となります。 1 つの反復子オブジェクトが、別の反復子オブジェクトが対応する要素よりも後にコンテナーで発生する要素に対応する場合、その反復子オブジェクトは別の反復子オブジェクトより大きくなります。

### <a name="example"></a>例

```cpp
// iterator_op_le.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 0 ; i < 6 ; ++i )  {
      vec.push_back ( 2 * i );
      }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ) + 1,
           rVPOS2 = vec.rbegin ( );

   cout << "The iterator rVPOS1 initially points to the "
           << "second element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   cout << "The iterator rVPOS2 initially points to the "
           << "first element\n in the reversed sequence: "
           << *rVPOS2 << "." << endl;

   if ( rVPOS1 <= rVPOS2 )
      cout << "The iterator rVPOS1 is less than or "
              << "equal to the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is greater than "
              << "the iterator rVPOS2." << endl;

   rVPOS2++;
   cout << "The iterator rVPOS2 now points to the second "
           << "element\n in the reversed sequence: "
           << *rVPOS2 << "." << endl;

   if ( rVPOS1 <= rVPOS2 )
      cout << "The iterator rVPOS1 is less than or "
              << "equal to the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is greater than "
              << "the iterator rVPOS2." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterator rVPOS1 initially points to the second element
in the reversed sequence: 8.
The iterator rVPOS2 initially points to the first element
in the reversed sequence: 10.
The iterator rVPOS1 is greater than the iterator rVPOS2.
The iterator rVPOS2 now points to the second element
in the reversed sequence: 8.
The iterator rVPOS1 is less than or equal to the iterator rVPOS2.
```

## <a name="operatorgt"></a><a name="op_gt"></a>operator&gt;

演算子の左側の反復子オブジェクトが右側の反復子オブジェクトより大きいかどうかを調べます。

```cpp
template <class RandomIterator>
bool operator>(const reverse_iterator<RandomIterator>& left, const reverse_iterator<RandomIterator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
iterator 型のオブジェクト。

*そうです*\
iterator 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 式の左側の反復子が式の右側の反復子より大きい場合は。**`false`** 右側の反復子以下の場合は。

### <a name="remarks"></a>解説

1 つの反復子オブジェクトが、別の反復子オブジェクトが対応する要素よりも後にコンテナーで発生する要素に対応する場合、その反復子オブジェクトは別の反復子オブジェクトより大きくなります。 1 つの反復子オブジェクトが、別の反復子オブジェクトが対応する要素と同じ要素またはその要素よりも前にコンテナーで発生する要素に対応する場合、その反復子オブジェクトは別の反復子オブジェクト以下となります。

### <a name="example"></a>例

```cpp
// iterator_op_gt.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 0 ; i < 6 ; ++i )  {
      vec.push_back ( 2 * i );
      }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
           rVPOS2 = vec.rbegin ( );

   cout << "The iterators rVPOS1 & rVPOS2 initially point to "
           << "the first element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   if ( rVPOS1 > rVPOS2 )
      cout << "The iterator rVPOS1 is greater than "
              << "the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is less than or "
              << "equal to the iterator rVPOS2." << endl;

   rVPOS1++;
   cout << "The iterator rVPOS1 now points to the second "
           << "element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   if ( rVPOS1 > rVPOS2 )
      cout << "The iterator rVPOS1 is greater than "
              << "the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is less than or "
              << "equal to the iterator rVPOS2." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterators rVPOS1 & rVPOS2 initially point to the first element
in the reversed sequence: 10.
The iterator rVPOS1 is less than or equal to the iterator rVPOS2.
The iterator rVPOS1 now points to the second element
in the reversed sequence: 8.
The iterator rVPOS1 is greater than the iterator rVPOS2.
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a>operator&gt;=

演算子の左側の反復子オブジェクトが右側の反復子オブジェクト以上かどうかを調べます。

```cpp
template <class RandomIterator>
bool operator>=(const reverse_iterator<RandomIterator>& left, const reverse_iterator<RandomIterator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
iterator 型のオブジェクト。

*そうです*\
iterator 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 式の左側の反復子が式の右側の反復子以上の場合は、を返します。**`false`** 右側の反復子より小さい場合は。

### <a name="remarks"></a>解説

1 つの反復子オブジェクトが、別の反復子オブジェクトが対応する要素と同じ要素またはその要素よりも後にコンテナーで発生する要素に対応する場合、その反復子オブジェクトは別の反復子オブジェクト以上となります。 1 つの反復子オブジェクトが、別の反復子オブジェクトが対応する要素よりも前にコンテナーで発生する要素に対応する場合、その反復子オブジェクトは別の反復子オブジェクト未満となります。

### <a name="example"></a>例

```cpp
// iterator_op_ge.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 0 ; i < 6 ; ++i )  {
      vec.push_back ( 2 * i );
      }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
           rVPOS2 = vec.rbegin ( ) + 1;

   cout << "The iterator rVPOS1 initially points to the "
           << "first element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   cout << "The iterator rVPOS2 initially points to the "
           << "second element\n in the reversed sequence: "
           << *rVPOS2 << "." << endl;

   if ( rVPOS1 >= rVPOS2 )
      cout << "The iterator rVPOS1 is greater than or "
              << "equal to the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is less than "
              << "the iterator rVPOS2." << endl;

   rVPOS1++;
   cout << "The iterator rVPOS1 now points to the second "
           << "element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   if ( rVPOS1 >= rVPOS2 )
      cout << "The iterator rVPOS1 is greater than or "
              << "equal to the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is less than "
              << "the iterator rVPOS2." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterator rVPOS1 initially points to the first element
in the reversed sequence: 10.
The iterator rVPOS2 initially points to the second element
in the reversed sequence: 8.
The iterator rVPOS1 is less than the iterator rVPOS2.
The iterator rVPOS1 now points to the second element
in the reversed sequence: 8.
The iterator rVPOS1 is greater than or equal to the iterator rVPOS2.
```

## <a name="operator"></a><a name="op_add"></a>演算子 +

反復子にオフセットを追加し、新しいオフセット位置に挿入された要素をアドレス指定する `move_iterator` または `reverse_iterator` アドレスを返します。

```cpp
template <class RandomIterator, class Diff>
move_iterator<RandomIterator>
operator+(
    Diff _Off,
    const move_iterator<RandomIterator>& right);

template <class RandomIterator>
reverse_iterator<RandomIterator>
operator+(
    Diff _Off,
    const reverse_iterator<RandomIterator>& right);
```

### <a name="parameters"></a>パラメーター

*_Off*\
const move_iterator または const reverse_iterator がオフセットされる位置の数。

*そうです*\
オフセットされる反復子。

### <a name="return-value"></a>戻り値

_Off*の合計を*返し  +  *_Off*ます。

### <a name="example"></a>例

```cpp
// iterator_op_insert.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 0 ; i < 6 ; ++i )  {
      vec.push_back ( 2 * i );
      }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( );

   cout << "The iterator rVPOS1 initially points to "
           << "the first element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   vector<int>::difference_type diff = 4;
   rVPOS1 = diff +rVPOS1;

   cout << "The iterator rVPOS1 now points to the fifth "
           << "element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterator rVPOS1 initially points to the first element
in the reversed sequence: 10.
The iterator rVPOS1 now points to the fifth element
in the reversed sequence: 2.
```

## <a name="operator-"></a><a name="operator-"></a>operator

ある反復子を別の反復子から減算し、その差異を返します。

```cpp
template <class RandomIterator1, class RandomIterator2>
Tdiff operator-(
    const move_iterator<RandomIterator1>& left,
    const move_iterator<RandomIterator2>& right);

template <class RandomIterator1, class RandomIterator2>
Tdiff operator-(
    const reverse_iterator<RandomIterator1>& left,
    const reverse_iterator<RandomIterator2>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
反復子。

*そうです*\
反復子。

### <a name="return-value"></a>戻り値

2 つの反復子の相違点。`.`

### <a name="remarks"></a>解説

1 つ目のテンプレート演算子は `left.base() - right.base()` を返します。

2 つ目のテンプレート演算子は `right.current - left.current` を返します。

`Tdiff` は、返される式の種類によって決まります。 それ以外の場合は、`RandomIterator1::difference_type` となります。

### <a name="example"></a>例

```cpp
// iterator_op_sub.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 0 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
          rVPOS2 = vec.rbegin ( );

   cout << "The iterators rVPOS1 & rVPOS2 initially point to "
        << "the first element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   for (i = 1; i < 5; ++i)
   {
      rVPOS2++;
   }
   cout << "The iterator rVPOS2 now points to the fifth "
        << "element\n in the reversed sequence: "
        << *rVPOS2 << "." << endl;

   vector<int>::difference_type diff = rVPOS2 - rVPOS1;
   cout << "The difference: rVPOS2 - rVPOS1= "
        << diff << "." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterators rVPOS1 & rVPOS2 initially point to the first element
in the reversed sequence: 10.
The iterator rVPOS2 now points to the fifth element
in the reversed sequence: 2.
The difference: rVPOS2 - rVPOS1= 4.
```
