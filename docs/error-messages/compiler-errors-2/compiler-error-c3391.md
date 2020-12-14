---
description: 詳細については、「コンパイラエラー C3391」を参照してください。
title: コンパイラ エラー C3391
ms.date: 11/04/2016
f1_keywords:
- C3391
helpviewer_keywords:
- C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
ms.openlocfilehash: 1bac535136b2c6115bf0f5ff31c9e098407e03bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313399"
---
# <a name="compiler-error-c3391"></a>コンパイラ エラー C3391

' type_arg ': ジェネリック ' generic_type ' のジェネリックパラメーター ' param ' の型引数が無効です。 null 非許容の値型でなければなりません

ジェネリック型のインスタンス化が正しく行われませんでした。 型定義を確認してください。 詳細については、「」および「ジェネリック」を参照してください <xref:System.Nullable> 。 [](../../extensions/generics-cpp-component-extensions.md)

## <a name="example"></a>例

次のサンプルでは、C# を使用して、C++/CLI でジェネリック型を作成するときにサポートされない特定の制約を持つジェネリック型を含むコンポーネントを作成します。 詳細については、「[型パラメーターの制約](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters)」を参照してください。

```csharp
// C3391.cs
// Compile by using: csc /target:library C3391.cs
// a C# program
public class GR<N>
where N : struct {}
```

C3391.dll コンポーネントが使用可能な場合、次の例では C3391 が生成されます。

```cpp
// C3391_b.cpp
// Compile by using: cl /clr C3391_b.cpp
#using <C3391.dll>
using namespace System;
value class VClass {};

int main() {
   GR< Nullable<VClass> >^ a =
      gcnew GR< Nullable<VClass> >();   // C3391 can't be Nullable
   GR<VClass>^ aa = gcnew GR<VClass>(); // OK
}
```
