---
title: 致命的なエラー C1054 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1054
dev_langs:
- C++
helpviewer_keywords:
- C1054
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a9daac4944c57dbf08fe0ebcbc95993a97838585
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198899"
---
# <a name="fatal-error-c1054"></a>致命的なエラー C1054
コンパイラの制限: 初期化子の入れ子が深すぎます。  
  
 コードは、(初期化されている型の組み合わせに応じて、10 ~ 15 レベル) の初期化子の入れ子の上限を超えています。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  入れ子の削減に初期化されているデータ型を簡略化します。  
  
2.  宣言の後に別のステートメントで変数を初期化します。