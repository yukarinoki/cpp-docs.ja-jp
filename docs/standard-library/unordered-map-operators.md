---
title: '&lt;unordered_map&gt; 演算子 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- unordered_map/std::operator!=
- unordered_map/std::operator==
dev_langs:
- C++
ms.assetid: 9d5add0b-84bd-4a79-bd82-3f58b55145ed
ms.openlocfilehash: 69a53ae6b54248f5b9938e2c9137a24f441c061d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="ltunorderedmapgt-operators"></a>&lt;unordered_map&gt; 演算子

|||||
|-|-|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|[operator!=](#op_neq_multimap)|[operator==](#op_eq_eq_multimap)|

## <a name="op_neq"></a>  operator!=

演算子の左側の [unordered_map](../standard-library/unordered-map-class.md) オブジェクトが右側の unordered_map オブジェクトと等しくないかどうかをテストします。

```cpp
bool operator!=(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

`left` 型のオブジェクト`unordered_map`です。

`right` 型のオブジェクト`unordered_map`です。

### <a name="return-value"></a>戻り値

unordered_map が等しくない場合は、`true`。等しい場合は、`false`。

### <a name="remarks"></a>コメント

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

**出力:**

`um1 != um2: true`

`um1 != um3: false`

`um2 != um3: true`

## <a name="op_eq_eq"></a>  operator==

演算子の左側の [unordered_map](../standard-library/unordered-map-class.md) オブジェクトが右側の unordered_map オブジェクトと等しいかどうかをテストします。

```cpp
bool operator==(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

`left` 型のオブジェクト`unordered_map`です。

`right` 型のオブジェクト`unordered_map`です。

### <a name="return-value"></a>戻り値

unordered_map が等しい場合は、`true`。等しくない場合は、`false`。

### <a name="remarks"></a>コメント

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

**出力:**

`um1 == um2: false`

`um1 == um3: true`

`um2 == um3: false`

## <a name="op_neq_multimap"></a>  operator!=

演算子の左側の [unordered_multimap](../standard-library/unordered-multimap-class.md) オブジェクトが右側の unordered_multimap オブジェクトと等しくないかどうかをテストします。

```cpp
bool operator!=(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

`left` 型のオブジェクト`unordered_multimap`です。

`right` 型のオブジェクト`unordered_multimap`です。

### <a name="return-value"></a>戻り値

unordered_multimap が等しくない場合は、`true`。等しい場合は、`false`。

### <a name="remarks"></a>コメント

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

**出力:**

`um1 != um2: true`

`um1 != um3: false`

`um2 != um3: true`

## <a name="op_eq_eq_multimap"></a>  operator==

演算子の左側の [unordered_multimap](../standard-library/unordered-multimap-class.md) オブジェクトが右側の unordered_multimap オブジェクトと等しいかどうかをテストします。

```cpp
bool operator==(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

`left` 型のオブジェクト`unordered_multimap`です。

`right` 型のオブジェクト`unordered_multimap`です。

### <a name="return-value"></a>戻り値

unordered_multimap が等しい場合は、`true`。等しくない場合は、`false`。

### <a name="remarks"></a>コメント

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

**出力:**

`um1 == um2: false`

`um1 == um3: true`

`um2 == um3: false`

## <a name="see-also"></a>関連項目

[<unordered_map>](../standard-library/unordered-map.md)<br/>
