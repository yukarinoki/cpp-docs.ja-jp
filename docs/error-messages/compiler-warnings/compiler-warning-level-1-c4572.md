---
title: コンパイラの警告 (レベル 1) C4572 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4572
dev_langs:
- C++
helpviewer_keywords:
- C4572
ms.assetid: 482dee5a-29bd-4fc3-b769-9dfd4cd2a964
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec0c0068a3da1033162f90330876d74d62878178
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33280469"
---
# <a name="compiler-warning-level-1-c4572"></a>コンパイラの警告 (レベル 1) C4572
[ParamArray] 属性は/clr、'...' を使用して代わりに  
  
 可変個引数リストを指定するため、古いスタイルが使用されました。 CLR をコンパイルするときは、代わりにある省略記号構文を使用して<xref:System.ParamArrayAttribute>です。 詳細については、次を参照してください[可変個引数リスト (...)。(C + + CLI)](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md).  
  
## <a name="example"></a>例  
 次の例では、C4572 を生成します。  
  
```  
// C4572.cpp  
// compile with: /clr /W1  
void Func([System::ParamArray] array<int> ^);   // C4572  
void Func2(... array<int> ^){}   // OK  
  
int main() {  
   Func2(1, 2, 3);  
}  
```