---
title: コンパイラの警告 (レベル 4) C4714 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4714
dev_langs:
- C++
helpviewer_keywords:
- C4714
ms.assetid: 22c7fd0c-899d-4e9b-95f3-725b2c49fb46
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f0f327e7ffc5d2fe00abe3c0845af10a846243bf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33295419"
---
# <a name="compiler-warning-level-4-c4714"></a>コンパイラの警告 (レベル 4) C4714
関数 'function' がマークされています _ _forceinline としてインライン関数  
  
 指定された関数がインライン展開を選択されましたが、コンパイラが実行されなかった、インライン展開されます。  
  
 `__forceinline`よりコンパイラに示す値がより強力なの`__inline`、インライン展開も、コンパイラの裁量により、実行なしヒューリスティックを使用して判断の利点が、インライン展開この関数。  
  
 場合によっては、コンパイラはインライン展開されない特定の関数機械的上の理由からします。 たとえば、コンパイラは、インライン展開されないを行います。  
  
-   SEH と C++ EH の両方の混在が失われる場合の関数。  
  
-   コピーの一部の関数は、-GX/がの場合、値によって渡されるオブジェクトを構築します。  
  
-   -GX/がの場合、値によって、アンワインド可能オブジェクトを返す関数。  
  
-   インライン アセンブリ Og Ox/O1//o2 なしでコンパイルするときに機能します。  
  
-   可変個引数リストは機能します。  
  
-   持つ関数、**再試行**(C++ 例外処理) のステートメント。  
  
 次の例では、C4714 が生成されます。  
  
```  
// C4714.cpp  
// compile with: /Ob1 /GX /W4  
__forceinline void func1()  
{  
   try  
   {  
   }  
   catch (...)  
   {  
   }  
}  
  
void func2()  
{  
   func1();   // C4714  
}  
  
int main()  
{  
}  
```