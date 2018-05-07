---
title: コンパイラ エラー C2507 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2507
dev_langs:
- C++
helpviewer_keywords:
- C2507
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82bd4fb028712093a44ada4ae58e97c2fbcf7eed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2507"></a>コンパイラ エラー C2507
'identifier': 基底クラスで virtual 修飾子が多すぎます  
  
 クラスまたは構造体として宣言されて`virtual`も複数回です。 1 つだけ`virtual`修飾子は、基本クラスの一覧の各クラスに対して使用できます。  
  
 次の例では、C2507 が生成されます。  
  
```  
// C2507.cpp  
// compile with: /c  
class A {};  
class B : virtual virtual public A {};   // C2507  
class C : virtual public A {};   // OK  
```