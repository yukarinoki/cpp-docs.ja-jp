---
title: コンパイラの警告 (レベル 1) C4142 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4142
dev_langs:
- C++
helpviewer_keywords:
- C4142
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c87b7689cf11ab28c1a6377ff85e1594fd1b5fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284434"
---
# <a name="compiler-warning-level-1-c4142"></a>コンパイラの警告 (レベル 1) C4142
型の害のない再定義されています  
  
 型は、生成されたコードに影響が方法で再定義されていません。  
  
 次のような原因をチェックして問題を解決するには:  
  
-   派生クラスのメンバー関数では、基本クラスの対応するメンバー関数から異なる戻り値の型があります。  
  
-   定義されている型、`typedef`別の構文を使用して、コマンドが再定義します。  
  
 次の例では、C4142 が生成されます。  
  
```  
// C4142.c  
// compile with: /W1  
float X2;  
X2 = 2.0 + 1.0;   // C4142  
  
int main() {  
   float X2;  
   X2 = 2.0 + 1.0;   // OK  
}  
```