---
title: コンパイラの警告 (レベル 2 および 3) C4008 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4008
dev_langs:
- C++
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4cdc88f222f9e5ce3829a63c131c955ce2abdd7d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>コンパイラの警告 (レベル 2 および 3) C4008
'identifier': 'attribute' 属性は無視されました  
  
 コンパイラは、関数 (レベル 3 警告) またはデータ (レベル 2 警告) の `__fastcall`、 **静的**、または **インライン** 属性を無視しました。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  データを伴う`__fastcall` 属性。  
  
2.  **メイン** 関数の **静的** または **インライン** 属性。