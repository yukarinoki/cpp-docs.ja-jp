---
description: 詳細については、「コンパイラエラー C3253」を参照してください。
title: コンパイラ エラー C3253
ms.date: 11/04/2016
f1_keywords:
- C3253
helpviewer_keywords:
- C3253
ms.assetid: da40be26-0f78-4730-8727-ad11cddf8869
ms.openlocfilehash: 492530dfdfbd5b4b219dcee920fd4f4940393b3c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194294"
---
# <a name="compiler-error-c3253"></a>コンパイラ エラー C3253

' function ': 明示的なオーバーライドでエラーが発生しています。

明示的なオーバーライドが正しく指定されませんでした。 たとえば、純粋として指定するオーバーライドの実装を指定することはできません。 詳細については、「 [明示的なオーバーライド](../../extensions/explicit-overrides-cpp-component-extensions.md)」を参照してください。

次の例では、C3253 が生成されます。

```cpp
// C3253.cpp
// compile with: /clr
public interface struct I {
   void a();
   void b();
   void c();
};

public ref struct R : I {
   virtual void a() = 0, I::a {}   // C3253
   virtual void b() = I::a {}   // OK
   virtual void c() = 0;   // OK
};
```
