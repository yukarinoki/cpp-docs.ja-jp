---
title: コンパイラの警告 (レベル 3) C4534
ms.date: 11/04/2016
f1_keywords:
- c4534
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
ms.openlocfilehash: 81445ff42aca78a8e40e9c88eff4bb76a41a8669
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58772658"
---
# <a name="compiler-warning-level-3-c4534"></a>コンパイラの警告 (レベル 3) C4534

'constructor' には、クラス 'class' が、既定の引数のための既定のコンス トラクターはできません。

非管理対象のクラスは、パラメーターの既定値を持つコンス トラクターを持つことができ、コンパイラはこれを既定のコンス トラクターとして使用されます。 マークされたクラス、`value`キーワードとして使用されませんコンス トラクターを既定値でそのパラメーターの既定のコンス トラクター。

詳細については、次を参照してください。[クラスと構造体](../../extensions/classes-and-structs-cpp-component-extensions.md)します。

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