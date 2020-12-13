---
description: 詳細については、「コンパイラエラー C3657」を参照してください。
title: コンパイラ エラー C3657
ms.date: 11/04/2016
f1_keywords:
- C3657
helpviewer_keywords:
- C3657
ms.assetid: 89a28a18-4c17-43a1-bda6-deb52c32d203
ms.openlocfilehash: 6e5cf5dd0b3739acdd703e5ef11d3eb553fa9e90
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134421"
---
# <a name="compiler-error-c3657"></a>コンパイラ エラー C3657

デストラクターは明示的にオーバーライドしたり明示的にオーバーライドしたりすることはできません

デストラクターまたはファイナライザーを明示的にオーバーライドすることはできません。 詳細については、「 [明示的なオーバーライド](../../extensions/explicit-overrides-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3657 が生成されます。

```cpp
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
