---
title: コンパイラ エラー C3114
ms.date: 11/04/2016
f1_keywords:
- C3114
helpviewer_keywords:
- C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
ms.openlocfilehash: c5a4feae5c8805a27c020b532fd58e0562e46b6b
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58773776"
---
# <a name="compiler-error-c3114"></a>コンパイラ エラー C3114

'argument': 属性引数のない有効な名前

属性クラスのデータ メンバーを引数の名前が有効にするためには、する必要がありますいないマークする必要が`static`、 `const`、または`literal`します。 プロパティがある必要がありますいない場合、プロパティ、`static`とする必要があります get および set アクセサー。

詳細については、[プロパティ](../../extensions/property-cpp-component-extensions.md)と[ユーザー定義の属性](../../extensions/user-defined-attributes-cpp-component-extensions.md)を参照してください。

## <a name="example"></a>例

次の例では、C3114 が生成されます。

```
// C3114.cpp
// compile with: /clr /c
public ref class A : System::Attribute {
public:
   static property int StaticProp {
      int get();
   }

   property int Prop2 {
      int get();
      void set(int i);
   }
};

[A(StaticProp=123)]   // C3114
public ref class R {};

[A(Prop2=123)]   // OK
public ref class S {};
```