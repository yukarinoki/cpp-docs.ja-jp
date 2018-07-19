---
title: コンパイラ エラー C3891 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3891
dev_langs:
- C++
helpviewer_keywords:
- C3891
ms.assetid: 6e1a9458-97f5-4580-bc0f-aa97a1bfd20d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 021f19d50d0b83c9526956684737ad23fea9fb01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272709"
---
# <a name="compiler-error-c3891"></a>コンパイラ エラー C3891
'var': リテラル データ メンバーは、左辺値として使用できません  
  
 A[リテラル](../../windows/literal-cpp-component-extensions.md)変数は const、および宣言で初期化された後、その値を変更することはできません。  
  
 次の例では、C3891 が生成されます。  
  
```  
// C3891.cpp  
// compile with: /clr  
ref struct Y1 {  
   literal int staticConst = 9;  
};  
  
int main() {  
   Y1::staticConst = 0;   // C3891  
}  
```