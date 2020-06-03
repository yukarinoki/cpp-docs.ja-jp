---
title: BSCMAKE リファレンス
ms.date: 05/06/2019
helpviewer_keywords:
- BSCMAKE, reference
- Microsoft Browse Information Maintenance Utility
- browse windows
- browse information files (.bsc), building
- .bsc files, building
- bsc files, building
- BSCMAKE
ms.assetid: b97ad994-1355-4809-98db-6abc12c6fb13
ms.openlocfilehash: f95e34b9599de628463b9f92ebf8f01036237891
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320735"
---
# <a name="bscmake-reference"></a>BSCMAKE リファレンス

> [!WARNING]
> BSCMAKE は、現在も Visual Studio と共にインストールされていますが、IDE では使用されなくなりました。 Visual Studio 2008 以降、ブラウザーとシンボルの情報は、ソリューション フォルダー内の SQL Server の .sdf ファイルに自動的に格納されます。

Microsoft Browse Information Maintenance Utility (BSCMAKE.EXE) は、コンパイル時に作成された .sbr ファイルから、ブラウザー情報ファイル (.bsc) を作成します。 特定のサードパーティ製ツールでは、コード分析に .bsc ファイルを使用します。

プログラムをビルドするときに、BSCMAKE を使用してファイルをビルドすれば、プログラムのブラウザー情報ファイルを自動的に作成できます。 Visual Studio 開発環境で参照情報ファイルを作成する場合は、BSCMAKE を実行する方法を知っている必要はありません。 ただし、このトピックを読めば、利用可能な選択肢を理解することができます。

開発環境の外部でプログラムをビルドする場合は、その環境で確認することができるカスタム .bsc ファイルを作成できます。 コンパイル中に作成した .sbr ファイル上で BSCMAKE を実行します。

> [!NOTE]
> このツールは、Visual Studio 開発者コマンド プロンプトからのみ開始できます。 システム コマンド プロンプトやエクスプローラーからは開始できません。

このセクションには、次のトピックが含まれます。

- [ブラウザー情報ファイルのビルド : 概要](building-browse-information-files-overview.md)

- [.bsc ファイルの作成](building-a-dot-bsc-file.md)

- [BSCMAKE コマンド ライン](bscmake-command-line.md)

- [BSCMAKE コマンド ファイル](bscmake-command-file-response-file.md)

- [BSCMAKE オプション](bscmake-options.md)

- [BSCMAKE 終了コード](bscmake-exit-codes.md)

## <a name="see-also"></a>関連項目

[その他の MSVC ビルド ツール](c-cpp-build-tools.md)
