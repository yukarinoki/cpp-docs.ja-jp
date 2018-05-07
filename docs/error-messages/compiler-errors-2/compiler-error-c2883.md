---
title: コンパイラ エラー C2883 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2883
dev_langs:
- C++
helpviewer_keywords:
- C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc3119db27127521f5078a5753bb82c82da381ed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2883"></a>コンパイラ エラー C2883
'name': 関数宣言が 'identifier' を使用して宣言によって導入されると競合しています  
  
 関数を複数回定義しようとするとします。 最初の定義が、名前空間から行われた、`using`宣言します。 2 つ目は、ローカルの定義をでした。  
  
 次の例では、C2883 が生成されます。  
  
```  
// C2883.cpp  
namespace A {  
   void z(int);  
}  
  
int main() {  
   using A::z;  
   void z(int);   // C2883  z is already defined  
}  
```