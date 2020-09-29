---
title: コンパイラ エラー C3390
description: Microsoft C++ コンパイラエラー C3390、その原因、およびその解決方法について説明します。
ms.date: 09/26/2020
f1_keywords:
- C3390
helpviewer_keywords:
- C3390
ms.assetid: 84800a87-c8e6-45aa-82ae-02f816dc8d97
ms.openlocfilehash: 467b379d7f5a349a217b566dc55b28d5fbd789da
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414361"
---
# <a name="compiler-error-c3390"></a>コンパイラ エラー C3390

> '*type_arg*': ジェネリック '*generic_type*' のジェネリックパラメーター '*param*' の型引数が無効です。参照型でなければなりません

ジェネリック型のインスタンス化が正しく行われませんでした。 型定義を確認してください。

## <a name="remarks"></a>解説

詳細については、「[ジェネリック](../../extensions/generics-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

最初のサンプルでは、C# を使用して、ジェネリック型を含むコンポーネントを作成します。 この型には、C++/CLI でジェネリック型を作成するときにサポートされない特定の制約があります。 詳細については、「[型パラメーターの制約](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters)」を参照してください。

```csharp
// C3390.cs
// Compile by using: csc /target:library C3390.cs
// a C# program
public class GR<C, V, N>
where C : class
where V : struct
where N : new() {}
```

C3390.dll コンポーネントが使用可能な場合、次の例では C3390 が生成されます。

```cpp
// C3390_b.cpp
// Compile by using: cl /clr C3390_b.cpp
#using <C3390.dll>
ref class R { R(int) {} };
value class V {};
ref struct N { N() {} };

int main () {
   GR<V, V, N^>^ gr2;   // C3390 first type must be a ref type
   GR<R^, V, N^>^ gr2b; // OK - do this instead
}
```
