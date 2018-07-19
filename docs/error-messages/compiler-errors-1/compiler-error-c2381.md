---
title: コンパイラ エラー C2381 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2381
dev_langs:
- C++
helpviewer_keywords:
- C2381
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7bd5f5edcf95144333524c41b803c24b728a621f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225278"
---
# <a name="compiler-error-c2381"></a>コンパイラ エラー C2381
'function': 再定義されています。__declspec(noreturn) 異なります  
  
 関数が宣言されており、その定義が使用されますが、定義、 [noreturn](../../cpp/noreturn.md) `__declspec`修飾子です。 使用`noreturn`構成関数の再定義; 宣言と定義の使用に同意する必要があります。`noreturn`です。  
  
 次の例では、C2381 が生成されます。  
  
```  
// C2381.cpp  
// compile with: /c  
void f1();  
void __declspec(noreturn) f1() {}   // C2381  
void __declspec(noreturn) f2() {}   // OK  
```