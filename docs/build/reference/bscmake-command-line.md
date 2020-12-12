---
description: '詳細情報: BSCMAKE コマンドライン'
title: BSCMAKE コマンド ライン
ms.date: 11/04/2016
helpviewer_keywords:
- BSCMAKE, command line
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
ms.openlocfilehash: a0d6cb81fb207c30cd89fbfe3a988380a865a399
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182659"
---
# <a name="bscmake-command-line"></a>BSCMAKE コマンド ライン

> [!WARNING]
> BSCMAKE は、現在も Visual Studio と共にインストールされていますが、IDE では使用されなくなりました。 Visual Studio 2008 以降、ブラウザーとシンボルの情報は、ソリューション フォルダー内の SQL Server の .sdf ファイルに自動的に格納されます。

BSCMAKE を実行するには、次のコマンドライン構文を使用します。

```
BSCMAKE [options] sbrfiles
```

オプションは、コマンドラインのフィールドにのみ表示され `options` ます。

*Sbrfiles* フィールドは、コンパイラまたはアセンブラーによって作成される1つ以上の .sbr ファイルを指定します。 .Sbr ファイルの名前は、スペースまたはタブで区切ります。 拡張機能を指定する必要があります。既定値はありません。 ファイル名を使用してパスを指定し、オペレーティングシステムのワイルドカード (および?) を使用することができ \* ます。

インクリメンタルビルド中に、元のビルドに含まれていなかった新しい .sbr ファイルを指定できます。 すべての投稿をブラウザー情報ファイルに残しておく場合は、.bsc ファイルを作成するために最初に使用したすべての .sbr ファイル (切り捨てられたファイルを含む) を指定する必要があります。 .Sbr ファイルを省略した場合、そのファイルのブラウザー情報ファイルへの影響は削除されます。

完全ビルドでは、切り捨てられた .sbr ファイルを指定しないでください。 完全ビルドでは、指定されたすべての .sbr ファイルからの貢献が必要です。 完全ビルドを実行する前に、プロジェクトを再コンパイルし、空のファイルごとに新しい .sbr ファイルを作成します。

次のコマンドでは、BSCMAKE を実行して、3つの .sbr ファイルからメイン .bsc という名前のファイルをビルドします。

```
BSCMAKE main.sbr file1.sbr file2.sbr
```

関連情報については、「 [Bscmake コマンドファイル](bscmake-command-file-response-file.md) 」と「 [bscmake オプション](bscmake-options.md)」を参照してください。

## <a name="see-also"></a>関連項目

[BSCMAKE リファレンス](bscmake-reference.md)
