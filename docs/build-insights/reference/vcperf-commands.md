---
title: 'リファレンス: vcperf コマンド'
description: コマンド ライン ユーティリティ vcperf.exe のリファレンスです。
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 42ca422e11824bdbdad4e42e7b55950317095703
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922206"
---
# <a name="reference-vcperf-commands"></a>リファレンス: vcperf コマンド

::: moniker range="<=msvc-150"

C++ Build Insights ツールは、Visual Studio 2019 で使用できます。 このバージョンのドキュメントを表示するには、この記事の Visual Studio の **[バージョン]** セレクター コントロールを Visual Studio 2019 に設定してください。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range="msvc-160"

この記事では、 *vcperf.exe* で使用できるコマンドと、それらの使用方法について説明します。

## <a name="commands-to-start-and-stop-traces"></a>トレースを開始および停止するコマンド

" *重要: 以下の全コマンドには管理特権が必要です。* "

| オプション           | 引数と説明 |
|------------------|---------------------------|
| `/start`         | `[/nocpusampling]` `<sessionName>` |
|                  | 指定したセッション名でトレースを開始するように *vcperf.exe* に指示します。 指定したコンピューター上には一度に 1 つのアクティブなセッションしか存在できません。 <br/><br/> `/nocpusampling` オプションを指定した場合、 *vcperf.exe* によって CPU サンプルが収集されることはありません。 Windows Performance Analyzer で CPU 使用率 (サンプリング) ビューを使用できなくなりますが、収集されるトレースは小さくなります。 <br/><br/> トレースが開始されると、 *vcperf.exe* はすぐに制御を返します。 イベントはシステム全体で、コンピューター上で実行されているすべてのプロセスに対して収集されます。 つまり、 *vcperf.exe* の実行に使用したのと同じコマンド プロンプトからプロジェクトをビルドする必要はありません。 たとえば、Visual Studio からプロジェクトをビルドしてもかまいません。 |
| `/stop`          | `<sessionName>` `<outputFile.etl>` |
|                  | 指定したセッション名によって識別されるトレースを停止します。 トレースに対して後処理の手順を実行し、Windows Performance Analyzer (WPA) で表示できるファイルを生成します。 最適な表示エクスペリエンスを得るには、C++ Build Insights アドインを含むバージョンの WPA を使用します。 詳細については、「[C++ Build Insights を使ってみる](../get-started-with-cpp-build-insights.md)」をご覧ください。 `<outputFile.etl>` パラメーターによって出力ファイルの保存場所を指定できます。 |
| `/stopnoanalyze` | `<sessionName>` `<rawOutputFile.etl>` |
|                  | 指定したセッション名によって識別されるトレースを停止し、生の処理されていないデータを指定した出力ファイルに書き込みます。 生成されたファイルは、WPA で表示するためのものではありません。 <br/><br/> `/stop` コマンドに伴う後処理の手順には、時間がかかることがあります。 `/stopnoanalyze` コマンドを使用すると、この後処理の手順を遅らせることができます。 Windows Performance Analyzer で表示可能なファイルを生成する準備ができたら、`/analyze` コマンドを使用します。 |

## <a name="miscellaneous-commands"></a>その他のコマンド

| オプション     | 引数と説明 |
|------------|---------------------------|
| `/analyze` | `<rawInputFile.etl> <outputFile.etl>` |
|            | `/stopnoanalyze` コマンドによって生成された生のトレース ファイルを受け取ります。 このトレースに対して後処理の手順を実行し、Windows Performance Analyzer で表示できるファイルを生成します。 最適な表示エクスペリエンスを得るには、C++ Build Insights アドインを含むバージョンの WPA を使用します。 詳細については、「[C++ Build Insights を使ってみる](../get-started-with-cpp-build-insights.md)」をご覧ください。 |

## <a name="see-also"></a>関連項目

[C++ Build Insights を使ってみる](../get-started-with-cpp-build-insights.md)\
[チュートリアル: Windows パフォーマンス アナライザーの基本](../tutorials/wpa-basics.md)\
[リファレンス: Windows パフォーマンス アナライザーのビュー](wpa-views.md)\
[Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end
