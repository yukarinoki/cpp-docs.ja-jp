---
title: コンパイラ エラー C2274
ms.date: 11/04/2016
f1_keywords:
- C2274
helpviewer_keywords:
- C2274
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
ms.openlocfilehash: f2fcb75098f18ad113ba68959035b37d9cddd6e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388869"
---
# <a name="compiler-error-c2274"></a>コンパイラ エラー C2274

'type': の右側にあるとして無効な '.' 演算子

メンバー アクセス (.) 演算子の右側のオペランドとして、型が表示されます。

このエラーは、ユーザー定義型の変換にアクセスしようとして発生することができます。 キーワードを使用して`operator`期間の間および`type`します。

次の例では C2286 が生成されます。

```
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