---
title: コンパイラ エラー C3225
ms.date: 11/04/2016
f1_keywords:
- C3225
helpviewer_keywords:
- C3225
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
ms.openlocfilehash: ed645535300e0a7c4d27f8bed43d3143bae7e97a
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742867"
---
# <a name="compiler-error-c3225"></a>コンパイラ エラー C3225

' arg ' のジェネリック型引数を ' type ' にすることはできません。値型またはハンドル型にする必要があります

ジェネリック型引数の型が正しくありませんでした。

詳細については、「[ジェネリック](../../extensions/generics-cpp-component-extensions.md)」を参照してください。

## <a name="examples"></a>例

ネイティブ型を使用してジェネリック型をインスタンス化することはできません。 次の例では、C3225 が生成されます。

```cpp
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

次の例では、C# を使用してコンポーネントを作成します。 制約によって、ジェネリック型が値型でのみインスタンス化できることが指定されていることに注意してください。

```
// C3225_b.cs
// compile with: /target:library
// a C# program
public class MyList<T> where T: struct {}
```

このサンプルでは、C# で作成されたコンポーネントを使用し、MyList が以外の値型を使用してのみインスタンス化できる制約に違反し <xref:System.Nullable> ます。 次の例では、C3225 が生成されます。

```cpp
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
