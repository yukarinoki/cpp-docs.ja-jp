---
title: コンパイラの警告 (レベル 1) C4628 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4628
dev_langs:
- C++
helpviewer_keywords:
- C4628
ms.assetid: 20fdc6f8-5f6a-40cc-aff8-c7ccf3d8ec26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ffc84b8b7ec9934bb0dae951f5868d271ab62be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4628"></a>コンパイラの警告 (レベル 1) C4628
digraphs は -Ze でサポートされていません。 文字のシーケンス 'digraph' は 'char' の代替トークンとして解釈されません。  
  
 Digraphs はではサポートされていません[/Ze](../../build/reference/za-ze-disable-language-extensions.md)です。 この警告は、エラーの後に指定されます。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。  
  
 次の例では、C4628 が生成されます。  
  
```  
// C4628.cpp  
// compile with: /WX  
#pragma warning(default : 4628)  
int main()  
<%   // C4628 <% digraph for {  
}  
```