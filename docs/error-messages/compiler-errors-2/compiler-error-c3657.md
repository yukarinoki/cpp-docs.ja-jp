---
title: コンパイラ エラー C3657
ms.date: 11/04/2016
f1_keywords:
- C3657
helpviewer_keywords:
- C3657
ms.assetid: 89a28a18-4c17-43a1-bda6-deb52c32d203
ms.openlocfilehash: 209bf779122f38326cb3958ed83a2061deb64185
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463402"
---
# <a name="compiler-error-c3657"></a>コンパイラ エラー C3657

デストラクターが明示的にオーバーライドできませんまたは明示的にオーバーライドします。

デストラクターまたはファイナライザーは、明示的にオーバーライドすることはできません。 詳細については、次を参照してください。[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C3657 が生成されます。

```
// C3657.cpp
// compile with: /clr
public ref struct I {
   virtual ~I() { }
   virtual void a();
};

public ref struct D : I {
   virtual ~D() = I::~I {}   // C3657
   virtual void a() = I::a {}   // OK
};
```