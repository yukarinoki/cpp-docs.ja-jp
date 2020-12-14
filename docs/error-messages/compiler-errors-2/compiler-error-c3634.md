---
description: 詳細については、「コンパイラエラー C3634」を参照してください。
title: コンパイラ エラー C3634
ms.date: 11/04/2016
f1_keywords:
- C3634
helpviewer_keywords:
- C3634
ms.assetid: fd09f10c-f863-483b-9756-71c16b760b02
ms.openlocfilehash: 21407af8a86a3f82331d0f2a1d424457d8bee833
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239247"
---
# <a name="compiler-error-c3634"></a>コンパイラ エラー C3634

' function ': マネージクラスまたは WinRTclass の抽象メソッドを定義することはできません。

マネージド クラスまたは WinRT クラスで抽象メソッドを宣言することはできますが、定義することはできません。

## <a name="example"></a>例

次の例では警告 C3634 が生成されます。

```cpp
// C3634.cpp
// compile with: /clr
ref class C {
   virtual void f() = 0;
};

void C::f() {   // C3634 - don't define managed class' pure virtual method
}
```
