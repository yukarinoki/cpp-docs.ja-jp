---
title: コンパイラ エラー C3114 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3114
dev_langs:
- C++
helpviewer_keywords:
- C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c7d0e324c00c4b304deca1d2538913a88690d023
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054611"
---
# <a name="compiler-error-c3114"></a>コンパイラ エラー C3114

'argument': 属性引数のない有効な名前

属性クラスのデータ メンバーを引数の名前が有効にするためには、する必要がありますいないマークする必要が`static`、 `const`、または`literal`します。 プロパティがある必要がありますいない場合、プロパティ、`static`とする必要があります get および set アクセサー。

詳細については、次を参照してください。[プロパティ](../../windows/property-cpp-component-extensions.md)と[ユーザー定義の属性](../../windows/user-defined-attributes-cpp-component-extensions.md)します。

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