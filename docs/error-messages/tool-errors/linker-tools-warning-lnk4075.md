---
title: リンカー ツールの警告 LNK4075 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4075
dev_langs:
- C++
helpviewer_keywords:
- LNK4075
ms.assetid: f39ad3f9-c263-4cf0-9d70-259fc56ac96d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4bd9a4ecdad30a0be2d45300367f6f79a65a6b31
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4075"></a>リンカー ツールの警告 LNK4075
により「・ オプション 2」仕様「オプション 1」を無視しています  
  
 2 番目のオプションは、1 つをオーバーライドします。  
  
 相互に排他的なリンカー オプションが指定されます。  リンカー オプションを確認します。  リンカーのオプションが指定されているプロジェクトをビルドしている方法によって異なります。  
  
-   開発環境で作成する場合、[リンカー] プロパティ ページ、プロジェクトのファイルの場所し、リンカーの両方のオプションが指定されている場所を参照してください。  参照してください[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)詳細についてはします。  
  
-   コマンドラインでビルドする場合があります指定されたリンカー オプションを調べます。  
  
-   ビルド スクリプトでビルドする場合は、これらのリンカー オプションが指定されている、スクリプトで検索します。  
  
 相互に排他的なリンカー オプションが指定されているが見つかったら、リンカー オプションのいずれかを削除します。  
  
 具体的な例:  
  
-   コンパイルされたモジュールをリンクする場合は **/ZI**、内部リンカー オプションを意味すると、/EDITANDCONTINUE ものではありません、/EDITANDCONTINUE と/opt:ref による、/OPT:ICF、または、/INCREMENTAL:NO でコンパイルされたモジュールが呼び出されると、ダイアログが表示されますLNK4075 を取得します。  参照してください[/Z7、/Zi、/ZI (デバッグ情報の形式)](../../build/reference/z7-zi-zi-debug-information-format.md)詳細についてはします。