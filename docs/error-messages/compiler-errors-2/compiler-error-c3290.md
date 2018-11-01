---
title: コンパイラ エラー C3290
ms.date: 11/04/2016
f1_keywords:
- C3290
helpviewer_keywords:
- C3290
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
ms.openlocfilehash: d82d3272563f7a5af5de399a2f7fff621500e612
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490481"
---
# <a name="compiler-error-c3290"></a>コンパイラ エラー C3290

'type': trivial プロパティに参照型を含めることはできません。

プロパティが正しく宣言されませんでした。 trivial プロパティを宣言すると、コンパイラは、プロパティが更新する変数を作成します。クラスに追跡参照変数を指定することはできません。

参照してください[プロパティ](../../windows/property-cpp-component-extensions.md)と[参照演算子の追跡](../../windows/tracking-reference-operator-cpp-component-extensions.md)詳細についてはします。

## <a name="example"></a>例

次の例では C3290 が生成されます。

```
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