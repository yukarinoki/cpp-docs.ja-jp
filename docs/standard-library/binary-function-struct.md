---
title: binary_function 構造体 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- functional/std::binary
dev_langs:
- C++
helpviewer_keywords:
- binary_function class
ms.assetid: 79b6d53d-644c-4add-b0ba-3a5f40f69c60
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5bb54ae332dac556333516c5e50129b9ba43ce07
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845077"
---
# <a name="binaryfunction-struct"></a>binary_function 構造体

二項関数オブジェクトを提供する派生クラスによって継承される可能性がある型を定義する空の基底構造体。

## <a name="syntax"></a>構文

```cpp
struct binary_function {
   typedef Arg1 first_argument_type;
   typedef Arg2 second_argument_type;
   typedef Result result_type;
   };
```

## <a name="remarks"></a>コメント

このテンプレート構造体は、フォームのメンバー関数を定義するクラスの基本として機能します。

**result_type operator()**( **constfirst_argument_type&**,

**const second_argument_type&** ) **const**

このような二項関数はすべて、最初の引数の型として **first_argument_type** を参照し、2 つ目の引数の型として **second_argument_type** を参照し、戻り値の型として ***result_type*** を参照できます。

## <a name="example"></a>例

```cpp
// functional_binary_function.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

template <class Type> class average:
binary_function<Type, Type, Type>
{
public:
   result_type operator( ) ( first_argument_type a,
                 second_argument_type b )
   {
      return (result_type) ( ( a + b ) / 2 );
   }
};

int main( )
{
   vector <double> v1, v2, v3 ( 6 );
   vector <double>::iterator Iter1, Iter2, Iter3;

   for ( int i = 1 ; i <= 6 ; i++ )
      v1.push_back( 11.0 / i );

   for ( int j = 0 ; j <= 5 ; j++ )
      v2.push_back( -2.0 * j );

   cout << "The vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "The vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // Finding the element-wise averages of the elements of v1 & v2
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),
      average<double>( ) );

   cout << "The element-wise averages are: ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;
}
\* Output:
The vector v1 = ( 11 5.5 3.66667 2.75 2.2 1.83333 )
The vector v2 = ( -0 -2 -4 -6 -8 -10 )
The element-wise averages are: ( 5.5 1.75 -0.166667 -1.625 -2.9 -4.08333 )
*\

```

## <a name="requirements"></a>要件

**ヘッダー:** \<functional>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
