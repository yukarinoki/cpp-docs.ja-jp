---
title: コンパイラ エラー C3392 |Microsoft ドキュメント
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
ms.openlocfilehash: 5e31c2b46c8b2688053bf02f40a2de6629632dd5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3392"></a>コンパイラ エラー C3392
'type_arg' : ジェネリック パラメーター 'param' (ジェネリック 'generic_type') の型引数が無効です。パブリックのパラメーターのないコンストラクターを含んでいなければなりません  
  
 ジェネリック型のインスタンス化が正しく行われませんでした。 型定義を確認してください。 詳細については、次を参照してください。[ジェネリック](../../windows/generics-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
C + におけるジェネリック型を作成するときにサポートされていない特定の制約を持つジェネリック型を含むコンポーネントを作成する C# の場合、次のサンプルを使用して + CLI です。 詳細については、「[型パラメーターの制約](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters)」を参照してください。  
  
```cs  
// C3392.cs  
// Compile by using: csc /target:library C3392.cs  
// a C# program  
public class GR<C, V, N>  
where C : class  
where V : struct  
where N : new() {}  
```  
  
C3392.dll コンポーネントが利用できる場合、次の例には C3392 が生成されます。  
  
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