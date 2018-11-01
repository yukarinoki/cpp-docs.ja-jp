---
title: コンパイラ エラー C3612
ms.date: 11/04/2016
f1_keywords:
- C3612
helpviewer_keywords:
- C3612
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
ms.openlocfilehash: a6084632ac0a84cc058ea73eb3c2b632208792eb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475934"
---
# <a name="compiler-error-c3612"></a>コンパイラ エラー C3612

'type': シール クラスを抽象にすることはできません

使用して定義されている型`value`は既定では、シール クラスは、その基本のすべてのメソッドを実装しない限り、抽象とします。 シールされた抽象クラスは基底クラスにもできます。 また、インスタンス化できます。

詳細については、次を参照してください。[クラスと構造体](../../windows/classes-and-structs-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C3612 が生成されます。

```
// C3612.cpp
// compile with: /clr /c
value struct V: public System::ICloneable {};   // C3612

// OK
value struct V2: public System::ICloneable {
   Object^ Clone();
};
```