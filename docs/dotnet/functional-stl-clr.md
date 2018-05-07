---
title: 機能 (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/functional>
dev_langs:
- C++
helpviewer_keywords:
- <functional> header [STL/CLR]
- <cliext/functional> header [STL/CLR]
- functional functions [STL/CLR]
ms.assetid: 88738b8c-5d37-4375-970e-a4442bf5efde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 38bfbe025c92aa54956a165367b367cecc6160b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="functional-stlclr"></a>functional (STL/CLR)
STL/CLR ヘッダーを含める`<cliext/functional>`を定義する、テンプレート クラスと関連するテンプレート デリゲート、および関数の数。  
  
## <a name="syntax"></a>構文  
  
```  
#include <functional>  
```  
  
## <a name="declarations"></a>宣言  
  
|Delegate|説明|  
|--------------|-----------------|  
|[binary_delegate (STL/CLR)](../dotnet/binary-delegate-stl-clr.md)|2 つの引数のデリゲート。|  
|[binary_delegate_noreturn (STL/CLR)](../dotnet/binary-delegate-noreturn-stl-clr.md)|2 つの引数のデリゲートを返す`void`です。|  
|[unary_delegate (STL/CLR)](../dotnet/unary-delegate-stl-clr.md)|引数が 1 つのデリゲート。|  
|[unary_delegate_noreturn (STL/CLR)](../dotnet/unary-delegate-noreturn-stl-clr.md)|引数が 1 つのデリゲートを返す`void`です。|  
  
|クラス|説明|  
|-----------|-----------------|  
|[binary_negate (STL/CLR)](../dotnet/binary-negate-stl-clr.md)|2 つの引数ファンクタを否定するファンクタ。|  
|[binder1st (STL/CLR)](../dotnet/binder1st-stl-clr.md)|2 つの引数ファンクタを最初の引数をバインドするファンクタ。|  
|[binder2nd (STL/CLR)](../dotnet/binder2nd-stl-clr.md)|2 つの引数ファンクタを 2 番目の引数をバインドするファンクタ。|  
|[divides (STL/CLR)](../dotnet/divides-stl-clr.md)|ファンクタを分割します。|  
|[equal_to (STL/CLR)](../dotnet/equal-to-stl-clr.md)|比較ファンクタ。|  
|[greater (STL/CLR)](../dotnet/greater-stl-clr.md)|大きい比較ファンクタ。|  
|[greater_equal (STL/CLR)](../dotnet/greater-equal-stl-clr.md)|大きいまたは等しい比較ファンクタ。|  
|[less (STL/CLR)](../dotnet/less-stl-clr.md)|小さい比較ファンクタ。|  
|[less_equal (STL/CLR)](../dotnet/less-equal-stl-clr.md)|小さいか等しい比較ファンクタ。|  
|[logical_and (STL/CLR)](../dotnet/logical-and-stl-clr.md)|論理 AND ファンクタ。|  
|[logical_not (STL/CLR)](../dotnet/logical-not-stl-clr.md)|論理ファンクタではありません。|  
|[logical_or (STL/CLR)](../dotnet/logical-or-stl-clr.md)|論理 OR ファンクタ。|  
|[minus (STL/CLR)](../dotnet/minus-stl-clr.md)|ファンクタを減算します。|  
|[modulus (STL/CLR)](../dotnet/modulus-stl-clr.md)|剰余ファンクタ。|  
|[multiplies (STL/CLR)](../dotnet/multiplies-stl-clr.md)|ファンクタを乗算します。|  
|[negate (STL/CLR)](../dotnet/negate-stl-clr.md)|否定その引数を返すファンクタ。|  
|[not_equal_to (STL/CLR)](../dotnet/not-equal-to-stl-clr.md)|等しくない比較ファンクタ。|  
|[plus (STL/CLR)](../dotnet/plus-stl-clr.md)|ファンクタを追加します。|  
|[unary_negate (STL/CLR)](../dotnet/unary-negate-stl-clr.md)|引数が 1 つファンクタを否定するファンクタ。|  
  
|関数|説明|  
|--------------|-----------------|  
|[bind1st (STL/CLR)](../dotnet/bind1st-stl-clr.md)|引数とファンクタ binder1st を生成します。|  
|[bind2nd (STL/CLR)](../dotnet/bind2nd-stl-clr.md)|引数とファンクタ binder2nd を生成します。|  
|[not1 (STL/CLR)](../dotnet/not1-stl-clr.md)|ファンクタを unary_negate を生成します。|  
|[not1 (STL/CLR)](../dotnet/not1-stl-clr.md)|ファンクタを binary_negate を生成します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/機能 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [STL/CLR ライブラリ リファレンス](../dotnet/stl-clr-library-reference.md)