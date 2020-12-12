---
description: 詳細については、「 &lt; unordered_map 演算子」を参照してください。 &gt;
title: '&lt;unordered_map&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- unordered_map/std::operator!=
- unordered_map/std::operator==
ms.assetid: 9d5add0b-84bd-4a79-bd82-3f58b55145ed
ms.openlocfilehash: b7bf3712a7068b3af2d8316249d169854401b93e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321479"
---
# <a name="ltunordered_mapgt-operators"></a>&lt;unordered_map&gt; 演算子

[unordered_map:: operator! =](#op_neq)\
[unordered_map:: operator = =](#op_eq_eq)\
[unordered_multimap:: operator! =](#op_neq_multimap)\
[unordered_multimap:: operator = =](#op_eq_eq_multimap)

## <a name="operator"></a><a name="op_neq"></a> operator! =

演算子の左側の [unordered_map](../standard-library/unordered-map-class.md) オブジェクトが右側の unordered_map オブジェクトと等しくないかどうかをテストします。

```cpp
bool operator!=(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`unordered_map` 型のオブジェクト。

*そうです*\
`unordered_map` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** unordered_maps が等しくない場合は。 **`false`** 等しい場合は。

### <a name="remarks"></a>解説

unordered_map オブジェクト間の比較は、要素を任意の順序で格納することによる影響を受けません。 同じ数の要素が存在し、一方のコンテナー内の要素がもう一方のコンテナー内の要素の順列である場合、2 つの unordered_map は等しくなります。 それ以外の場合は等しくありません。

### <a name="example"></a>例

```cpp
// unordered_map_op_ne.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_map>
#include <iostream>
#include <ios>

int main( )
{
   using namespace std;
   unordered_map<int, int> um1, um2, um3;

   for ( int i = 0 ; i < 3 ; ++i ) {
      um1.insert( make_pair( i+1, i ) );
      um1.insert( make_pair( i, i ) );

      um2.insert( make_pair( i, i+1 ) );
      um2.insert( make_pair( i, i ) );

      um3.insert( make_pair( i, i ) );
      um3.insert( make_pair( i+1, i ) );
   }

   cout << boolalpha;
   cout << "um1 != um2: " << (um1 != um2) << endl;
   cout << "um1 != um3: " << (um1 != um3) << endl;
   cout << "um2 != um3: " << (um2 != um3) << endl;
}

/* Output:
um1 != um2: true
um1 != um3: false
um2 != um3: true
*/
```

## <a name="operator"></a><a name="op_eq_eq"></a> operator = =

演算子の左側の [unordered_map](../standard-library/unordered-map-class.md) オブジェクトが右側の unordered_map オブジェクトと等しいかどうかをテストします。

```cpp
bool operator==(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`unordered_map` 型のオブジェクト。

*そうです*\
`unordered_map` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** unordered_maps が等しい場合は。 **`false`** 等しくない場合。

### <a name="remarks"></a>解説

unordered_map オブジェクト間の比較は、要素を任意の順序で格納することによる影響を受けません。 同じ数の要素が存在し、一方のコンテナー内の要素がもう一方のコンテナー内の要素の順列である場合、2 つの unordered_map は等しくなります。 それ以外の場合は等しくありません。

### <a name="example"></a>例

```cpp
// unordered_map_op_eq.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_map>
#include <iostream>
#include <ios>

int main( )
{
   using namespace std;
   unordered_map<int, int> um1, um2, um3;

   for ( int i = 0 ; i < 3 ; ++i ) {
      um1.insert( make_pair( i+1, i ) );
      um1.insert( make_pair( i, i ) );

      um2.insert( make_pair( i, i+1 ) );
      um2.insert( make_pair( i, i ) );

      um3.insert( make_pair( i, i ) );
      um3.insert( make_pair( i+1, i ) );
   }

   cout << boolalpha;
   cout << "um1 == um2: " << (um1 == um2) << endl;
   cout << "um1 == um3: " << (um1 == um3) << endl;
   cout << "um2 == um3: " << (um2 == um3) << endl;
}

/* Output:
um1 == um2: false
um1 == um3: true
um2 == um3: false
*/
```

## <a name="operator-multimap"></a><a name="op_neq_multimap"></a> operator! = (multimap)

演算子の左側の [unordered_multimap](../standard-library/unordered-multimap-class.md) オブジェクトが右側の unordered_multimap オブジェクトと等しくないかどうかをテストします。

```cpp
bool operator!=(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`unordered_multimap` 型のオブジェクト。

*そうです*\
`unordered_multimap` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** unordered_multimaps が等しくない場合は。 **`false`** 等しい場合は。

### <a name="remarks"></a>解説

unordered_multimap オブジェクト間の比較は、要素を任意の順序で格納することによる影響を受けません。 同じ数の要素が存在し、一方のコンテナー内の要素がもう一方のコンテナー内の要素の順列である場合、2 つの unordered_multimap は等しくなります。 それ以外の場合は等しくありません。

### <a name="example"></a>例

```cpp
// unordered_multimap_op_ne.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_map>
#include <iostream>
#include <ios>

int main( )
{
   using namespace std;
   unordered_multimap<int, int> um1, um2, um3;

   for ( int i = 0 ; i < 3 ; ++i ) {
      um1.insert( make_pair( i, i ) );
      um1.insert( make_pair( i, i ) );

      um2.insert( make_pair( i, i ) );
      um2.insert( make_pair( i, i ) );
      um2.insert( make_pair( i, i ) );

      um3.insert( make_pair( i, i ) );
      um3.insert( make_pair( i, i ) );
   }

   cout << boolalpha;
   cout << "um1 != um2: " << (um1 != um2) << endl;
   cout << "um1 != um3: " << (um1 != um3) << endl;
   cout << "um2 != um3: " << (um2 != um3) << endl;
}

/* Output:
um1 != um2: true
um1 != um3: false
um2 != um3: true
*/
```

## <a name="operator-multimap"></a><a name="op_eq_eq_multimap"></a> operator = = (multimap)

演算子の左側の [unordered_multimap](../standard-library/unordered-multimap-class.md) オブジェクトが右側の unordered_multimap オブジェクトと等しいかどうかをテストします。

```cpp
bool operator==(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`unordered_multimap` 型のオブジェクト。

*そうです*\
`unordered_multimap` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** unordered_multimaps が等しい場合は。 **`false`** 等しくない場合。

### <a name="remarks"></a>解説

unordered_multimap オブジェクト間の比較は、要素を任意の順序で格納することによる影響を受けません。 同じ数の要素が存在し、一方のコンテナー内の要素がもう一方のコンテナー内の要素の順列である場合、2 つの unordered_multimap は等しくなります。 それ以外の場合は等しくありません。

### <a name="example"></a>例

```cpp
// unordered_multimap_op_eq.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_map>
#include <iostream>
#include <ios>

int main( )
{
   using namespace std;
   unordered_multimap<int, int> um1, um2, um3;

   for ( int i = 0 ; i < 3 ; ++i ) {
      um1.insert( make_pair( i, i ) );
      um1.insert( make_pair( i, i ) );

      um2.insert( make_pair( i, i ) );
      um2.insert( make_pair( i, i ) );
      um2.insert( make_pair( i, i ) );

      um3.insert( make_pair( i, i ) );
      um3.insert( make_pair( i, i ) );
   }

   cout << boolalpha;
   cout << "um1 == um2: " << (um1 == um2) << endl;
   cout << "um1 == um3: " << (um1 == um3) << endl;
   cout << "um2 == um3: " << (um2 == um3) << endl;
}

/* Output:
um1 == um2: false
um1 == um3: true
um2 == um3: false
*/
```

## <a name="see-also"></a>関連項目

[<unordered_map>](../standard-library/unordered-map.md)
