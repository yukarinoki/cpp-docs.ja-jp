---
title: コマンド ライン エラー D8027 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D8027
dev_langs:
- C++
helpviewer_keywords:
- D8027
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc93edb939001a1e1bed5d3f7a4113e8483e81dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="command-line-error-d8027"></a>コマンド ライン エラー D8027
'コンポーネント' を実行できません。  
  
 特定のコンパイラ コンポーネントまたはリンカー、コンパイラは実行できませんでした。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  メモリ不足のため、コンポーネントを読み込めません。 (Nmake の) に、コンパイラが呼び出される場合は、外部メイクファイルでコンパイラを実行します。  
  
2.  現在のオペレーティング システムでは、コンポーネントは実行できませんでした。 確認パス ポイント実行可能ファイルをオペレーティング システムに合った適切なします。  
  
3.  コンポーネントが破損しています。 セットアップ プログラムを使用して、パッケージ内のディスクからのコンポーネントを再コピーします。  
  
4.  オプションが正しく指定されていません。 例えば:  
  
    ```  
    cl /B1 file1.c  
    ```