---
title: リンカー ツールの警告 LNK4075 |Microsoft Docs
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
ms.openlocfilehash: 1a021a9345975dcb197ab578901baf22f76db846
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059655"
---
# <a name="linker-tools-warning-lnk4075"></a>リンカー ツールの警告 LNK4075

により、"option2"仕様"option1"を無視します。

2 番目のオプションは、1 つ目をオーバーライドします。

相互に排他的なリンカー オプションが指定されます。  リンカーのオプションを確認します。  リンカー オプションが指定されているプロジェクトをビルドしている方法によって異なります。

- 開発環境を構築している場合は、プロジェクトの [リンカー] プロパティ ページで参照し、両方のリンカー オプションが指定されています。  参照してください[プロジェクト プロパティの操作](../../ide/working-with-project-properties.md)詳細についてはします。

- コマンドラインでビルドする場合があります指定されたリンカー オプションを調べます。

- ビルド スクリプトを構築する場合は、これらのリンカー オプションが指定されているスクリプトを参照します。

相互に排他的なリンカー オプションが指定されているが見つかったら、リンカー オプションのいずれかを削除します。

具体的な例:

- コンパイルされたモジュールをリンクする場合 **/ZI**は、内部リンカー オプションが含まれて、/EDITANDCONTINUE ものではありません、/EDITANDCONTINUE と/OPT:REF、/OPT:ICF、または、/INCREMENTAL:NO でコンパイルされたモジュールが呼び出されると、LNK4075 を取得します。  参照してください[/Z7、/Zi、/ZI (デバッグ情報の形式)](../../build/reference/z7-zi-zi-debug-information-format.md)詳細についてはします。