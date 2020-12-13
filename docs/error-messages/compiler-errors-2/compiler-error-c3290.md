---
description: 詳細については、「コンパイラエラー C3290」を参照してください。
title: コンパイラ エラー C3290
ms.date: 11/04/2016
f1_keywords:
- C3290
helpviewer_keywords:
- C3290
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
ms.openlocfilehash: 68c0e79c233f7fbd416f6bdbe42cc555c04731fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337426"
---
# <a name="compiler-error-c3290"></a>コンパイラ エラー C3290

'type': trivial プロパティに参照型を含めることはできません。

プロパティが正しく宣言されませんでした。 trivial プロパティを宣言すると、コンパイラは、プロパティが更新する変数を作成します。クラスに追跡参照変数を指定することはできません。

詳細については、「 [プロパティ](../../extensions/property-cpp-component-extensions.md) And [Tracking Reference Operator](../../extensions/tracking-reference-operator-cpp-component-extensions.md) 」を参照してください。

## <a name="example"></a>例

次の例では C3290 が生成されます。

```cpp
// C3290.cpp
// compile with: /clr /c
ref struct R {};

ref struct X {
   R^ mr;

   property R % y;   // C3290
   property R ^ x;   // OK

   // OK
   property R% prop {
      R% get() {
         return *mr;
      }

      void set(R%) {}
   }
};

int main() {
   X x;
   R% xp = x.prop;
}
```
