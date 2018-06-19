---
title: コンパイラ エラー C2990 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2990
dev_langs:
- C++
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 669cfcd1e9a715b247c9264856e8877275d6407c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33243030"
---
# <a name="compiler-error-c2990"></a>コンパイラ エラー C2990
'class': 非クラス型既にクラス型として宣言されています。  
  
 非ジェネリックまたはテンプレート クラスは、ジェネリックまたはテンプレート クラスを再定義します。 競合のヘッダー ファイルを確認してください。  
  
 次の例では、C2990 が生成されます。  
  
```  
// C2990.cpp  
// compile with: /c  
template <class T>  
class C{};  
class C{};   // C2990  
```  
  
 C2990 は、ジェネリックを使用するときにも発生することができます。  
  
```  
// C2990b.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct GC;  
  
ref struct GC {};   // C2990  
```  
  
 C2990 も発生する可能性が重大な変更について、Visual C コンパイラで Visual C 2005 です。コンパイラは、今すぐ、同じ種類の複数の宣言がテンプレートの仕様と一致させることが必要です。  
  
 次の例では、C2990 が生成されます。  
  
```  
// C2990c.cpp  
// compile with: /c  
template<class T>  
class A;  
  
template<class T>  
struct A2 {  
   friend class A;   // C2990  
};  
  
// OK  
template<class T>  
struct B {  
   template<class T>  
   friend class A;  
};  
```