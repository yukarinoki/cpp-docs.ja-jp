---
title: コンパイラ エラー C3392 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3392
dev_langs:
- C++
helpviewer_keywords:
- C3392
ms.assetid: e4757596-e2aa-4314-b01e-5c4bfd2110e9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04c69220cf9b6bf10a6bae8f9557f83d1e004752
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112812"
---
# <a name="compiler-error-c3392"></a>コンパイラ エラー C3392

'type_arg' : ジェネリック パラメーター 'param' (ジェネリック 'generic_type') の型引数が無効です。パブリックのパラメーターのないコンストラクターを含んでいなければなりません

ジェネリック型のインスタンス化が正しく行われませんでした。 型定義を確認してください。 詳細については、次を参照してください。[ジェネリック](../../windows/generics-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例を使用して c# を c++ のジェネリック型を作成するときに、サポートされていない特定の制約を持つジェネリック型を含むコンポーネントを作成する/cli CLI。 詳細については、「[型パラメーターの制約](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters)」を参照してください。

```cs
// C3392.cs
// Compile by using: csc /target:library C3392.cs
// a C# program
public class GR<C, V, N>
where C : class
where V : struct
where N : new() {}
```

C3392.dll コンポーネントは、次の例では C3392 が生成されます。

```cpp
// C3392_b.cpp
// Compile by using: cl /clr C3392_b.cpp
#using <C3392.dll>

ref class R { R(int) {} };
ref class N { N() {} };

value class V {};

ref class N2 { public: N2() {} };
ref class R2 { public: R2() {} };

int main () {
   GR<R^, V, N^>^ gr1;   // C3392
   GR<R^, V, N2^>^ gr1a; // OK

   GR<R^, N^, N^>^ gr3;  // C3392
   GR<R^, V, N2^>^ gr3a; // OK

   GR<R^, V, R^>^ gr4;   // C3392
   GR<R^, V, R2^>^ gr4a; // OK
}
```