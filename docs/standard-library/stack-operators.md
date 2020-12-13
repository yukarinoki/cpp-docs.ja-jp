---
description: '詳細情報: &lt; stack &gt; 演算子'
title: '&lt;stack&gt; operators'
ms.date: 11/04/2016
f1_keywords:
- stack/std::operator!=
- stack/std::operator&gt;
- stack/std::operator&gt;=
- stack/std::operator&lt;
- stack/std::operator&lt;=
- stack/std::operator==
ms.assetid: 9c1fc282-2f61-4727-9e80-84ea5d4934a2
helpviewer_keywords:
- std::operator!= (stack)
- std::operator&gt; (stack)
- std::operator&gt;= (stack)
- std::operator&lt; (stack)
- std::operator&lt;= (stack)
- std::operator== (stack)
ms.openlocfilehash: 56d5dcf7d23fd685cd7d805d773ac9eb77d85506
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153851"
---
# <a name="ltstackgt-operators"></a>&lt;stack&gt; operators

## <a name="operator"></a><a name="op_neq"></a> operator! =

演算子の左辺のスタック オブジェクトが右辺のスタック オブジェクトと等しくないかどうかを調べます。

```cpp
bool operator!=(const stack <Type, Container>& left, const stack <Type, Container>& right,);
```

### <a name="parameters"></a>パラメーター

*左側*\
`stack` 型のオブジェクト。

*そうです*\
`stack` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** スタックまたはスタックが等しくない場合は。 **`false`** スタックまたはスタックが等しい場合は。

### <a name="remarks"></a>解説

stack オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの stack は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。

### <a name="example"></a>例

```cpp
// stack_op_me.cpp
// compile with: /EHsc
#include <stack>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares stacks with vector base containers
   stack <int, vector<int> > s1, s2, s3;

   // The following would have cause an error because stacks with
   // different base containers are not equality comparable
   // stack <int, list<int> >  s3;

   s1.push( 1 );
   s2.push( 2 );
   s3.push( 1 );

   if ( s1 != s2 )
      cout << "The stacks s1 and s2 are not equal." << endl;
   else
      cout << "The stacks s1 and s2 are equal." << endl;

   if ( s1 != s3 )
      cout << "The stacks s1 and s3 are not equal." << endl;
   else
      cout << "The stacks s1 and s3 are equal." << endl;
}
```

```Output
The stacks s1 and s2 are not equal.
The stacks s1 and s3 are equal.
```

## <a name="operatorlt"></a><a name="op_lt"></a> operator&lt;

演算子の左辺のスタック オブジェクトが右辺のスタック オブジェクトより小さいかどうかを調べます。

```cpp
bool operator<(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`stack` 型のオブジェクト。

*そうです*\
`stack` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺のスタックがより小さく、演算子の右辺のスタックと等しくない場合は、を返します。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

stack オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの stack オブジェクト間の小なり関係は、最初の等しくない要素のペアの比較に基づいています。

### <a name="example"></a>例

```cpp
// stack_op_lt.cpp
// compile with: /EHsc
#include <stack>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares stacks with list base container
   stack <int, list<int> > s1, s2, s3;

   s1.push( 2 );
   s1.push( 4 );
   s1.push( 6 );
   s1.push( 8 );
   s2.push( 5 );
   s2.push( 10 );
   s3.push( 2 );
   s3.push( 4 );
   s3.push( 6 );
   s3.push( 8 );

   if ( s1 >= s2 )
      cout << "The stack s1 is greater than or equal to "
           << "the stack s2." << endl;
   else
      cout << "The stack s1 is less than "
           << "the stack s2." << endl;

   if ( s1>= s3 )
      cout << "The stack s1 is greater than or equal to "
           << "the stack s3." << endl;
   else
      cout << "The stack s1 is less than "
           << "the stack s3." << endl;

   // to print out the stack s1 ( by unstacking the elements):
   stack <int>::size_type i_size_s1 = s1.size( );
   cout << "The stack s1 from the top down is: ( ";
   unsigned int i;
   for ( i = 1 ; i <= i_size_s1 ; i++ )
   {
      cout << s1.top( ) << " ";
      s1.pop( );
   }
   cout << ")." << endl;
}
```

```Output
The stack s1 is less than the stack s2.
The stack s1 is greater than or equal to the stack s3.
The stack s1 from the top down is: ( 8 6 4 2 ).
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a> operator&lt;=

演算子の左辺のスタック オブジェクトが右辺のスタック オブジェクト以下かどうかを調べます。

