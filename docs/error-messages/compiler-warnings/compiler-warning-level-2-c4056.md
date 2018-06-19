---
title: コンパイラの警告 (レベル 2) C4056 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4056
dev_langs:
- C++
helpviewer_keywords:
- C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6bf5a5855d0b4291105826679e2ae81ed6d69e5f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290567"
---
# <a name="compiler-warning-level-2-c4056"></a>コンパイラの警告 (レベル 2) C4056
浮動小数点定数演算でオーバーフローしました。  
  
 浮動小数点定数演算では、許容される最大値を超える結果が生成されます。  
  
 この警告は、定数演算中に実行されるコンパイラの最適化によって可能性があります。 場合はそれが停止してからの最適化をオフにするときに安全にこの警告は無視できます ([/Od](../../build/reference/od-disable-debug.md))。  
  
 次の例では、C4056 が生成されます。  
  
```  
// C4056.cpp  
// compile with: /W2 /LD  
#pragma warning (default : 4056)  
float fp_val = 1.0e300 * 1.0e300;   // C4056  
```