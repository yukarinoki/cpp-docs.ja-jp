---
title: コンパイラ エラー C2061 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2061
dev_langs:
- C++
helpviewer_keywords:
- C2061
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d4d4b018dbab16e8e376a3331a85d0f1b1004f5d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2061"></a>コンパイラ エラー C2061
構文エラー: 識別子 'identifier'  
  
 コンパイラは、ことが想定されている識別子を検出します。 確認して`identifier`が宣言されているは、使用する前にします。  
  
 初期化子は、かっこで囲むことがあります。 この問題を避けるためには、宣言子をかっこで囲みますまたはやすく、`typedef`です。  
  
 コンパイラが、クラス テンプレート引数として式を検出したときに、このエラーを発生する可能性がありますも使用して[typename](../../cpp/typename.md)これは、型をコンパイラに指示します。  
  
 次の例では、C2061 が生成されます。  
  
```  
// C2061.cpp  
// compile with: /c  
template < A a >   // C2061  
// try the following line instead  
// template < typename b >  
class c{};  
```  
  
 C2061 は、インスタンス名を渡す場合に発生する可能性が[typeid](../../windows/typeid-cpp-component-extensions.md):  
  
```  
// C2061b.cpp  
// compile with: /clr  
ref struct G {  
   int i;  
};  
  
int main() {  
   G ^ pG = gcnew G;  
   System::Type ^ pType = typeid<pG>;   // C2061  
   System::Type ^ pType2 = typeid<G>;   // OK  
}  
```