---
title: コンパイラエラー C3114
ms.date: 11/04/2016
f1_keywords:
- C3114
helpviewer_keywords:
- C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
ms.openlocfilehash: 481e0ac5a395b38bc9d1874959b010ecd71f9fb5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233380"
---
# <a name="compiler-error-c3114"></a>コンパイラエラー C3114

' argument ': 有効な名前付き属性引数ではありません

属性クラスのデータメンバーが有効な名前付き引数であるためには、、、またはとしてマークされていない必要があり **`static`** **`const`** **`literal`** ます。 プロパティの場合、プロパティはではなく、 **`static`** get アクセサーと set アクセサーを持つ必要があります。

詳細については、「[プロパティ](../../extensions/property-cpp-component-extensions.md)と[ユーザー定義の属性](../../extensions/user-defined-attributes-cpp-component-extensions.md)」を参照してください。

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
