---
title: コンパイラ エラー C2017 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2017
dev_langs:
- C++
helpviewer_keywords:
- C2017
ms.assetid: 1083eed9-9906-4a97-883c-54e52d7e82cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 019c166b1945bee26c11115000fae3c2f3f99968
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2017"></a>コンパイラ エラー C2017
無効なエスケープ シーケンス  
  
 \T などのエスケープ シーケンスが文字または文字列の外部で出現定数。  
  
 次の例では、C2017 が生成されます。  
  
```  
// C2017.cpp  
int main() {  
   char test1='a'\n;   // C2017  
   char test2='a\n';   // ok  
}  
```  
  
 C2017 は、エスケープ シーケンスを含む文字列を文字列化演算子を使用する場合に発生することができます。  
  
 次の例では、C2017 が生成されます。  
  
```  
// C2017b.cpp  
#define TestDfn(x) AfxMessageBox(#x)  
TestDfn(CString("\\") + CString(".h\"\n\n"));   // C2017  
```