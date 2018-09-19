---
title: コンパイラ エラー C3225 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3225
dev_langs:
- C++
helpviewer_keywords:
- C3225
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8d8b1251b9c13a71faf771c85924a75681deab7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033252"
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