---
description: '詳細情報: コンパイラの警告 (レベル 1) C4142'
title: コンパイラの警告 (レベル 1) C4142
ms.date: 11/04/2016
f1_keywords:
- C4142
helpviewer_keywords:
- C4142
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
ms.openlocfilehash: d82403d79310d577cd45fe835cd486719ea0fdc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115730"
---
# <a name="compiler-warning-level-1-c4142"></a>コンパイラの警告 (レベル 1) C4142

型の問題のない再定義

型は、生成されたコードに影響を与えない方法で再定義されます。

次のような原因をチェックして問題を解決するには:

- 派生クラスのメンバー関数は、基底クラスの対応するメンバー関数とは異なる戻り値の型を持っています。

- コマンドで定義された型 **`typedef`** が、別の構文を使用して再定義されています。

次の例では、C4142 が生成されます。

```c
// C4142.c
// compile with: /W1
float X2;
X2 = 2.0 + 1.0;   // C4142

int main() {
   float X2;
   X2 = 2.0 + 1.0;   // OK
}
```
