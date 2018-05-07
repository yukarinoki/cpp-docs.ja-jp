---
title: リンカ ツール エラー LNK1201 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1201
dev_langs:
- C++
helpviewer_keywords:
- LNK1201
ms.assetid: 64c3f496-a428-4b54-981e-faa82ef9c8a1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ad83fecfe4df211cb7c5f301626454b5d2c9e47
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1201"></a>リンカ ツール エラー LNK1201
プログラム データベース 'filename' への書き込みエラーディスク領域の不足、無効なパス、または十分な特権の確認します。  
  
 リンクは、出力ファイルのプログラム データベース (PDB) に書き込めませんでした。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  ファイルが壊れています。 PDB ファイルと再リンクを削除します。  
  
2.  ファイルの書き込みにディスク領域が十分ではありません。  
  
3.  ドライブは、ネットワークの問題の原因として考えられます。  
  
4.  デバッガーは、リンクしようとしているプログラム上でアクティブです。  
  
5.  ヒープ領域不足。  参照してください[C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md)詳細についてはします。