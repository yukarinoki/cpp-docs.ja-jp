---
title: コンパイラの警告 (レベル 1) C4566 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4566
dev_langs:
- C++
helpviewer_keywords:
- C4566
ms.assetid: 65f40730-e86f-447c-b37b-16caadcfe311
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8044df3a37e54585f7f3b495b99314e258934f1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284226"
---
# <a name="compiler-warning-level-1-c4566"></a>コンパイラの警告 (レベル 1) C4566
ユニバーサル文字名 'char' で表される文字は、現在のコード ページ (ページ) で表されることはできません。  
  
 現在の ANSI コード ページにないすべての Unicode 文字を表現できます。  
  
 ナロー文字列 (1 バイト文字) は、ワイド文字列 (2 バイト文字) がありませんが、マルチバイト文字に変換されます。  
  
 次の例では、C4566 が生成されます。  
  
```  
// C4566.cpp  
// compile with: /W1  
int main() {  
   char c1 = '\u03a0';   // C4566  
   char c2 = '\u0642';   // C4566  
  
   wchar_t c3 = L'\u03a0';   // OK  
   wchar_t c4 = L'\u0642';   // OK  
}  
```