---
title: コンパイラ エラー C3185 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3185
dev_langs:
- C++
helpviewer_keywords:
- C3185
ms.assetid: 5bf96279-043c-4981-9d02-b4550071b192
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd7f94f86165fdfd25bb5a901cdb4349a0e48494
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044523"
---
# <a name="compiler-error-c3185"></a>コンパイラ エラー C3185

マネージドまたは WinRT 型 'type' で 'typeid' が使用されました。代わりに 'operator' を使用してください

適用することはできません、 [typeid](../../cpp/typeid-operator.md)演算子をマネージまたは WinRT 型は、使用して[typeid](../../windows/typeid-cpp-component-extensions.md)代わりにします。

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
