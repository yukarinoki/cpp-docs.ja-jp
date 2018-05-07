---
title: コンパイラ エラー C3391 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3391
dev_langs:
- C++
helpviewer_keywords:
- C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28615d85eca534966a4d8b90cef20ea577e0d592
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3391"></a>コンパイラ エラー C3391
'type_arg': ジェネリック パラメーター 'param' のジェネリック 'generic_type' の無効な型引数が null 非許容値型にする必要があります  
  
ジェネリック型のインスタンス化が正しく行われませんでした。 型定義を確認してください。 詳細については、次を参照してください。<xref:System.Nullable>と[ジェネリック](../../windows/generics-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
C + におけるジェネリック型を作成するときにサポートされていない特定の制約を持つジェネリック型を含むコンポーネントを作成する C# の場合、次のサンプルを使用して + CLI です。 詳細については、「[型パラメーターの制約](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters)」を参照してください。  
  
```cs  
// C3391.cs  
// Compile by using: csc /target:library C3391.cs  
// a C# program  
public class GR<N>  
where N : struct {}  
```  
  
C3391.dll コンポーネントが利用できる場合、次の例には C3391 が生成されます。  
  
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