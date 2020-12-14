---
description: 詳細については、「コンパイラエラー C3611」を参照してください。
title: コンパイラ エラー C3611
ms.date: 11/04/2016
f1_keywords:
- C3611
helpviewer_keywords:
- C3611
ms.assetid: 42f3e320-41de-420a-bd05-8924cab765aa
ms.openlocfilehash: 9c18e8e757e3962af1f2e0fbcc0d33384f3b6329
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262296"
---
# <a name="compiler-error-c3611"></a>コンパイラ エラー C3611

' function ': シールされた関数は、純粋指定子を持つことはできません

シールされた関数の宣言が正しくありません。  詳細については、「[sealed](../../extensions/sealed-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3611 が生成されます。

```cpp
// C3611.cpp
// compile with: /clr /c

ref struct V {
   virtual void Test() sealed = 0;   // C3611
   virtual void Test2() sealed;   // OK
   virtual void Test3() = 0;   // OK
};
```
