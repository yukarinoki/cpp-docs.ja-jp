---
title: コンパイラ エラー C3390
ms.date: 11/04/2016
f1_keywords:
- C3390
helpviewer_keywords:
- C3390
ms.assetid: 84800a87-c8e6-45aa-82ae-02f816dc8d97
ms.openlocfilehash: 4c0544df55fc71ace697d7e0a53ba303706e1378
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201124"
---
# <a name="compiler-error-c3390"></a>コンパイラ エラー C3390

'type_arg' : ジェネリック 'generic_type' のジェネリック パラメーター 'param' の型引数が無効です。参照型でなければなりません

ジェネリック型のインスタンス化が正しく行われませんでした。  型定義をご確認ください。  詳細については、「[ジェネリック](../../extensions/generics-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

最初のサンプルでC#は、を使用して、/clr でC++ジェネリック型を作成するときにサポートされない特定の制約を持つジェネリック型を含むコンポーネントを作成します。 詳細については、「[型パラメーターの制約](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters)」を参照してください。

```csharp
// C3390.cs
// Compile by using: csc /target:library C3390.cs
// a C# program
public class GR<C, V, N>
where C : class
where V : struct
where N : new() {}
```

C3390 コンポーネントが使用可能になると、次の例では C3390 が生成されます。

```cpp
// C3390_b.cpp
// Compile by using: cl /clr C3390_b.cpp
#using <C3390.dll>
ref class R { R(int) {} };
value class V {};
ref struct N { N() {} };

int main () {
   GR<V, V, N^>^ gr2;   // C3390 first type must be a ref type
   GR<R^, V, N^>^ gr2b; // OK
}
```
