---
title: コンパイラ エラー C3199 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3199
dev_langs:
- C++
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cddad2218e81603f59cad51e3a684303e144171e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3199"></a>コンパイラ エラー C3199
無効な浮動小数点プラグマの使用: 例外は precise でないモードでサポートされていません  
  
 [Float_control](../../preprocessor/float-control.md)プラグマは、下の浮動小数点例外モデルを指定に使用された、 [/fp](../../build/reference/fp-specify-floating-point-behavior.md)以外に設定 **/fp: 正確な**します。  
  
 次の例では、C3199 が生成されます。  
  
```  
// C3199.cpp  
// compile with: /fp:fast  
#pragma float_control(except, on)   // C3199  
```