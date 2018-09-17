---
title: BSCMAKE コマンドライン |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- BSCMAKE, command line
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bda0457eecdf6ef7c846d7c12e24078faa4d0da5
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720045"
---
# <a name="bscmake-command-line"></a>BSCMAKE コマンド ライン

BSCMAKE を実行するには、次のコマンドライン構文を使用します。

```
BSCMAKE [options] sbrfiles
```

オプションでのみ表示されます、`options`コマンドラインでフィールド。

*Sbrfiles*フィールドは、コンパイラまたはアセンブラーによって作成された 1 つ以上の .sbr ファイルを指定します。 スペースまたはタブでは、.sbr ファイルの名前を区切ります。 拡張子を指定する必要があります。既定値はありません。 ファイル名は、パスを指定して、オペレーティング システムのワイルドカードを使用することができます (\*と?)。

インクリメンタル ビルドでは、最初のビルドに含まれていない新しい .sbr ファイルを指定できます。 すべての貢献をブラウザー情報ファイルに保持する場合は、.bsc ファイルの作成に使用された最初 (切り捨てられたファイルを含む) すべての .sbr ファイルを指定する必要があります。 .Sbr ファイルを省略した場合は、ブラウザー情報ファイルをそのファイルの貢献度が削除されます。

フル ビルドの切り捨てられた .sbr ファイルを指定しません。 完全なビルドでは、すべての指定した .sbr ファイルからの投稿が必要です。 フル ビルドを実行する前に、プロジェクトを再コンパイルし、空のファイルごとに新しい .sbr ファイルを作成します。

次のコマンドは、3 つの .sbr ファイルから MAIN.bsc をという名前のファイルをビルドするにを実行します。

```
BSCMAKE main.sbr file1.sbr file2.sbr
```

関連情報については、次を参照してください。 [BSCMAKE コマンド ファイル](../../build/reference/bscmake-command-file-response-file.md)と[BSCMAKE オプション](../../build/reference/bscmake-options.md)します。

## <a name="see-also"></a>関連項目

[BSCMAKE リファレンス](../../build/reference/bscmake-reference.md)