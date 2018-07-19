---
title: コンパイラ エラー C2379 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2379
dev_langs:
- C++
helpviewer_keywords:
- C2379
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a1016bedfa9df0e9dfacb56734ee60397108d046
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198077"
---
# <a name="compiler-error-c2379"></a>コンパイラ エラー C2379
正式なパラメーター数が昇格するときに別の種類  
  
 指定されたパラメーターの型は互換性のある、既定値のプロモーション、前の宣言で型を使用します。 これは ANSI C ではエラー ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) および Microsoft の拡張機能と警告 (**/Ze**)。  
  
 次の例では、C2379 が生成されます。  
  
```  
// C2379.c  
// compile with: /Za  
void func();  
void func(char);   // C2379, char promotes to int  
```