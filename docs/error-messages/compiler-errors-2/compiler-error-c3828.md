---
title: コンパイラ エラー C3828
ms.date: 11/04/2016
f1_keywords:
- C3828
helpviewer_keywords:
- C3828
ms.assetid: 8d9cee75-9504-4bc8-88b6-2413618a3f45
ms.openlocfilehash: 68a82105a2ff7d58090e9f345bf7aafb34d492d4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515285"
---
# <a name="compiler-error-c3828"></a>コンパイラ エラー C3828

'object type': 仮引数のマネージ インスタンスの作成は許可されませんまたは WinRTclasses

マネージ型または Windows ランタイム型のオブジェクトを作成する場合は、演算子の配置形式を使用することはできません[ref new、gcnew](../../windows/ref-new-gcnew-cpp-component-extensions.md)または[新しい](../../cpp/new-operator-cpp.md)します。

次の例では、C3828 を生成し、その修正方法を示しています。

```
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