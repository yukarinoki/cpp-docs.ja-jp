---
description: 詳細については、「コンパイラエラー C3673」を参照してください。
title: コンパイラ エラー C3673
ms.date: 11/04/2016
f1_keywords:
- C3673
helpviewer_keywords:
- C3673
ms.assetid: bb6d2079-05af-4e2c-be0e-75c892e6c590
ms.openlocfilehash: 8e503497322a8141aa514c50354f19b8638b1e64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228886"
---
# <a name="compiler-error-c3673"></a>コンパイラ エラー C3673

' type ': クラスにコピーコンストラクターがありません。

CLR ref 型のオブジェクトをコピーするには、ユーザー定義のコンストラクターが必要です。 詳細については、「 [参照型の C++ スタックセマンティクス](../../dotnet/cpp-stack-semantics-for-reference-types.md)」を参照してください。

## <a name="examples"></a>例

次の例では、C3673 が生成されます。

```cpp
// C3673.cpp
// compile with: /clr
public ref struct R {
public:
   R() {}
   // Uncomment the following line to resolve.
   // R(R% p) {}
};

int main() {
   R r;
   R s = r;   // C3673
}
```

次の例では、C3673 が生成されます。

```cpp
// C3673_b.cpp
// compile with: /clr /c
// C3673 expected
using namespace System;
[AttributeUsage(AttributeTargets::Class)]
ref class MyAttr : public Attribute {
public:
   MyAttr() {}
   // Uncomment the following line to resolve.
   // MyAttr(int i) {}
   property int Priority;
   property int Version;
};

[MyAttr]
ref class ClassA {};   // OK, no arguments

[MyAttr(Priority = 1)]
ref class ClassB {};   // OK, named argument

[MyAttr(123)]
ref class ClassC {};   // Positional argument

[MyAttr(123, Version = 1)]
ref class ClassD {};   // Positional and named
```
