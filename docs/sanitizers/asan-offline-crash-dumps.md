---
title: AddressSanitizer クラウドまたは分散テスト
description: Visual Studio と Azure の AddressSanitizer 機能の拡張
ms.date: 03/02/2021
helpviewer_keywords:
- AddressSanitizer cloud or distributed testing
ms.openlocfilehash: 53bbb1ca04a5c4636914591cf10bfcc6bf275d42
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102471326"
---
# <a name="addresssanitizer-cloud-or-distributed-testing"></a>AddressSanitizer クラウドまたは分散テスト

AddressSanitizer エラーが発生したときとその場所については、デバッグする必要はありません。 エラーが発生したときに、すべての AddressSanitizer 固有のコンテキストを格納するクラッシュダンプを作成するようにランタイムを構成します。 その後、デバッグのためにクラッシュダンプを別の PC に送信します。 オフラインデバッグは、クラウドまたは分散テストで AddressSanitizer を実行するときに重要な大幅節約になることがあります。 ダンプは、エラーが発生したテストまたは実稼働インフラストラクチャに作成し、後で開発者の PC でデバッグできます。

Visual Studio デバッガーでは、正確に診断される AddressSanitizer エラーが提供されます。 これらのバグは、テストを再実行したり、大規模なデータセットをコピーしたり、失われたデータを検出したり、オフラインになったテストコンピューターを検索したりする必要はありません。 必要なのは、クラッシュダンプの読み込みだけです。

クラッシュダンプは、次の環境変数を設定することによって、AddressSanitizer の障害が発生したときに作成されます。

`set ASAN_SAVE_DUMPS=MyFileName.dmp`

> [!NOTE]
> *`.dmp`* Visual Studio の名前付け規則に従うには、ファイル名にサフィックスが必要です。

この [ダンプファイル](/previous-versions/windows/desktop/proc_snap/export-a-process-snapshot-to-a-file) は、別のコンピューターで後から Visual Studio を使用して表示できます。

Visual Studio では、エラー情報を元のソースコードのコンテキストで表示できます。 これを行うには、Visual Studio でシンボルと[インデックス付きソースコード](/windows-hardware/drivers/debugger/source-indexing)を[デバッグ](/windows/win32/dxtecharts/debugging-with-symbols)する必要があります。 最適なデバッグエクスペリエンスを実現するには、これらのバイナリを生成するために使用される EXE、PDB、およびソースコードが一致する必要があります。

ソースとシンボルの格納の詳細については、「 [source and symbols](#source) 」セクションを参照してください。 実装の詳細ときめ細かい制御については、「 [デバッガーの統合](asan-debugger-integration.md)」を参照してください。

## <a name="example---build-test-and-analyze"></a>例-ビルド、テスト、および分析

A、B、C の3台のコンピューターを考えてみます。ビルドはコンピューター B で実行され、テストはコンピューター C で実行され、コンピューター A でのエラーを分析します。エラーは、ソースコードのソース行と列番号に対して報告されます。 呼び出し履歴を、その [正確なバージョンのソースコード](#source)を使用して生成された PDB ファイル内の一連のシンボルと共に表示できます。

次の手順は、.dmp ファイルを作成し、その AddressSanitizer ダンプファイルをオフラインで表示する、ローカルまたは分散のシナリオを対象としています。

### <a name="produce-a-dmp-locally"></a>.Dmp をローカルに生成する

- ビルド
- 実行可能ファイルをテストする
- 生成された .dmp ファイルをビルドディレクトリにコピーする
- 同じディレクトリ内にある .pdb という .pdb ファイルを開きます。

### <a name="produce-a-dmp-on-a-distributed-system"></a>分散システムでの .dmp の生成

- [ソースインデックス作成データブロック](/windows/win32/debug/source-server-and-source-indexing)の[PDB の](#source)ビルドと後処理
- (.Exe, .pdb) のアトミックペアをテストコンピューターにコピーし、テストを実行します
- (.Pdb、.dmp) のアトミックペアをバグ報告データベースに書き込みます。
- 同じディレクトリ内に .pdb という pdb がある .dmp ファイルが Visual Studio によって開かれます。

> [!NOTE]
> 分析に使用する Visual Studio 2019 マシンは、GitHub または内部の、 *`\\Machine\share`* インデックス付きソースが格納されている場所にアクセスできる必要があります。

## <a name="view-addresssanitizer-dmp-files"></a>AddressSanitizer ファイルを表示する

1. デバッガー IDE で PDB とソースファイルが見つかることを確認します。

1. Visual Studio を開き、[ **コードなしで続行** する] を選択します。 次に、[ファイル] [ファイルを開く] の順に **選択し**、[ファイル  >    >  を開く] ダイアログを開きます。 ファイル名のサフィックスが **.dmp** であることを確認します。

   :::image type="content" source="./media/asan-open-crash-dump-file.png" alt-text="Visual Studio の [ファイル] [ファイルを開く] メニューのスクリーンショット。":::

   ここに表示される画面では、IDE がシンボルとソースにアクセスできるようにするためのもう1つの手順が必要です。

1. シンボルパスを設定し、[ **ネイティブのみでデバッグ**] を選択します。

   :::image type="content" source="./media/asan-dump-file-open.png" alt-text="Visual Studio のミニダンプ概要表示のスクリーンショット。":::

このスクリーンショットは、ソースと AddressSanitizer メタデータが読み込まれた、最終的に読み込まれたダンプファイルを示しています。

:::image type="content" source="./media/asan-view-crash-metadata.png" alt-text="ソースファイルと AddressSanitizer メタデータを表示しているデバッガーのスクリーンショット。":::

## <a name="source-and-symbols"></a><a name="source"></a> ソースとシンボル

ソースサーバーを使用すると、クライアントは、アプリケーションのビルドに使用されるソースファイルの **正確なバージョン** を取得できます。 実行可能ファイルまたは DLL のソースコードは、時間の経過と共に、バージョン間で変わる可能性があります。 これを使用して、アプリケーションの特定のバージョンをビルドしたのと同じソースコードを確認できます。

PDB ファイルで EXE をデバッグするときに、デバッガーは埋め込み元サーバーのデータブロックを使用して、ソース管理から適切なファイルを取得できます。 このメソッドは、コンパイラオプションによって PDB に自動的に格納される完全修飾名にマップされるファイルを読み込み **`/Zi`** ます。

ソースサーバーを使用するには、を使用して *`pdbstr.exe`* データブロックを PDB ファイルに書き込むことによって、アプリケーションが "ソースインデックス" になっている必要があり `srcsrv` ます。 詳細については、「 [ソースサーバーとソースのインデックス作成](/windows/win32/debug/source-server-and-source-indexing)」の「データブロック」セクションを参照してください。 ソースのインデックスを作成 [し、シンボルを発行する手順](/azure/devops/pipelines/tasks/build/index-sources-publish-symbols) と、 [デバッガーのシンボルとソースコードを指定する方法](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger) についても説明します。

外部のドキュメントについては、以下を参照してください。

- [Git を使用したソースのインデックス作成](https://gist.github.com/baldurk/c6feb31b0305125c6d1a)
- [デバッグしやすくするためのガイド](https://www.codeproject.com/articles/115125/source-indexing-and-symbol-servers-a-guide-to-easi)
- [ソースのインデックス作成には機能性があります](https://randomascii.wordpress.com/2011/11/11/source-indexing-is-underused-awesomeness/)

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)
