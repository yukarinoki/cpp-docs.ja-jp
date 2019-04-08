---
title: コンパイラ エラー C3391
ms.date: 11/04/2016
f1_keywords:
- C3391
helpviewer_keywords:
- C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
ms.openlocfilehash: 32ba1ca63a3a6fafa3290946a976e6845385126f
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58772593"
---
# <a name="compiler-error-c3391"></a>コンパイラ エラー C3391

'type_arg': ジェネリック パラメーター 'param' のジェネリック 'generic_type' の無効な型引数は null 非許容値型である必要があります

ジェネリック型のインスタンス化が正しく行われませんでした。 型定義を確認してください。 詳細については、<xref:System.Nullable>と[ジェネリック](../../extensions/generics-cpp-component-extensions.md)を参照してください。

## <a name="example"></a>例

次の例を使用して C# を c++ のジェネリック型を作成するときに、サポートされていない特定の制約を持つジェネリック型を含むコンポーネントを作成する/cli CLI。 詳細については、「[型パラメーターの制約](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters)」を参照してください。

```cs
// C3391.cs
// Compile by using: csc /target:library C3391.cs
// a C# program
public class GR<N>
where N : struct {}
```

C3391.dll コンポーネントは、次の例では C3391 が生成されます。

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