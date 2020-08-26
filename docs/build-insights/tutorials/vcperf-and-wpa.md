---
title: 'チュートリアル: vcperf および Windows パフォーマンス アナライザー'
description: C++ のビルド トレースを分析するための vcperf および WPA の使用方法に関するチュートリアル。
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f3a0b4a9c57fd55c6788481adbf91c48e362444e
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833401"
---
# <a name="tutorial-vcperf-and-windows-performance-analyzer"></a>チュートリアル: vcperf および Windows パフォーマンス アナライザー

::: moniker range="<=vs-2017"

C++ Build Insights ツールは、Visual Studio 2019 で使用できます。 このバージョンのドキュメントを表示するには、この記事の Visual Studio の **[バージョン]** セレクター コントロールを Visual Studio 2019 に設定してください。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range="vs-2019"

このチュートリアルでは、*vcperf.exe* を使用して C++ ビルドのトレースを収集する方法について説明します。 また、Windows パフォーマンス アナライザーでこのトレースを表示する方法についても説明します。

## <a name="step-1-install-and-configure-windows-performance-analyzer"></a>手順 1: Windows パフォーマンス アナライザーをインストールして構成する

WPA は、Windows アセスメント &amp; デプロイメント キット (ADK) で使用できるトレース ビューアーです。 これは、Visual Studio インストーラーを使用してインストールできるコンポーネントの一部ではない、独立したユーティリティです。

