---
title: BSCMAKE エラー BK1514 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1514
dev_langs:
- C++
helpviewer_keywords:
- BK1514
ms.assetid: 7c7e2504-a490-44ab-bb1f-47385ee2f4b0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 23f1c72760f0597709de430588052445366e434d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="bscmake-error-bk1514"></a>BSCMAKE エラー BK1514
すべての。SBR ファイルが切り捨てられました filename 内に見つかりません。  
  
 更新プログラムに対して指定された .sbr ファイルのいずれも、元の参照情報 (.bsc) ファイルの一部であった。 このエラーの原因となった .sbr ファイルの名前を検索するには、読み取り、 [BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md)前に警告します。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  .Sbr または .bsc ファイルに指定されたファイル名が間違っています。  
  
2.  破損した .bsc ファイルには、再構築する BSCMAKE が必要です。