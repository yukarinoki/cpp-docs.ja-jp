---
title: コンパイラ エラー C2450 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2450
dev_langs:
- C++
helpviewer_keywords:
- C2450
ms.assetid: 929f1c06-8774-468b-be2a-f428757875a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db8702703337d01bf8073dd31bcb54d876010c10
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225395"
---
# <a name="compiler-error-c2450"></a>コンパイラ エラー C2450
型 'type' の switch 式は無効です。  
  
 `switch`式に無効な型に評価します。 整数型またはクラス型に評価される必要がありますが、整数型への明確な変換を持つ。 ユーザー定義型に評価されて、変換演算子を指定してください。  
  
 次の例では、C2450 が生成されます。  
  
```  
// C2450.cpp  
class X {  
public:  
   int i;  
} x;  
  
class Y {  
public:  
   int i;  
   operator int() { return i; }   // conversion operator  
} y;  
  
int main() {  
   int j = 1;  
   switch ( x ) {   // C2450, x is not type int  
   // try the following line instead  
   // switch ( y ) {  
      default:  ;  
   }  
}  
```