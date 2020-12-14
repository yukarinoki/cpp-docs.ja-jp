---
description: 詳細については、「コンパイラエラー C3145」を参照してください。
title: コンパイラ エラー C3145
ms.date: 11/04/2016
f1_keywords:
- C3145
helpviewer_keywords:
- C3145
ms.assetid: f165c874-0f51-45c7-85e8-ebe321cbc168
ms.openlocfilehash: 5410273dd1ceff38c8a234ba1d76ca1bf5283287
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204005"
---
# <a name="compiler-error-c3145"></a>コンパイラ エラー C3145

'object': グローバルまたは静的変数は、マネージド型または WinRT 型の ’type’ を含むことはできません。

関数スコープ内では CLR オブジェクトまたは WinRT オブジェクトのみ定義できます。

次の例は C3145 を生成し、その修正方法を示しています。

```cpp
// C3145.cpp
// compile with: /clr
using namespace System;
ref class G {};

G ^ ptr;   // C3145
G ^ ptr2 = gcnew G;   // C3145

ref class GlobalObjects {
public:
   static G ^ ptr;   // OK
   static G ^ ptr2 = gcnew G;   // OK
};

int main() {
   G ^ ptr;   // OK
   G ^ ptr2 = gcnew G;   // OK
}
```

次の例では C3145 を生成します。

```cpp
// C3145b.cpp
// compile with: /clr
ref class MyClass {
public:
   static int data;
};

interior_ptr<int> p = &(MyClass::data);   // C3145

void Test(interior_ptr<int> x) {}

int main() {
   MyClass ^ h_MyClass = gcnew MyClass;
   interior_ptr<int> p = &(h_MyClass->data);
}
```
