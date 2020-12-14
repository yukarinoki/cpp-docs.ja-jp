---
description: '詳細情報: &lt; vector &gt; 演算子'
title: '&lt;vector&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- vector/std::operator!=
- vector/std::operator&gt;
- vector/std::operator&gt;=
- vector/std::operator&lt;
- vector/std::operator&lt;=
- vector/std::operator==
ms.assetid: 1d14f312-6f59-4ec7-88ae-95f89a558823
helpviewer_keywords:
- std::operator!= (vector)
- std::operator&gt; (vector)
- std::operator&gt;= (vector)
- std::operator&lt; (vector)
- std::operator&lt;= (vector)
- std::operator== (vector)
ms.openlocfilehash: a7a03d3ef843c995970552201e63d2df3cb3161d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187898"
---
# <a name="ltvectorgt-operators"></a>&lt;vector&gt; 演算子

## <a name="operator"></a><a name="op_neq"></a> operator! =

演算子の左側のオブジェクトが右側のオブジェクトと等しくないかどうかを調べます。

```cpp
bool operator!=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`vector` 型のオブジェクト。

*そうです*\
`vector` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** ベクターが等しくない場合は。 **`false`** ベクターが等しい場合は。

### <a name="remarks"></a>解説

2 つの vector は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。

### <a name="example"></a>例

```cpp
// vector_op_ne.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
     v2.push_back( 2 );

   if ( v1 != v2 )
      cout << "Vectors not equal." << endl;
   else
      cout << "Vectors equal." << endl;
}
```

```Output
Vectors not equal.
```

## <a name="operatorlt"></a><a name="op_lt"></a> operator&lt;

演算子の左側のオブジェクトが右側のオブジェクトより小さいかどうかを調べます。

```cpp
bool operator<(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`vector` 型のオブジェクト。

*そうです*\
`vector` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺の vector が演算子の右辺の vector より小さい場合は、です。それ以外の場合は **`false`** 。

### <a name="example"></a>例

```cpp
// vector_op_lt.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 2 );
   v1.push_back( 4 );

   v2.push_back( 1 );
   v2.push_back( 3 );

   if ( v1 < v2 )
      cout << "Vector v1 is less than vector v2." << endl;
   else
      cout << "Vector v1 is not less than vector v2." << endl;
}
```

```Output
Vector v1 is less than vector v2.
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a> operator&lt;=

演算子の左側のオブジェクトが右側のオブジェクト以下かどうかを調べます。

```cpp
bool operator<=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`vector` 型のオブジェクト。

*そうです*\
`vector` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺の vector が演算子の右辺のベクトル以下である場合は、を返します。それ以外の場合は **`false`** 。

### <a name="example"></a>例

```cpp
// vector_op_le.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 2 );
   v1.push_back( 4 );

   v2.push_back( 1 );
   v2.push_back( 3 );

   if ( v1 <= v2 )
      cout << "Vector v1 is less than or equal to vector v2." << endl;
   else
      cout << "Vector v1 is greater than vector v2." << endl;
}
```

```Output
Vector v1 is less than or equal to vector v2.
```

## <a name="operator"></a><a name="op_eq_eq"></a> operator = =

演算子の左側のオブジェクトが右側のオブジェクトと等しいかどうかを調べます。

```cpp
bool operator==(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`vector` 型のオブジェクト。

*そうです*\
`vector` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺の vector が演算子の右辺のベクトルと等しい場合は、です。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

2 つの vector は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。

### <a name="example"></a>例

```cpp
// vector_op_eq.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v2.push_back( 1 );

   if ( v1 == v2 )
      cout << "Vectors equal." << endl;
   else
      cout << "Vectors not equal." << endl;
}
```

```Output
Vectors equal.
```

## <a name="operatorgt"></a><a name="op_gt"></a> operator&gt;

演算子の左側のオブジェクトが右側のオブジェクトより大きいかどうかを調べます。

```cpp
bool operator>(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`vector` 型のオブジェクト。

*そうです*\
`vector` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺の vector が演算子の右辺の vector より大きい場合は、です。それ以外の場合は **`false`** 。

### <a name="example"></a>例

```cpp
// vector_op_gt.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 3 );
   v1.push_back( 1 );

   v2.push_back( 1 );
   v2.push_back( 2 );
   v2.push_back( 2 );

   if ( v1 > v2 )
      cout << "Vector v1 is greater than vector v2." << endl;
   else
      cout << "Vector v1 is not greater than vector v2." << endl;
}
```

```Output
Vector v1 is greater than vector v2.
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a> operator&gt;=

演算子の左側のオブジェクトが右側のオブジェクト以上であるかどうかを調べます。

```cpp
bool operator>=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`vector` 型のオブジェクト。

*そうです*\
`vector` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺のベクターがベクターの右辺のベクトル以上である場合は、を返します。それ以外の場合は **`false`** 。

### <a name="example"></a>例

```cpp
// vector_op_ge.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 3 );
   v1.push_back( 1 );

     v2.push_back( 1 );
   v2.push_back( 2 );
   v2.push_back( 2 );

   if ( v1 >= v2 )
      cout << "Vector v1 is greater than or equal to vector v2." << endl;
   else
      cout << "Vector v1 is less than vector v2." << endl;
}
```

```Output
Vector v1 is greater than or equal to vector v2.
```
