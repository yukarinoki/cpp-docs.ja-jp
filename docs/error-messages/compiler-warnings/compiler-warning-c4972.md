---
title: コンパイラの警告 C4972 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4972
dev_langs:
- C++
helpviewer_keywords:
- C4972
ms.assetid: d18e8e65-b2ef-4d75-a207-fbd0c17c9060
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf5337a60781c6fb39281f051657ea7ebd9371fa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-c4972"></a>コンパイラの警告 C4972
アンボックス操作の結果を左辺の値として扱う、または直接変更することは検証可能ではありません  
  
 ハンドルの値型への逆参照 (ボックス化解除) およびその後の割り当てを検証できません。  
  
 詳細については、次を参照してください。[ボックス化](../../windows/boxing-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では C4972 警告が生成されます。  
  
```  
// C4972.cpp  
// compile with: /clr:safe  
using namespace System;  
ref struct R {  
   int ^ p;   // a value type  
};  
  
int main() {  
   R ^ r = gcnew R;  
   *(r->p) = 10;   // C4972  
  
   // OK  
   r->p = 10;  
   Console::WriteLine( r->p );  
   Console::WriteLine( *(r->p) );  
}  
```