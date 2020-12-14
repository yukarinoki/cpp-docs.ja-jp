---
description: '詳細情報: コンパイラの警告 (レベル 1) C4545'
title: コンパイラの警告 (レベル 1) C4545
ms.date: 11/04/2016
f1_keywords:
- C4545
helpviewer_keywords:
- C4545
ms.assetid: 43f8f34f-ed46-4661-95c0-c588c577ff73
ms.openlocfilehash: 15a86a537d6fdde7d1bc9a70f5bbacda64b939df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310687"
---
# <a name="compiler-warning-level-1-c4545"></a>コンパイラの警告 (レベル 1) C4545

コンマ前の式は、引数リストのない関数として評価します。

コンパイラにより、正しくない形式のコンマ式が検出されました。

既定では、この警告はオフに設定されています。 詳細については、「 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。

次の例では、C4545 が生成されます。

```cpp
// C4545.cpp
// compile with: /W1
#pragma warning (default : 4545)

void f() { }

int main()
{
   *(&f), 10;   // C4545
   // try the following line instead
   // (*(&f))(), 10;
}
```
