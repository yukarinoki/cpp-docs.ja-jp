---
title: コンパイラ エラー C2079 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2079
dev_langs:
- C++
helpviewer_keywords:
- C2079
ms.assetid: ca58d6d5-eccd-40b7-ba14-c003223c5bc7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b29200be08c10dcfaeb178941309c6f3aec6ff9e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33168033"
---
# <a name="compiler-error-c2079"></a>コンパイラ エラー C2079
'identifier' が定義されていないクラス/構造体/共用体 'name' を使用します。  
  
 指定された識別子は、未定義のクラス、構造体、または共用体です。  
  
 このエラーは、無名共用体を初期化することによって発生することができます。  
  
 次の例では、C2079 が生成されます。  
  
```  
// C2079.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   std::ifstream g;   // C2079  
}  
```  
  
 考えられる解決方法:  
  
```  
// C2079b.cpp  
// compile with: /EHsc  
#include <fstream>  
int main( ) {  
   std::ifstream g;  
}  
```  
  
 C2079 は、スコープ内だけでは、宣言型のスタックにオブジェクトを宣言しようとする場合にも発生することができます。  
  
```  
// C2079c.cpp  
class A;  
  
class B {  
   A a;   // C2079  
};  
  
class A {};  
```  
  
 考えられる解決方法:  
  
```  
// C2079d.cpp  
// compile with: /c  
class A;  
class C {};  
  
class B {  
   A * a;  
   C c;  
};  
  
class A {};  
```