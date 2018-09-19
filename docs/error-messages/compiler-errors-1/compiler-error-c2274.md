---
title: コンパイラ エラー C2274 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2274
dev_langs:
- C++
helpviewer_keywords:
- C2274
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0fcc6b0afe78e089c268f69274be1cbfb6f3d32c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093205"
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