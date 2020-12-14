---
description: 詳細については、「コンパイラエラー C3189」を参照してください。
title: コンパイラエラー C3189
ms.date: 11/04/2016
f1_keywords:
- C3189
helpviewer_keywords:
- C3189
ms.assetid: b254de79-931e-4a59-a9f4-1c690d90ca5e
ms.openlocfilehash: 9253a1d4333a7454bfbff5442cfaa5a24ebc68ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242003"
---
# <a name="compiler-error-c3189"></a>コンパイラエラー C3189

' typeid \<type abstract declarator> ': この構文はサポートされなくなりました。代わりに:: typeid を使用してください

[Typeid](../../extensions/typeid-cpp-component-extensions.md)の古い形式が使用されました。新しいフォームを使用してください。

次の例では、C3189 が生成されます。

```cpp
// C3189.cpp
// compile with: /clr
int main() {
   System::Type^ t  = typeid<System::Object>;   // C3189
   System::Type^ t2  = System::Object::typeid;   // OK
}
```
