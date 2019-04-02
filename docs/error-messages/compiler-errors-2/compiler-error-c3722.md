---
title: コンパイラ エラー C3722
ms.date: 11/04/2016
f1_keywords:
- C3722
helpviewer_keywords:
- C3722
ms.assetid: 3cb28363-5eff-4548-bd0d-d5c615846353
ms.openlocfilehash: e9a8c9cc26aeedf49484bb1f7357a76d0eb42bb5
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768607"
---
# <a name="compiler-error-c3722"></a>コンパイラ エラー C3722

汎用イベントは許可されていません

コンパイラは、ジェネリック クラス、構造体、および関数にのみ使用できます。  詳細については、「[ジェネリック](../../extensions/generics-cpp-component-extensions.md)」を参照してください。

次の例では、C3722 が生成されます。

```
// C3722.cpp
// compile with: /clr
generic <typename T>
public delegate void MyEventHandler(System::Object^ sender, System::EventArgs^ e, T optional);

generic <class T>
public ref struct MyButton {
   generic<typename U>
   event MyEventHandler<U>^ Click;   // C3722
};
```