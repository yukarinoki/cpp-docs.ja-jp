---
title: コンパイラの警告 (レベル 1) C4326 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4326
dev_langs:
- C++
helpviewer_keywords:
- C4326
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 838c79d6ba897905dad18788adc5ee682ff2fa2c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4326"></a>コンパイラの警告 (レベル 1) C4326
'function' の戻り値の型が 'type2' ではなく ' type1' をする必要があります。  
  
 関数が以外の型を返しました***type1***です。 たとえばを使用して[/Za](../../build/reference/za-ze-disable-language-extensions.md)、main が返されませんでした、`int`です。  
  
 次の例では、C4326 が生成されます。  
  
```  
// C4326.cpp  
// compile with: /Za /W1  
char main()  
{   // C4326 try int main  
}  
```