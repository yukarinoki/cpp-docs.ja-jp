---
title: コンパイラ エラー C2977 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2977
dev_langs:
- C++
helpviewer_keywords:
- C2977
ms.assetid: 3c4218e0-5d03-4a2b-b757-c507c35f3542
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a00da68007834b85846fedf07d2466f1448a5b45
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33242214"
---
# <a name="compiler-error-c2977"></a>コンパイラ エラー C2977
'identifier': 型引数が多すぎます  
  
 ジェネリックまたはテンプレートの実引数が多すぎます。 ジェネリックまたはテンプレート宣言を確認して、正しい数のパラメーターを調べてください。  
  
 次の例では C2977 が生成されます。  
  
```  
// C2977.cpp  
// compile with: /c  
template<class T, int i>   
class MyClass {};  
  
template MyClass< int , 1, 1 >;   // C2977  
template MyClass< int , 1 >;   // OK  
```  
  
 C2977 は、ジェネリックを使用しているときも発生する場合があります。  
  
```  
// C2977b.cpp  
// compile with: /clr  
// C2977 expected  
generic <class T, class U>   
void f(){}  
  
generic <class T>   
ref struct GC1 {};  
  
int main() {  
   // Delete the following 2 lines to resolve.  
   GC1<int, char> ^ pgc1;  
   f<int,int,int>();  
  
   // OK  
   GC1<int> ^ pgc1;  
   f<int, int>();  
}  
```