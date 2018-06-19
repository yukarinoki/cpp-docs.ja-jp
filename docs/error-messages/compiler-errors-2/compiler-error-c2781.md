---
title: コンパイラ エラー C2781 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2781
dev_langs:
- C++
helpviewer_keywords:
- C2781
ms.assetid: f29b9963-f55b-427c-8db6-50f37713df5a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa42627085494047e10644f86a938b9311cb1625
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33235522"
---
# <a name="compiler-error-c2781"></a>コンパイラ エラー C2781
'declaration': には少なくとも value1 引数 - value2 提供  
  
 変数パラメーター リストを持つ関数テンプレートが、引数が少なすぎます。  
  
 次の例では、C2781 が生成されます。  
  
```  
// C2781.cpp  
template<typename T>  
void f(T, T, ...){}  
  
int main() {  
   f(1);   // C2781  
  
   // try the following line instead  
   f(1,1);  
}  
```