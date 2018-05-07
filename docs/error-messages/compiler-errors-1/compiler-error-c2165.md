---
title: コンパイラ エラー C2165 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2165
dev_langs:
- C++
helpviewer_keywords:
- C2165
ms.assetid: b108313b-b8cb-4dce-b2ec-f2b31c9cdc87
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db8d434993ad913efca3fdff58fb7ed9cc0715e5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2165"></a>コンパイラ エラー C2165
'keyword' : データへのポインターは変更できません  
  
 `__stdcall`、 `__cdecl`、または `__fastcall` キーワードはデータへのポインターを変更しようとしています。  
  
 次の例では C2165 が生成されます。  
  
```  
// C2165.cpp  
// compile with: /c  
char __cdecl *p;   // C2165  
char *p;   // OK  
```