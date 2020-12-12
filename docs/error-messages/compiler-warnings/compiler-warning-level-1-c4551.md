---
description: '詳細情報: コンパイラの警告 (レベル 1) C4551'
title: コンパイラの警告 (レベル 1) C4551
ms.date: 11/04/2016
f1_keywords:
- C4551
helpviewer_keywords:
- C4551
ms.assetid: 458b59bd-e2d7-425f-9ba6-268ff200424f
ms.openlocfilehash: 74a0f773f304c4ed4ce2da53a393a858f316c80b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265949"
---
# <a name="compiler-warning-level-1-c4551"></a>コンパイラの警告 (レベル 1) C4551

関数呼び出しに引数リストがありません

関数がパラメーターを受け取らない場合でも、関数の呼び出しでは、関数名の後に開閉かっこを含める必要があります。

次の例では、C4551 が生成されます。

```cpp
// C4551.cpp
// compile with: /W1
void function1() {
}

int main() {
   function1;   // C4551
   function1();   // OK
}
```
