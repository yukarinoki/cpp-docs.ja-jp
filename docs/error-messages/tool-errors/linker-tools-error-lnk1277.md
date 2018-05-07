---
title: リンカ ツール エラー LNK1277 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1277
dev_langs:
- C++
helpviewer_keywords:
- LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec8f00793fcda748c60d9d8ea775611e3d025cd9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1277"></a>リンカ ツール エラー LNK1277
オブジェクトのレコードが pgd (ファイル名) に見つかりませんでした。  
  
 使用する場合[/LTCG:PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md)、入力 .lib、def、または .obj ファイルの 1 つのパスが/LTCG:PGINSTRUMENT 中に検出されたパスと異なっています。 これは、/LTCG:PGINSTRUMENT 後に、LIB 環境変数での変更説明可能性があります。 入力ファイルへの完全パスは、.pgd ファイルに格納されます。  
  
 /LTCG:PGOPTIMIZE では、入力、/LTCG:PGINSTRUMENT フェーズに同一であることが必要です。  
  
 この警告を解決するには、次のいずれかの操作を行います。  
  
-   /LTCG:PGINSTRUMENT を実行し、すべてのテストの実行を再実行/LTCG:PGOPTIMIZE を実行します。  
  
-   /LTCG:PGINSTRUMENT を実行したときに、LIB 環境変数を変更します。  
  
 回避する LNK1277/LTCG:PGUPDATE を使用して、これは推奨されません。