---
title: コンパイラの警告 (レベル 1) C4822
ms.date: 11/04/2016
f1_keywords:
- C4822
helpviewer_keywords:
- C4822
ms.assetid: 0f231a30-2eb0-4722-aaa0-e2d19d3e7eea
ms.openlocfilehash: 59c42227c7e8be9bd31c37776d9724d23db61837
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174870"
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
