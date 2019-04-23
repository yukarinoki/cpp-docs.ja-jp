---
title: コンパイラ エラー C3185
ms.date: 11/04/2016
f1_keywords:
- C3185
helpviewer_keywords:
- C3185
ms.assetid: 5bf96279-043c-4981-9d02-b4550071b192
ms.openlocfilehash: 45afe70b454f72dd8c9b8ce9771ce1f5aef6a10e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777784"
---
# <a name="compiler-error-c3185"></a>コンパイラ エラー C3185

マネージドまたは WinRT 型 'type' で 'typeid' が使用されました。代わりに 'operator' を使用してください

適用することはできません、 [typeid](../../cpp/typeid-operator.md)演算子をマネージまたは WinRT 型は、使用して[typeid](../../extensions/typeid-cpp-component-extensions.md)代わりにします。

次の例は C3185 を生成し、その修正方法を示しています。

```
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
