---
title: コンパイラ エラー C2274
ms.date: 11/04/2016
f1_keywords:
- C2274
helpviewer_keywords:
- C2274
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
ms.openlocfilehash: 5907664ba367d6e4005698e112d0a19f3a2a26e9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220380"
---
# <a name="compiler-error-c2274"></a>コンパイラ エラー C2274

' type ': '. ' 演算子の右側が正しくありません。

型は、メンバーアクセス (.) 演算子の右オペランドとして表示されます。

このエラーは、ユーザー定義型変換にアクセスしようとした場合に発生する可能性があります。 ピリオドとの間にキーワードを使用し **`operator`** `type` ます。

次の例では C2286 が生成されます。

```cpp
// C2274.cpp
struct MyClass {
   operator int() {
      return 0;
   }
};

int main() {
   MyClass ClassName;
   int i = ClassName.int();   // C2274
   int j = ClassName.operator int();   // OK
}
```
