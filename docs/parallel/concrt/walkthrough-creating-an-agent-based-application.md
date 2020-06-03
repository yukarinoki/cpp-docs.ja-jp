---
title: 'チュートリアル: エージェント ベースのアプリケーションの作成'
ms.date: 04/25/2019
helpviewer_keywords:
- asynchronous agents, creating
- agent class, example
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
ms.openlocfilehash: 20197786e3d3c2d34d29af748c1cc073902cf70d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377458"
---
# <a name="walkthrough-creating-an-agent-based-application"></a>チュートリアル: エージェント ベースのアプリケーションの作成

ここでは、基本的なエージェント ベースのアプリケーションの作成方法について説明します。 このチュートリアルでは、テキスト ファイルから非同期的にデータを読み取るエージェントを作成できます。 このアプリケーションでは、Adler-32 チェックサム アルゴリズムを使用して、そのファイルの内容のチェックサムを計算します。

## <a name="prerequisites"></a>前提条件

このチュートリアルを完了するには、次のトピックを理解する必要があります。

- [非同期エージェント](../../parallel/concrt/asynchronous-agents.md)

- [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)

- [メッセージパッシング関数](../../parallel/concrt/message-passing-functions.md)

- [同期データ構造](../../parallel/concrt/synchronization-data-structures.md)

## <a name="sections"></a><a name="top"></a>セクション

このチュートリアルでは、次のタスクを実行する方法を示します。

