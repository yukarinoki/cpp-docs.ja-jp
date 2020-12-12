---
description: '詳細については、「方法: オーバーサブスクリプションを使用して待機時間をオフセットする」を参照してください。'
title: '方法: オーバーサブスクリプションを使用して待機時間を短縮する'
ms.date: 11/04/2016
helpviewer_keywords:
- oversubscription, using [Concurrency Runtime]
- using oversubscription [Concurrency Runtime]
ms.assetid: a1011329-2f0a-4afb-b599-dd4043009a10
ms.openlocfilehash: ec7b96703da2cbbe8a4d3caac3bfb1a1ff6f602a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341569"
---
# <a name="how-to-use-oversubscription-to-offset-latency"></a>方法: オーバーサブスクリプションを使用して待機時間を短縮する

オーバーサブスクリプションを使用すると、待機時間の長いタスクが含まれた一部のアプリケーションの全体的な効率を向上できます。 このトピックでは、オーバーサブスクリプションを使用して、ネットワーク接続からのデータの読み込みが原因で発生する待機時間を短縮する方法について説明します。

## <a name="example"></a>例

この例では、 [非同期エージェントライブラリ](../../parallel/concrt/asynchronous-agents-library.md) を使用して、HTTP サーバーからファイルをダウンロードします。 `http_reader`クラスは[concurrency:: agent](../../parallel/concrt/reference/agent-class.md)から派生し、メッセージパッシングを使用して、ダウンロードする URL 名を非同期に読み取ります。

クラスは、 `http_reader` [concurrency:: task_group](reference/task-group-class.md) クラスを使用して、各ファイルを同時に読み取ります。 各タスクは、パラメーターをに設定して [concurrency:: Context:: Oversubscribe](reference/context-class.md#oversubscribe) メソッドを呼び出し、 `_BeginOversubscription` 現在の **`true`** コンテキストでオーバーサブスクリプションを有効にします。 次に、各タスクは、Microsoft Foundation Classes (MFC) の [CInternetSession](../../mfc/reference/cinternetsession-class.md) クラスと [CHttpFile](../../mfc/reference/chttpfile-class.md) クラスを使用してファイルをダウンロードします。 最後に、各タスクは、 `Context::Oversubscribe` パラメーターをに設定してを呼び出し、 `_BeginOversubscription` **`false`** オーバーサブスクリプションを無効にします。

オーバーサブスクリプションを有効にすると、タスクを実行する 1 つの追加スレッドがランタイムによって作成されます。 これらのスレッドのそれぞれで現在のコンテキストをオーバーサブスクライブして、追加のスレッドを作成することもできます。 クラスは、 `http_reader` [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) オブジェクトを使用して、アプリケーションが使用するスレッドの数を制限します。 agent は、トークン値の固定数でバッファーを初期化します。 それぞれのダウンロード操作に対して、agent はバッファーからトークン値を読み込んでから操作を開始し、操作が完了すると値をバッファーに書き戻します。 バッファーが空の場合、agent はいずれかのダウンロード操作によって値がバッファーに書き戻されるまで待機します。

次の例は、同時に実行するタスクの数を、使用できるハードウェア スレッドの数の 2 倍に制限します。 オーバーサブスクリプションの効果を調べる場合は、この値から始めることをお勧めします。 特定の処理環境に合った値を使用したり、この値を動的に変更して実際の作業負荷に対応したりできます。

[!code-cpp[concrt-download-oversubscription#1](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_1.cpp)]

この例では、4 つのプロセッサを備えたコンピューターで次の出力を生成します。

```Output
Downloading http://www.adatum.com/...
Downloading http://www.adventure-works.com/...
Downloading http://www.alpineskihouse.com/...
Downloading http://www.cpandl.com/...
Downloading http://www.cohovineyard.com/...
Downloading http://www.cohowinery.com/...
Downloading http://www.cohovineyardandwinery.com/...
Downloading http://www.contoso.com/...
Downloading http://www.consolidatedmessenger.com/...
Downloading http://www.fabrikam.com/...
Downloading http://www.fourthcoffee.com/...
Downloading http://www.graphicdesigninstitute.com/...
Downloading http://www.humongousinsurance.com/...
Downloading http://www.litwareinc.com/...
Downloading http://www.lucernepublishing.com/...
Downloading http://www.margiestravel.com/...
Downloading http://www.northwindtraders.com/...
Downloading http://www.proseware.com/...
Downloading http://www.fineartschool.net...
Downloading http://www.tailspintoys.com/...
Downloaded 1801040 bytes in 3276 ms.
```

この例でオーバーサブスクリプションを有効にすると、他のタスクが潜在的な操作の完了を待っている間に別のタスクが実行されるので、実行時間を短縮できます。

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付けて `download-oversubscription.cpp` から、 **visual Studio のコマンドプロンプト** ウィンドウで次のコマンドのいずれかを実行します。

```cmd
cl.exe /EHsc /MD /D "_AFXDLL" download-oversubscription.cpp
cl.exe /EHsc /MT download-oversubscription.cpp
```

## <a name="robust-programming"></a>信頼性の高いプログラミング

オーバーサブスクリプションは、不要になったら必ず無効にしてください。 たとえば、ある関数が、別の関数によってスローされた例外を処理しないとします。 関数から制御が返されたときにオーバーサブスクリプションが無効になっていない場合、他のすべての並列処理でも現在のコンテキストがオーバーサブスクライブされます。

*リソース取得は初期化*(RAII) パターンを使用して、オーバーサブスクリプションを特定のスコープに制限することができます。 RAII パターンでは、データ構造はスタック上に割り当てられます。 データ構造は、作成されたときにリソースを初期化または取得し、破棄されたときにそのリソースを破棄または解放します。 RAII パターンでは、外側のスコープが終了する前に、常にデストラクターが呼び出されます。 このため、例外がスローされた場合、または関数に複数のステートメントが含まれている場合は、リソースが正しく管理され **`return`** ます。

次の例では、`scoped_blocking_signal` という名前の構造を定義します。 `scoped_blocking_signal` 構造のコンストラクターによってオーバーサブスクリプションが有効になり、デストラクターによってオーバーサブスクリプションが無効になります。

[!code-cpp[concrt-download-oversubscription#2](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_2.cpp)]

次の例では、関数から制御が返される前にオーバーサブスクリプションを無効にするために、RAII を使用するように `download` メソッドの本体に変更を加えています。 この方法により、`download` メソッドは例外セーフになります。

[!code-cpp[concrt-download-oversubscription#3](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_3.cpp)]

## <a name="see-also"></a>関連項目

[コンテキスト](../../parallel/concrt/contexts.md)<br/>
[Context::Oversubscribe メソッド](reference/context-class.md#oversubscribe)
