---
title: コンパイラの警告 (レベル 1) C4486
ms.date: 11/04/2016
f1_keywords:
- C4486
helpviewer_keywords:
- C4486
ms.assetid: 2c0c59e3-d025-4d97-8da2-fa27df1402fc
ms.openlocfilehash: b6e1fc7001908202efc2fb0ef3653153c007eac0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456031"
---
# <a name="compiler-warning-level-1-c4486"></a>コンパイラの警告 (レベル 1) C4486

'function': ref クラスまたは値クラスのプライベート仮想メソッドは、'シールド' マークする必要があります

マークする必要がありますので、マネージ クラスまたは構造体のプライベート仮想メンバー関数はアクセスできないか、またはオーバーライドして、[シール](../../windows/sealed-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C4486 が生成されます。

```
// C4486.cpp
// compile with: /clr /c /W1
ref class B {
private:
   virtual void f() {}   // C4486
   virtual void f1() sealed {}   // OK
};
```

## <a name="example"></a>例

次の例では、プライベートの封印された、仮想関数の 1 つの考えられる用途を示します。

```
// C4486_b.cpp
// compile with: /clr /c
ref class B {};

ref class D : B {};

interface class I {
   B^ mf();
};

ref class E : I {
private:
   virtual B^ g() sealed = I::mf {
      return gcnew B;
   }

public:
   virtual D^ mf() {
      return gcnew D;
   }
};
```