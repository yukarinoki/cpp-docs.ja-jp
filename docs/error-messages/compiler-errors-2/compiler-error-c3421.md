---
title: コンパイラ エラー C3421
ms.date: 11/04/2016
f1_keywords:
- C3421
helpviewer_keywords:
- C3421
ms.assetid: b52050c6-17a4-424a-8894-337b0cec7010
ms.openlocfilehash: 399224a3d091a26066a03df0c77511997ae2403c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448907"
---
# <a name="compiler-error-c3421"></a>コンパイラ エラー C3421

'type': このクラスのファイナライザーは、アクセスできないか、または存在しないため、呼び出すことができません

ファイナライザーは暗黙的にプライベートであるため、それを囲む型の外部から呼び出すことはできません。

詳細については、次を参照してください。[する方法のデストラクターおよびファイナライザー: クラスと構造体定義および使用 (C +/cli CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)します。

## <a name="example"></a>例

次の例では C3421 が生成されます。

```
// C3421.cpp
// compile with: /clr
ref class A {};

ref class B {
   !B() {}

public:
   ~B() {}
};

int main() {
   A a;
   a.!A();   // C3421

   B b;
   b.!B();   // C3421
}
```