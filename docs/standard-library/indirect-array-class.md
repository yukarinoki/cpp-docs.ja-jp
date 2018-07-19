---
title: indirect_array クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- valarray/std::indirect_array
dev_langs:
- C++
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 676cc8ea493d113e9ef8a6f85108fdf3bad6ce5f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38959508"
---
# <a name="indirectarray-class"></a>indirect_array クラス

親 valarray のインデックスのサブセットを指定することにより定義されるサブセット配列間の演算を実行して valarray のサブセットとして機能するオブジェクトをサポートする、内部の補助テンプレート クラス。

## <a name="syntax"></a>構文

## <a name="remarks"></a>Remarks

クラスは、オブジェクトへの参照を格納するオブジェクトを表します`va`クラスの[valarray](../standard-library/valarray-class.md)**\<型 >**、オブジェクトと共に`xa`クラスの`valarray<size_t>`、選択する要素のシーケンスを説明する、`valarray<Type>`オブジェクト。

構築する、`indirect_array<Type>`オブジェクト形式の式を記述するだけ`va[xa]`です。 クラス indirect_array のメンバー関数に対して定義された対応する関数のシグネチャのように動作します`valarray<Type>`選択した要素のシーケンスだけが影響を受けることを除いて、します。

シーケンスから成る**xa** 。[サイズ](../standard-library/valarray-class.md#size)要素、場所要素`I`インデックスになります**xa**[ `I`] 内で`va`します。

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

## <a name="requirements"></a>必要条件

**ヘッダー:** \<valarray>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
