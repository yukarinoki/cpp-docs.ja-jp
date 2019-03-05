---
title: 'チュートリアル: エージェント ベースのアプリケーションを作成します。'
ms.date: 11/04/2016
helpviewer_keywords:
- asynchronous agents, creating
- agent class, example
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
ms.openlocfilehash: 1d55c9879a3dd90bb4a40b61a3bf958dbe960bc3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290093"
---
# <a name="walkthrough-creating-an-agent-based-application"></a>チュートリアル: エージェント ベースのアプリケーションを作成します。

ここでは、基本的なエージェント ベースのアプリケーションの作成方法について説明します。 このチュートリアルでは、テキスト ファイルから非同期的にデータを読み取るエージェントを作成できます。 このアプリケーションでは、Adler-32 チェックサム アルゴリズムを使用して、そのファイルの内容のチェックサムを計算します。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを完了するには、次のトピックを理解する必要があります。

- [非同期エージェント](../../parallel/concrt/asynchronous-agents.md)

- [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)

- [メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)

- [同期データ構造](../../parallel/concrt/synchronization-data-structures.md)

##  <a name="top"></a> セクション

このチュートリアルでは、次のタスクを実行する方法を示します。

- [コンソール アプリケーションの作成](#createapplication)

- [File_reader クラスの作成](#createagentclass)

- [アプリケーションで file_reader クラスの使用](#useagentclass)

##  <a name="createapplication"></a> コンソール アプリケーションを作成します。

ここでは、プログラムで使用されるヘッダー ファイルを参照する Visual C++ コンソール アプリケーションの作成方法について説明します。

#### <a name="to-create-a-visual-c-application-by-using-the-win32-console-application-wizard"></a>Win32 コンソール アプリケーション ウィザードを使用して Visual C++ アプリケーションを作成するには

1. **ファイル** メニューのをクリックして**新規**、 をクリックし、**プロジェクト**を表示する、**新しいプロジェクト** ダイアログ ボックス。

1. **新しいプロジェクト**ダイアログ ボックスで、 **Visual C**内のノード、**プロジェクトの種類**クリックしてウィンドウ**Win32 コンソール アプリケーション****テンプレート**ウィンドウ。 たとえば、プロジェクトの名前を入力`BasicAgent`、順にクリックします **[ok]** を表示する、 **Win32 コンソール アプリケーション ウィザード**します。

1. **Win32 コンソール アプリケーション ウィザード**ダイアログ ボックスで、をクリックして**完了**します。

1. stdafx.h に、次のコードを追加します。

[!code-cpp[concrt-basic-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_1.h)]

   Agents.h ヘッダー ファイルの機能が含まれています、 [concurrency::agent](../../parallel/concrt/reference/agent-class.md)クラス。

1. アプリケーションをビルドして実行することにより、アプリケーションが正常に作成されたことを確認します。 アプリケーションを構築する、**ビルド** メニューのをクリックして**ソリューションのビルド**します。 アプリケーションが正常にビルドする場合をクリックしてアプリケーションを実行**デバッグの開始**上、**デバッグ**メニュー。

[[トップ](#top)]

##  <a name="createagentclass"></a> File_reader クラスの作成

ここでは、`file_reader` クラスの作成方法について説明します。 ランタイムは、各エージェントがそれぞれのコンテキストで処理を実行するようにスケジュールを設定します。 そのため、処理を同期的に実行する一方で、他のコンポーネントとは非同期的に通信するエージェントを作成できます。 
  `file_reader` クラスでは、指定された入力ファイルからデータを読み取り、そのファイルのデータを指定されたターゲット コンポーネントに送信します。

#### <a name="to-create-the-filereader-class"></a>file_reader クラスを作成するには

1. 新しい C++ ヘッダー ファイルをプロジェクトに追加します。 これを行うを右クリックし、**ヘッダー ファイル**ノード**ソリューション エクスプ ローラー**、 をクリックして**追加**、順にクリックします**新しい項目の**します。 **テンプレート**ペインで、**ヘッダー ファイル (.h)** します。 **新しい項目の追加**ダイアログ ボックスに「`file_reader.h`で、**名前**ボックスをクリックして**追加**します。

1. file_reader.h に、次のコードを追加します。

[!code-cpp[concrt-basic-agent#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_2.h)]

1. file_reader.h に、`file_reader` から派生する `agent` という名前のクラスを作成します。

[!code-cpp[concrt-basic-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_3.h)]

1. クラスの `private` セクションに次のデータ メンバーを追加します。

[!code-cpp[concrt-basic-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_4.h)]

   
  `_file_name` メンバーは、エージェントが読み取る対象のファイル名です。 `_target`メンバーは、 [concurrency::itarget](../../parallel/concrt/reference/itarget-class.md)オブジェクト、エージェントが、ファイルの内容を書き込みます。 
  `_error` メンバーでは、エージェントの有効期間中に発生したエラーを保持します。

1. 
  `file_reader` クラスの `public` セクションに `file_reader` コンストラクターの次のコードを追加します。

[!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_5.h)]

   各コンストラクター オーバーロードによって、`file_reader` データ メンバーが設定されます。 2 番目と 3 番目のコンストラクター オーバーロードによって、アプリケーションでエージェントに対して特定のスケジューラを使用できるようにします。 最初のオーバーロードでは、エージェントに対して既定のスケジューラを使用します。

1. 
  `get_error` クラスのパブリック セクションに `file_reader` メソッドを追加します。

[!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_6.h)]

   
  `get_error` メソッドにより、エージェントの有効期間中に発生したエラーを取得します。

1. 実装、 [concurrency::agent::run](reference/agent-class.md#run)メソッドで、`protected`クラスのセクション。

[!code-cpp[concrt-basic-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_7.h)]


  `run` メソッドによりファイルを開き、そこからデータを読み取ります。 
  `run` メソッドでは、例外処理を使用して、ファイルの処理中に発生したエラーをキャプチャします。

   このメソッドは、ファイルからデータを読み取るたびに呼び出す、 [concurrency::asend](reference/concurrency-namespace-functions.md#asend)ターゲット バッファーにデータを送信します。 処理の終了を示す際には、空の文字列をターゲット バッファーに送信します。

file_reader.h の内容全体の例を次に示します。

[!code-cpp[concrt-basic-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_8.h)]

[[トップ](#top)]

##  <a name="useagentclass"></a> アプリケーションで file_reader クラスの使用

ここでは、`file_reader` クラスを使用して、テキスト ファイルの内容を読み取る方法について説明します。 作成する方法も示します、 [concurrency::call](../../parallel/concrt/reference/call-class.md)オブジェクトをこのファイル データを受け取り、その adler-32 チェックサムを計算します。

#### <a name="to-use-the-filereader-class-in-your-application"></a>アプリケーションで file_reader クラスを使用するには

1. BasicAgent.cpp に、次の `#include` ステートメントを追加します。

[!code-cpp[concrt-basic-agent#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_9.cpp)]

1. BasicAgent.cpp に、次の `using` ディレクティブを追加します。

[!code-cpp[concrt-basic-agent#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_10.cpp)]

1. `_tmain`関数を作成、 [concurrency::event](../../parallel/concrt/reference/event-class.md)処理の終端を表すオブジェクト。

[!code-cpp[concrt-basic-agent#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_11.cpp)]

1. データを受け取ったときにチェックサムを更新する `call` オブジェクトを作成します。

[!code-cpp[concrt-basic-agent#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_12.cpp)]

   また、この `call` オブジェクトは、処理の終了を通知する空の文字列を受け取ると、`event` オブジェクトを設定します。

1. test.txt ファイルから読み取り、そのファイルの内容を `file_reader` オブジェクトに書き込む `call` オブジェクトを作成します。

[!code-cpp[concrt-basic-agent#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_13.cpp)]

1. エージェントを開始し、エージェントが終了するまで待機します。

[!code-cpp[concrt-basic-agent#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_14.cpp)]

1. 
  `call` オブジェクトがすべてのデータを受け取り、終了するまで待機します。

[!code-cpp[concrt-basic-agent#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_15.cpp)]

1. エラーが発生していないかどうかファイル リーダーを確認します。 エラーが発生していない場合は、最終的な Adler-32 チェックサムを計算し、その結果をコンソールに出力します。

[!code-cpp[concrt-basic-agent#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_16.cpp)]

完全な BasicAgent.cpp ファイルの例を次に示します。

[!code-cpp[concrt-basic-agent#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_17.cpp)]

[[トップ](#top)]

## <a name="sample-input"></a>入力のサンプル

これは、入力ファイル text.txt の内容のサンプルです。

```Output
The quick brown fox
jumps
over the lazy dog
```

## <a name="sample-output"></a>出力例

入力のサンプルを使用すると、このプログラムでは、次の出力が生成されます。

```Output
Adler-32 sum is fefb0d75
```

## <a name="robust-programming"></a>信頼性の高いプログラミング

データ メンバーへの同時アクセスを回避するために、クラスの `protected` セクションまたは `private` セクションに、処理を実行するメソッドを追加することをお勧めします。 クラスの `public` セクションには、メッセージをエージェントに送信するメソッドまたはメッセージをエージェントから受信するメソッドのみを追加してください。

常に呼び出し、 [concurrency::agent:: 完了](reference/agent-class.md#done)完了状態に、エージェントを移動するメソッド。 通常、このメソッドは、`run` メソッドから制御が戻る前に呼び出します。

## <a name="next-steps"></a>次の手順

エージェント ベースのアプリケーションの別の例を参照してください。[チュートリアル。Join デッドロックの防止を使用した](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)します。

## <a name="see-also"></a>関連項目

[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)<br/>
[同期データ構造](../../parallel/concrt/synchronization-data-structures.md)<br/>
[チュートリアル: join を使用したデッドロックの防止](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)
