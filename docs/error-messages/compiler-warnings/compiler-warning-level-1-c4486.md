---
description: '詳細情報: コンパイラの警告 (レベル 1) C4486'
title: コンパイラの警告 (レベル 1) C4486
ms.date: 11/04/2016
f1_keywords:
- C4486
helpviewer_keywords:
- C4486
ms.assetid: 2c0c59e3-d025-4d97-8da2-fa27df1402fc
ms.openlocfilehash: e664c9654b41932ab81c596494953807b8bb5d13
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212442"
---
# <a name="compiler-warning-level-1-c4486"></a>コンパイラの警告 (レベル 1) C4486

' function ': ref クラスまたは値クラスのプライベート仮想メソッドは ' sealed ' に設定されなければなりません

マネージクラスまたは構造体のプライベート仮想メンバー関数にアクセスしたりオーバーライドしたりすることはできないため、 [sealed](../../extensions/sealed-cpp-component-extensions.md)とマークする必要があります。

## <a name="examples"></a>例

次の例では、C4486 が生成されます。

```cpp
// C4486.cpp
// compile with: /clr /c /W1
ref class B {
private:
   virtual void f() {}   // C4486
   virtual void f1() sealed {}   // OK
};
```

次のサンプルは、プライベートのシールドされた仮想関数の1つの使用方法を示しています。

```cpp
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
