---
title: コンパイラ エラー C3395 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3395
dev_langs:
- C++
helpviewer_keywords:
- C3395
ms.assetid: 26a9ebc9-ed97-47ce-b436-19aa2bcf6e50
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 202162ecac8907852ca621599f5306884e59ae98
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3395"></a>コンパイラ エラー C3395
'function': 方式を伴う関数に適用できません、 \__clrcall 呼び出し規約  
  
 `__declspec(dllexport)` および[_ _clrcall](../../cpp/clrcall.md)は互換性がありません。  詳細については、次を参照してください。 [dllexport、dllimport](../../cpp/dllexport-dllimport.md)です。  
  
 次の例では、C3395 が生成されます。  
  
```  
// C3395.cpp  
// compile with: /clr /c  
  
__declspec(dllexport) void __clrcall Test(){}   // C3395  
void __clrcall Test2(){}   // OK  
__declspec(dllexport) void Test3(){}   // OK  
```