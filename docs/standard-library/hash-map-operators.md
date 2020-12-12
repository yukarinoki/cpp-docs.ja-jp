---
description: 詳細については、「 &lt; hash_map 演算子」を参照してください。 &gt;
title: '&lt;hash_map&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- hash_map/std::operator!=
- hash_map/std::operator==
ms.assetid: 24b9bb9e-e983-4060-bce5-2c7c8161ee61
ms.openlocfilehash: f3374ee86a989a90add86e85d6a9bf15959e26b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324123"
---
# <a name="lthash_mapgt-operators"></a>&lt;hash_map&gt; 演算子

[operator! =](#op_neq)\
[operator! = (multimap)](#op_neq_mm)\
[operator = =](#op_eq_eq)\
[operator = = (multimap)](#op_eq_eq_mm)

## <a name="operator"></a><a name="op_neq"></a> operator! =

> [!NOTE]
> この API は、互換性のために残されています。 代わりに、[unordered_map クラス](unordered-map-class.md)を使用してください。

演算子の左辺の hash_map オブジェクトが右辺の hash_map オブジェクトと等しくないかどうかを調べます。

```cpp
bool operator!=(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`hash_map` 型のオブジェクト。

*そうです*\
`hash_map` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** hash_maps が等しくない場合は。 **`false`** hash_maps が等しい場合は。

### <a name="remarks"></a>解説

hash_map オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの hash_maps は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。

[<hash_map](hash-map.md)のメンバーは、 [Stdext 名前空間](stdext-namespace.md)の hash_set ヘッダーファイルを>および[<](hash-set.md)します。

### <a name="example"></a>例

```cpp
// hash_map_op_ne.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1, hm2, hm3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hm1.insert ( Int_Pair ( i, i ) );
      hm2.insert ( Int_Pair ( i, i * i ) );
      hm3.insert ( Int_Pair ( i, i ) );
   }

   if ( hm1 != hm2 )
      cout << "The hash_maps hm1 and hm2 are not equal." << endl;
   else
      cout << "The hash_maps hm1 and hm2 are equal." << endl;

   if ( hm1 != hm3 )
      cout << "The hash_maps hm1 and hm3 are not equal." << endl;
   else
      cout << "The hash_maps hm1 and hm3 are equal." << endl;
}
```

```Output
The hash_maps hm1 and hm2 are not equal.
The hash_maps hm1 and hm3 are equal.
```

## <a name="operator"></a><a name="op_eq_eq"></a> operator = =

> [!NOTE]
> この API は、互換性のために残されています。 代わりに、[unordered_map クラス](unordered-map-class.md)を使用してください。

演算子の左辺の hash_map オブジェクトが右辺の hash_map オブジェクトと等しいかどうかを調べます。

```cpp
bool operator==(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`hash_map` 型のオブジェクト。

*そうです*\
`hash_map` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺の hash_map が、演算子の右辺の hash_map と等しい場合は、。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

hash_map オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの hash_maps は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。

### <a name="example"></a>例

```cpp
// hash_map_op_eq.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1, hm2, hm3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hm1.insert ( Int_Pair ( i, i ) );
      hm2.insert ( Int_Pair ( i, i * i ) );
      hm3.insert ( Int_Pair ( i, i ) );
   }

   if ( hm1 == hm2 )
      cout << "The hash_maps hm1 and hm2 are equal." << endl;
   else
      cout << "The hash_maps hm1 and hm2 are not equal." << endl;

   if ( hm1 == hm3 )
      cout << "The hash_maps hm1 and hm3 are equal." << endl;
   else
      cout << "The hash_maps hm1 and hm3 are not equal." << endl;
}
```

```Output
The hash_maps hm1 and hm2 are not equal.
The hash_maps hm1 and hm3 are equal.
```

## <a name="operator-hash_multimap"></a><a name="op_neq_mm"></a> operator! = (hash_multimap)

> [!NOTE]
> この API は、互換性のために残されています。 代替が必要な場合は、 [unordered_multimap Class](unordered-multimap-class.md)をご使用ください。

演算子の左側の hash_multimap オブジェクトが右側の hash_multimap オブジェクトと等しくないかどうかをテストします。

```cpp
bool operator!=(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`hash_multimap` 型のオブジェクト。

*そうです*\
`hash_multimap` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** hash_multimaps が等しくない場合は。 **`false`** hash_multimaps が等しい場合は。

### <a name="remarks"></a>解説

hash_multimap オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの hash_multimaps は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。

### <a name="example"></a>例

```cpp
// hash_multimap_op_ne.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1, hm2, hm3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hm1.insert ( Int_Pair ( i, i ) );
      hm2.insert ( Int_Pair ( i, i * i ) );
      hm3.insert ( Int_Pair ( i, i ) );
   }

   if ( hm1 != hm2 )
      cout << "The hash_multimaps hm1 and hm2 are not equal." << endl;
   else
      cout << "The hash_multimaps hm1 and hm2 are equal." << endl;

   if ( hm1 != hm3 )
      cout << "The hash_multimaps hm1 and hm3 are not equal." << endl;
   else
      cout << "The hash_multimaps hm1 and hm3 are equal." << endl;
}
```

```Output
The hash_multimaps hm1 and hm2 are not equal.
The hash_multimaps hm1 and hm3 are equal.
```

## <a name="operator--hash_multimap"></a><a name="op_eq_eq_mm"></a> operator = = (hash_multimap)

> [!NOTE]
> この API は、互換性のために残されています。 代替が必要な場合は、 [unordered_multimap Class](unordered-multimap-class.md)をご使用ください。

演算子の左側の hash_multimap オブジェクトが右側の hash_multimap オブジェクトと等しいかどうかをテストします。

```cpp
bool operator==(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`hash_multimap` 型のオブジェクト。

*そうです*\
`hash_multimap` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺の hash_multimap が、演算子の右辺の hash_multimap と等しい場合は、。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

hash_multimap オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの hash_multimaps は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。

### <a name="example"></a>例

```cpp
// hash_multimap_op_eq.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap<int, int> hm1, hm2, hm3;
   int i;
   typedef pair<int, int> Int_Pair;

   for (i = 0; i < 3; i++)
   {
      hm1.insert(Int_Pair(i, i));
      hm2.insert(Int_Pair(i, i*i));
      hm3.insert(Int_Pair(i, i));
   }

   if ( hm1 == hm2 )
      cout << "The hash_multimaps hm1 and hm2 are equal." << endl;
   else
      cout << "The hash_multimaps hm1 and hm2 are not equal." << endl;

   if ( hm1 == hm3 )
      cout << "The hash_multimaps hm1 and hm3 are equal." << endl;
   else
      cout << "The hash_multimaps hm1 and hm3 are not equal." << endl;
}
```

```Output
The hash_multimaps hm1 and hm2 are not equal.
The hash_multimaps hm1 and hm3 are equal.
```

## <a name="see-also"></a>関連項目

[<hash_map>](hash-map.md)
