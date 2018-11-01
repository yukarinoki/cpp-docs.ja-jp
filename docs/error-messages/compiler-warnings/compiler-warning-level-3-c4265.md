---
title: コンパイラの警告 (レベル 3) C4265
ms.date: 11/04/2016
f1_keywords:
- C4265
helpviewer_keywords:
- C4265
ms.assetid: 20547159-6f30-4cc4-83aa-927884c8bb4c
ms.openlocfilehash: f06e70f88bc0a34e2feecba19da8dd9edc630230
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558354"
---
# <a name="compiler-warning-level-3-c4265"></a>コンパイラの警告 (レベル 3) C4265

'class': クラスは仮想関数を含んでいますが、デストラクターが仮想ではありません。

クラスは、非仮想デストラクターですが仮想関数が、オブジェクト型の可能性があります破棄されません正しく、基底クラスのポインターを介して、クラスが破棄されるときに。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

次の例では、C4265 が生成されます。

```
// C4265.cpp
// compile with: /W3 /c
#pragma warning(default : 4265)
class B
{
public:
   virtual void vmf();

   ~B();
   // try the following line instead
   // virtual ~B();
};   // C4265

int main()
{
   B b;
}
```