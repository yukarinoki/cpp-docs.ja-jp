---
title: コンパイラ エラー C3225 |Microsoft ドキュメント
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
ms.openlocfilehash: 8f9f6691ddacf6b3c1347b9fd4cac134433741a6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33250580"
---
# <a name="compiler-error-c3225"></a>コンパイラ エラー C3225
'arg' のジェネリック型引数は 'type' をすることはできません、値型であるまたはハンドル型にする必要があります。  
  
 ジェネリック型引数は、適切な型でした。  
  
 詳細については、「[ジェネリック](../../windows/generics-cpp-component-extensions.md)」を参照してください。  
  
## <a name="example"></a>例  
 ネイティブ型を持つジェネリック型をインスタンス化することはできません。 次の例では、C3225 を生成します。  
  
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
 次の例では、c# を使用してコンポーネントを作成します。 制約では、ジェネリック型が値型でインスタンス化できますのみ指定されることを確認します。  
  
```  
// C3225_b.cs  
// compile with: /target:library  
// a C# program  
public class MyList<T> where T: struct {}  
```  
  
## <a name="example"></a>例  
 このサンプルを使用して c# でコンポーネントを作成して MyList のみが有効な制約に違反する以外の値の型でインスタンス化される<xref:System.Nullable>です。 次の例では、C3225 を生成します。  
  
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