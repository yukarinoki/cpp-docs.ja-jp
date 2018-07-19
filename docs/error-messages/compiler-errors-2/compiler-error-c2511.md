---
title: コンパイラ エラー C2511 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2511
dev_langs:
- C++
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d97cbbd75d3b39b55ff640ed99e261ba349043d3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33199629"
---
# <a name="compiler-error-c2511"></a>コンパイラ エラー C2511
'identifier': オーバー ロード メンバー関数の 'class' に見つかりませんでした  
  
 指定されたパラメーターでは、関数のバージョンは宣言されていません。  以下の原因が考えられます。  
  
1.  不適切なパラメーターは、関数に渡されます。  
  
2.  間違った順序でパラメーターが渡されます。  
  
3.  パラメーター名のスペルが間違っています。  
  
 次の例では、C2511 が生成されます。  
  
```  
// C2511.cpp  
// compile with: /c  
class C {  
   int c_2;  
   int Func(char *, char *);  
};  
  
int C::Func(char *, char *, int i) {   // C2511  
// try the following line instead  
// int C::Func(char *, char *) {  
   return 0;  
}  
```