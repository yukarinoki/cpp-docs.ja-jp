---
title: コンパイラ エラー C2665 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2665
dev_langs:
- C++
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18cc99d6ea0a45e7c096a13cfe57dc841ca351bf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2665"></a>コンパイラ エラー C2665
'function': number1 オーバー ロードのいずれも型 'type' からパラメーター number2 を変換することができます  
  
 オーバー ロードされた関数のパラメーターは、必要な型に変換できません。  考えられる解決策:  
  
-   変換演算子を指定します。  
  
-   明示的な変換を使用します。  
  
## <a name="example"></a>例  
 次の例では、C2665 を生成します。  
  
```  
// C2665.cpp  
void func(short, char*){}  
void func(char*, char*){}  
  
int main() {  
   func(0, 1);   // C2665  
   func((short)0, (char*)1);   // OK  
}  
```