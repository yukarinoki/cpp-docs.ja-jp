---
title: コンパイラ エラー C2974 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2974
dev_langs:
- C++
helpviewer_keywords:
- C2974
ms.assetid: 1b444260-f2bf-48d7-ab1e-35573d8c4a0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12af6bcd61642d8563eb08888229aab6217b6085
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2974"></a>コンパイラ エラー C2974
無効な型引数 'number' 型が必要です。  
  
 ジェネリックまたはテンプレートの引数では、ジェネリックまたはテンプレート宣言が一致しません。 型は、山かっこ内で表示されます。 正しい型を検索するジェネリックまたはテンプレートの定義を確認します。  
  
 次の例では、C2974 が生成されます。  
  
```  
// C2974.cpp  
// C2974 expected  
template <class T>  
struct TC {};  
  
template <typename T>  
void tf(T){}  
  
int main() {  
   // Delete the following 2 lines to resolve  
   TC<1>* tc;  
   tf<"abc">("abc");  
  
   TC<int>* tc;  
   tf<const char *>("abc");  
}  
```  
  
 C2974 は、ジェネリックを使用するときにも発生することができます。  
  
```  
// C2974b.cpp  
// compile with: /clr  
// C2974 expected  
using namespace System;  
generic <class T>  
ref struct GCtype {};  
  
generic <typename T>  
void gf(T){}  
  
int main() {  
   // Delete the following 2 lines to resolve  
   GCtype<"a">^ gc;  
   gf<"a">("abc");  
  
   // OK  
   GCtype<int>^ gc;  
   gf<String ^>("abc");  
}  
```