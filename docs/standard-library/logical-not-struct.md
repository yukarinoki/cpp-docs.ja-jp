---
description: '詳細については、次を参照してください: logical_not 構造体'
title: logical_not 構造体
ms.date: 11/04/2016
f1_keywords:
- functional/std::logical_not
helpviewer_keywords:
- logical_not class
- logical_not struct
ms.assetid: 892db678-31da-4540-974b-17b05efc0849
ms.openlocfilehash: dc89a5a764d9f3182609b47c5f05eb8b3e167cec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277688"
---
# <a name="logical_not-struct"></a>logical_not 構造体

引数に対して論理否定演算 (`operator!`) を実行する定義済みの関数オブジェクト。

## <a name="syntax"></a>構文

```
template <class Type = void>
struct logical_not : public unary_function<Type, bool>
{
    bool operator()(const Type& Left) const;
};

// specialized transparent functor for operator!
template <>
struct logical_not<void>
{
  template <class Type>
  auto operator()(Type&& Left) const`
     -> decltype(!std::forward<Type>(Left));
};
```

### <a name="parameters"></a>パラメーター

*各種*\
指定または推論された型のオペランドを受け取る `operator!` をサポートする任意の型。

*左側*\
論理否定演算のオペランド。 非特殊テンプレートは、type *型* の左辺値参照引数を受け取ります。 特殊化されたテンプレートは、推論された型の *型* の左辺値および右辺値参照引数の完全転送を行います。

## <a name="return-value"></a>戻り値

`!Left` の結果。 特殊化されたテンプレートは、結果の完全転送を行います。結果には `operator!` によって返された型が含まれます。

## <a name="example"></a>例

```cpp
// functional_logical_not.cpp
// compile with: /EHsc
#include <deque>
#include <algorithm>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;
   deque<bool> d1, d2 ( 7 );
   deque<bool>::iterator iter1, iter2;

   int i;
   for ( i = 0 ; i < 7 ; i++ )
   {
      d1.push_back((bool)((i % 2) != 0));
   }

   cout << boolalpha;    // boolalpha I/O flag on

   cout << "Original deque:\n d1 = ( " ;
   for ( iter1 = d1.begin( ) ; iter1 != d1.end( ) ; iter1++ )
      cout << *iter1 << " ";
   cout << ")" << endl;

   // To flip all the truth values of the elements,
   // use the logical_not function object
   transform( d1.begin( ), d1.end( ), d2.begin( ),logical_not<bool>( ) );
   cout << "The deque with its values negated is:\n d2 = ( " ;
   for ( iter2 = d2.begin( ) ; iter2 != d2.end( ) ; iter2++ )
      cout << *iter2 << " ";
   cout << ")" << endl;
}
```

```Output
Original deque:
d1 = ( false true false true false true false )
The deque with its values negated is:
d2 = ( true false true false true false true )
```
