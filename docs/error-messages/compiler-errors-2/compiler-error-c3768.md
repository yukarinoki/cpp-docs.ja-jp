---
title: コンパイラ エラー C3768 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3768
dev_langs:
- C++
helpviewer_keywords:
- C3768
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3634ecf3eb1417095cce144706838113b5ad2a0e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3768"></a>コンパイラ エラー C3768
純粋マネージ コードで仮想 vararg 関数のアドレスを取得することはできません。  
  
 **/Clr: 純粋な**コンパイラ オプションは Visual Studio 2015 で推奨されなくなりました。  
  
 コンパイルするときに`/clr:pure`、仮想のアドレスを取得することはできません`vararg`関数。  
  
## <a name="example"></a>例  

 次の例では、C3768 が生成されます。  
  
```  
// C3768.cpp  
// compile with: /clr:pure  
struct A  
{  
   virtual void f(...);  
};  
  
int main()  
{  
   &(A::f);   // C3768  
}  
```