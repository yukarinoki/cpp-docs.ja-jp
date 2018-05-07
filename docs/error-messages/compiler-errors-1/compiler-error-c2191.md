---
title: コンパイラ エラー C2191 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2191
dev_langs:
- C++
helpviewer_keywords:
- C2191
ms.assetid: 051b8350-e5de-4f51-ab6e-96d32366bcef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aa4b590b494355450909032c78822553004beddc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2191"></a>コンパイラ エラー C2191
最初よりも長い 2 番目のパラメーター リスト  
  
 C の関数は、長いパラメーター リストで 2 番目の時間を宣言されました。 C では、オーバー ロードされた関数はサポートされません。  
  
## <a name="example"></a>例  
 次の例では、C2191 が生成されます。  
  
```  
// C2191.c  
// compile with: /Za /c  
void func( int );  
void func( int, float );   // C2191 different parameter list  
void func2( int, float );   // OK  
```