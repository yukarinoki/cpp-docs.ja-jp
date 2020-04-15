---
title: 'チュートリアル: vcperf と Windows パフォーマンス アナライザ'
description: C++ ビルド トレースの分析に vcperf および WPA を使用する方法についてのチュートリアルです。
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c22f3dfddfd346d4f0eee898cb5164fd8923336e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323423"
---
# <a name="tutorial-vcperf-and-windows-performance-analyzer"></a>チュートリアル: vcperf と Windows パフォーマンス アナライザ

::: moniker range="<=vs-2017"

C++ ビルドインサイト ツールは、Visual Studio 2019 で使用できます。 このバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range="vs-2019"

このチュートリアルでは、c++ ビルドのトレースを収集する*vcperf.exe*を使用する方法を学習します。 Windows パフォーマンス アナライザでこのトレースを表示する方法についても説明します。

## <a name="step-1-install-and-configure-windows-performance-analyzer"></a>手順 1: Windows パフォーマンス アナライザーをインストールして構成する

WPA は、Windows アセスメントと展開キット (ADK) で使用できるトレース ビューアーです。 これは、Visual Studio インストーラーを使用してインストールできるコンポーネントの一部ではない別のユーティリティです。

C++ ビルド インサイトをサポートする WPA のバージョンは、現在 Windows ADK インサイダー プレビューでのみ使用できます。 このプレビューにアクセスするには[、Windows Insider プログラム](https://insider.windows.com)にサインアップする必要があります。 Windows ADK プレビューを取得するのに Windows 10 インサイダー プレビュー オペレーティング システムをインストールする必要はありません。 マイクロソフト アカウントを Windows インサイダー プログラムに登録するだけで済みます。

### <a name="to-download-and-install-wpa"></a>WPA をダウンロードしてインストールするには

注: Windows パフォーマンス アナライザーをインストールするには、Windows 8 以降が必要です。

1. Windows ADK インサイダー プレビュー[のダウンロード ページ](https://www.microsoft.com/en-us/software-download/windowsinsiderpreviewADK)を参照します。

1. Windows ADK インサイダー プレビューをダウンロードします。 それはディスクイメージです。

1. ディスク イメージを開き *、adksetup.exe*インストーラーを実行します。

1. インストールする機能を指定するプロンプトが表示されたら **、Windows パフォーマンス ツールキット**を選択します。 必要に応じて他の機能を選択できますが、WPA のインストールには必要ありません。

   ![Windows パフォーマンス アナライザインストーラの機能選択画面](media/wpa-installation.png)

### <a name="to-configure-build-insights"></a><a name="configuration-steps"></a>インサイトの構築を構成するには

1. WPA を起動します。

1. **[ウィンドウ**>**選択テーブル (実験)]** を選択します。

1. [**診断**] セクションまでスクロールします。

1. すべての MSVC ビルド インサイト ビューを選択します。

   ![Windows パフォーマンス アナライザのテーブル選択パネル](media/wpa-configuration.png)

## <a name="step-2-trace-your-build-with-vcperfexe"></a>手順 2: vcperf.exe を使用してビルドをトレースする

C++ ビルドインサイトデータを表示するには、まず次の手順に従ってトレース ファイルに収集します。

1. Visual Studio 2019 のネイティブ ツールまたはクロス ツール開発者コマンド プロンプトを管理者モードで開きます。 ([スタート] メニュー項目を右クリックし、[**管理者として****実行]** > を選択します)。

1. コマンド プロンプト ウィンドウで、次のコマンドを入力します。

   **セッション名を開始します _。_**

   セッション名 に覚えている*セッション名*を選択してください。

1. 通常どおりにプロジェクトをビルドします。 同じコマンド プロンプト ウィンドウを使用してビルドする必要はありません。

1. コマンド プロンプト ウィンドウで、次のコマンドを入力します。

   **を_クリック__します。_**

   前に SessionName で選択したのと同じ*セッション名*を使用します。 *トレースファイル.etl*トレース ファイルの適切な名前を選択します。

開発者のコマンド プロンプト ウィンドウでの一般的な*vcperf.exe*コマンド シーケンスは次のようになります。

![単純な vcperf.exe の使用シナリオ](media/vcperf-simple-usage.png)

### <a name="important-notes-about-vcperfexe"></a>vcperf.exe に関する重要な注意事項

- *vcperf.exe*トレースを開始または停止するには、管理者特権が必要です。 **[管理者として実行**] を使用して開いた開発者コマンド プロンプト ウィンドウを使用します。

- 1 つのコンピューターで実行できるのは、一度に 1 つのトレース セッションだけです。

- トレースの開始に使用したセッション名を必ず覚えておいてください。 その名前を知らなくても、実行中のセッションを停止するのは面倒です。

- *cl.exe*や*link.exe*と同様に、コマンド ライン ユーティリティ*vcperf.exe*は MSVC のインストールに含まれています。 このコンポーネントを取得するために追加の手順は必要ありません。

- *vcperf.exe は*、システム上で実行されているすべての MSVC ツールに関する情報を収集します。 そのため、トレースの収集に使用したのと同じコマンド プロンプトからビルドを開始する必要はありません。 プロジェクトは、別のコマンド プロンプトからビルドすることも、Visual Studio でビルドすることもできます。

## <a name="step-3-view-your-trace-in-windows-performance-analyzer"></a>手順 3: Windows パフォーマンス アナライザーでトレースを表示する

WPA を起動し、収集したトレースを開きます。 WPA は C++ ビルドインサイトトレースとして認識し、左側のグラフエクスプローラパネルに次のビューが表示されます。

- ビルド エクスプローラー
- ファイル
- 機能

これらのビューが表示されない場合は、[手順 1](#configuration-steps)の説明に従って WPA が正しく構成されていることを再確認してください。 次に示すように、ビューを右側の空の [分析] ウィンドウにドラッグすると、ビルド データを表示できます。

![Windows パフォーマンス アナライザで C++ ビルドインサイトトレースを表示する](media/wpa-viewing-trace.gif)

その他のビューは、グラフエクスプローラパネルで使用できます。 含まれている情報に関心がある場合は、分析ウィンドウにドラッグします。 有用な 1 つは、ビルド全体の CPU 使用率を示す CPU (サンプル) ビューです。

## <a name="more-information"></a>詳細情報

[チュートリアル: Windows パフォーマンス アナライザの基本](wpa-basics.md)\
ビルド トレースの分析に役立つ一般的な WPA 操作について説明します。

[リファレンス: vcperf コマンド](/cpp/build-insights/reference/vcperf-commands)\
*vcperf.exe*コマンド リファレンスには、使用可能なすべてのコマンド オプションが一覧表示されています。

[リファレンス: Windows パフォーマンス アナライザービュー](/cpp/build-insights/reference/wpa-views)\
WPA の C++ ビルド インサイト ビューの詳細については、この記事を参照してください。

[パフォーマンス アナライザー](/windows-hardware/test/wpt/windows-performance-analyzer)\
公式の WPA ドキュメント サイト。

::: moniker-end
