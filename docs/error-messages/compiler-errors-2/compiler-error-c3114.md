---
description: 詳細については、「コンパイラエラー C3114」を参照してください。
title: コンパイラエラー C3114
ms.date: 11/04/2016
f1_keywords:
- C3114
helpviewer_keywords:
- C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
ms.openlocfilehash: 18d14ae01c0ae101ff0b66d837edd0699312af9c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115951"
---
# <a name="compiler-error-c3114"></a>コンパイラエラー C3114

' argument ': 有効な名前付き属性引数ではありません

属性クラスのデータメンバーが有効な名前付き引数であるためには、、、またはとしてマークされていない必要があり **`static`** **`const`** **`literal`** ます。 プロパティの場合、プロパティはではなく、 **`static`** get アクセサーと set アクセサーを持つ必要があります。

詳細については、「 [プロパティ](../../extensions/property-cpp-component-extensions.md) と [ユーザー定義の属性](../../extensions/user-defined-attributes-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3114 が生成されます。

```cpp
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
