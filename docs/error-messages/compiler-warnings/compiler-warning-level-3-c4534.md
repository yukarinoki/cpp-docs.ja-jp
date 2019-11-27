---
title: コンパイラの警告 (レベル 3) C4534
ms.date: 11/04/2016
f1_keywords:
- c4534
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
ms.openlocfilehash: 2e617b18f2c7ed3b51d25eb44101629bbadcef9d
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2019
ms.locfileid: "74189090"
---
# <a name="compiler-warning-level-3-c4534"></a>コンパイラの警告 (レベル 3) C4534

既定の引数により、' constructor ' はクラス ' class ' の既定のコンストラクターになりません

アンマネージクラスは、既定値を持つパラメーターを持つコンストラクターを持つことができ、コンパイラはこれを既定のコンストラクターとして使用します。 `value` キーワードでマークされたクラスは、パラメーターの既定値を持つコンストラクターを既定のコンストラクターとして使用しません。

詳細については、「[クラスと構造体](../../extensions/classes-and-structs-cpp-component-extensions.md)」を参照してください。

次の例では、C4534 が生成されます。

```cpp
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