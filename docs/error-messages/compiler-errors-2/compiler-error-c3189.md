---
title: コンパイラ エラー C3189
ms.date: 11/04/2016
f1_keywords:
- C3189
helpviewer_keywords:
- C3189
ms.assetid: b254de79-931e-4a59-a9f4-1c690d90ca5e
ms.openlocfilehash: fe9dc38748fd667734c5d80f1284348184fed450
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456980"
---
# <a name="compiler-error-c3189"></a>コンパイラ エラー C3189

' typeid\<抽象宣言子を入力 >': この構文はサポートされていませんを使用して、:: typeid 代わりに

古い形式として、 [typeid](../../windows/typeid-cpp-component-extensions.md)が使用すると、新しいフォームを使用します。

次の例では、C3189 が生成されます。

```
// C3189.cpp
// compile with: /clr
int main() {
   System::Type^ t  = typeid<System::Object>;   // C3189
   System::Type^ t2  = System::Object::typeid;   // OK
}
```