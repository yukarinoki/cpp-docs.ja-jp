---
description: 詳細については、「コンパイラエラー C3185」を参照してください。
title: コンパイラエラー C3185
ms.date: 11/04/2016
f1_keywords:
- C3185
helpviewer_keywords:
- C3185
ms.assetid: 5bf96279-043c-4981-9d02-b4550071b192
ms.openlocfilehash: 7dbcf11aa7c88d883aeccc8325832849f8b7a238
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242016"
---
# <a name="compiler-error-c3185"></a>コンパイラエラー C3185

マネージドまたは WinRT 型 'type' で 'typeid' が使用されました。代わりに 'operator' を使用してください

[Typeid](../../cpp/typeid-operator.md)演算子をマネージ型または WinRT 型に適用することはできません。代わりに[typeid](../../extensions/typeid-cpp-component-extensions.md)を使用してください。

次の例は C3185 を生成し、その修正方法を示しています。

```cpp
// C3185a.cpp
// compile with: /clr
ref class Base {};
ref class Derived : public Base {};

int main() {
   Derived ^ pd = gcnew Derived;
   Base ^pb = pd;
   const type_info & t1 = typeid(pb);   // C3185
   System::Type ^ MyType = Base::typeid;   // OK
};
```
