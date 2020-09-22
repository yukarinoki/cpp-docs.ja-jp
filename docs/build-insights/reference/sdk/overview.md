---
title: C++Build Insights SDK
description: Visual Studio の C++ Build Insights SDK の概要。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyzing
- Relogging
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6f53a9b6c682a0af7d8a01f6378ed0574d8fa4ca
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041173"
---
# <a name="c-build-insights-sdk"></a>C++Build Insights SDK

::: moniker range="<=vs-2015"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=vs-2017"

C++ Build Insights SDK は、C++ Build Insights プラットフォーム上でパーソナライズされたツールを作成できる API のコレクションです。 このページでは、作業を開始するために役立つ概要を説明します。

## <a name="obtaining-the-sdk"></a>SDK の取得

次の手順に従って、C++ Build Insights SDK を NuGet パッケージとしてダウンロードできます。

1. Visual Studio 2017 以降で、新しい C++ プロジェクトを作成します。
1. **[ソリューション エクスプローラー]** ウィンドウで、プロジェクトを右クリックします。
1. コンテキスト メニューから **[NuGet パッケージの管理]** を選択します。
1. 右上で、 **[nuget.org]** パッケージ ソースを選択します。
1. Microsoft.Cpp.BuildInsights パッケージの最新バージョンを検索します。
1. **[インストール]** を選択します。
1. ライセンスに同意します。

