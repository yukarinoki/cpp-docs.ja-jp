---
title: コンパイラ エラー C3225
ms.date: 11/04/2016
f1_keywords:
- C3225
helpviewer_keywords:
- C3225
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
ms.openlocfilehash: 81316864c9c04c18ca1c96d1e74ad9988734eb72
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541493"
---
# <a name="compiler-error-c3225"></a>コンパイラ エラー C3225

'arg' のジェネリック型引数は 'type' をすることはできません、値型であるまたはハンドル型にする必要があります。

ジェネリック型引数は、正しい型でした。

詳細については、「[ジェネリック](../../windows/generics-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

ネイティブ型を持つジェネリック型をインスタンス化することはできません。 次の例では、C3225 が生成されます。

```
// C3225.cpp
// compile with: /clr
class A {};

ref class B {};

generic <class T>
ref class C {};

int main() {
   C<A>^ c = gcnew C<A>;   // C3225
   C<B^>^ c2 = gcnew C<B^>;   // OK
}
```

## <a name="example"></a>例

次の例では、c# を使用してコンポーネントを作成します。 制約は、ジェネリック型が値型でインスタンス化できますのみ指定に注意してください。

```
// C3225_b.cs
// compile with: /target:library
// a C# program
public class MyList<T> where T: struct {}
```

## <a name="example"></a>例

この例は、次の使用、c# のコンポーネントを作成し、MyList のみが有効な制約に違反する以外の値の型でインスタンス化された<xref:System.Nullable>します。 次の例では、C3225 が生成されます。

```
// C3225_c.cpp
// compile with: /clr
#using "C3225_b.dll"
ref class A {};
value class B {};
int main() {
   MyList<A> x;   // C3225
   MyList<B> y;   // OK
}
```