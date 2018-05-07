---
title: コンパイラ エラー C3865 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3865
dev_langs:
- C++
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99a872d4cf7ed285a0798461c77adf904cfa3e71
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3865"></a>コンパイラ エラー C3865
'calling_convention': ネイティブ メンバー関数でのみ使用できます  
  
 グローバル関数となった関数またはマネージ メンバー関数の呼び出し規約が使用されました。 呼び出し規約は、ネイティブ (マネージ) メンバー関数でのみ使用できます。  
  
 詳細については、次を参照してください。[呼び出し規約](../../cpp/calling-conventions.md)です。  
  
 次の例では、C3865 が生成されます。  
  
```  
// C3865.cpp  
// compile with: /clr  
// processor: x86  
void __thiscall Func(){}   // C3865  
  
// OK  
struct MyType {  
   void __thiscall Func(){}  
};  
```