SDK の一般的な概念に関する情報を参照してください。 公式の [C++ Build Insights サンプルの GitHub リポジトリ](https://github.com/microsoft/cpp-build-insights-samples)にアクセスして、SDK を使用する C++ アプリケーションの実例を参照することもできます。

## <a name="collecting-a-trace"></a>トレースの収集

C++ Build Insights SDK を使用して、MSVC ツールチェーンから発生するイベントを分析するには、最初にトレースを収集する必要があります。 この SDK では、基になるトレース テクノロジとして Event Tracing for Windows (ETW) が使用されます。 トレースを収集するには、次の 2 つの方法があります。

### <a name="method-1-using-vcperf-in-visual-studio-2019-and-above"></a>方法 1: Visual Studio 2019 以降の vcperf を使用する

1. VS 2019 用の x64 Native Tools コマンド プロンプトを管理者特権で開きます。
1. 次のコマンドを実行します。`vcperf /start MySessionName`
1. プロジェクトをビルドします。
1. 次のコマンドを実行します。`vcperf /stopnoanalyze MySessionName outputTraceFile.etl`

   > [!IMPORTANT]
   > vcperf を使用してトレースを停止する場合は、`/stopnoanalyze` コマンドを使用します。 通常の `/stop` コマンドによって停止されたトレースの分析に、C++ Build Insights SDK を使用することはできません。

### <a name="method-2-programmatically"></a>方法 2: プログラムを使用する

プログラムでトレースを開始および停止するには、C++ Build Insights SDK の次のトレース収集関数のいずれかを使用します。 **これらの関数呼び出しを実行するプログラムには、管理特権が必要です。** 管理特権を必要とするのは、トレースの開始および停止関数のみです。 C++ Build Insights SDK 内のその他のすべての関数は、管理特権がなくても実行できます。

### <a name="sdk-functions-related-to-trace-collection"></a>トレースの収集に関連する SDK 関数

| 機能 | C++ API | C API |
|--|--|--|
| トレースの開始 | [StartTracingSession](functions/start-tracing-session.md) | [StartTracingSessionA](functions/start-tracing-session-a.md)<br />[StartTracingSessionW](functions/start-tracing-session-w.md) |
| トレースの停止 | [StopTracingSession](functions/stop-tracing-session.md) | [StopTracingSessionA](functions/stop-tracing-session-a.md)<br />[StopTracingSessionW](functions/stop-tracing-session-w.md) |
| トレースを停止し、<br />即座に結果を分析する | [StopAndAnalyzeTracingSession](functions/stop-and-analyze-tracing-session.md) | [StopAndAnalyzeTracingSessionA](functions/stop-and-analyze-tracing-session-a.md)<br />[StopAndAnalyzeTracingSession](functions/stop-and-analyze-tracing-session-w.md) |
| トレースを停止し、<br />即座に結果を再ロギングする | [StopAndRelogTracingSession](functions/stop-and-relog-tracing-session.md) | [StopAndRelogTracingSessionA](functions/stop-and-relog-tracing-session-a.md)<br />[StopAndRelogTracingSessionW](functions/stop-and-relog-tracing-session-w.md) |

以降のセクションでは、分析または再ログ セッションを構成する方法について説明します。 これは、機能を結合した関数 ([StopAndAnalyzeTracingSession](functions/stop-and-analyze-tracing-session.md) など) に必要です。

## <a name="consuming-a-trace"></a>トレースの使用

ETW トレースを収集したら、C++ Build Insights SDK を使用してアンパックします。 SDK によって、ツールをすばやく開発できる形式でイベントが提供されます。 SDK を使用せずに未処理の ETW トレースを使用することはお勧めしません。 MSVC で使用されるイベント形式はドキュメント化されておらず、非常に大規模なビルドにスケーリングできるように最適化されており、理解するのは困難です。 さらに、C++ Build Insights SDK API は安定していますが、未処理の ETW トレースは予告なしに変更される可能性があります。

### <a name="sdk-types-and-functions-related-to-trace-consumption"></a>トレースの使用に関連する SDK の種類と関数

| 機能 | C++ API | C API | メモ |
|--|--|--|--|
| イベント コールバックの設定 | [IAnalyzer](other-types/ianalyzer-class.md)<br />[IRelogger](other-types/irelogger-class.md) | [ANALYSIS_CALLBACKS](other-types/analysis-callbacks-struct.md)<br />[RELOG_CALLBACKS](other-types/relog-callbacks-struct.md) | C++ Build Insights SDK によって、コールバック関数を介してイベントが提供されます。 C++ では、IAnalyzer または IRelogger を継承するアナライザーまたは再ロガー クラスを作成することによって、コールバック関数を実装します。 C では、コールバックをグローバル関数で実装し、それらを指すポインターを ANALYSIS_CALLBACKS または RELOG_CALLBACKS 構造体で提供します。 |
| グループの構築 | [MakeStaticAnalyzerGroup](functions/make-static-analyzer-group.md)<br />[MakeStaticReloggerGroup](functions/make-static-relogger-group.md)<br />[MakeDynamicAnalyzerGroup](functions/make-dynamic-analyzer-group.md)<br />[MakeDynamicReloggerGroup](functions/make-dynamic-relogger-group.md) |  | C++ API には、複数のアナライザーおよび再ロガー オブジェクトをグループ化するヘルパー関数と型が用意されています。 グループは、複雑な分析をより簡単な手順に分割するための便利な方法です。 [vcperf](https://github.com/microsoft/vcperf) は、この方法で整理されています。 |
| 分析または再ログ | [分析](functions/analyze.md)<br />[再ログ](functions/relog.md) | [AnalyzeA](functions/analyze-a.md)<br />[AnalyzeW](functions/analyze-w.md)<br />[RelogA](functions/relog-a.md)<br />[RelogW](functions/relog-w.md) |  |

### <a name="analyzing-and-relogging"></a>分析と再ログ

トレースの使用は、分析セッションまたは再ログ セッションのいずれかを介して行われます。

ほとんどのシナリオでは、通常の分析の使用が適しています。 この方法を使用すると、出力形式 (`printf` テキスト、xml、JSON、データベース、REST 呼び出しなど) を柔軟に選択できます。

再ログは、ETW 出力ファイルを生成する必要がある特定用途の分析に使用されます。 再ログを使用すると、C++ Build Insights イベントを独自の ETW イベント形式に変換できます。 再ログの使用が適切なのは、C ++ Build Insights データを既存の ETW ツールとインフラストラクチャにフックする場合です。 たとえば、[vcperf](https://github.com/microsoft/vcperf) では、再ログ インターフェイスが使用されます。 これは、ETW ツールである Windows Performance Analyzer で理解できるデータを生成する必要があるためです。 再ログ インターフェイスの使用を計画する場合は、ETW の動作方法について事前の知識が多少必要です。

### <a name="creating-analyzer-groups"></a>アナライザー グループの作成

グループの作成方法を理解することが重要です。 アクティビティ開始イベントを受け取るごとに *Hello, world!* を印刷するアナライザー グループの 作成方法を示す例を次に示します。

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

### <a name="sdk-types-and-functions-related-to-events"></a>イベントに関連する SDK の種類と関数

| 機能 | C++ API | C API | メモ |
|--|--|--|--|
| イベントの照合とフィルター処理 | [MatchEventStackInMemberFunction](functions/match-event-stack-in-member-function.md)<br />[MatchEventStack](functions/match-event-stack.md)<br />[MatchEventInMemberFunction](functions/match-event-in-member-function.md)<br />[MatchEvent](functions/match-event.md) |  | C++ API には、注意を要するイベントをトレースから簡単に抽出できる関数が用意されています。 C API では、このフィルター処理を手動で行う必要があります。 |
| イベント データ型 | [アクティビティ](cpp-event-data-types/activity.md)<br />[BackEndPass](cpp-event-data-types/back-end-pass.md)<br />[BottomUp](cpp-event-data-types/bottom-up.md)<br />[C1DLL](cpp-event-data-types/c1-dll.md)<br />[C2DLL](cpp-event-data-types/c2-dll.md)<br />[CodeGeneration](cpp-event-data-types/code-generation.md)<br />[CommandLine](cpp-event-data-types/command-line.md)<br />[Compiler](cpp-event-data-types/compiler.md)<br />[CompilerPass](cpp-event-data-types/compiler-pass.md)<br />[EnvironmentVariable](cpp-event-data-types/environment-variable.md)<br />[Event](cpp-event-data-types/event.md)<br />[EventGroup](cpp-event-data-types/event-group.md)<br />[EventStack](cpp-event-data-types/event-stack.md)<br />[ExecutableImageOutput](cpp-event-data-types/executable-image-output.md)<br />[ExpOutput](cpp-event-data-types/exp-output.md)<br />[FileInput](cpp-event-data-types/file-input.md)<br />[FileOutput](cpp-event-data-types/file-output.md)<br />[ForceInlinee](cpp-event-data-types/force-inlinee.md)<br />[FrontEndFile](cpp-event-data-types/front-end-file.md)<br />[FrontEndFileGroup](cpp-event-data-types/front-end-file-group.md)<br />[FrontEndPass](cpp-event-data-types/front-end-pass.md)<br />[関数](cpp-event-data-types/function.md)<br />[ImpLibOutput](cpp-event-data-types/imp-lib-output.md)<br />[[呼び出し]](cpp-event-data-types/invocation.md)<br />[InvocationGroup](cpp-event-data-types/invocation-group.md)<br />[LibOutput](cpp-event-data-types/lib-output.md)<br />[リンカー](cpp-event-data-types/linker.md)<br />[LinkerGroup](cpp-event-data-types/linker-group.md)<br />[LinkerPass](cpp-event-data-types/linker-pass.md)<br />[LTCG](cpp-event-data-types/ltcg.md)<br />[ObjOutput](cpp-event-data-types/obj-output.md)<br />[OptICF](cpp-event-data-types/opt-icf.md)<br />[OptLBR](cpp-event-data-types/opt-lbr.md)<br />[OptRef](cpp-event-data-types/opt-ref.md)<br />[Pass1](cpp-event-data-types/pass1.md)<br />[Pass2](cpp-event-data-types/pass2.md)<br />[PreLTCGOptRef](cpp-event-data-types/pre-ltcg-opt-ref.md)<br />[SimpleEvent](cpp-event-data-types/simple-event.md)<br />[SymbolName](cpp-event-data-types/symbol-name.md)<br />[TemplateInstantiation](cpp-event-data-types/template-instantiation.md)<br />[TemplateInstantiationGroup](cpp-event-data-types/template-instantiation-group.md)<br />[スレッド](cpp-event-data-types/thread.md)<br />[TopDown](cpp-event-data-types/top-down.md)<br />[TraceInfo](cpp-event-data-types/trace-info.md)<br />[WholeProgramAnalysis](cpp-event-data-types/whole-program-analysis.md) | [CL_PASS_DATA](c-event-data-types/cl-pass-data-struct.md)<br />[EVENT_COLLECTION_DATA](c-event-data-types/event-collection-data-struct.md)<br />[EVENT_DATA](c-event-data-types/event-data-struct.md)<br />[EVENT_ID](c-event-data-types/event-id-enum.md)<br />[FILE_DATA](c-event-data-types/file-data-struct.md)<br />[FILE_TYPE_CODE](c-event-data-types/file-type-code-enum.md)<br />[FRONT_END_FILE_DATA](c-event-data-types/front-end-file-data-struct.md)<br />[FUNCTION_DATA](c-event-data-types/function-data-struct.md)<br />[FUNCTION_FORCE_INLINEE_DATA](c-event-data-types/function-force-inlinee-data-struct.md)<br />[INVOCATION_DATA](c-event-data-types/invocation-data-struct.md)<br />[INVOCATION_VERSION_DATA](c-event-data-types/invocation-version-data-struct.md)<br />[MSVC_TOOL_CODE](c-event-data-types/msvc-tool-code-enum.md)<br />[NAME_VALUE_PAIR_DATA](c-event-data-types/name-value-pair-data-struct.md)<br />[SYMBOL_NAME_DATA](c-event-data-types/symbol-name-data-struct.md)<br />[TEMPLATE_INSTANTIATION_DATA](c-event-data-types/template-instantiation-data-struct.md)<br />[TEMPLATE_INSTANTIATION_KIND_CODE](c-event-data-types/template-instantiation-kind-code-enum.md)<br />[TRACE_INFO_DATA](c-event-data-types/trace-info-data-struct.md)<br />[TRANSLATION_UNIT_PASS_CODE](c-event-data-types/translation-unit-pass-code-enum.md) |  |

### <a name="activities-and-simple-events"></a>アクティビティと簡易イベント

発生するイベントには、"*アクティビティ*" と "*簡易イベント*" の 2 つのカテゴリがあります。 アクティビティは継続的なプロセスであり、時間に始まりと終わりがあります。 簡易イベントは時間どおりに発生し、継続時間はありません。 C++ Build Insights SDK を使用して MSVC トレースを分析する場合、アクティビティが開始したときと停止したときに個別のイベントを受け取ります。 簡易イベントの場合、発生時に 1 つのイベントのみを受け取ります。

### <a name="parent-child-relationships"></a>親子関係

アクティビティおよび簡易イベントは、親子関係を介して相互に関連付けられます。 アクティビティまたは簡易イベントの親は包括的なアクティビティであり、アクティビティまたは簡易イベントはその中で発生します。 たとえば、ソース ファイルをコンパイルする場合、コンパイラでは、ファイルを解析し、その後コードを生成する必要があります。 解析とコード生成のアクティビティは両方とも、コンパイラ アクティビティの子です。

簡易イベントに継続時間はないので、その中で他のイベントは発生しません。 したがって、それらに子はありません。

各アクティビティおよび簡易イベントの親子関係は、[イベント テーブル](event-table.md) に示されます。 C++ Build Insights イベントを使用する場合、これらの関係を把握することが重要です。 多くの場合、イベントの完全なコンテキストを理解するには、それらに依存する必要があります。

### <a name="properties"></a>Properties

すべてのイベントには次のプロパティがあります。

| プロパティ | [説明] |
|--|--|
| 種類識別子 | イベントの種類を一意に識別する数字。 |
| インスタンス識別子 | トレース内のイベントを一意に識別する数字。 トレース内で同じ種類の 2 つのイベントが発生した場合、両方とも一意のインスタンス識別子を取得します。 |
| 開始時刻 | アクティビティが開始した時刻、または簡易イベントが発生した時刻。 |
| プロセス識別子 | イベントが発生したプロセスを識別する数字。 |
| スレッド識別子 | イベントが発生したスレッドを識別する数字。 |
| プロセッサ インデックス | イベントを生成した論理プロセッサを示す、0 から始まるインデックス。 |
| イベント名 | イベントの種類を説明する文字列。 |

簡易イベント以外のすべてのアクティビティには、次のプロパティもあります。

| プロパティ | [説明] |
|--|--|
| 停止時刻 | アクティビティが停止した時刻。 |
| 排他継続時間 | アクティビティに費やされた時間。子アクティビティに費やされた時間は含まれません。 |
| CPU 時間 | アクティビティに接続されたスレッド内でコードの実行に費やされた CPU 時間。 アクティビティに接続されたスレッドがスリープ状態だった時間は含まれません。 |
| 排他 CPU 時間 | CPU 時間と同じです。ただし、子アクティビティによって費やされた CPU 時間は含まれません。 |
| ウォール クロック時間責任 | ウォール クロック時間全体に対するアクティビティの影響。 ウォール クロック時間責任では、アクティビティ間の並列処理が考慮されます。 たとえば、2 つの関連のないアクティビティが並行して実行されているとしましょう。 どちらの継続時間も 10 秒で、開始時刻と終了時刻はまったく同じです。 この場合、Build Insights では、両方に 5 秒のウォール クロック時間責任を割り当てます。 これに対して、これらのアクティビティが重複することなく順に実行される場合、両方に 10 秒のウォール クロック時間責任が割り当てられます。 |
| 排他的ウォール クロック時間責任 | ウォール クロック時間責任と同じですが、子アクティビティのウォール クロック時間責任は含まれません。 |

一部のイベントには、前述以外の独自のプロパティがあります。 この場合、これらの追加プロパティは、[イベント テーブル](event-table.md)に一覧表示されます。

### <a name="consuming-events-provided-by-the-c-build-insights-sdk"></a>C++ Build Insights SDK で提供されるイベントの使用

#### <a name="the-event-stack"></a>イベント スタック

C++ Build Insights SDK では、イベントを提供する場合、必ずスタックの形式で提供します。 スタック内の最後のエントリは現在のイベントであり、それより前のエントリは、その親階層です。 たとえば、[LTCG](event-table.md#ltcg) の開始および停止イベントは、リンカーのパス 1 で発生するとします。 この場合、受け取るスタックには、\[[LINKER](event-table.md#linker)、[PASS1](event-table.md#pass1)、LTCG\] が含まれます。 親階層は、イベントをそのルートまでトレースできるので便利です。 前述の LTCG アクティビティの速度が遅い場合、どのリンカー呼び出しが関係していたかをすぐに知ることができます。

#### <a name="matching-events-and-event-stacks"></a>イベントとイベント スタックの照合

C++ Build Insights SDK では、トレース内のすべてのイベントが提供されますが、ほとんどの場合、注意を要するのはそれらのサブセットのみです。 場合によっては、注意を要するのは、"*イベント スタック*" のサブセットのみであることもあります。 SDK では、必要なイベントまたはイベント スタックをすばやく抽出して、不要なイベントを拒否するのに役立つ機能が提供されます。 これは、次の照合関数を使用して実行されます。

| 機能 | [説明] |
|--|--|
| [MatchEvent](functions/match-event.md) | イベントが指定された種類のいずれかと一致する場合、それを保持します。 一致するイベントをラムダまたはその他の呼び出し可能な型に転送します。 この関数では、イベントの親階層は考慮されません。 |
| [MatchEventInMemberFunction](functions/match-event-in-member-function.md) | イベントがメンバー関数のパラメーターで指定された種類と一致する場合、それを保持します。 一致するイベントをメンバー関数に転送します。 この関数では、イベントの親階層は考慮されません。 |
| [MatchEventStack](functions/match-event-stack.md) | イベントとその親階層の両方が指定された種類と一致する場合、そのイベントを保持します。 イベントおよび一致する親階層イベントをラムダまたはその他の呼び出し可能な型に転送します。 |
| [MatchEventStackInMemberFunction](functions/match-event-stack-in-member-function.md) | イベントとその親階層の両方がメンバー関数のパラメーター リストで指定された種類と一致する場合、そのイベントを保持します。 イベントおよび一致する親階層イベントをメンバー関数に転送します。 |

`MatchEventStack` などのイベント スタック照合関数では、親階層を照合するときにギャップを許容します。 たとえば、\[[LINKER](event-table.md#linker)、[LTCG](event-table.md#ltcg)\]スタックに関心があるとします。 これは、\[LINKER, [PASS1](event-table.md#pass1), LTCG\] スタックとも一致します。 最後に指定する種類は、照合するイベントの種類である必要があり、親階層には含まれません。

#### <a name="capture-classes"></a>キャプチャ クラス

`Match*` 関数を使用するには、照合する種類を指定する必要があります。 これらの種類は、"*キャプチャ クラス*" の一覧から選択されます。 キャプチャ クラスには、次に示す複数のカテゴリがあります。

| カテゴリ | 説明 |
|--|--|
| [Exact] | これらのキャプチャ クラスは、特定のイベントの種類と照合するためにのみ使用されます。 1 つの例として、[Compiler](cpp-event-data-types/compiler.md) があります。これは、[COMPILER](event-table.md#compiler) イベントと一致します。 |
| ワイルドカード | これらのキャプチャ クラスは、サポートされるイベントの一覧にあるいずれかのイベントと照合するために使用できます。 たとえば、[Activity](cpp-event-data-types/activity.md) ワイルドカードは、任意のアクティビティ イベントと一致します。 もう 1 つの例は、[CompilerPass](cpp-event-data-types/compiler-pass.md) ワイルドカードです。これは、[FRONT_END_PASS](event-table.md#front-end-pass) または [BACK_END_PASS](event-table.md#back-end-pass) イベントのいずれかと一致します。 |
| Group | グループ キャプチャ クラスの名前は、*Group* で終わります。 これらは、ギャップを無視して、同じ種類の複数のイベントを連続して照合するために使用されます。 イベント スタック内に存在する個数がわからないため、再帰イベントを照合する場合にのみ意味があります。 たとえば、[FRONT_END_FILE](event-table.md#front-end-file) アクティビティは、コンパイラでファイルを解析するたびに発生します。 ファイルの解析中にコンパイラによってインクルード ディレクティブが検出される可能性があるため、このアクティビティは再帰的です。 [FrontEndFile](cpp-event-data-types/front-end-file.md) クラスは、スタック内の 1 つの FRONT_END_FILE イベントとのみ一致します。 インクルード階層全体を一致させるには、[FrontEndFileGroup](cpp-event-data-types/front-end-file-group.md) クラスを使用します。 |
| ワイルドカード グループ | ワイルドカード グループは、ワイルドカードとグループのプロパティを組み合わせたものです。 このカテゴリのクラスは、[InvocationGroup](cpp-event-data-types/invocation-group.md)のみです。これは、単一のイベント スタック内にあるすべての [LINKER](event-table.md#linker) および [COMPILER](event-table.md#compiler) イベントを照合し、キャプチャします。 |

各イベントの照合に使用できるキャプチャ クラスについては、「[イベント テーブル](event-table.md)」を参照してください。

#### <a name="after-matching-using-captured-events"></a>照合後: キャプチャされたイベントの使用

照合が正常に完了すると、`Match*` 関数によって、キャプチャ クラス オブジェクトが構築され、指定された関数に転送されます。 これらのキャプチャ クラス オブジェクトを使用して、イベントのプロパティにアクセスします。

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
