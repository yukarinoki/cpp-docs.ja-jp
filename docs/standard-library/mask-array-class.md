---
title: mask_array クラス
ms.date: 11/04/2016
f1_keywords:
- valarray/std::mask_array
helpviewer_keywords:
- mask_array class
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
ms.openlocfilehash: 108c942bef33e44b515d46e953c9d99274e3ce8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475820"
---
# <a name="maskarray-class"></a>mask_array クラス

サブセット配列間の演算を提供することにより、ブール式で指定された親 valarray のサブセットとして機能するオブジェクトをサポートする、内部の補助テンプレート クラス。

## <a name="syntax"></a>構文

## <a name="remarks"></a>Remarks

クラスは、オブジェクトへの参照を格納するオブジェクトを表します`va`クラスの[valarray](../standard-library/valarray-class.md)**\<型 >**、オブジェクトと共に`ba`クラスの[valarray\<bool >](../standard-library/valarray-bool-class.md)から選択する要素のシーケンスを説明する、`valarray<Type>`オブジェクト。

構築する、`mask_array<Type>`オブジェクト形式の式を記述するだけ[va&#91;ba&#93;](../standard-library/valarray-class.md#op_at)します。 クラス mask_array のメンバー関数に対して定義された対応する関数のシグネチャのように動作します`valarray<Type>`選択した要素のシーケンスだけが影響を受けることを除いて、します。

シーケンスは最大で成る`ba.size`要素。 要素 *J* は **ba**[ *J*] が true である場合にのみ含まれます。 したがって、シーケンス内で true の要素がある多くの要素がある`ba`します。 場合`I`最下位の true 要素でのインデックスは、 `ba`、し**va**[ `I`] は選択した順序で要素 0 です。

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

## <a name="requirements"></a>必要条件

**ヘッダー:** \<valarray>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
