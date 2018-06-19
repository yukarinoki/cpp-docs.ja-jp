---
title: 数値 (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/numeric>
dev_langs:
- C++
helpviewer_keywords:
- numeric functions [STL/CLR]
- <cliext/numeric> header [STL/CLR]
- <numeric> header [STL/CLR]
ms.assetid: 1dc4d9a3-e734-459c-9678-5d9be0ef4c79
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8d02423b2f8a2573fb4a90fd6f348a8e012dc91b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33139527"
---
# <a name="numeric-stlclr"></a>数値 (STL/CLR)
数値処理のために用意されているアルゴリズムを実行するコンテナーのテンプレート関数を定義します。  
  
## <a name="syntax"></a>構文  
  
```  
#include <cliext/numeric>  
```  
  
## <a name="functions"></a>関数  
  
|関数|説明|  
|--------------|-----------------|  
|[accumulate (STL/CLR)](../dotnet/accumulate-stl-clr.md)|連続する部分和を計算することで、いくつかの初期値を含め、指定された範囲のすべての要素の合計を計算します。または、指定された二項演算を使用して取得した、合計以外の連続する部分的な結果を計算します。|  
|[adjacent_difference (STL/CLR)](../dotnet/adjacent-difference-stl-clr.md)|入力範囲内の各要素とその先行要素との連続する差分を計算し、結果をターゲット範囲に出力するか、または差分演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。|  
|[inner_product (STL/CLR)](../dotnet/inner-product-stl-clr.md)|2 つの範囲の要素ごとの積の合計を計算し、それを指定された初期値に加算するか、または和や積の二項演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。|  
|[partial_sum (STL/CLR)](../dotnet/partial-sum-stl-clr.md)|一連の最初の要素から入力範囲内の合計を計算、`i`番目の要素でこのような各合計の結果を格納および`i`番目の要素をターゲット範囲の汎用化されたプロシージャの結果を計算または場所合計演算指定した別の二項演算に置き換えられます。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/numeric >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [STL/CLR ライブラリ リファレンス](../dotnet/stl-clr-library-reference.md)