---
title: コンパイラ エラー C2273
ms.date: 11/04/2016
f1_keywords:
- C2273
helpviewer_keywords:
- C2273
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
ms.openlocfilehash: f5780c299eb4da03ece3611ee55062ee7ebcdaae
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212788"
---
# <a name="compiler-error-c2273"></a>コンパイラ エラー C2273

' type ': '-> ' 演算子の右辺が正しくありません。

型は、演算子の右オペランドとして表示され `->` ます。

このエラーは、ユーザー定義型変換にアクセスしようとした場合に発生する可能性があります。 -> との間にキーワードを使用し **`operator`** `type` ます。

次の例では、C2273 が生成されます。

```cpp
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
