---
description: '詳細情報: コンパイラの警告 (レベル 1) C4822'
title: コンパイラの警告 (レベル 1) C4822
ms.date: 11/04/2016
f1_keywords:
- C4822
helpviewer_keywords:
- C4822
ms.assetid: 0f231a30-2eb0-4722-aaa0-e2d19d3e7eea
ms.openlocfilehash: 8e5fe62d70243da0121d58e553c500e5a079022a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198051"
---
# <a name="compiler-warning-level-1-c4822"></a>コンパイラの警告 (レベル 1) C4822

'member': ローカル クラスのメンバー関数は本体がありません

ローカル クラス メンバー関数が宣言されましたが、クラスに定義されていません。 ローカル クラス メンバー関数を使用するには、その関数をクラスに定義する必要があります。 クラスで宣言する関数をクラス外に定義することはできません。

ローカル クラス メンバー関数をクラス外に定義すると、エラーになります。

次の例では C4822 が生成されます。

```cpp
// C4822.cpp
// compile with: /W1
int main() {
   struct C {
      void func1(int);   // C4822
      // try the following line instead
      // void func1(int){}
  };
}
```
