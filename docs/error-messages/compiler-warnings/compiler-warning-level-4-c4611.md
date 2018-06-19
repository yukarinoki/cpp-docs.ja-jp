---
title: コンパイラの警告 (レベル 4) C4611 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4611
dev_langs:
- C++
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5946c10b5e0e0e7e08f1ee37c77120896937adb1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293154"
---
# <a name="compiler-warning-level-4-c4611"></a>コンパイラの警告 (レベル 4) C4611
'function' と C++ オブジェクト デストラクション間の対話は互換性がありません。  
  
 含む関数の一部のプラットフォームで**キャッチ**スコープ外と破棄の C++ オブジェクトのセマンティクスをサポートしていません。  
  
 予期しない動作を回避するのには使用しないでください**キャッチ**をコンス トラクターとデストラクターを持つ関数でします。  
  
 この警告は回だけです。参照してください[pragma 警告](../../preprocessor/warning.md)です。