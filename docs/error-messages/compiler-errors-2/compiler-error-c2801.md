---
title: コンパイラ エラー C2801 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2801
dev_langs:
- C++
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f68b3f575fcb8b909f58ac2ffbcaca26580279da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2801"></a>コンパイラ エラー C2801
'operator 演算子' は非静的メンバーである必要があります。  
  
 非静的メンバーとしてのみ、次の演算子はオーバー ロードできます。  
  
-   割り当て `=`  
  
-   クラス メンバーへのアクセス `->`  
  
-   添字演算子 `[]`  
  
-   関数呼び出し `()`  
  
 C2801 エラーの原因が考えられます。  
  
-   オーバー ロードされた演算子は、クラス、構造体、または共用体のメンバーではありません。  
  
-   オーバー ロードされた演算子が宣言されて`static`です。  
  
-   次の例では、C2801 が生成されます。  
  
```  
// C2801.cpp  
// compile with: /c  
operator[]();   // C2801 not a member  
class A {  
   static operator->();   // C2801 static  
   operator()();   // OK  
};  
```