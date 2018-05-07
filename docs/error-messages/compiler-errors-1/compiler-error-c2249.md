---
title: コンパイラ エラー C2249 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2249
dev_langs:
- C++
helpviewer_keywords:
- C2249
ms.assetid: bdd6697c-e04b-49b9-8e40-d9eb6d74f2b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6a4d5ab3de2a3bd04ba2a2bb9c90ebe8f04b3e67
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2249"></a>コンパイラ エラー C2249
'member': アクセス メンバーにアクセス可能なパスを仮想ベース 'class' で宣言されていません。  
  
 `member` 、Nonpublic から継承された`virtual`基底クラスまたは構造体。  
  
## <a name="example"></a>例  
 次の例では、C2249 を生成します。  
  
```  
// C2249.cpp  
class A {  
private:  
   void privFunc( void ) {};  
public:  
   void pubFunc( void ) {};  
};  
  
class B : virtual public A {} b;  
  
int main() {  
   b.privFunc();    // C2249, private member of A  
   b.pubFunc();    // OK  
}  
```  
  
## <a name="example"></a>例  
 C2249 は、C++ 標準ライブラリの別のストリームにストリームを割り当てようとする場合にも発生することができます。  次の例では、C2249 を生成します。  
  
```  
// C2249_2.cpp  
#include <iostream>  
using namespace std;  
int main() {  
   cout = cerr;   // C2249  
   #define cout cerr;   // OK  
}  
```