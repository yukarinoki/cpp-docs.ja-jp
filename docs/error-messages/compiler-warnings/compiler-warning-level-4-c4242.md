---
title: コンパイラの警告 (レベル 4) C4242 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4242
dev_langs:
- C++
helpviewer_keywords:
- C4242
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: befe02b363c17a670d3b33632ffa50ed8a7cb1f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4242"></a>コンパイラの警告 (レベル 4) C4242
'identifier': 'type1' から 'type2' にデータ損失の可能性への変換  
  
 型が異なるです。 型変換すると、データが失われる可能性があります。 コンパイラでは、型変換を行います。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。  
  
 C4242 の詳細については、次を参照してください。[一般的なコンパイラ エラー](http://msdn.microsoft.com/library/windows/desktop/aa384160)です。  
  
 次の例では、C4242 が生成されます。  
  
```  
// C4242.cpp  
// compile with: /W4  
#pragma warning(4:4242)  
int func() {  
   return 0;  
}  
  
int main() {  
   char a;  
   a = func();   // C4242, return type and variable type do not match  
}  
```