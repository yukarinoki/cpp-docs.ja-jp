---
description: 詳細については、「コンパイラエラー C3798」を参照してください。
title: コンパイラ エラー C3798
ms.date: 11/04/2016
f1_keywords:
- C3798
helpviewer_keywords:
- C3798
ms.assetid: b2f8b1d8-8812-49b8-a346-28e48f02ba5c
ms.openlocfilehash: 394fe0f420c25fbabab44204e1793dc7dd5e9058
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244837"
---
# <a name="compiler-error-c3798"></a>コンパイラ エラー C3798

' 指定子 ': プロパティ宣言は、オーバーライド指定子を含むことはできません (代わりにプロパティの get/set メソッドに配置する必要があります)

プロパティが正しく宣言されませんでした。 詳細については、「

- [property](../../extensions/property-cpp-component-extensions.md)

- [abstract](../../extensions/abstract-cpp-component-extensions.md)

- [sealed](../../extensions/sealed-cpp-component-extensions.md)

## <a name="example"></a>例

次の例では、C3798 が生成されます。

```cpp
// C3798.cpp
// compile with: /clr /c
ref struct A {
   property int Prop_1 abstract;   // C3798
   property int Prop_2 sealed;   // C3798

   // OK
   property int Prop_3 {
      virtual int get() abstract;
      virtual void set(int i) abstract;
   }

   property int Prop_4 {
      virtual int get() sealed;
      virtual void set(int i) sealed;
   }
};
```