```cpp
bool operator<=(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`stack` 型のオブジェクト。

*そうです*\
`stack` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺のスタックが演算子の右側のスタック以下である場合は、です ()。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

stack オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの stack オブジェクト間の "以下" 関係は、最初の等しくない要素のペアの比較に基づいています。

### <a name="example"></a>例

```cpp
// stack_op_le.cpp
// compile with: /EHsc
#include <stack>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares stacks with default deque base container
   stack <int> s1, s2, s3;

   s1.push( 5 );
   s1.push( 10 );
   s2.push( 1 );
   s2.push( 2 );
   s3.push( 5 );
   s3.push( 10 );

   if ( s1 <= s2 )
      cout << "The stack s1 is less than or equal to "
           << "the stack s2." << endl;
   else
      cout << "The stack s1 is greater than "
           << "the stack s2." << endl;

   if ( s1 <= s3 )
      cout << "The stack s1 is less than or equal to "
           << "the stack s3." << endl;
   else
      cout << "The stack s1 is greater than "
           << "the stack s3." << endl;
}
```

```Output
The stack s1 is greater than the stack s2.
The stack s1 is less than or equal to the stack s3.
```

## <a name="operator"></a><a name="op_eq_eq"></a> operator = =

演算子の左辺のスタック オブジェクトが右辺のスタック オブジェクトと等しいかどうかを調べます。

```cpp
bool operator==(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`stack` 型のオブジェクト。

*そうです*\
`stack` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** スタックまたはスタックが等しい場合は。 **`false`** スタックまたはスタックが等しくない場合は。

### <a name="remarks"></a>解説

stack オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの stack は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。

### <a name="example"></a>例

```cpp
// stack_op_eq.cpp
// compile with: /EHsc
#include <stack>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares stacks with vector base containers
   stack <int, vector<int> > s1, s2, s3;

   // The following would have cause an error because stacks with
   // different base containers are not equality comparable
   // stack <int, list<int> > s3;

   s1.push( 1 );
   s2.push( 2 );
   s3.push( 1 );

   if ( s1 == s2 )
      cout << "The stacks s1 and s2 are equal." << endl;
   else
      cout << "The stacks s1 and s2 are not equal." << endl;

   if ( s1 == s3 )
      cout << "The stacks s1 and s3 are equal." << endl;
   else
      cout << "The stacks s1 and s3 are not equal." << endl;
}
```

```Output
The stacks s1 and s2 are not equal.
The stacks s1 and s3 are equal.
```

## <a name="operatorgt"></a><a name="op_gt"></a> operator&gt;

演算子の左辺のスタック オブジェクトが右辺のスタック オブジェクトより大きいかどうかを調べます。

```cpp
bool operator>(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`stack` 型のオブジェクト。

*そうです*\
`stack` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺のスタックが、演算子の右辺のスタックと等しくなく、かつ等しい場合は、。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

stack オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの stack オブジェクト間の大なり関係は、最初の等しくない要素のペアの比較に基づいています。

### <a name="example"></a>例

```cpp
// stack_op_gt.cpp
// compile with: /EHsc
#include <stack>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares stacks with list base container
   stack <int, list<int> > s1, s2, s3;

   s1.push( 1 );
   s1.push( 2 );
   s1.push( 3 );
   s2.push( 5 );
   s2.push( 10 );
   s3.push( 1 );
   s3.push( 2 );

   if ( s1 > s2 )
      cout << "The stack s1 is greater than "
           << "the stack s2." << endl;
   else
      cout << "The stack s1 is not greater than "
           << "the stack s2." << endl;

   if ( s1> s3 )
      cout << "The stack s1 is greater than "
           << "the stack s3." << endl;
   else
      cout << "The stack s1 is not greater than "
           << "the stack s3." << endl;
}
```

```Output
The stack s1 is not greater than the stack s2.
The stack s1 is greater than the stack s3.
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a> operator&gt;=

演算子の左辺のスタック オブジェクトが右辺のスタック オブジェクト以上かどうかを調べます。

```cpp
bool operator>=(const stack <Type, Container>& left, const stack <Type, Container>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`stack` 型のオブジェクト。

*そうです*\
`stack` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺のスタックが、演算子の右辺のスタックより厳密に小さい場合は、それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

stack オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの stack オブジェクト間の "以上" 関係は、最初の等しくない要素のペアの比較に基づいています。

### <a name="example"></a>例

```cpp
// stack_op_ge.cpp
// compile with: /EHsc
#include <stack>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares stacks with list base container
   stack <int, list<int> > s1, s2, s3;

   s1.push( 1 );
   s1.push( 2 );
   s2.push( 5 );
   s2.push( 10 );
   s3.push( 1 );
   s3.push( 2 );

   if ( s1 >= s2 )
      cout << "The stack s1 is greater than or equal to "
           << "the stack s2." << endl;
   else
      cout << "The stack s1 is less than "
           << "the stack s2." << endl;

   if ( s1>= s3 )
      cout << "The stack s1 is greater than or equal to "
           << "the stack s3." << endl;
   else
      cout << "The stack s1 is less than "
           << "the stack s3." << endl;
}
```

```Output
The stack s1 is less than the stack s2.
The stack s1 is greater than or equal to the stack s3.
```