- [コンソール アプリケーションの作成](#createapplication)

- [file_reader クラスの作成](#createagentclass)

- [アプリケーションでの file_reader クラスの使用](#useagentclass)

## <a name="creating-the-console-application"></a><a name="createapplication"></a>コンソール アプリケーションの作成

このセクションでは、プログラムで使用するヘッダー ファイルを参照する C++ コンソール アプリケーションを作成する方法を示します。 最初の手順は、使用している Visual Studio のバージョンによって異なります。 Visual Studio の優先バージョンのドキュメントを表示するには、**バージョン**セレクター コントロールを使用します。 このページの目次の上部に表示されます。

::: moniker range="vs-2019"

### <a name="to-create-a-c-console-application-in-visual-studio-2019"></a>Visual Studio 2019 で C++ コンソール アプリケーションを作成するには

1. メイン メニューで、**[ファイル]** > **[新規作成]** > **[プロジェクト]** の順に選択して、**[新しいプロジェクトの作成]** ダイアログ ボックスを開きます。

1. ダイアログの上部で、**[言語]** を **[C++]** に、**[プラットフォーム]** を **[Windows]** に、**[プロジェクト タイプ]** を **[コンソール]** に設定します。

1. フィルター処理されたプロジェクト タイプの一覧から、**[コンソール アプリ]** を選択して、**[次へ]** を選択します。 次のページで、プロジェクト`BasicAgent`の名前を入力し、必要に応じてプロジェクトの場所を指定します。

1. **[作成]** ボタンをクリックしてプロジェクトを作成します。

1. **ソリューション エクスプローラ**でプロジェクト ノードを右クリックし、[**プロパティ]** をクリックします。 [**構成プロパティ** > **C/C++** > **プリコンパイル済みヘッダープリ** > **コンパイル済みヘッダー** ] で、[**作成**] を選択します。

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-a-c-console-application-in-visual-studio-2017-and-earlier"></a>Visual Studio 2017 以前で C++ コンソール アプリケーションを作成するには

1. [**ファイル**] メニューの [**新規作成**] をクリックし、[**プロジェクト**] をクリックして [**新しいプロジェクト**] ダイアログ ボックスを表示します。

1. [**新しいプロジェクト**] ダイアログ ボックスで、[**プロジェクトの種類**] ウィンドウで **[Visual C++]** ノードを選択し、[**テンプレート]** ウィンドウで **[Win32 コンソール アプリケーション**] を選択します。 プロジェクトの名前を入力し、`BasicAgent`次に **[OK]** をクリックして**Win32 コンソール アプリケーション ウィザード**を表示します。

1. **[Win32 コンソール アプリケーション ウィザード**] ダイアログ ボックスで、[**完了**] をクリックします。

::: moniker-end

1. *pch.h* (2017 年以前のバージョンでは*stdafx.h)* に次のコードを追加します。

[!code-cpp[concrt-basic-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_1.h)]

   ヘッダー ファイル agents.h には[、同時実行の機能が含まれています::エージェント](../../parallel/concrt/reference/agent-class.md)クラス。

1. アプリケーションをビルドして実行することにより、アプリケーションが正常に作成されたことを確認します。 アプリケーションをビルドするには、[**ビルド**] メニューの [**ソリューションのビルド**] をクリックします。 アプリケーションが正常にビルドされた場合は、[**デバッグ**] メニューの [**デバッグの開始**] をクリックしてアプリケーションを実行します。

[[トップ](#top)]

## <a name="creating-the-file_reader-class"></a><a name="createagentclass"></a>file_readerクラスの作成

ここでは、`file_reader` クラスの作成方法について説明します。 ランタイムは、各エージェントがそれぞれのコンテキストで処理を実行するようにスケジュールを設定します。 そのため、処理を同期的に実行する一方で、他のコンポーネントとは非同期的に通信するエージェントを作成できます。 `file_reader` クラスでは、指定された入力ファイルからデータを読み取り、そのファイルのデータを指定されたターゲット コンポーネントに送信します。

#### <a name="to-create-the-file_reader-class"></a>file_reader クラスを作成するには

1. 新しい C++ ヘッダー ファイルをプロジェクトに追加します。 これを行うには、**ソリューション エクスプローラ**で **[ヘッダー ファイル]** ノードを右クリックし、[**追加**]**をクリックします**。 [**テンプレート**] ウィンドウで 、[**ヘッダー ファイル (.h)]** を選択します。 [**新しい項目の追加**] ダイアログ`file_reader.h`ボックスで、[**名前**] ボックスに入力し、[**追加**] をクリックします。

1. file_reader.h に、次のコードを追加します。

[!code-cpp[concrt-basic-agent#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_2.h)]

1. file_reader.h に、`file_reader` から派生する `agent` という名前のクラスを作成します。

[!code-cpp[concrt-basic-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_3.h)]

1. クラスの `private` セクションに次のデータ メンバーを追加します。

[!code-cpp[concrt-basic-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_4.h)]

   `_file_name` メンバーは、エージェントが読み取る対象のファイル名です。 メンバー`_target`は、エージェントがファイルの内容を書き込む[、同時実行::ITarget](../../parallel/concrt/reference/itarget-class.md)オブジェクトです。 `_error` メンバーでは、エージェントの有効期間中に発生したエラーを保持します。

1. `file_reader` クラスの `public` セクションに `file_reader` コンストラクターの次のコードを追加します。

[!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_5.h)]

   各コンストラクター オーバーロードによって、`file_reader` データ メンバーが設定されます。 2 番目と 3 番目のコンストラクター オーバーロードによって、アプリケーションでエージェントに対して特定のスケジューラを使用できるようにします。 最初のオーバーロードでは、エージェントに対して既定のスケジューラを使用します。

1. `get_error` クラスのパブリック セクションに `file_reader` メソッドを追加します。

[!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_6.h)]

   `get_error` メソッドにより、エージェントの有効期間中に発生したエラーを取得します。

1. クラスの`protected`セクションに[同時実行を](reference/agent-class.md#run)実装します。

[!code-cpp[concrt-basic-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_7.h)]

`run` メソッドによりファイルを開き、そこからデータを読み取ります。 `run` メソッドでは、例外処理を使用して、ファイルの処理中に発生したエラーをキャプチャします。

   このメソッドは、ファイルからデータを読み取るたびに、[同時実行関数::asend](reference/concurrency-namespace-functions.md#asend)関数を呼び出して、そのデータをターゲット バッファーに送信します。 処理の終了を示す際には、空の文字列をターゲット バッファーに送信します。

file_reader.h の内容全体の例を次に示します。

[!code-cpp[concrt-basic-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_8.h)]

[[トップ](#top)]

## <a name="using-the-file_reader-class-in-the-application"></a><a name="useagentclass"></a>アプリケーションでのfile_readerクラスの使用

ここでは、`file_reader` クラスを使用して、テキスト ファイルの内容を読み取る方法について説明します。 また、このファイルデータを受け取り、Adler-32チェックサムを計算する[、同時実行::call](../../parallel/concrt/reference/call-class.md)オブジェクトを作成する方法も示しています。

#### <a name="to-use-the-file_reader-class-in-your-application"></a>アプリケーションで file_reader クラスを使用するには

1. BasicAgent.cpp に、次の `#include` ステートメントを追加します。

[!code-cpp[concrt-basic-agent#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_9.cpp)]

1. BasicAgent.cpp に、次の `using` ディレクティブを追加します。

[!code-cpp[concrt-basic-agent#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_10.cpp)]

1. 関数で`_tmain`、処理の終了を通知する[並行性::イベント](../../parallel/concrt/reference/event-class.md)オブジェクトを作成します。

[!code-cpp[concrt-basic-agent#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_11.cpp)]

1. データを受け取ったときにチェックサムを更新する `call` オブジェクトを作成します。

[!code-cpp[concrt-basic-agent#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_12.cpp)]

   また、この `call` オブジェクトは、処理の終了を通知する空の文字列を受け取ると、`event` オブジェクトを設定します。

1. test.txt ファイルから読み取り、そのファイルの内容を `file_reader` オブジェクトに書き込む `call` オブジェクトを作成します。

[!code-cpp[concrt-basic-agent#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_13.cpp)]

1. エージェントを開始し、エージェントが終了するまで待機します。

[!code-cpp[concrt-basic-agent#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_14.cpp)]

1. `call` オブジェクトがすべてのデータを受け取り、終了するまで待機します。

[!code-cpp[concrt-basic-agent#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_15.cpp)]

1. エラーが発生していないかどうかファイル リーダーを確認します。 エラーが発生していない場合は、最終的な Adler-32 チェックサムを計算し、その結果をコンソールに出力します。

[!code-cpp[concrt-basic-agent#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_16.cpp)]

完全な BasicAgent.cpp ファイルの例を次に示します。

[!code-cpp[concrt-basic-agent#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_17.cpp)]

[[トップ](#top)]

## <a name="sample-input"></a>サンプル入力

これは、入力ファイル text.txt の内容のサンプルです。

```Output
The quick brown fox
jumps
over the lazy dog
```

## <a name="sample-output"></a>サンプル出力

入力のサンプルを使用すると、このプログラムでは、次の出力が生成されます。

```Output
Adler-32 sum is fefb0d75
```

## <a name="robust-programming"></a>信頼性の高いプログラミング

データ メンバーへの同時アクセスを回避するために、クラスの `protected` セクションまたは `private` セクションに、処理を実行するメソッドを追加することをお勧めします。 クラスの `public` セクションには、メッセージをエージェントに送信するメソッドまたはメッセージをエージェントから受信するメソッドのみを追加してください。

エージェントを完了状態に移動するには、常に[:d同時実行を](reference/agent-class.md#done)呼び出します。 通常、このメソッドは、`run` メソッドから制御が戻る前に呼び出します。

## <a name="next-steps"></a>次の手順

エージェント ベースのアプリケーションの別の例については、「[チュートリアル: 結合を使用したデッドロックの防止](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)」を参照してください。

## <a name="see-also"></a>関連項目

[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[メッセージパッシング関数](../../parallel/concrt/message-passing-functions.md)<br/>
[同期データ構造](../../parallel/concrt/synchronization-data-structures.md)<br/>
[チュートリアル: join を使用したデッドロックの防止](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)
