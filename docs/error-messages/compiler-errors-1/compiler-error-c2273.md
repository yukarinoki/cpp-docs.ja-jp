---
title: コンパイラ エラー C2273 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2273
dev_langs:
- C++
helpviewer_keywords:
- C2273
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 995f75487820976d045e5db05fe2b170260240cc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066220"
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