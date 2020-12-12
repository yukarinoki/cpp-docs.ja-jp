---
description: 詳細については、「コンパイラエラー C3414」を参照してください。
title: コンパイラ エラー C3414
ms.date: 11/04/2016
f1_keywords:
- C3414
helpviewer_keywords:
- C3414
ms.assetid: 715f5432-b509-4f8f-84f5-e1463bac490f
ms.openlocfilehash: c16f57be5665110d8186bdedbb2ada0ac2fdacaa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321928"
---
# <a name="compiler-error-c3414"></a>コンパイラ エラー C3414

' member ': インポートされたメンバー関数は定義できません

メンバーは、参照されたアセンブリでも定義されているコードで定義されています。

次の例では、C3414 が生成されます。

```cpp
// C3414a2.cpp
// compile with: /clr /LD
public ref class MyClass {
public:
   void Test(){}
};
```

この場合、次のようになります。

```cpp
// C3414b2.cpp
// compile with: /clr
#using <C3414a2.dll>

void MyClass::Test() {    // C3414
}

System::Object::Object() {    // C3414
}
```
