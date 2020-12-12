---
description: 詳細については、「乗算構造体」を参照してください
title: multiplies 構造体
ms.date: 11/04/2016
f1_keywords:
- functional/std::multiplies
helpviewer_keywords:
- multiplies class
- multiplies struct
ms.assetid: ec85e8af-70ad-44ad-90f0-d961a5847864
ms.openlocfilehash: 552f36d2060ca9ad6141438a45a128e84b705630
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114989"
---
# <a name="multiplies-struct"></a>multiplies 構造体

引数に対して乗算演算 (二項 `operator*`) を実行する定義済みの関数オブジェクト。

## <a name="syntax"></a>構文

```
template <class Type = void>
struct multiplies : public binary_function <Type, Type, Type>
{
    Type operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator*
template <>
struct multiplies<void>
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const`
    -> decltype(std::forward<T>(Left) * std::forward<U>(Right));
};
```

### <a name="parameters"></a>パラメーター

*型*、 *T*、 *U*\
指定または推論された型のオペランドを受け取る二項 `operator*` をサポートする型。

*左側*\
乗算演算の左オペランド。 非特殊テンプレートは、type *型* の左辺値参照引数を受け取ります。 特殊化されたテンプレートは、推論された型 *T* の左辺値および右辺値参照引数の完全転送を行います。

*そうです*\
乗算演算の右オペランド。 非特殊テンプレートは、type *型* の左辺値参照引数を受け取ります。 特殊化されたテンプレートは、推論された型 *U* の左辺値および右辺値参照引数の完全転送を行います。

## <a name="return-value"></a>戻り値

`Left * Right` の結果。 特殊化されたテンプレートは、結果の完全転送を行います。結果には `operator*` によって返された型が含まれます。

## <a name="example"></a>例

```cpp
// functional_multiplies.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main( )
{
   vector <int> v1, v2, v3 ( 6 );
   vector <int>::iterator Iter1, Iter2, Iter3;

   int i;
   for ( i = 1 ; i <= 6 ; i++ )
   {
      v1.push_back( 2 * i );
   }

   int j;
   for ( j = 1 ; j <= 6 ; j++ )
   {
      v2.push_back( 3 * j );
   }

   cout << "The vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "The vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // Finding the element-wise products of the elements of v1 & v2
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),
      multiplies<int>( ) );

   cout << "The element-wise products of vectors V1 & v2\n are: ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;
}
```

```Output
The vector v1 = ( 2 4 6 8 10 12 )
The vector v2 = ( 3 6 9 12 15 18 )
The element-wise products of vectors V1 & v2
are: ( 6 24 54 96 150 216 )
```
