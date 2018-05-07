---
title: コンパイラの警告 (レベル 1) C4091 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4091
dev_langs:
- C++
helpviewer_keywords:
- C4091
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 79a0a74ad2cf6471679fd776f296d465ee8dd29c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4091"></a>コンパイラの警告 (レベル 1) C4091
'keyword': 'type' の左側で変数が宣言されていない場合は無視されます  
  
 ここで、変数を宣言するためのもので、ユーザーが可能性がありますが、コンパイラは、変数を宣言することができませんでした状況が検出されました。  
  
## <a name="example"></a>例  
 A`__declspec`その型の変数にユーザー定義型の宣言の冒頭にある属性が適用されます。 C4091 では、変数が宣言されていないことを示します。 次の例では、C4091 を生成します。  
  
```  
// C4091.cpp  
// compile with: /W1 /c  
__declspec(dllimport) class X {}; // C4091  
  
// __declspec attribute applies to varX  
__declspec(dllimport) class X2 {} varX;  
  
// __declspec attribute after the class or struct keyword   
// applies to user defined type  
class __declspec(dllimport) X3 {};  
```  
  
## <a name="example"></a>例  
 識別子が typedef である場合は、その変数名こともできません。 次の例では、C4091 を生成します。  
  
```  
// C4091_b.cpp  
// compile with: /c /W1 /WX  
#define LIST 4  
typedef struct _LIST {} LIST;   // C4091  
```