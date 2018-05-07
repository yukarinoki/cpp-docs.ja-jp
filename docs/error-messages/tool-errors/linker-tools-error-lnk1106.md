---
title: リンカ ツール エラー LNK1106 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1106
dev_langs:
- C++
helpviewer_keywords:
- LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3dedaa2bd500b11f06f9cfa98802fdd6ca84534
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1106"></a>リンカ ツール エラー LNK1106
無効なファイルまたはディスクがいっぱいです: の場所にシークできません。  
  
 ツールの読み取りまたは書き込みでしたいない`location`メモリ マップト ファイルにします。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  ディスクがいっぱいです。  
  
     領域を解放し、リンクを再度クリックします。  
  
2.  ネットワーク経由でリンクしようとしています。  
  
     いくつかのネットワークは、リンカーによって使用されるメモリ マップト ファイルを完全にはサポートしていません。 ローカル ディスクにリンクしてください。  
  
3.  ディスク上の不良ブロックです。  
  
     ディスクのハードウェアとオペレーティング システムでは、このようなエラーが検出が必要、ディスク チェック プログラムを実行することがあります。  
  
4.  ヒープ領域不足。  
  
     参照してください[C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md)詳細についてはします。