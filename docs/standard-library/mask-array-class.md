---
description: '詳細情報: mask_array クラス'
title: mask_array クラス
ms.date: 11/04/2016
f1_keywords:
- valarray/std::mask_array
helpviewer_keywords:
- mask_array class
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
ms.openlocfilehash: d3eb105c7779ff54ddbec3d68a518dc74d089903
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149358"
---
# <a name="mask_array-class"></a>mask_array クラス

サブセット配列間の演算を提供することにより、ブール式で指定された親 valarrays のサブセットであるオブジェクトをサポートする、内部の補助クラステンプレート。

## <a name="syntax"></a>構文

## <a name="remarks"></a>解説

クラスは、クラス valarray のオブジェクトへの参照を、 `va` [](../standard-library/valarray-class.md) **\<Type>** `ba` オブジェクトから選択する要素のシーケンスを記述する [valarray \<bool>](../standard-library/valarray-bool-class.md)クラスのオブジェクトと共に格納するオブジェクトを表し `valarray<Type>` ます。

オブジェクトを構築するには、 `mask_array<Type>` [va&#91;ba&#93;](../standard-library/valarray-class.md#op_at)の形式の式を記述する必要があります。 クラス mask_array のメンバー関数は、に対して定義されている対応する関数シグネチャと同様に動作し `valarray<Type>` ますが、選択された要素のシーケンスのみが影響を受けます。

シーケンスは、ほとんどの要素で構成さ `ba.size` れます。 要素 *J* は、 **ba**[ *j*] が true の場合にのみ含まれます。 したがって、シーケンス内には、に true 要素があるのと同じ数の要素があり `ba` ます。 `I`がの最下位の true 要素のインデックスである場合 `ba` 、 **va**[ `I` ] は選択されたシーケンスの要素0です。

## <a name="example"></a>例

```cpp
// mask_array.cpp
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

   // Use masked subsets to assign a value of 10
   // to all elements grrater than 3 in value
   va [va > 3 ] = 10;
   cout << "The modified operand valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;
}
```

### <a name="output"></a>出力

```Output
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 2 -1 10 -1 10 -1 10 -1).
```

## <a name="requirements"></a>要件

**ヘッダー:**\<valarray>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
