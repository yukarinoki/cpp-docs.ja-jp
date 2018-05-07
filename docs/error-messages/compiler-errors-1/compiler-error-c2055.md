---
title: コンパイラ エラー C2055 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2055
dev_langs:
- C++
helpviewer_keywords:
- C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f16d9c3948c0211da69142f1b9c7c1a6a32d8c37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2055"></a>コンパイラ エラー C2055
型リストではなく、仮パラメーター リストが必要です。  
  
 関数の定義には、仮パラメーター リストの代わりにパラメーターの型リストが含まれています。 ANSI C には、void または、省略記号でない限り、名前を指定する仮パラメーターが必要です (`...`)。  
  
 次の例では、C2055 が生成されます。  
  
```  
// C2055.c  
// compile with: /c  
void func(int, char) {}  // C2055  
void func (int i, char c) {}   // OK  
```