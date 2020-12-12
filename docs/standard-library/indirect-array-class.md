---
description: '詳細情報: indirect_array クラス'
title: indirect_array クラス
ms.date: 11/04/2016
f1_keywords:
- valarray/std::indirect_array
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
ms.openlocfilehash: 47c9a0e604fd9873d7705f70624e67d9b3a22a7a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324042"
---
# <a name="indirect_array-class"></a>indirect_array クラス

親 valarray のインデックスのサブセットを指定することによって定義されたサブセット配列間の演算を提供することによって、valarray のサブセットであるオブジェクトをサポートする、内部の補助クラステンプレート。

## <a name="syntax"></a>構文

## <a name="remarks"></a>解説

クラスは、クラス valarray のオブジェクトへの参照を、 `va` [](../standard-library/valarray-class.md) **\<Type>** `xa` `valarray<size_t>` オブジェクトから選択する要素のシーケンスを記述するクラスのオブジェクトと共に格納するオブジェクトを表し `valarray<Type>` ます。

オブジェクトを構築するには、 `indirect_array<Type>` フォームの式を記述する必要が `va[xa]` あります。 クラス indirect_array のメンバー関数は、に対して定義されている対応する関数シグネチャと同様に動作し `valarray<Type>` ますが、選択された要素のシーケンスのみが影響を受けます。

シーケンスは xa で構成さ **れます。** 要素の [サイズ](../standard-library/valarray-class.md#size)を変更 `I` します。要素は内のインデックス **xa**[] になり `I` `va` ます。

## <a name="example"></a>例:

```cpp
// indirect_array.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      va [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 2 )
      va [ i ] =  -1;

   cout << "The initial operand valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   // Select 2nd, 4th & 6th elements
   // and assign a value of 10 to them
   valarray<size_t> indx ( 3 );
   indx [0] = 2;
   indx [1] = 4;
   indx [2] = 6;
   va[indx] = 10;

   cout << "The modified operand valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;
}
```

### <a name="output"></a>出力

```cpp
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 10 -1 10 -1 10 -1 8 -1).
```

## <a name="requirements"></a>要件

**ヘッダー:**\<valarray>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
