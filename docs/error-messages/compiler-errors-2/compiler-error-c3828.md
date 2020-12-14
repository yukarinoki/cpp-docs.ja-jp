---
description: 詳細については、「コンパイラエラー C3828」を参照してください。
title: コンパイラ エラー C3828
ms.date: 11/04/2016
f1_keywords:
- C3828
helpviewer_keywords:
- C3828
ms.assetid: 8d9cee75-9504-4bc8-88b6-2413618a3f45
ms.openlocfilehash: 90c731ffc636355b5c9a1963facbcccabf356700
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249322"
---
# <a name="compiler-error-c3828"></a>コンパイラ エラー C3828

' object type ': マネージクラスまたは WinRTclasses のインスタンスの作成中に配置引数を使用することはできません

マネージ型または Windows ランタイム型のオブジェクトを作成するときに、operator [ref new、gcnew](../../extensions/ref-new-gcnew-cpp-component-extensions.md) 、または [new](../../cpp/new-operator-cpp.md)の配置形式を使用することはできません。

次の例では、C3828 を生成し、その修正方法を示しています。

```cpp
// C3828a.cpp
// compile with: /clr
ref struct M {
};

ref struct N {
   static array<char>^ bytes = gcnew array<char>(256);
};

int main() {
   M ^m1 = new (&N::bytes) M();   // C3828
   // The following line fixes the error.
   // M ^m1 = gcnew M();
}
```
