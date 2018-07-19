---
title: if ステートメント (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- else
- if
dev_langs:
- C++
helpviewer_keywords:
- if keyword [C]
- else clauses
- else keyword [C]
- if keyword [C], if statement syntax
- nested statements
ms.assetid: d7fc16a0-fdbc-4f39-b596-76e1ca4ad4a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f307860ce71e8c9fc74b2ab97e88ced02e08332f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32387051"
---
# <a name="if-statement-c"></a>if ステートメント (C)
**if** ステートメントは、条件分岐を制御します。 **if** ステートメントの本体は、式の値が 0 でないの場合に実行されます。 **if** ステートメントの構文には 2 とおりの形式があります。  
  
## <a name="syntax"></a>構文  
 *selection-statement*:  
 **if (**  *expression*  **)**  *statement*  
  
 **if (**  *expression*  **)**  *statement*  **else**  *statement*  
  
 **if** ステートメントの両方の形式で、構造体以外のすべての値を持つことができる式が、すべての副作用を含めて評価されます。  
  
 最初の構文では、*expression* が true (0 以外) の場合、*statement* が実行されます。 *expression* が false の場合、*statement* は無視されます。 **else** を使用する 2 番目の構文形式では、*expression* が false の場合、2 番目の *statement* が実行されます。 どちらの形式でも、いずれかのステートメントに **break**、**continue**、または `goto` が含まれていない場合は、制御が **if** ステートメントからプログラムの次のステートメントに移ります。  
  
 **if** ステートメントの例を次に示します。  
  
```  
if ( i > 0 )  
    y = x / i;  
else   
{  
    x = i;  
    y = f( x );  
}  
```  
  
 この例では、ステートメント本体 `y = x/i;` は、`i` が 0 を超える場合に実行されます。 `i` が 0 以下の場合、`i` が `x` に割り当てられ、`f( x )` が `y` に割り当てられます。 **if** 句を形成するステートメントはセミコロンで終わることに注意してください。  
  
 **if** ステートメントと **else** 句を入れ子にする場合は、意図がはっきりわかるように、中かっこを使用してステートメントと句を複合ステートメントにグループ化します。 中かっこがない場合、コンパイラは各 **else** を **if** のない最も近い **else** と関連付けることで、あいまいさを解消します。  
  
```  
if ( i > 0 )           /* Without braces */  
    if ( j > i )  
        x = j;  
    else  
        x = i;  
```  
  
 **else** 句は、この例の内側の **if** ステートメントに関連付けられます。 `i` が 0 以下の場合、`x` に値は割り当てられません。  
  
```  
if ( i > 0 )   
{                      /* With braces */  
    if ( j > i )  
        x = j;  
}  
else  
    x = i;  
```  
  
 この例の内側の **if** ステートメントを囲んでいる中かっこにより、**else** 句は外側の **if** ステートメントの一部になります。 `i` が 0 以下の場合、`i` が `x` に割り当てられます。  
  
## <a name="see-also"></a>参照  
 [if-else ステートメント (C++)](../cpp/if-else-statement-cpp.md)