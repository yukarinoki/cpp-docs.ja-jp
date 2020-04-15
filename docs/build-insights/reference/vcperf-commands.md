---
title: 'リファレンス: vcperf コマンド'
description: コマンド ライン ユーティリティ vcperf.exe のリファレンスです。
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9d3b0a9dbdfe922dc87f91006441e1f65d54c8a7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323253"
---
# <a name="reference-vcperf-commands"></a>リファレンス: vcperf コマンド

::: moniker range="<=vs-2017"

C++ ビルドインサイト ツールは、Visual Studio 2019 で使用できます。 そのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range="vs-2019"

この資料では *、vcperf.exe*で使用できるコマンドとその使用方法について説明します。

## <a name="commands-to-start-and-stop-traces"></a>トレースを開始および停止するコマンド

*重要: 次のコマンドはすべて、管理者特権を必要とします。*

| オプション           | 引数と説明 |
|------------------|---------------------------|
| `/start`         | `[/nocpusampling]` `<sessionName>` |
|                  | *vcperf.exe*に、指定されたセッション名でトレースを開始するように指示します。 特定のマシン上で一度に 1 つのアクティブ・セッションしか存在できません。 <br/><br/> このオプション`/nocpusampling`を指定した場合 *、vcperf.exe*は CPU サンプルを収集しません。 Windows パフォーマンス アナライザーで CPU 使用率 (サンプル) ビューを使用できなくなりますが、収集されたトレースのサイズは小さくなります。 <br/><br/> トレースが開始されると *、vcperf.exe*はすぐに返します。 イベントは、コンピュータ上で実行されているすべてのプロセスについてシステム全体で収集されます。 つまり *、vcperf.exe*を実行するために使用したコマンド プロンプトと同じコマンド プロンプトからプロジェクトをビルドする必要はありません。 たとえば、Visual Studio からプロジェクトをビルドできます。 |
| `/stop`          | `<sessionName>` `<outputFile.etl>` |
|                  | 指定されたセッション名で識別されるトレースを停止します。 トレースの後処理ステップを実行して、Windows パフォーマンス アナライザー (WPA) で表示可能なファイルを生成します。 最適な表示エクスペリエンスを得るため、C++ ビルド インサイト アドインを含む WPA のバージョンを使用します。 詳細については、「 [C++ ビルドインサイトの概要](/cpp/build-insights/get-started-with-cpp-build-insights)」を参照してください。 この`<outputFile.etl>`パラメーターは、出力ファイルの保存場所を指定します。 |
| `/stopnoanalyze` | `<sessionName>` `<rawOutputFile.etl>` |
|                  | 指定されたセッション名で識別されたトレースを停止し、未処理の未処理データを、指定された出力ファイルに書き込みます。 結果のファイルは WPA で表示されることを意図していません。 <br/><br/> コマンドに関連する`/stop`後処理ステップは、時間が長くなる場合があります。 このコマンドを`/stopnoanalyze`使用して、この後処理ステップを遅らせることができます。 Windows`/analyze`パフォーマンス アナライザで表示可能なファイルを生成する準備ができたら、このコマンドを使用します。 |

## <a name="miscellaneous-commands"></a>その他のコマンド

| オプション     | 引数と説明 |
|------------|---------------------------|
| `/analyze` | `<rawInputFile.etl> <outputFile.etl>` |
|            | コマンドによって生成された生のトレース・ファイル`/stopnoanalyze`を受け入れます。 このトレースで処理後の手順を実行し、Windows パフォーマンス アナライザで表示可能なファイルを生成します。 最適な表示エクスペリエンスを得るため、C++ ビルド インサイト アドインを含む WPA のバージョンを使用します。 詳細については、「 [C++ ビルドインサイトの概要](/cpp/build-insights/get-started-with-cpp-build-insights)」を参照してください。 |

## <a name="see-also"></a>関連項目

[C++ ビルドインサイトの概要](/cpp/build-insights/get-started-with-cpp-build-insights)\
[チュートリアル: Windows パフォーマンス アナライザの基本](/cpp/build-insights/tutorials/wpa-basics)\
[リファレンス: Windows パフォーマンス アナライザービュー](wpa-views.md)\
[Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end
