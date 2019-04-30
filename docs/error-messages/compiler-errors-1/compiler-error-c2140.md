---
title: コンパイラ エラー C2140
ms.date: 11/04/2016
f1_keywords:
- C2140
helpviewer_keywords:
- C2140
ms.assetid: d44a0500-002c-4632-9e5e-c71c3a473ec4
ms.openlocfilehash: 35b6e38290acddb41bdf53d9663a058259300ee8
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345690"
---
# <a name="compiler-error-c2140"></a>コンパイラ エラー C2140

'type': ジェネリック型パラメーターに依存する型がコンパイラの組み込み型の特徴である 'trait' への引数として許可されていません

無効な型の指定子は、型の特徴に渡されました。

詳細については、次を参照してください。[型の特徴のコンパイラ サポート](../../extensions/compiler-support-for-type-traits-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C2140 が生成されます。

```
// C2140.cpp
// compile with: /clr /c
template <class T>

struct is_polymorphic {
   static const bool value = __is_polymorphic(T);
};

class x {};

generic <class T>
ref class C {
   void f() {
      System::Console::WriteLine(__is_polymorphic(T));   // C2140
      System::Console::WriteLine(is_polymorphic<T>::value);   // C2140

      System::Console::WriteLine(__is_polymorphic(x));   // OK
      System::Console::WriteLine(is_polymorphic<x>::value);   // OK
   }
};
```