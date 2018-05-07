---
title: コンパイラの警告 (レベル 4) C4481 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4481
dev_langs:
- C++
helpviewer_keywords:
- C4481
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aeef5f2121808c5444af942fac0e3b72919f2354
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4481"></a>コンパイラの警告 (レベル 4) C4481
使用される標準の拡張機能: オーバーライド指定子 'キーワード'  
  
 /Clr でも動作するオーバーライド指定子のいずれかの例では、C++ 標準に含まれていないキーワードが使用されました。  詳細については、次のトピックを参照してください。  
  
-   [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [オーバーライド指定子](../../windows/override-specifiers-cpp-component-extensions.md)  
  
## <a name="example"></a>例  
 次の例では、C4481 を生成します。  
  
```  
// C4481.cpp  
// compile with: /W4 /c  
class B {  
   virtual void f(unsigned);  
};  
  
class C : B {  
   void f(unsigned) override;   // C4481  
   void f2(unsigned);  
};  
```