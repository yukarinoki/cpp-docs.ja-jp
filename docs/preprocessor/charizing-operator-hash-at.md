---
title: 演算子文字定数化 (#@) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#@'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9e0c0d140d937b7359ff3abf9c0eae145a89210
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="charizing-operator-"></a>文字定数化演算子 (#@)
**Microsoft 固有の仕様**  
  
 文字定数化演算子は、マクロの引数でのみ使用できます。 場合**#@** 仮パラメーターの前に、実際の引数の単一引用符で囲むし、マクロが展開されている場合は、文字として扱わマクロの定義でします。 例えば:  
  
```  
#define makechar(x)  #@x  
```  
  
 は、次のステートメント  
  
```  
a = makechar(b);  
```  
  
 を次のように展開します  
  
```  
a = 'b';  
```  
  
 単一引用符文字は charizing 演算子では使用できません。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)