---
description: '詳細については、次を参照してください: less_equal 構造体'
title: less_equal 構造体
ms.date: 11/04/2016
f1_keywords:
- functional/std::less_equal
helpviewer_keywords:
- less_equal function
- less_equal struct
ms.assetid: 32085782-c7e0-4310-9b40-8aa3c1bff211
ms.openlocfilehash: b2d715971c5278629a6ea812c5a9c199f00c4a07
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312892"
---
# <a name="less_equal-struct"></a>less_equal 構造体

引数に対して "以下" 演算 (`operator<=`) を実行する二項述語。

## <a name="syntax"></a>構文

```cpp
template <class Type = void>
struct less_equal : public binary_function <Type, Type, bool>
{
    bool operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator<=
template <>
struct less_equal<void>
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const
    -> decltype(std::forward<T>(Left) <= std::forward<U>(Right));
};
```

### <a name="parameters"></a>パラメーター

*型*、 *T*、 *U*\
指定または推論された型のオペランドを受け取る `operator<=` をサポートする任意の型。

*左側*\
以下演算の左オペランド。 非特殊テンプレートは、type *型* の左辺値参照引数を受け取ります。 特殊化されたテンプレートは、推論された型 *T* の左辺値および右辺値参照引数の完全転送を行います。

*そうです*\
以下演算の右オペランド。 非特殊テンプレートは、type *型* の左辺値参照引数を受け取ります。 特殊化されたテンプレートは、推論された型 *U* の左辺値および右辺値参照引数の完全転送を行います。

## <a name="return-value"></a>戻り値

`Left <= Right` の結果。 特殊化されたテンプレートは、結果の完全転送を行います。結果には `operator<=` によって返された型が含まれます。

## <a name="remarks"></a>解説

二項述語> は、型 `less_equal` < `Type` の要素値のセットの厳密弱順序を等価クラスに提供します。これは、この型が、順序付けされた標準の数学的要件を満たす場合に限ります。 任意のポインター型に対する特殊化によって、要素の完全な順序付けが生成されます。この場合、一意の値を持つすべての要素が、相互の値に基づいて並べ替えられます。

## <a name="example"></a>例

```cpp
// functional_less_equal.cpp
// compile with: /EHsc
#define _CRT_RAND_S
#include <stdlib.h>
#include <vector>
#include <algorithm>
#include <functional>
#include <cstdlib>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;
   vector <int>::reverse_iterator rIter1;
   unsigned int randomNumber;

   int i;
   for ( i = 0 ; i < 5 ; i++ )
   {
      if ( rand_s( &randomNumber ) == 0 )
      {
         // Convert the random number to be between 1 - 50000
         // This is done for readability purposes
         randomNumber = ( unsigned int) ((double)randomNumber /
            (double) UINT_MAX * 50000) + 1;

         v1.push_back( randomNumber );
      }
   }
   for ( i = 0 ; i < 3 ; i++ )
   {
      v1.push_back( 2836 );
   }

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in ascending order,
   // use the binary predicate less_equal<int>( )
   sort( v1.begin( ), v1.end( ), less_equal<int>( ) );
   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

```Output
Original vector v1 = (31247 37154 48755 15251 6205 2836 2836 2836)
Sorted vector v1 = (2836 2836 2836 6205 15251 31247 37154 48755)
```
