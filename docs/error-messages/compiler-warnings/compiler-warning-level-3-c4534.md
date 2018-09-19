---
title: コンパイラの警告 (レベル 3) C4534 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- c4534
dev_langs:
- C++
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad85a6b9dff1715cbdce9738608f26c8680319d0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099812"
---
# <a name="compiler-warning-level-3-c4534"></a>コンパイラの警告 (レベル 3) C4534

'constructor' には、クラス 'class' が、既定の引数のための既定のコンス トラクターはできません。

非管理対象のクラスは、パラメーターの既定値を持つコンス トラクターを持つことができ、コンパイラはこれを既定のコンス トラクターとして使用されます。 マークされたクラス、`value`キーワードとして使用されませんコンス トラクターを既定値でそのパラメーターの既定のコンス トラクター。

詳細については、次を参照してください。[クラスと構造体](../../windows/classes-and-structs-cpp-component-extensions.md)します。

次の例では、C4534 が生成されます。

```
// C4534.cpp
// compile with: /W3 /clr /WX
value class MyClass {
public:
   int ii;
   MyClass(int i = 9) {   // C4534, will not be the default constructor
      i++;
   }
};

int main() {
   MyClass ^ xx = gcnew MyClass;
   xx->ii = 0;
}
```