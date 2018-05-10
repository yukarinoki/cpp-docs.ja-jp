---
title: コンパイラの警告 (レベル 1) C4744 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4744
dev_langs:
- C++
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a45207f85575c8047f673b415ce802dbac24318
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4744"></a>コンパイラの警告 (レベル 1) C4744
'var' が 'file1' および 'file2' で別の種類: 'type1' および 'type2'  
  
 参照または 2 つのファイルで定義された外部変数にそれらのファイルのさまざまな種類です。  を解決するには、同じ種類の定義を作成するか、ファイルの 1 つの変数名を変更します。  
  
 /Gl ファイルはコンパイル時にだけ C4744 が生成されます。  詳細については、「[/GL (プログラム全体の最適化)](../../build/reference/gl-whole-program-optimization.md)」を参照してください。  
  
> [!NOTE]
>  C++ では、変数名は、型情報で装飾されているために、C4744 は通常 C (C++ ではなく) ファイルで発生します。  (以下) のサンプルでは、C++ としてコンパイルが、リンカー エラー lnk2019 エラーが表示されます。  
  
## <a name="example"></a>例  
 このサンプルには、最初の定義が含まれています。  
  
```  
// C4744.c  
// compile with: /c /GL  
int global;  
```  
  
## <a name="example"></a>例  
 次の例では、C4744 を生成します。  
  
```  
// C4744b.c  
// compile with: C4744.c /GL /W1  
// C4744 expected  
#include <stdio.h>  
  
extern unsigned global;  
  
main()   
{  
    printf_s("%d\n", global);  
}  
```