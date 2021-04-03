---
description: '詳細情報: 致命的なエラー C1090 PDB API 呼び出しに失敗しました'
title: 致命的なエラー C1090
ms.date: 04/01/2021
f1_keywords:
- C1090
helpviewer_keywords:
- C1090
ms.openlocfilehash: 4195fd069aa770593a4ec088286aad7f3ec9e062
ms.sourcegitcommit: be9a1af0b9d3f1d6c2987d8744392170b8dccab0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "106232589"
---
# <a name="fatal-error-c1090"></a>致命的なエラー C1090

> PDB API の呼び出しに失敗しました。エラーコード '*エラー番号*': *メッセージ*

PDB ファイルの処理中にエラーが発生しました。

エラー C1090 は、個別に報告されない一般的なコンパイラ PDB ファイルエラーのキャッチオールです。 この問題を解決するための一般的なアドバイスは次のとおりです。

- ビルドディレクトリでクリーン操作を実行し、ソリューションの完全なビルドを実行します。

- コンピューターを再起動するか、mspdbsrv.exe プロセスに応答していないかどうかを確認し、TaskManager で強制終了します。

- プロジェクトディレクトリのウイルス対策チェックをオフにします。

- [`/Zf`](../../build/reference/zf.md) [`/MP`](../../build/reference/mp-build-with-multiple-processes.md) MSBuild または別の並行ビルドプロセスでを使用する場合は、コンパイラオプションを使用します。

- 64ビットでホストされたツールセットを使用してビルドしてみてください。

トラブルシューティングや回避策の詳細については、 [開発者コミュニティ](https://aka.ms/vsfeedback/browsecpp) または [Stack Overflow](https://stackoverflow.com/search?q=C1090)でこのエラーを検索してください。

また、開発者コミュニティで問題を報告することもできます。 詳細については、「 [Microsoft C++ ツールセットで問題を報告する方法](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md)」を参照してください。
