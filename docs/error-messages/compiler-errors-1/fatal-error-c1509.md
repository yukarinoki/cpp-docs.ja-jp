---
title: 致命的なエラー C1509 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1509
dev_langs:
- C++
helpviewer_keywords:
- C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fec83f6b6138eacc613e560b9da4557079d6677d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198795"
---
# <a name="fatal-error-c1509"></a>致命的なエラー C1509
コンパイラの制限: 関数 'function' の例外ハンドラが多すぎます。 関数を簡略化します。  
  
 コードは、例外ハンドラーの状態 (32,768) 数の内部制限を超えています。  
  
 最も一般的な原因は、関数がクラスのユーザー定義変数および算術演算子の複雑な式が含まれているです。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  一時変数に共通部分式を割り当てることで式を簡略化します。  
  
2.  関数を小さな関数に分割します。