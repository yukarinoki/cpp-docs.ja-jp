---
title: コンパイラ エラー C2395 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2395
dev_langs:
- C++
helpviewer_keywords:
- C2395
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 411a8d62de801591ff6a90a7bf74f3b2cfe67c7a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225431"
---
# <a name="compiler-error-c2395"></a>コンパイラ エラー C2395
'your_type::operator'op'' : CLR または WinRT 演算子が無効です。 少なくとも 1 つのパラメーターが次の型である必要があります: 'T'、'T%'、'T&'、'T^'、'T^%'、'T^&' (T = 'your_type')。  
  
 Windows ランタイムまたはマネージ型の演算子に、演算子の戻り値の型と同じ型を持つ 1 つ以上のパラメーターがありません。  
  
 次の例では、C2395 を生成し、その修正方法を示しています。  
  
```  
// C2395.cpp  
// compile with: /clr /c  
value struct V {  
   static V operator *(int i, char c);   // C2395  
  
   // OK  
   static V operator *(V v, char c);  
   // or  
   static V operator *(int i, V& rv);  
};  
```