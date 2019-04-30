---
title: コンパイラ エラー C2273
ms.date: 11/04/2016
f1_keywords:
- C2273
helpviewer_keywords:
- C2273
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
ms.openlocfilehash: f2ed5c49a9f8243fd5c9c302caf2876493c26bc3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388944"
---
# <a name="compiler-error-c2273"></a>コンパイラ エラー C2273

'type': '->' 演算子の右辺で使用できません

右側のオペランドとして、型が表示されます、`->`演算子。

このエラーは、ユーザー定義型の変換にアクセスしようとして発生することができます。 キーワードを使用して`operator`間]-> [および`type`します。

次の例では、C2273 が生成されます。

```
// C2273.cpp
struct MyClass {
   operator int() {
      return 0;
   }
};
int main() {
   MyClass * ClassPtr = new MyClass;
   int i = ClassPtr->int();   // C2273
   int j = ClassPtr-> operator int();   // OK
}
```