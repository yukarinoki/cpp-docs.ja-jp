---
title: '方法: ジェネリック (Visual C) でパフォーマンスを向上させる |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- performance, C++
- Visual C++, performance
- Visual C++, generics
- generics [C++], performance
ms.assetid: f14a175b-301f-46cc-86e4-c82d35f9aa3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: da74cce5f41c3399fb102180cfdfe8c1215c8bf9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877567"
---
# <a name="how-to-improve-performance-with-generics-visual-c"></a>方法: ジェネリックを使用してパフォーマンスを改善する (Visual C++)
ジェネリック型パラメーターに基づく再利用可能なコードを作成できます。 型パラメーターの実際の型は、クライアント コードで呼び出されるまで延期されます。 ジェネリックの詳細については、次を参照してください。[ジェネリック](../windows/generics-cpp-component-extensions.md)です。  
  
 この記事では、ジェネリックの利用コレクションを使用するアプリケーションのパフォーマンスを向上させる方法について説明します。  
  
## <a name="example"></a>例  
 .NET Framework が付属してコレクション クラスの多く、<xref:System.Collections?displayProperty=fullName>名前空間。 これらのコレクションのほとんどの操作の種類のオブジェクトの<xref:System.Object?displayProperty=fullName>します。 これにより、値の型でも、.NET Framework のすべての型から派生するために、任意の型を格納するコレクション<xref:System.Object?displayProperty=fullName>です。 ただしは、この方法を次の 2 つの欠点があります。  
  
 場合は、コレクションは、整数などの値の型を格納するが、値必要があるをコレクションに追加される前にボックス化、値がコレクションから取得されたときにボックス化解除します。 これらは、負荷の高い操作です。  
  
 次に、コレクションに追加できる種類を制御する方法はありません。 整数および文字列を同じコレクションに追加する場合でも、これはおそらくありません意図するものとします。 そのため、ために、コードがタイプ セーフであるに、コレクションから取得した型が実際にある想定された事項を確認する必要があります。  
  
 次のコード例では、ジェネリックの前に .NET Framework のコレクションの 2 つの主な欠点を示します。  
  
```  
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
 新しい<xref:System.Collections.Generic?displayProperty=fullName>多くについては、同じコレクションの名前空間が含まれています、<xref:System.Collections?displayProperty=fullName>名前空間が、ジェネリック型パラメーターを受け入れるように変更されました。 これにより、非ジェネリック コレクションの 2 つの欠点: ボックス化と、コレクションに格納される値の型と型を指定することができないのボックス化解除します。 2 つのコレクションでの操作は同じです。インスタンス化方法でのみが異なります。  
  
 この例で、ジェネリックを使用する上記の記述の例を比較<xref:System.Collections.Generic.Stack%601>コレクション。 頻繁にアクセスする大規模なコレクション、この例のパフォーマンスが前の例よりも大幅に大きくなります。  
  
```  
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