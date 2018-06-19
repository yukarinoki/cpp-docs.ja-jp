---
title: コンパイラ エラー C2703 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2703
dev_langs:
- C++
helpviewer_keywords:
- C2703
ms.assetid: 384295c3-643d-47ae-a9a6-865b3036aa84
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4cb6e011213250790fd4f8b60563be23cb8c5861
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230989"
---
# <a name="compiler-error-c2703"></a>コンパイラ エラー C2703
無効な _ _leave ステートメント  
  
 A`__leave`ステートメントは、内部になければなりません、`__try`ブロックします。  
  
 次の例では、C2703 が生成されます。  
  
```  
// C2703.cpp  
int main() {  
   __leave;   // C2703  
   __try {  
      // try the following line instead  
      __leave;  
   }  
   __finally {}  
}  
```