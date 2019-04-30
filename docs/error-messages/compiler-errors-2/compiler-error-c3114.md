---
title: コンパイラ エラー C3114
ms.date: 11/04/2016
f1_keywords:
- C3114
helpviewer_keywords:
- C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
ms.openlocfilehash: c5a4feae5c8805a27c020b532fd58e0562e46b6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404118"
---
# <a name="compiler-error-c3114"></a>コンパイラ エラー C3114

'argument': 属性引数のない有効な名前

属性クラスのデータ メンバーを引数の名前が有効にするためには、する必要がありますいないマークする必要が`static`、 `const`、または`literal`します。 プロパティがある必要がありますいない場合、プロパティ、`static`とする必要があります get および set アクセサー。

詳細については、次を参照してください。[プロパティ](../../extensions/property-cpp-component-extensions.md)と[ユーザー定義の属性](../../extensions/user-defined-attributes-cpp-component-extensions.md)します。

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