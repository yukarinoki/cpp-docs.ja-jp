---
title: コンパイラ エラー C2657 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2657
dev_langs:
- C++
helpviewer_keywords:
- C2657
ms.assetid: f7cf29a9-684a-4605-9469-ecfee9ba4b03
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70814ce7423bee3147f68d6298babc10eeac56fb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2657"></a>コンパイラ エラー C2657
' クラス:: *' ステートメントの先頭が見つかりました (を忘れましたか種類を指定しますか?)  
  
 メンバーへのポインターの識別子を持つ行を開始しました。  
  
 このエラーは、メンバーへのポインターの宣言で型指定子がありませんが発生することができます。  
  
 次の例では、C2657 が生成されます。  
  
```  
// C2657.cpp  
class C {};  
int main() {  
   C::* pmc1;        // C2657  
   int C::* pmc2;   // OK  
}  
```