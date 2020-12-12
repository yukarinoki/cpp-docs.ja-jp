---
description: 詳細については、「コンパイラエラー C2274」を参照してください。
title: コンパイラ エラー C2274
ms.date: 11/04/2016
f1_keywords:
- C2274
helpviewer_keywords:
- C2274
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
ms.openlocfilehash: 31b9d63b9cf87114ce2d1d79f1f38fff97d4ebbb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268354"
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
