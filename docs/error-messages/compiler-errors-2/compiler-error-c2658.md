---
title: コンパイラ エラー C2658 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2658
dev_langs:
- C++
helpviewer_keywords:
- C2658
ms.assetid: 638368e8-7893-4a14-abec-13c768a9543a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8e071e070b259dee7293d607d292a51ee608b71c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33234738"
---
# <a name="compiler-error-c2658"></a>コンパイラ エラー C2658
'member': 匿名構造体/共用体での再定義  
  
 2 つの匿名構造体または共用体には、さまざまな種類が、同じ識別子を持つメンバーの宣言が含まれています。 [/Za](../../build/reference/za-ze-disable-language-extensions.md)、同じ識別子と型を持つメンバーに対してもこのエラーが表示されます。  
  
 次の例では、C2658 が生成されます。  
  
```  
// C2658.cpp  
// compile with: /c  
struct X {  
   union { // can be struct too  
      int i;  
   };  
   union {  
      int i;   // Under /Za, C2658  
      // int i not needed here because it is defined in the first union  
   };  
};  
  
struct Z {  
   union {  
      char *i;  
   };  
  
   union {  
      void *i;   // C2658 redefinition of 'i'  
      // try the following line instead  
      // void *ii;  
   };  
};  
```