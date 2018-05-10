---
title: BSCMAKE エラー BK1506 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1506
dev_langs:
- C++
helpviewer_keywords:
- BK1506
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e19ec77818c8017387519b03e400c09d47021bc5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="bscmake-error-bk1506"></a>BSCMAKE エラー BK1506
ファイル 'filename' を開くことができません [: 理由]  
  
 BSCMAKE では、ファイルを開くことができません。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  別のプロセスによってロックされているファイルです。 場合`reason`という**権限が拒否されました**、ファイル ブラウザーを使用することがあります。 [参照] ウィンドウを閉じて、ビルドを再試行してください。  
  
2.  ディスクがいっぱいです。  
  
3.  ハードウェア エラーです。  
  
4.  指定された出力ファイルは、同じ名前の既存のサブフォルダーがします。