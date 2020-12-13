---
description: 詳細については、「コンパイラエラー C2273」を参照してください。
title: コンパイラ エラー C2273
ms.date: 11/04/2016
f1_keywords:
- C2273
helpviewer_keywords:
- C2273
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
ms.openlocfilehash: 656b5477682ace779cd872b2233d911cfb67c0e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336262"
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
