---
title: '&lt;map&gt; 演算子 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- map/std::operator!=
- map/std::operator&gt;
- map/std::operator&gt;=
- map/std::operator&lt;
- map/std::operator&lt;=
- map/std::operator==
dev_langs:
- C++
ms.assetid: 7df02b9f-701c-44ed-834a-a819badc5bd0
helpviewer_keywords:
- std::operator!= (map)
- std::operator&gt; (map)
- std::operator&gt;= (map)
- std::operator&lt; (map)
- std::operator&lt;= (map)
- std::operator== (map)
ms.openlocfilehash: 0113f792a20c1680ce931d43cbaf016e7bcfaf59
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44108307"
---
# <a name="ltmapgt-operators"></a>&lt;map&gt; 演算子

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|
|[operator!= (multimap)](#op_neq_multimap)|[operator&gt;](#op_gt_multimap)|[operator&gt;=](#op_gt_eq_multimap)|
|[operator&lt;](#op_lt_multimap)|[operator&lt;=](#op_lt_eq_multimap)|[operator==](#op_eq_eq_multimap)|

## <a name="op_neq"></a>  operator!=

演算子の左辺の map オブジェクトが右辺の map オブジェクトと等しくないかどうかを調べます。

```cpp
bool operator!=(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
`map` 型のオブジェクト。

*right*<br/>
`map` 型のオブジェクト。

### <a name="return-value"></a>戻り値

map が等しくない場合は **true**、map が等しい場合は **false**。

### <a name="remarks"></a>Remarks

map オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの map は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。

### <a name="example"></a>例

```cpp
// map_op_ne.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1, m2, m3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 != m2 )
      cout << "The maps m1 and m2 are not equal." << endl;
   else
      cout << "The maps m1 and m2 are equal." << endl;

   if ( m1 != m3 )
      cout << "The maps m1 and m3 are not equal." << endl;
   else
      cout << "The maps m1 and m3 are equal." << endl;
}
\* Output:
The maps m1 and m2 are not equal.
The maps m1 and m3 are equal.
*\
```

## <a name="op_lt"></a>  operator&lt;

演算子の左辺の map オブジェクトが右辺の map オブジェクトより小さいかどうかを調べます。

```cpp
bool operator<(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
`map` 型のオブジェクト。

*right*<br/>
`map` 型のオブジェクト。

### <a name="return-value"></a>戻り値

演算子の左辺の map が演算子の右辺の map より厳密に小さい場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>Remarks

map オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つのオブジェクト間の小なり関係は、最初の等しくない要素のペアの比較に基づいています。

### <a name="example"></a>例

```cpp
// map_op_lt.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map<int, int> m1, m2, m3;
   int i;
   typedef pair<int, int> Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
   }

   if ( m1 < m2 )
      cout << "The map m1 is less than the map m2." << endl;
   else
      cout << "The map m1 is not less than the map m2." << endl;

   if ( m1 < m3 )
      cout << "The map m1 is less than the map m3." << endl;
   else
      cout << "The map m1 is not less than the map m3." << endl;
}
\* Output:
The map m1 is less than the map m2.
The map m1 is not less than the map m3.
*\
```

## <a name="op_lt_eq"></a>  演算子&lt;=

演算子の左辺の map オブジェクトが右辺の map オブジェクト以下かどうかを調べます。

```cpp
bool operator<=(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
`map` 型のオブジェクト。

*right*<br/>
`map` 型のオブジェクト。

### <a name="return-value"></a>戻り値

演算子の左辺の map が演算子の右辺の map 以下である場合は **true**、それ以外の場合は **false**。

### <a name="example"></a>例

```cpp
// map_op_le.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1, m2, m3, m4;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
      m4.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 <= m2 )
      cout << "The map m1 is less than or equal to the map m2." << endl;
   else
      cout << "The map m1 is greater than the map m2." << endl;

   if ( m1 <= m3 )
      cout << "The map m1 is less than or equal to the map m3." << endl;
   else
      cout << "The map m1 is greater than the map m3." << endl;

   if ( m1 <= m4 )
      cout << "The map m1 is less than or equal to the map m4." << endl;
   else
      cout << "The map m1 is greater than the map m4." << endl;
}
\* Output:
The map m1 is less than or equal to the map m2.
The map m1 is greater than the map m3.
The map m1 is less than or equal to the map m4.
*\
```

## <a name="op_eq_eq"></a>  operator==

演算子の左辺の map オブジェクトが右辺の map オブジェクトと等しいかどうかを調べます。

```cpp
bool operator==(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
`map` 型のオブジェクト。

*right*<br/>
`map` 型のオブジェクト。

### <a name="return-value"></a>戻り値

演算子の左辺の map が演算子の右辺の map と等しい場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>Remarks

map オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの map は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。

### <a name="example"></a>例

```cpp
// map_op_eq.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map < int, int > m1, m2, m3;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 == m2 )
      cout << "The maps m1 and m2 are equal." << endl;
   else
      cout << "The maps m1 and m2 are not equal." << endl;

   if ( m1 == m3 )
      cout << "The maps m1 and m3 are equal." << endl;
   else
      cout << "The maps m1 and m3 are not equal." << endl;
}
\* Output:
The maps m1 and m2 are not equal.
The maps m1 and m3 are equal.
*\
```

## <a name="op_gt"></a>  operator&gt;

演算子の左辺の map オブジェクトが右辺の map オブジェクトより大きいかどうかを調べます。

```cpp
bool operator>(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
`map` 型のオブジェクト。

*right*<br/>
`map` 型のオブジェクト。

### <a name="return-value"></a>戻り値

演算子の左辺の map が演算子の右辺の map より大きい場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>Remarks

map オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つのオブジェクト間の大なり関係は、最初の等しくない要素のペアの比較に基づいています。

### <a name="example"></a>例

```cpp
// map_op_gt.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map < int, int > m1, m2, m3;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
   }

   if ( m1 > m2 )
      cout << "The map m1 is greater than the map m2." << endl;
   else
      cout << "The map m1 is not greater than the map m2." << endl;

   if ( m1 > m3 )
      cout << "The map m1 is greater than the map m3." << endl;
   else
      cout << "The map m1 is not greater than the map m3." << endl;
}
\* Output:
The map m1 is not greater than the map m2.
The map m1 is greater than the map m3.
*\
```

## <a name="op_gt_eq"></a>  演算子&gt;=

演算子の左辺の map オブジェクトが右辺の map オブジェクト以上かどうかを調べます。

```cpp
bool operator>=(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
`map` 型のオブジェクト。

*right*<br/>
`map` 型のオブジェクト。

### <a name="return-value"></a>戻り値

演算子の左側の map がリストの右側の map 以上の場合は **true**、それ以外の場合は **false**。

### <a name="example"></a>例

```cpp
// map_op_ge.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map < int, int > m1, m2, m3, m4;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
      m4.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 >= m2 )
      cout << "Map m1 is greater than or equal to map m2." << endl;
   else
      cout << "The map m1 is less than the map m2." << endl;

   if ( m1 >= m3 )
      cout << "Map m1 is greater than or equal to map m3." << endl;
   else
      cout << "The map m1 is less than the map m3." << endl;

   if ( m1 >= m4 )
      cout << "Map m1 is greater than or equal to map m4." << endl;
   else
      cout << "The map m1 is less than the map m4." << endl;
}
\* Output:
The map m1 is less than the map m2.
Map m1 is greater than or equal to map m3.
Map m1 is greater than or equal to map m4.
*\
```

## <a name="op_neq_multimap"></a>  operator!= (multimap)

演算子の左辺の multimap オブジェクトが右辺の multimap オブジェクトと等しくないかどうかをテストします。

```cpp
bool operator!=(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
`multimap` 型のオブジェクト。

*right*<br/>
`multimap` 型のオブジェクト。

### <a name="return-value"></a>戻り値

multimap が等しくない場合は **true**、multimap が等しい場合は **false**。

### <a name="remarks"></a>Remarks

multimap オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの multimap は、同じ数の要素を持ち各要素の値が同じである場合に、等しくなります。 それ以外の場合は等しくありません。

### <a name="example"></a>例

```cpp
// multimap_op_ne.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1, m2, m3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 != m2 )
      cout << "The multimaps m1 and m2 are not equal." << endl;
   else
      cout << "The multimaps m1 and m2 are equal." << endl;

   if ( m1 != m3 )
      cout << "The multimaps m1 and m3 are not equal." << endl;
   else
      cout << "The multimaps m1 and m3 are equal." << endl;
}
\* Output:
The multimaps m1 and m2 are not equal.
The multimaps m1 and m3 are equal.
*\
```

## <a name="op_lt_multimap"></a>  operator&lt;

演算子の左辺の multimap オブジェクトが右辺の multimap オブジェクトより小さいかどうかをテストします。

```cpp
bool operator<(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
`multimap` 型のオブジェクト。

*right*<br/>
`multimap` 型のオブジェクト。

### <a name="return-value"></a>戻り値

演算子の左辺の multimap が演算子の右辺の multimap より厳密に小さい場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>Remarks

multimap オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つのオブジェクト間の小なり関係は、最初の等しくない要素のペアの比較に基づいています。

### <a name="example"></a>例

```cpp
// multimap_op_lt.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap < int, int > m1, m2, m3;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
   }

   if ( m1 < m2 )
      cout << "The multimap m1 is less than the multimap m2." << endl;
   else
      cout << "The multimap m1 is not less than the multimap m2." << endl;

   if ( m1 < m3 )
      cout << "The multimap m1 is less than the multimap m3." << endl;
   else
      cout << "The multimap m1 is not less than the multimap m3." << endl;
}
\* Output:
The multimap m1 is less than the multimap m2.
The multimap m1 is not less than the multimap m3.
*\
```

## <a name="eq_multimap"></a>  演算子&lt;=

演算子の左辺の multimap オブジェクトが右辺の multimap オブジェクト以下かどうかをテストします。

```cpp
bool operator<=(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
`multimap` 型のオブジェクト。

*right*<br/>
`multimap` 型のオブジェクト。

### <a name="return-value"></a>戻り値

演算子の左辺の multimap が演算子の右辺の multimap 以下の場合は **true**、それ以外の場合は **false**。

### <a name="example"></a>例

```cpp
// multimap_op_le.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1, m2, m3, m4;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
      m4.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 <= m2 )
      cout << "m1 is less than or equal to m2" << endl;
   else
      cout << "m1 is greater than m2" << endl;

   if ( m1 <= m3 )
      cout << "m1 is less than or equal to m3" << endl;
   else
      cout << "m1 is greater than m3" << endl;

   if ( m1 <= m4 )
      cout << "m1 is less than or equal to m4" << endl;
   else
      cout << "m1 is greater than m4" << endl;
}
\* Output:
m1 is less than or equal to m2
m1 is greater than m3
m1 is less than or equal to m4
*\
```

## <a name="op_eq_eq_multimap"></a>  operator==

演算子の左辺の multimap オブジェクトが右辺の multimap オブジェクトと等しいかどうかをテストします。

```cpp
bool operator==(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
`multimap` 型のオブジェクト。

*right*<br/>
`multimap` 型のオブジェクト。

### <a name="return-value"></a>戻り値

演算子の左辺の multimap が演算子の右辺の multimap と等しい場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>Remarks

multimap オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの multimap は、同じ数の要素を持ち各要素の値が同じである場合に、等しくなります。 それ以外の場合は等しくありません。

### <a name="example"></a>例

```cpp
// multimap_op_eq.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap<int, int> m1, m2, m3;
   int i;
   typedef pair<int, int> Int_Pair;

   for (i = 0; i < 3; i++)
   {
      m1.insert(Int_Pair(i, i));
      m2.insert(Int_Pair(i, i*i));
      m3.insert(Int_Pair(i, i));
   }

   if ( m1 == m2 )
      cout << "m1 and m2 are equal" << endl;
   else
      cout << "m1 and m2 are not equal" << endl;

   if ( m1 == m3 )
      cout << "m1 and m3 are equal" << endl;
   else
      cout << "m1 and m3 are not equal" << endl;
}
\* Output:
m1 and m2 are not equal
m1 and m3 are equal
*\
```

## <a name="op_gt_multimap"></a>  operator&gt;

演算子の左辺の multimap オブジェクトが右辺の multimap オブジェクトより大きいかどうかをテストします。

```cpp
bool operator>(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
`multimap` 型のオブジェクト。

*right*<br/>
`multimap` 型のオブジェクト。

### <a name="return-value"></a>戻り値

演算子の左辺の multimap が演算子の右辺の multimap より大きい場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>Remarks

multimap オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つのオブジェクト間の大なり関係は、最初の等しくない要素のペアの比較に基づいています。

### <a name="example"></a>例

```cpp
// multimap_op_gt.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap < int, int > m1, m2, m3;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
   }

   if ( m1 > m2 )
      cout << "The multimap m1 is greater than the multimap m2." << endl;
   else
      cout << "Multimap m1 is not greater than multimap m2." << endl;

   if ( m1 > m3 )
      cout << "The multimap m1 is greater than the multimap m3." << endl;
   else
      cout << "The multimap m1 is not greater than the multimap m3." << endl;
}
\* Output:
Multimap m1 is not greater than multimap m2.
The multimap m1 is greater than the multimap m3.
*\
```

## <a name="op_gt_eq_multimap"></a>  演算子&gt;=

演算子の左辺の multimap オブジェクトが右辺の multimap オブジェクト以上かどうかをテストします。

```cpp
bool operator>=(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
`multimap` 型のオブジェクト。

*right*<br/>
`multimap` 型のオブジェクト。

### <a name="return-value"></a>戻り値

演算子の左側の multimap がリストの右側の multimap 以上の場合は **true**、それ以外の場合は **false**。

### <a name="example"></a>例

```cpp
// multimap_op_ge.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap < int, int > m1, m2, m3, m4;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
      m4.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 >= m2 )
      cout << "The multimap m1 is greater than or equal to the multimap m2." << endl;
   else
      cout << "The multimap m1 is less than the multimap m2." << endl;

   if ( m1 >= m3 )
      cout << "The multimap m1 is greater than or equal to the multimap m3." << endl;
   else
      cout << "The multimap m1 is less than the multimap m3." << endl;

   if ( m1 >= m4 )
      cout << "The multimap m1 is greater than or equal to the multimap m4." << endl;
   else
      cout << "The multimap m1 is less than the multimap m4." << endl;
}
\* Output:
The multimap m1 is less than the multimap m2.
The multimap m1 is greater than or equal to the multimap m3.
The multimap m1 is greater than or equal to the multimap m4.
*\
```

## <a name="see-also"></a>関連項目

[\<map>](../standard-library/map.md)<br/>
