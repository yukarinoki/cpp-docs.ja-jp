---
title: コンパイラの警告 (レベル 1) C4420 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4420
dev_langs:
- C++
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98336a30e7174b62df48e93a04ba9ee7ddcc919a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4420"></a>コンパイラの警告 (レベル 1) C4420
'operator': 演算子は使用できません代わりに 'operator' を使用する。実行時のチェックは中途終了される可能性があります。  
  
 使用するときに、この警告が生成された、 [/rtcv させる](../../build/reference/rtc-run-time-error-checks.md)(新規/削除の確認をベクトル) ベクター フォームが存在しない場合。 この例では、非ベクター形式が使用されます。  
  
 /Rtcv を正しく動作させるためには、コンパイラは常に呼び出すベクトル形式の[新しい](../../cpp/new-operator-cpp.md)/[削除](../../cpp/delete-operator-cpp.md)ベクター構文を使用した場合。