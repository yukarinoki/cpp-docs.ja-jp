---
title: リンカ ツール エラー LNK1318 |Microsoft ドキュメント
ms.custom: ''
ms.date: 05/29/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1318
dev_langs:
- C++
helpviewer_keywords:
- LNK1318
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 364c819c6ec2bf6e1195011eced6e6ad1699877b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34570697"
---
# <a name="linker-tools-error-lnk1318"></a>リンカ ツール エラー LNK1318

> PDB の予期しないエラーです。*原因*'*詳細*'

リンカーでは、開く、読み取り、または PDB ファイルに書き込むときに予期しないエラーが発生しました。

PDB ファイル内の一般的でない問題については、このエラー メッセージが生成されます。 *原因*と*詳細*障害が発生した場合、リンカーに利用できる情報を表すです。 これを PDB ファイルを処理する場合、個別のもっとわかりやすいエラー メッセージがあるときに一般的なエラーとして、非常に役にできない可能性があります。

エラーの原因が共通でないためにがある一般的なアドバイスのみこの問題を解決するために使用できます。

- ビルド ディレクトリでクリーン操作を実行し、ソリューションの完全ビルドを実行します。

- コンピューターを再起動して、または無効なまたはハング mspdbsrv.exe プロセスを確認および TaskManager でそれらを終了します。

- プロジェクトのディレクトリでのウイルス対策のチェックをオフにします。

- 使用して、 [/Zf](../../build/reference/zf.md)コンパイラ オプションを使用する場合[/MP](../../build/reference/mp-build-with-multiple-processes.md) MSBuild または別の並列処理を構築します。

- 64 ビットのホストされたツールセットを使用してビルドを再試行してください。

- 必要な場合は、並列のリンクの問題を軽減するためにリンクをシリアル化します。 Mspdbsrv.exe リンクの 1 つのインスタンスが起動され、リンクの別のインスタンスが行われる前にシャット ダウンする場合は、このエラーを発生することができますを使用します。 これを修正する場合の欠点は、プロジェクトのビルドが完了するかなり長くかかる場合があります。