---
title: C++ ビルド インサイト SDK
description: ビジュアル スタジオ C++ ビルド インサイト SDK の概要。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyzing
- Relogging
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 126abb0d039227eb269500966d46ef0a729763ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323261"
---
# <a name="c-build-insights-sdk"></a>C++ ビルド インサイト SDK

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

C++ ビルド インサイト SDK は、C++ ビルド インサイト プラットフォームの上にパーソナライズされたツールを作成できる API のコレクションです。 このページでは、概要を説明し、作業を開始できます。

## <a name="obtaining-the-sdk"></a>SDK の取得

次の手順に従って、C++ ビルド インサイト SDK を NuGet パッケージとしてダウンロードできます。

1. Visual Studio 2017 以降では、新しい C++ プロジェクトを作成します。
1. ソリューション**エクスプローラー**ペインで、プロジェクトを右クリックします。
1. コンテキスト メニューから **[NuGet パッケージの管理**] を選択します。
1. 右上で **、nuget.org**パッケージ ソースを選択します。
1. パッケージの最新バージョンを検索します。
1. [**インストール ]** を選択します。
1. ライセンスを受け入れます。

SDK を取り巻く一般的な概念については、このトピックを参照してください。 公式[C++ ビルドインサイトサンプル GitHub リポジトリ](https://github.com/microsoft/cpp-build-insights-samples)にアクセスして、SDK を使用する実際の C++ アプリケーションの例を確認することもできます。

## <a name="collecting-a-trace"></a>トレースの収集

C++ ビルド インサイト SDK を使用して MSVC ツールチェーンから発生するイベントを分析するには、まずトレースを収集する必要があります。 SDK では、Windows のイベント トレース (ETW) を基になるトレース テクノロジとして使用します。 トレースの収集は、次の 2 つの方法で行うことができます。

### <a name="method-1-using-vcperf-in-visual-studio-2019-and-above"></a>方法 1: Visual Studio 2019 以降で vcperf を使用する

1. VS 2019 の管理者特権で x64 ネイティブ ツール コマンド プロンプトを開きます。
1. 次のコマンドを実行します。`vcperf /start MySessionName`
1. プロジェクトをビルドします。
1. 次のコマンドを実行します。`vcperf /stopnoanalyze MySessionName outputTraceFile.etl`

   > [!IMPORTANT]
   > vcperf でトレースを`/stopnoanalyze`停止する場合は、このコマンドを使用します。 C++ ビルドインサイト SDK を使用して、通常`/stop`のコマンドによって停止されたトレースを分析することはできません。

### <a name="method-2-programmatically"></a>方法 2 : プログラムを使用して

これらの C++ Build Insights SDK トレース コレクション関数を使用して、プログラムでトレースを開始および停止します。 **これらの関数呼び出しを実行するプログラムには、管理者特権が必要です。** 管理特権が必要なのは、開始および停止のトレース機能だけです。 C++ ビルドインサイト SDK の他のすべての関数は、それらを使用せずに実行できます。

### <a name="sdk-functions-related-to-trace-collection"></a>トレースコレクションに関連する SDK 関数

| 機能 | C++ API | C API |
|--|--|--|
| トレースの開始 | [トレースセッションを開始する](functions/start-tracing-session.md) | [トレースセッションを開始する](functions/start-tracing-session-a.md)<br />[トレースセッションを開始](functions/start-tracing-session-w.md) |
| トレースの停止 | [セッションを停止します。](functions/stop-tracing-session.md) | [ストップトレースセッションA](functions/stop-tracing-session-a.md)<br />[ストップトレースセッションW](functions/stop-tracing-session-w.md) |
| トレースを停止し、<br />結果を直ちに分析する | [トレースセッションを停止して分析する](functions/stop-and-analyze-tracing-session.md) | [トレースセッションを停止して分析する](functions/stop-and-analyze-tracing-session-a.md)<br />[トレースセッションを停止して分析する](functions/stop-and-analyze-tracing-session-w.md) |
| トレースを停止し、<br />結果を直ちに再ログする | [セッションを停止します。](functions/stop-and-relog-tracing-session.md) | [ストップアンドログトレーシングセッション](functions/stop-and-relog-tracing-session-a.md)<br />[停止アンドログトレーシングセッション](functions/stop-and-relog-tracing-session-w.md) |

以下のセクションでは、分析セッションまたは再ロギング セッションの構成方法を示します。 これは、組み合わされた機能 ([たとえば、StopAndAnalyzeTracingSession](functions/stop-and-analyze-tracing-session.md)など) に必要です。

## <a name="consuming-a-trace"></a>トレースの使用

ETW トレースを取得したら、C++ ビルド インサイト SDK を使用してアンパックします。 SDK では、ツールを迅速に開発できる形式のイベントが提供されます。 SDK を使用せずに、未処理の ETW トレースを使用することはお勧めしません。 MSVC で使用されるイベント形式は文書化されておらず、巨大なビルドに合わせて最適化されており、意味を理解するのは難しいです。 さらに、C++ ビルド インサイト SDK API は安定していますが、未処理の ETW トレース形式は予告なく変更される可能性があります。

### <a name="sdk-types-and-functions-related-to-trace-consumption"></a>トレースの消費に関連する SDK の種類と関数

| 機能 | C++ API | C API | Notes |
|--|--|--|--|
| イベントコールバックの設定 | [Iアナライザ](other-types/ianalyzer-class.md)<br />[イレロガー](other-types/irelogger-class.md) | [ANALYSIS_CALLBACKS](other-types/analysis-callbacks-struct.md)<br />[RELOG_CALLBACKS](other-types/relog-callbacks-struct.md) | C++ ビルドインサイト SDK は、コールバック関数を通じてイベントを提供します。 C++ では、IAnalyzer または IRelogger インターフェイスを継承するアナライザーまたはリロガー クラスを作成してコールバック関数を実装します。 C では、グローバル関数でコールバックを実装し、ANALYSIS_CALLBACKSまたはRELOG_CALLBACKS構造体でコールバックへのポインターを提供します。 |
| ビルディンググループ | [メイクアップスタティックアナライザグループ](functions/make-static-analyzer-group.md)<br />[リロガーグループを作成します。](functions/make-static-relogger-group.md)<br />[メイクダイナミックアナライザグループ](functions/make-dynamic-analyzer-group.md)<br />[メイクダイナミックリロガーグループ](functions/make-dynamic-relogger-group.md) |  | C++ API は、複数のアナライザーとリロガー オブジェクトをグループ化するためのヘルパー関数と型を提供します。 グループは、複雑な分析を簡単なステップに分割する適切な方法です。 [vcperf](https://github.com/microsoft/vcperf)はこのように編成されます。 |
| 分析または再ロギング | [分析](functions/analyze.md)<br />[リログ](functions/relog.md) | [分析A](functions/analyze-a.md)<br />[分析W](functions/analyze-w.md)<br />[リロガ](functions/relog-a.md)<br />[リログ](functions/relog-w.md) |  |

### <a name="analyzing-and-relogging"></a>分析と再ロギング

トレースの使用は、分析セッションまたは再ロギング セッションを通じて行われます。

通常の分析を使用することは、ほとんどのシナリオに適しています。 このメソッドを使用すると、`printf`テキスト、xml、JSON、データベース、REST 呼び出しなどの出力形式を柔軟に選択できます。

ログの記録は、ETW 出力ファイルを生成する必要がある特殊な分析のためのものです。 再ロギングを使用すると、C++ のビルドインサイトイベントを独自の ETW イベント形式に変換できます。 再ロギングの適切な使用は、既存の ETW ツールとインフラストラクチャに C++ ビルドインサイトデータをフックすることです。 たとえば[、vcperf](https://github.com/microsoft/vcperf)は再ロギング インターフェイスを使用します。 これは、ETW ツールである Windows パフォーマンス アナライザーが理解できるデータを生成する必要があるためです。 再ロギング インターフェイスを使用する場合は、ETW の動作に関する事前知識が必要です。

### <a name="creating-analyzer-groups"></a>アナライザ グループの作成

グループの作成方法を知ることが重要です。 Hello world を印刷するアナライザー グループを作成する方法を示す例を次に示*します。* 受信するすべてのアクティビティ開始イベントに対して。

```cpp
using namespace Microsoft::Cpp::BuildInsights;

class Hello : public IAnalyzer
{
public:
    AnalysisControl OnStartActivity(
        const EventStack& eventStack) override
    {
        std::cout << "Hello, " << std::endl;
        return AnalysisControl::CONTINUE;
    }
};

class World : public IAnalyzer
{
public:
    AnalysisControl OnStartActivity(
        const EventStack& eventStack) override
    {
        std::cout << "world!" << std::endl;
        return AnalysisControl::CONTINUE;
    }
};

int main()
{
    Hello hello;
    World world;

    // Let's make Hello the first analyzer in the group
    // so that it receives events and prints "Hello, "
    // first.
    auto group = MakeStaticAnalyzerGroup(&hello, &world);

    unsigned numberOfAnalysisPasses = 1;

    // Calling this function initiates the analysis and
    // forwards all events from "inputTrace.etl" to my analyzer
    // group.
    Analyze("inputTrace.etl", numberOfAnalysisPasses, group);

    return 0;
}
```

## <a name="using-events"></a>イベントの使用

### <a name="sdk-types-and-functions-related-to-events"></a>イベントに関連する SDK の型と関数

| 機能 | C++ API | C API | Notes |
|--|--|--|--|
| イベントのマッチングとフィルタリング | [関数を一致させます。](functions/match-event-stack-in-member-function.md)<br />[イベントスタックを一致させる](functions/match-event-stack.md)<br />[関数を指定します。](functions/match-event-in-member-function.md)<br />[マッチイベント](functions/match-event.md) |  | C++ API には、トレースから関心のあるイベントを簡単に抽出できる関数が用意されています。 C API では、このフィルタリングは手操作で行う必要があります。 |
| イベント データ型 | [アクティビティ](cpp-event-data-types/activity.md)<br />[バックエンドパス](cpp-event-data-types/back-end-pass.md)<br />[ボトムアップ](cpp-event-data-types/bottom-up.md)<br />[C1DLL](cpp-event-data-types/c1-dll.md)<br />[C2DLL](cpp-event-data-types/c2-dll.md)<br />[コードジェネレーション](cpp-event-data-types/code-generation.md)<br />[コマンドライン](cpp-event-data-types/command-line.md)<br />[コンパイラ](cpp-event-data-types/compiler.md)<br />[コンパイラパス](cpp-event-data-types/compiler-pass.md)<br />[EnvironmentVariable](cpp-event-data-types/environment-variable.md)<br />[イベント](cpp-event-data-types/event.md)<br />[イベントグループ](cpp-event-data-types/event-group.md)<br />[イベントスタック](cpp-event-data-types/event-stack.md)<br />[イメージ出力](cpp-event-data-types/executable-image-output.md)<br />[出力](cpp-event-data-types/exp-output.md)<br />[ファイル入力](cpp-event-data-types/file-input.md)<br />[ファイル出力](cpp-event-data-types/file-output.md)<br />[フォースインリネ](cpp-event-data-types/force-inlinee.md)<br />[フロントエンドファイル](cpp-event-data-types/front-end-file.md)<br />[フロントエンドファイルグループ](cpp-event-data-types/front-end-file-group.md)<br />[フロントエンドパス](cpp-event-data-types/front-end-pass.md)<br />[関数](cpp-event-data-types/function.md)<br />[インプリブ出力](cpp-event-data-types/imp-lib-output.md)<br />[[呼び出し]](cpp-event-data-types/invocation.md)<br />[呼び出しグループ](cpp-event-data-types/invocation-group.md)<br />[リブアウトプット](cpp-event-data-types/lib-output.md)<br />[リンカー](cpp-event-data-types/linker.md)<br />[リンカーグループ](cpp-event-data-types/linker-group.md)<br />[リンカーパス](cpp-event-data-types/linker-pass.md)<br />[Ltcg](cpp-event-data-types/ltcg.md)<br />[出力](cpp-event-data-types/obj-output.md)<br />[オプティフ](cpp-event-data-types/opt-icf.md)<br />[オプトLBR](cpp-event-data-types/opt-lbr.md)<br />[オプトレフ](cpp-event-data-types/opt-ref.md)<br />[パス1](cpp-event-data-types/pass1.md)<br />[パス2](cpp-event-data-types/pass2.md)<br />[プレエルトCGオプトレフ](cpp-event-data-types/pre-ltcg-opt-ref.md)<br />[シンプルイベント](cpp-event-data-types/simple-event.md)<br />[シンボル名](cpp-event-data-types/symbol-name.md)<br />[テンプレートのインスタンス化](cpp-event-data-types/template-instantiation.md)<br />[テンプレートインスタンス化グループ](cpp-event-data-types/template-instantiation-group.md)<br />[スレッド](cpp-event-data-types/thread.md)<br />[トップダウン](cpp-event-data-types/top-down.md)<br />[トレース情報](cpp-event-data-types/trace-info.md)<br />[プログラム分析全体](cpp-event-data-types/whole-program-analysis.md) | [CL_PASS_DATA](c-event-data-types/cl-pass-data-struct.md)<br />[EVENT_COLLECTION_DATA](c-event-data-types/event-collection-data-struct.md)<br />[EVENT_DATA](c-event-data-types/event-data-struct.md)<br />[EVENT_ID](c-event-data-types/event-id-enum.md)<br />[FILE_DATA](c-event-data-types/file-data-struct.md)<br />[FILE_TYPE_CODE](c-event-data-types/file-type-code-enum.md)<br />[FRONT_END_FILE_DATA](c-event-data-types/front-end-file-data-struct.md)<br />[FUNCTION_DATA](c-event-data-types/function-data-struct.md)<br />[FUNCTION_FORCE_INLINEE_DATA](c-event-data-types/function-force-inlinee-data-struct.md)<br />[INVOCATION_DATA](c-event-data-types/invocation-data-struct.md)<br />[INVOCATION_VERSION_DATA](c-event-data-types/invocation-version-data-struct.md)<br />[MSVC_TOOL_CODE](c-event-data-types/msvc-tool-code-enum.md)<br />[NAME_VALUE_PAIR_DATA](c-event-data-types/name-value-pair-data-struct.md)<br />[SYMBOL_NAME_DATA](c-event-data-types/symbol-name-data-struct.md)<br />[TEMPLATE_INSTANTIATION_DATA](c-event-data-types/template-instantiation-data-struct.md)<br />[TEMPLATE_INSTANTIATION_KIND_CODE](c-event-data-types/template-instantiation-kind-code-enum.md)<br />[TRACE_INFO_DATA](c-event-data-types/trace-info-data-struct.md)<br />[TRANSLATION_UNIT_PASS_CODE](c-event-data-types/translation-unit-pass-code-enum.md) |  |

### <a name="activities-and-simple-events"></a>アクティビティと簡単なイベント

イベントには *、アクティビティ*と*シンプルイベント*の 2 つのカテゴリがあります。 活動は、開始と終了を持つ時間内の継続的なプロセスです。 単純なイベントは時間厳守の発生であり、期間がありません。 C++ ビルド インサイト SDK を使用して MSVC トレースを分析する場合、アクティビティが開始および停止したときに個別のイベントが表示されます。 単純なイベントが発生した場合は、1 つのイベントのみが表示されます。

### <a name="parent-child-relationships"></a>親子関係

アクティビティと単純なイベントは、親子関係を介して相互に関連付けられます。 アクティビティまたは単純なイベントの親は、それらが発生する包括的なアクティビティです。 たとえば、ソース ファイルをコンパイルする場合、コンパイラはファイルを解析してからコードを生成する必要があります。 解析とコード生成アクティビティは、コンパイラ アクティビティの子です。

単純なイベントには期間が設定されていないので、その中で何も起こり得ません。 したがって、彼らは子供を持つことはありません。

各アクティビティと単純イベントの親子関係は、[イベント テーブル](event-table.md)に示されています。 C++ の分析情報イベントを使用する場合は、これらの関係を把握することが重要です。 イベントの完全なコンテキストを理解するために、多くの場合、それらに頼る必要があります。

### <a name="properties"></a>プロパティ

すべてのイベントには、次のプロパティがあります。

| プロパティ | 説明 |
|--|--|
| 型識別子 | イベントの種類を一意に識別する数値。 |
| インスタンス識別子 | トレース内のイベントを一意に識別する番号。 同じタイプの 2 つのイベントがトレースで発生した場合、どちらも一意のインスタンス識別子を取得します。 |
| 開始時刻 | アクティビティーが開始された時刻、または単純なイベントが発生した時刻。 |
| プロセス識別子 | イベントが発生したプロセスを識別する番号。 |
| スレッド識別子 | イベントが発生したスレッドを識別する番号。 |
| プロセッサ インデックス | イベントがどの論理プロセッサによって生成されたかを示す 0 から始まるインデックス。 |
| イベント名 | イベントの種類を説明する文字列。 |

単純なイベント以外のすべてのアクティビティにも、次のプロパティがあります。

| プロパティ | 説明 |
|--|--|
| 停止時間 | アクティビティが停止した時刻。 |
| 排他期間 | 子アクティビティで費やされた時間を除く、アクティビティで費やされた時間。 |
| CPU 時間 | アクティビティにアタッチされたスレッドのコードの実行に CPU が費やした時間。 アクティビティにアタッチされたスレッドがスリープ状態になっていた時間は含みません。 |
| 排他 CPU 時間 | CPU 時間と同じですが、子アクティビティーによって費やされた CPU 時間は除きます。 |
| ウォールクロック時間責任 | 全体的な壁時計時間へのアクティビティの貢献。 ウォールクロック時間の責任は、アクティビティ間の並列性を考慮に入れます。 たとえば、2 つの無関係なアクティビティが並列に実行されているとします。 どちらも 10 秒の持続時間があり、開始時間と停止時間はまったく同じです。 この場合、Build Insights は両方とも 5 秒のウォールクロック時間の責任を割り当てます。 これに対し、これらのアクティビティがオーバーラップなしで次々に実行される場合、両方とも 10 秒のウォールクロック時間の責任が割り当てられます。 |
| 排他的なウォールクロック時間責任 | ウォールクロックの時間責任と同じですが、子アクティビティのウォールクロック時間の責任は除外されます。 |

一部のイベントには、言及されているものを超える独自のプロパティがあります。 この場合、これらの追加プロパティは[イベント テーブル](event-table.md)に一覧表示されます。

### <a name="consuming-events-provided-by-the-c-build-insights-sdk"></a>C++ ビルドインサイト SDK によって提供されるイベントの使用

#### <a name="the-event-stack"></a>イベント スタック

C++ ビルドインサイト SDK がイベントを提供するたびに、スタックの形式で表示されます。 スタックの最後のエントリは現在のイベントであり、その親階層になる前のエントリです。 たとえば[、LTCG](event-table.md#ltcg)の開始イベントと停止イベントは、リンカーのパス 1 の間に発生します。 この場合、受信するスタックには\[[LINKER](event-table.md#linker) [、PASS1](event-table.md#pass1)、LTCG が\]含まれます。 親階層は、イベントをルートにトレースバックできるため便利です。 上記の LTCG アクティビティが遅い場合は、どのリンカー呼び出しが関係していたかをすぐに知ることができます。

#### <a name="matching-events-and-event-stacks"></a>イベントとイベント スタックの照合

C++ ビルドインサイト SDK は、トレース内のすべてのイベントを提供しますが、ほとんどの場合、そのサブセットのみを気にします。 場合によっては、イベント スタックのサブセットだけを気*にする場合があります*。 SDK には、必要なイベントやイベント スタックをすばやく抽出し、必要としないイベントスタックを拒否する機能が用意されています。 この関数は、次の一致関数を使用して実行されます。

|  |  |
|--|--|
| [マッチイベント](functions/match-event.md) | イベントが指定された型のいずれかに一致する場合は、イベントを保持します。 一致したイベントをラムダまたはその他の呼び出し可能な型に転送します。 イベントの親階層は、この関数では考慮されません。 |
| [関数を指定します。](functions/match-event-in-member-function.md) | メンバー関数のパラメーターで指定された型と一致する場合は、イベントを保持します。 一致したイベントをメンバー関数に転送します。 イベントの親階層は、この関数では考慮されません。 |
| [イベントスタックを一致させる](functions/match-event-stack.md) | イベントとその親階層の両方が指定された型と一致する場合は、イベントを保持します。 イベントと一致する親階層イベントをラムダまたはその他の呼び出し可能な型に転送します。 |
| [関数を一致させます。](functions/match-event-stack-in-member-function.md) | イベントとその親階層の両方がメンバー関数のパラメーター リストで指定された型と一致する場合は、イベントを保持します。 イベントと一致する親階層イベントをメンバー関数に転送します。 |

イベント スタックの照合関数`MatchEventStack`などは、親階層を一致させるときにギャップを許容します。 たとえば、\[[リンカー](event-table.md#linker) [、LTCG](event-table.md#ltcg)\]スタックに興味があるとします。 また、\[リンカー、[パス1、LTCG](event-table.md#pass1)\]スタックにも一致します。 最後に指定する型は、一致するイベントの種類である必要があり、親階層の一部ではありません。

#### <a name="capture-classes"></a>クラスのキャプチャ

関数を`Match*`使用するには、一致させる型を指定する必要があります。 これらの型は、*キャプチャ クラス*の一覧から選択されます。 キャプチャ クラスには、以下に説明するいくつかのカテゴリがあります。

| カテゴリ | 説明 |
|--|--|
| [Exact] | これらのキャプチャ クラスは、特定のイベントタイプと一致するために使用され、他には一致しません。 たとえば[、COMPILER](cpp-event-data-types/compiler.md)[イベントと](event-table.md#compiler)一致するコンパイラ クラスがあります。 |
| ワイルドカード | これらのキャプチャ クラスは、サポートするイベントのリストから任意のイベントを照合するために使用できます。 たとえば、[アクティビティ](cpp-event-data-types/activity.md)ワイルドカードは、任意のアクティビティ イベントと一致します。 もう 1 つの例として、FRONT_END_PASS[イベントまたは](event-table.md#front-end-pass)[BACK_END_PASS](event-table.md#back-end-pass)イベントのいずれかに一致する[CompilerPass](cpp-event-data-types/compiler-pass.md)ワイルドカードがあります。 |
| グループ | グループ キャプチャ クラスの名前は *、グループ*で終わる 。 これらは、同じ種類の複数のイベントを連続して照合するために使用され、ギャップは無視されます。 再帰的なイベントを照合する場合にのみ意味をなします。 たとえば[、FRONT_END_FILE](event-table.md#front-end-file)アクティビティは、コンパイラがファイルを解析するたびに発生します。 コンパイラはファイルの解析中に include ディレクティブを見つける可能性があるため、このアクティビティは再帰的です。 [クラス](cpp-event-data-types/front-end-file.md)は、スタック内の 1 つのFRONT_END_FILEイベントにのみ一致します。 [クラスを](cpp-event-data-types/front-end-file-group.md)使用して、インクルード階層全体を一致させます。 |
| ワイルドカード グループ | ワイルドカード グループは、ワイルドカードとグループのプロパティを結合します。 このカテゴリの唯一のクラスは[InvocationGroup](cpp-event-data-types/invocation-group.md)で、すべての[LINKER](event-table.md#linker)イベントと[COMPILER](event-table.md#compiler)イベントを 1 つのイベント スタックに一致してキャプチャします。 |

[イベントテーブル](event-table.md)を参照して、各イベントに一致させるためにどのキャプチャクラスを使用できるかを確認してください。

#### <a name="after-matching-using-captured-events"></a>マッチング後: キャプチャされたイベントを使用する

一致が正常に完了すると、関数`Match*`はキャプチャ クラス オブジェクトを構築し、指定された関数に転送します。 これらのキャプチャ クラス オブジェクトを使用して、イベントのプロパティにアクセスします。

#### <a name="example"></a>例

```cpp
AnalysisControl MyAnalyzer::OnStartActivity(const EventStack& eventStack)
{
    // The event types to match are specified in the PrintIncludes function
    // signature.  
    MatchEventStackInMemberFunction(eventStack, this, &MyAnalyzer::PrintIncludes);
}

// We want to capture event stacks where:
// 1. The current event is a FrontEndFile activity.
// 2. The current FrontEndFile activity has at least one parent FrontEndFile activity
//    and possibly many.
void PrintIncludes(FrontEndFileGroup parentIncludes, FrontEndFile currentFile)
{
    // Once we reach this point, the event stack we are interested in has been matched.
    // The current FrontEndFile activity has been captured into 'currentFile', and
    // its entire inclusion hierarchy has been captured in 'parentIncludes'.

    cout << "The current file being parsed is: " << currentFile.Path() << endl;
    cout << "This file was reached through the following inclusions:" << endl;

    for (auto& f : parentIncludes)
    {
        cout << f.Path() << endl;
    }
}
```

::: moniker-end
