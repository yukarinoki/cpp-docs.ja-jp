---
title: コンパイラの警告 (レベル 4) C4208 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4208
dev_langs:
- C++
helpviewer_keywords:
- C4208
ms.assetid: 5cb0a36e-3fb5-422f-a5f9-e40b70776c27
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b61f8b0a6a0ac61982bee79abb81f083d40a48f1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4208"></a>コンパイラの警告 (レベル 4) C4208
使用される標準の拡張機能: delete [exp] - exp を評価が無視されます  
  
 Microsoft 拡張機能 (/Ze) と角かっこ内の値を使用して配列を削除することができます、 [delete 演算子](../../cpp/delete-operator-cpp.md)です。 値は無視されます。  
  
```  
// C4208.cpp  
// compile with: /W4  
int main()  
{  
   int * MyArray = new int[18];  
   delete [18] MyArray;      // C4208  
   MyArray = new int[18];  
   delete [] MyArray;        // ok  
}  
```  
  
 このような値は ANSI 互換では使用できません ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。