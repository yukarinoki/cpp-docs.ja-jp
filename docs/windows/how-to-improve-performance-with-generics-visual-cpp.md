---
title: '方法: ジェネリックによるパフォーマンスの向上 (C +/cli CLI)'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- performance, C++
- C++, performance
- C++, generics
- generics [C++], performance
ms.assetid: f14a175b-301f-46cc-86e4-c82d35f9aa3e
ms.openlocfilehash: 61d858542505b0e37b03e13cca803df10ffbdddc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50527960"
---
# <a name="how-to-improve-performance-with-generics-ccli"></a>方法: ジェネリックによるパフォーマンスの向上 (C +/cli CLI)

ジェネリック型パラメーターに基づく再利用可能なコードを作成できます。 型パラメーターの実際の型は、クライアント コードによって呼び出されるまで遅延されます。 ジェネリックの詳細については、「 [Generics](../windows/generics-cpp-component-extensions.md)」を参照してください。

この記事では、方法、コレクションを使用するアプリケーションのパフォーマンスを向上させるジェネリックがヘルプについて説明します。

## <a name="example"></a>例

.NET Framework コレクション クラスの多くに付属の<xref:System.Collections?displayProperty=fullName>名前空間。 これらのコレクションのほとんどの操作の種類のオブジェクトの<xref:System.Object?displayProperty=fullName>します。 これにより、値の型も、.NET Framework のすべての型から派生するために、任意の型を格納するコレクション<xref:System.Object?displayProperty=fullName>します。 ただし、これにはこの方法の 2 つの欠点があります。

最初に、コレクションは、整数などの値型に格納する場合、値する必要がありますをコレクションに追加される前となります値がコレクションから取得されたときにします。 これらは、負荷の高い操作です。

次に、コレクションに追加できる種類を制御する方法はありません。 整数および文字列を同じコレクションに追加する場合でも、これが意図されたものでない可能性があります。 そのため、コードがタイプ セーフで、確認する必要がコレクションから取得した型が実際にあるものが必要です。

次のコード例では、ジェネリックより前に、の .NET Framework コレクションの 2 つの主な欠点を示します。

```cpp
// perf_pre_generics.cpp
// compile with: /clr

using namespace System;
using namespace System::Collections;

int main()
{
    // This Stack can contain any type.
    Stack ^s = gcnew Stack();

    // Push an integer to the Stack.
    // A boxing operation is performed here.
    s->Push(7);

    // Push a String to the same Stack.
    // The Stack now contains two different data types.
    s->Push("Seven");

    // Pop the items off the Stack.
    // The item is returned as an Object, so a cast is
    // necessary to convert it to its proper type.
    while (s->Count> 0)
    {
        Object ^o = s->Pop();
        if (o->GetType() == Type::GetType("System.String"))
        {
            Console::WriteLine("Popped a String: {0}", (String ^)o);
        }
        else if (o->GetType() == Type::GetType("System.Int32"))
        {
            Console::WriteLine("Popped an int: {0}", (int)o);
        }
        else
        {
            Console::WriteLine("Popped an unknown type!");
        }
    }
}
```

```Output
Popped a String: Seven
Popped an int: 7
```

## <a name="example"></a>例

新しい<xref:System.Collections.Generic?displayProperty=fullName>名前空間では、同じコレクションで見つかったの多くが含まれる、<xref:System.Collections?displayProperty=fullName>をジェネリック型パラメーターを受け入れるように変更されたが、名前空間。 これにより、非ジェネリック コレクションの 2 つの欠点: ボックス化と、コレクションに格納される値型と型を指定することができないのボックス化解除します。 2 つのコレクションでの操作は同じです。インスタンス化する方法のみが異なります。

ジェネリックを使用するこの例ではこれまでに記述例を比較<xref:System.Collections.Generic.Stack%601>コレクション。 頻繁にアクセスされる大規模なコレクションでこの例のパフォーマンスは、前の例よりもかなり大きいになります。

```cpp
// perf_post_generics.cpp
// compile with: /clr

#using <System.dll>

using namespace System;
using namespace System::Collections::Generic;

int main()
{
    // This Stack can only contain integers.
    Stack<int> ^s = gcnew Stack<int>();

    // Push an integer to the Stack.
    // A boxing operation is performed here.
    s->Push(7);
    s->Push(14);

    // You can no longer push a String to the same Stack.
    // This will result in compile time error C2664.
    //s->Push("Seven");

    // Pop an item off the Stack.
    // The item is returned as the type of the collection, so no
    // casting is necessary and no unboxing is performed for
    // value types.
    int i = s->Pop();
    Console::WriteLine(i);

    // You can no longer retrieve a String from the Stack.
    // This will result in compile time error C2440.
    //String ^str = s->Pop();
}
```

```Output
14
```

## <a name="see-also"></a>関連項目

[ジェネリック](../windows/generics-cpp-component-extensions.md)