---
title: リンカ ツール エラー LNK1140 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1140
dev_langs:
- C++
helpviewer_keywords:
- LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc0d59589a1882aca4ef2deb419e1e4f1081e52b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302738"
---
# <a name="linker-tools-error-lnk1140"></a>リンカ ツール エラー LNK1140
プログラム データベース モジュールが多すぎます/PDB とのリンク: なし  
  
 プロジェクトには、4096 以上のモジュールが含まれています。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  使用して再リンク[/PDB: NONE](../../build/reference/pdb-use-program-database.md)です。  
  
2.  デバッグ情報なしには、一部のモジュールをコンパイルします。  
  
3.  モジュールの数を減らします。