C++ Build Insights をサポートする WPA のバージョンは、現在 Windows ADK Insider プレビューでのみ使用できます。 このプレビューにアクセスするには、[Windows Insider プログラム](https://insider.windows.com)にサインアップする必要があります。 Windows ADK プレビューを入手するために、Windows 10 Insider Preview オペレーティング システムをインストールする必要はありません。 Microsoft アカウントを Windows Insider プログラムに登録するだけです。

### <a name="to-download-and-install-wpa"></a>WPA をダウンロードしてインストールするには

注:Windows パフォーマンス アナライザーをインストールするには、Windows 8 以降が必要です。

1. Windows ADK の[ダウンロード ページ](/windows-hardware/get-started/adk-install)を参照してください。

1. Windows ADK の最新バージョンをダウンロードしてインストールします。

1. インストールする機能の入力を求められたら、 **[Windows Performance Toolkit]** を選択します。 必要に応じて他の機能を選択することもできますが、WPA をインストールする必要はありません。

   ![Windows パフォーマンス アナライザー インストーラーの機能の選択画面](media/wpa-installation.png)

### <a name="to-configure-wpa"></a><a name="configuration-steps"></a> WPA を構成するには

WPA で C++ Build Insights トレースを表示するには、特別なアドインが必要です。 次の手順に従ってインストールしてください。

1. 次のコンポーネントのいずれかをダウンロードして、アドインを入手します。 両方を入手する必要はありません。 最も便利なものを選択します。
    1. [Visual Studio 2019 バージョン 16.6 以降](https://visualstudio.microsoft.com/downloads/)、または
    1. [C++ Build Insights NuGet パッケージ](https://www.nuget.org/packages/Microsoft.Cpp.BuildInsights/)。

1. `perf_msvcbuildinsights.dll` ファイルを WPA インストール ディレクトリにコピーします。
    1. Visual Studio 2019 バージョン 16.6 以降では、このファイルは `C:\Program Files (x86)\Microsoft Visual Studio\2019\{Edition}\VC\Tools\MSVC\{Version}\bin\Host{Architecture}\{Architecture}` にあります。
    1. C++ Build Insights NuGet パッケージでは、このファイルは `wpa\{Architecture}` にあります。
    1. 上記のパスで、中かっこで囲まれた変数を次のように置き換えます。
        1. `{Edition}` は、Community、Professional、Enterprise などの Visual Studio 2019 のエディションです。
        1. `{Version}` は MSVC のバージョンです。 入手できる中で最新のものを選択します。
        1. `{Architecture}`: 64 ビット バージョンの Windows を使用している場合は、`x64` を選択します。 それ以外の場合は、`x86` を選択します。
    1. WPA のインストール ディレクトリは、通常は `C:\Program Files (x86)\Windows Kits\10\Windows Performance Toolkit` です。

1. WPA のインストール ディレクトリにある `perfcore.ini` ファイルを開き、`perf_msvcbuildinsights.dll` のエントリを追加します。

## <a name="step-2-trace-your-build-with-vcperfexe"></a>手順 2: vcperf.exe を使用してビルドをトレースする

C++ Build Insights データを表示するには、まず、次の手順に従ってトレース ファイルに収集します。

1. 管理者モードで、VS 2019 の **x64** または **x86 Native Tools コマンド プロンプト**を開きます ([スタート] メニュー項目を右クリックして、 **[その他]**  >  **[管理者として実行]** を選択します。)
    1. 64 ビット版の Windows を使用している場合は **x64** を選択します。 それ以外の場合は **x86** を選択します。

1. コマンド プロンプト ウィンドウで、次のコマンドを入力します。

   **vcperf.exe /start _SessionName_**

   *SessionName* のセッション名を選択し、覚えておきます。

1. 通常どおりにプロジェクトをビルドします。 ビルドに同じコマンド プロンプト ウィンドウを使用する必要はありません。

1. コマンド プロンプト ウィンドウで、次のコマンドを入力します。

   **vcperf.exe /stop _SessionName_ _traceFile.etl_**

   以前に *SessionName* に選択したものと同じセッション名を使用します。 *traceFile.etl* トレース ファイルに適切な名前を選択します。

開発者コマンド プロンプト ウィンドウでの一般的な *vcperf.exe* コマンド シーケンスは次のようになります。

![単純な vcperf.exe の使用シナリオ](media/vcperf-simple-usage.png)

### <a name="important-notes-about-vcperfexe"></a>vcperf.exe に関する重要な注意事項

- *vcperf.exe* トレースを開始または停止するには、管理者特権が必要です。 **[管理者として実行]** を使用して開いた開発者コマンド プロンプト ウィンドウを使用します。

- マシン上で実行できるトレース セッションは一度に 1 つだけです。

- トレースの開始に使用したセッション名を忘れないようにしてください。 名前がわからない場合、実行中のセッションを停止することが困難になる場合があります。

- *cl.exe* と *link.exe* と同様に、コマンドライン ユーティリティ *vcperf.exe* は MSVC インストールに含まれています。 このコンポーネントを取得するために追加の手順は必要ありません。

- *vcperf.exe* を使用すると、システムで実行されているすべての MSVC ツールに関する情報を収集できます。 そのため、トレースの収集に使用したものと同じコマンド プロンプトからビルドを開始する必要はありません。 別のコマンド プロンプトから、または Visual Studio からでもプロジェクトをビルドできます。

### <a name="vcperfexe-is-open-source"></a>vcperf.exe はオープンソースです

独自のバージョンの *vcperf.exe* をビルドして実行する場合は、[vcperf GitHub リポジトリ](https://github.com/microsoft/vcperf)から複製しても構いません。

## <a name="step-3-view-your-trace-in-windows-performance-analyzer"></a>手順 3: Windows パフォーマンス アナライザーでトレースを表示する

WPA を起動し、先ほど収集したトレースを開きます。 WPA ではこれが C++ Build Insights トレースとして認識され、左側の Graph エクスプローラー パネルに次のビューが表示されます。

- ビルド エクスプローラー
- ファイル
- 関数
- テンプレートのインスタンス化

これらのビューが表示されない場合は、[手順 1](#configuration-steps) の説明に従って、WPA が正しく構成されていることを再確認します。 次に示すように、ビューを右側の空の分析ウィンドウにドラッグすることで、ビルド データを表示できます。

![Windows パフォーマンス アナライザーでの C++ Build Insights トレースの表示](media/wpa-viewing-trace.gif)

その他のビューは、Graph エクスプローラー パネルで使用できます。 表示されている情報に関心がある場合は、それらを [分析] ウィンドウにドラッグします。 便利なものとして、ビルド全体の CPU 使用率を示す CPU (サンプリングされた) ビューがあります。

## <a name="more-information"></a>詳細情報

[チュートリアル: Windows パフォーマンス アナライザーの基本](wpa-basics.md)\
ビルド トレースの分析に役立つ一般的な WPA 操作について説明します。

[リファレンス: vcperf コマンド](/cpp/build-insights/reference/vcperf-commands)\
*vcperf.exe* コマンド リファレンスには、使用できるすべてのコマンド オプションが掲載されています。

[リファレンス: Windows パフォーマンス アナライザーのビュー](/cpp/build-insights/reference/wpa-views)\
WPA の C++ Build Insights ビューの詳細については、この記事を参照してください。

[Windows パフォーマンス アナライザー](/windows-hardware/test/wpt/windows-performance-analyzer)\
WPA の公式ドキュメント サイト。

::: moniker-end
