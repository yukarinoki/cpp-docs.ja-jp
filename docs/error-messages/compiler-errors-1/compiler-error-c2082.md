---
title: コンパイラ エラー C2082 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2082
dev_langs:
- C++
helpviewer_keywords:
- C2082
ms.assetid: 87a6d442-157c-46e8-9bff-8388f8338ae0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbbaa7f59b8853dd1b1ad0f2e839b00086db8eac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2082"></a>コンパイラ エラー C2082
仮パラメーター 'identifier' が再定義されました  
  
 関数の仮パラメーターが、関数本体の中で再宣言されています。 エラーを解決するには、再定義を削除します。  
  
 次の例では C2082 が生成されます。  
  
```  
// C2082.cpp  
void func(int i) {  
   int i;   // C2082  
   int ii;   // OK  
}  
```