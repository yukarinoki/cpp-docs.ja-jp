---
title: コンパイラの警告 (レベル 1) C4080 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4080
dev_langs:
- C++
helpviewer_keywords:
- C4080
ms.assetid: 964fb3f4-b9fd-450b-aa23-35cece126172
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ae964b4ae4b67cbcbd85dac56eddac0c03370f6d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4080"></a>コンパイラの警告 (レベル 1) C4080
セグメント名の識別子が必要です。'symbol' が見つかりました。  
  
 [#pragma alloc_text](../../preprocessor/alloc-text.md) 内のセグメントの名前は、文字列または識別子である必要があります。 有効な識別子が見つからない場合、コンパイラはプラグマを無視します。  
  
 次の例では C4080 が生成されます。  
  
```  
// C4080.cpp  
// compile with: /W1  
extern "C" void func(void);  
  
#pragma alloc_text()   // C4080  
  
// try this line to resolve the warning  
// #pragma alloc_text("mysection", func)  
  
int main() {  
}  
  
void func(void) {  
}  
```