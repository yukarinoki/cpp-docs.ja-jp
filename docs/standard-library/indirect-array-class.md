---
title: indirect_array クラス
ms.date: 11/04/2016
f1_keywords:
- valarray/std::indirect_array
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
ms.openlocfilehash: 5db5f2ce60038267b70ae8e77d9dd929d972af6a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456338"
---
# <a name="indirectarray-class"></a>indirect_array クラス

親 valarray のインデックスのサブセットを指定することにより定義されるサブセット配列間の演算を実行して valarray のサブセットとして機能するオブジェクトをサポートする、内部の補助テンプレート クラス。

## <a name="syntax"></a>構文

## <a name="remarks"></a>Remarks

クラス`va`は、クラス[valarray](../standard-library/valarray-class.md) **\<> 型**のオブジェクトへの参照と、クラス`valarray<size_t>`のオブジェクト`xa`への参照を格納するオブジェクトを記述します。このオブジェクトは、選択する要素のシーケンスを記述します。`valarray<Type>`オブジェクト。

オブジェクトを`indirect_array<Type>`構築するには、フォーム`va[xa]`の式を記述する必要があります。 クラス indirect_array のメンバー関数は、に対し`valarray<Type>`て定義されている対応する関数シグネチャのように動作します。ただし、選択した要素のシーケンスのみが影響を受けます。

シーケンスは xa で構成さ**れます。** 要素の[サイズ](../standard-library/valarray-class.md#size)を変更`I`します。要素は`I`内`va`のインデックス**xa**[] になります。

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

### <a name="output"></a>Output

```cpp
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 10 -1 10 -1 10 -1 8 -1).
```

## <a name="requirements"></a>必要条件

**ヘッダー:** \<valarray>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
