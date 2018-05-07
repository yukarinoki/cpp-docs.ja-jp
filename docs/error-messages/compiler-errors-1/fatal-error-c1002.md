---
title: 致命的なエラー C1002 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1002
dev_langs:
- C++
helpviewer_keywords:
- C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c63a8d399b3e8c781694d89825e7898fd1db4639
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1002"></a>致命的なエラー C1002
パス 2 の実行中に、ヒープ領域を使い果たしました。  
  
 コンパイラはおそらくシンボルまたは複雑な式が多すぎるとプログラムにより、2 番目のパスの中に動的メモリの領域不足になりました。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  ソース ファイルをいくつかの小さなファイルに分割します。  
  
2.  式を小さな部分に分割します。  
  
3.  その他のプログラムまたはメモリを消費するドライバーを削除します。