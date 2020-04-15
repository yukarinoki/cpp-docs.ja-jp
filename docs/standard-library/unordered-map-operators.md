---
title: '&lt;unordered_map&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- unordered_map/std::operator!=
- unordered_map/std::operator==
ms.assetid: 9d5add0b-84bd-4a79-bd82-3f58b55145ed
ms.openlocfilehash: f062c4fd0332525a8b8940d2d93df41df56d2baa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373118"
---
# <a name="ltunordered_mapgt-operators"></a>&lt;unordered_map&gt; 演算子

|||||
|-|-|-|-|
|[演算子!=](#op_neq)|[演算子==](#op_eq_eq)|[演算子!=](#op_neq_multimap)|[演算子==](#op_eq_eq_multimap)|

## <a name="operator"></a><a name="op_neq"></a>演算子!=

演算子の左側の [unordered_map](../standard-library/unordered-map-class.md) オブジェクトが右側の unordered_map オブジェクトと等しくないかどうかをテストします。

```cpp
bool operator!=(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左*\
`unordered_map` 型オブジェクト。

*そうです*\
`unordered_map` 型オブジェクト。

### <a name="return-value"></a>戻り値

unordered_mapsが等しくない場合は**true。** 等しい場合は**false。**

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
```

**出力：**

`um1 != um2: true`

`um1 != um3: false`

`um2 != um3: true`

## <a name="operator"></a><a name="op_eq_eq"></a>演算子==

演算子の左側の [unordered_map](../standard-library/unordered-map-class.md) オブジェクトが右側の unordered_map オブジェクトと等しいかどうかをテストします。

```cpp
bool operator==(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左*\
`unordered_map` 型オブジェクト。

*そうです*\
`unordered_map` 型オブジェクト。

### <a name="return-value"></a>戻り値

unordered_mapsが等しい場合は**true。** 等しくない場合は**false。**

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
```

**出力：**

`um1 == um2: false`

`um1 == um3: true`

`um2 == um3: false`

## <a name="operator"></a><a name="op_neq_multimap"></a>演算子!=

演算子の左側の [unordered_multimap](../standard-library/unordered-multimap-class.md) オブジェクトが右側の unordered_multimap オブジェクトと等しくないかどうかをテストします。

```cpp
bool operator!=(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左*\
`unordered_multimap` 型オブジェクト。

*そうです*\
`unordered_multimap` 型オブジェクト。

### <a name="return-value"></a>戻り値

unordered_multimapsが等しくない場合は**true。** 等しい場合は**false。**

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
```

**出力：**

`um1 != um2: true`

`um1 != um3: false`

`um2 != um3: true`

## <a name="operator"></a><a name="op_eq_eq_multimap"></a>演算子==

演算子の左側の [unordered_multimap](../standard-library/unordered-multimap-class.md) オブジェクトが右側の unordered_multimap オブジェクトと等しいかどうかをテストします。

```cpp
bool operator==(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左*\
`unordered_multimap` 型オブジェクト。

*そうです*\
`unordered_multimap` 型オブジェクト。

### <a name="return-value"></a>戻り値

unordered_multimapsが等しい場合は**true。** 等しくない場合は**false。**

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
```

**出力：**

`um1 == um2: false`

`um1 == um3: true`

`um2 == um3: false`

## <a name="see-also"></a>関連項目

[<unordered_map>](../standard-library/unordered-map.md)
