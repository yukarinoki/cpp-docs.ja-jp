---
title: コンパイラ エラー C3225
ms.date: 11/04/2016
f1_keywords:
- C3225
helpviewer_keywords:
- C3225
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
ms.openlocfilehash: cae0572002c849fb5aed771993d3a89ed82c726a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "58778313"
---
# <a name="compiler-error-c3225"></a>コンパイラ エラー C3225

'arg' のジェネリック型引数は 'type' をすることはできません、値型であるまたはハンドル型にする必要があります。

ジェネリック型引数は、正しい型でした。

詳細については、「[ジェネリック](../../extensions/generics-cpp-component-extensions.md)」を参照してください。

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

次の例では、C# を使用してコンポーネントを作成します。 制約は、ジェネリック型が値型でインスタンス化できますのみ指定に注意してください。

```
// C3225_b.cs
// compile with: /target:library
// a C# program
public class MyList<T> where T: struct {}
```

## <a name="example"></a>例

この例は、次の使用、C# のコンポーネントを作成し、MyList のみが有効な制約に違反する以外の値の型でインスタンス化された<xref:System.Nullable>します。 次の例では、C3225 が生成されます。

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