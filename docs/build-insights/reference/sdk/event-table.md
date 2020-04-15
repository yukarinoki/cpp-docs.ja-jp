---
title: 'C++ ビルド インサイト SDK: イベント テーブル'
description: ビジュアル スタジオ C++ ビルド インサイト SDK のイベント リファレンス
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Events
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 932b78347e05d313e7962da2fdff8c3454dec963
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324142"
---
# <a name="c-build-insights-sdk-event-table"></a>C++ ビルド インサイト SDK: イベント テーブル

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

## <a name="compiler-events"></a>コンパイラ イベント

[コンパイラ](#compiler)\
[COMMAND_LINE](#command-line)\
[ENVIRONMENT_VARIABLE](#environment-variable)\
[FILE_INPUT](#file-input)\
[OBJ_OUTPUT](#obj-output)\
[FRONT_END_PASS](#front-end-pass)\
[BACK_END_PASS](#back-end-pass)

## <a name="compiler-front-end-events"></a>コンパイラフロントエンドイベント

[C1_DLL](#c1-dll)\
[FRONT_END_FILE](#front-end-file)\
[TEMPLATE_INSTANTIATION](#template-instantiation)\
[SYMBOL_NAME](#symbol-name)

## <a name="compiler-back-end-events"></a>コンパイラのバックエンド イベント

[C2_DLL](#c2-dll)\
[WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis)\
[TOP_DOWN](#top-down)\
[BOTTOM_UP](#bottom-up)\
[CODE_GENERATION](#code-generation)\
[スレッド](#thread)\
[関数](#function)\
[FORCE_INLINEE](#force-inlinee)

## <a name="linker-events"></a>リンカー イベント

[リンカー](#linker)\
[COMMAND_LINE](#command-line)\
[ENVIRONMENT_VARIABLE](#environment-variable)\
[FILE_INPUT](#file-input)\
[EXECUTABLE_IMAGE_OUTPUT](#executable-image-output)\
[EXP_OUTPUT](#exp-output)\
[IMP_LIB_OUTPUT](#imp-lib-output)\
[LIB_OUTPUT](#lib-output)\
[パス1](#pass1)\
[PRE_LTCG_OPT_REF](#pre-ltcg-opt-ref)\
[Ltcg](#ltcg)\
[OPT_REF](#opt-ref)\
[OPT_ICF](#opt-icf)\
[OPT_LBR](#opt-lbr)\
[パス2](#pass2)

## <a name="event-table"></a>イベントテーブル

| Event | プロパティ | 説明 |
|--|--|--|
| <a name="back-end-pass"></a>BACK_END_PASS | Type | アクティビティ |
|  | Parents | [コンパイラ](#compiler) |
|  | Children | [C2_DLL](#c2-dll) |
|  | プロパティ | - 入力ソースファイルへの絶対パス<br/>- 出力オブジェクトファイルへの絶対パス |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[コンパイラパス](cpp-event-data-types/compiler-pass.md)<br/>[バックエンドパス](cpp-event-data-types/back-end-pass.md) |
|  | 説明 | コンパイラのバックエンド パスの開始と終了に発生します。 このパスは、解析された C/C++ ソース コードを最適化し、それをマシン コードに変換します。 |
| <a name="bottom-up"></a>BOTTOM_UP | Type | アクティビティ |
|  | Parents | [WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Children | なし |
|  | プロパティ | なし |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[ボトムアップ](cpp-event-data-types/bottom-up.md) |
|  | 説明 | プログラム分析全体のボトムアップ パスの開始と停止で発生します。 |
| <a name="c1-dll"></a>C1_DLL | Type | アクティビティ |
|  | Parents | [FRONT_END_PASS](#front-end-pass) |
|  | Children | [FRONT_END_FILE](#front-end-file)<br/>[SYMBOL_NAME](#symbol-name)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | プロパティ | なし |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[C1DLL](cpp-event-data-types/c1-dll.md) |
|  | 説明 | *c1.dll または c1xx.dll*の*c1xx.dll*呼び出しの開始と停止で発生します。 これらの DLL は、コンパイラの C および C++ フロント エンドです。 コンパイラ ドライバ (*cl.exe*) だけが呼び出されます。 |
| <a name="c2-dll"></a>C2_DLL | Type | アクティビティ |
|  | Parents | [BACK_END_PASS](#back-end-pass)<br/>[Ltcg](#ltcg) |
|  | Children | [CODE_GENERATION](#code-generation)<br/>[WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | プロパティ | なし |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[C2DLL](cpp-event-data-types/c2-dll.md) |
|  | 説明 | *c2.dll*呼び出しの開始と停止時に発生します。 この DLL は、コンパイラのバックエンドです。 これはコンパイラ ドライバ (*cl.exe*) によって呼び出されます。 リンク時のコード生成を使用する場合は、リンカー (*link.exe*) によっても呼び出されます。 |
| <a name="code-generation"></a>CODE_GENERATION | Type | アクティビティ |
|  | Parents | [C2_DLL](#c2-dll) |
|  | Children | [関数](#function)<br/>[スレッド](#thread) |
|  | プロパティ | なし |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[コードジェネレーション](cpp-event-data-types/code-generation.md) |
|  | 説明 | バックエンドのコード生成フェーズの開始と終了に発生します。 |
| <a name="command-line"></a>COMMAND_LINE | Type | 簡易イベント |
|  | Parents | [コンパイラ](#compiler)<br/>[リンカー](#linker) |
|  | Children | なし |
|  | プロパティ | - *cl.exe*または*link.exe*を呼び出すために使用されたコマンド ライン |
|  | クラスのキャプチャ | [シンプルイベント](cpp-event-data-types/simple-event.md)<br/>[コマンドライン](cpp-event-data-types/command-line.md) |
|  | 説明 | コンパイラとリンカーがコマンド ラインの評価を完了したときに発生します。 評価されたコマンド ラインには、応答ファイルを介して渡されるすべての*cl.exe*パラメータと*link.exe*パラメータが含まれます。 また、CL、CL、LINK、LINK\_\_などの\_環境変数を使用して渡される\_ *cl.exe*および*link.exe*へのパラメータも含まれています。 |
| <a name="compiler"></a>コンパイラ | Type | アクティビティ |
|  | Parents | なし |
|  | Children | [BACK_END_PASS](#back-end-pass)<br/>[COMMAND_LINE](#command-line)<br/>[ENVIRONMENT_VARIABLE](#environment-variable)<br/>[FILE_INPUT](#file-input)<br/>[OBJ_OUTPUT](#obj-output)<br/>[FRONT_END_PASS](#front-end-pass) |
|  | プロパティ | - コンパイラバージョン<br/>- 作業ディレクトリ<br/>- 呼び出された*cl.exe*への絶対パス |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[[呼び出し]](cpp-event-data-types/invocation.md)<br/>[コンパイラ](cpp-event-data-types/compiler.md) |
|  | 説明 | *cl.exe*呼び出しの開始と停止時に発生します。 |
| <a name="environment-variable"></a>ENVIRONMENT_VARIABLE | Type | 簡易イベント |
|  | Parents | [コンパイラ](#compiler)<br/>[リンカー](#linker) |
|  | Children | なし |
|  | プロパティ | - 環境変数の名前<br/>- 環境変数の値。 |
|  | クラスのキャプチャ | [シンプルイベント](cpp-event-data-types/simple-event.md)<br/>[EnvironmentVariable](cpp-event-data-types/environment-variable.md) |
|  | 説明 | *cl.exe または link.exe*が呼び出された*link.exe*時点で、既存の環境変数ごとに 1 回発生します。 |
| <a name="executable-image-output"></a>EXECUTABLE_IMAGE_OUTPUT | Type | 簡易イベント |
|  | Parents | [リンカー](#linker) |
|  | Children | なし |
|  | プロパティ | - DLL または実行可能な出力ファイルへの絶対パス。 |
|  | クラスのキャプチャ | [シンプルイベント](cpp-event-data-types/simple-event.md)<br/>[ファイル出力](cpp-event-data-types/file-output.md)<br/>[イメージ出力](cpp-event-data-types/executable-image-output.md) |
|  | 説明 | リンカー入力の 1 つが DLL または実行可能イメージ ファイルである場合に発生します。 |
| <a name="exp-output"></a>EXP_OUTPUT | Type | 簡易イベント |
|  | Parents | [リンカー](#linker) |
|  | Children | なし |
|  | プロパティ | - *.exp*出力ファイルへの絶対パス。 |
|  | クラスのキャプチャ | [シンプルイベント](cpp-event-data-types/simple-event.md)<br/>[ファイル出力](cpp-event-data-types/file-output.md)<br/>[出力](cpp-event-data-types/exp-output.md) |
|  | 説明 | リンカー出力の 1 つが *.exp*ファイルである場合に発生します。 |
| <a name="file-input"></a>FILE_INPUT | Type | 簡易イベント |
|  | Parents | [コンパイラ](#compiler)<br/>[リンカー](#linker) |
|  | Children | なし |
|  | プロパティ | - 入力ファイルへの絶対パス<br/>- 入力ファイルのタイプ |
|  | クラスのキャプチャ | [シンプルイベント](cpp-event-data-types/simple-event.md)<br/>[ファイル入力](cpp-event-data-types/file-input.md) |
|  | 説明 | *cl.exe*または*link.exe*の入力をアナウンスするために発生します。 |
| <a name="force-inlinee"></a>FORCE_INLINEE | Type | 簡易イベント |
|  | Parents | [関数](#function) |
|  | Children | なし |
|  | プロパティ | - 強制インライン化関数の名前。<br/>- 強制インライン化関数のサイズで、中間命令数として表されます。 |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[フォースインリネ](cpp-event-data-types/force-inlinee.md) |
|  | 説明 | キーワードを使用して関数が別の関数に強制的にインライン展開されている場合に発生します`__forceinline`。 |
| <a name="front-end-file"></a>FRONT_END_FILE | Type | アクティビティ |
|  | Parents | [C1_DLL](#c1-dll)<br/>[FRONT_END_FILE](#front-end-file) |
|  | Children | [FRONT_END_FILE](#front-end-file)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | プロパティ | - ファイルへの絶対パス。 |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[フロントエンドファイル](cpp-event-data-types/front-end-file.md) |
|  | 説明 | コンパイラのフロント エンドがファイルの処理を開始し、停止したときに発生します。 このイベントは再帰的です。 再帰は、フロントエンドがインクルードされたファイルを解析しているときに発生します。 |
| <a name="front-end-pass"></a>FRONT_END_PASS | Type | アクティビティ |
|  | Parents | [コンパイラ](#compiler) |
|  | Children | [C1_DLL](#c1-dll) |
|  | プロパティ | - 入力ソースファイルへの絶対パス<br/>- 出力オブジェクトファイルへの絶対パス |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[コンパイラパス](cpp-event-data-types/compiler-pass.md)<br/>[フロントエンドパス](cpp-event-data-types/front-end-pass.md) |
|  | 説明 | コンパイラのフロントエンド パスの開始と終了に発生します。 このパスは、C/C++ ソース コードを解析し、中間言語に変換します。 |
| <a name="function"></a>関数 | Type | アクティビティ |
|  | Parents | [CODE_GENERATION](#code-generation)<br/>[スレッド](#thread)<br/>[TOP_DOWN](#top-down) |
|  | Children | [FORCE_INLINEE](#force-inlinee) |
|  | プロパティ | - 関数の名前 |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[関数](cpp-event-data-types/function.md) |
|  | 説明 | 関数のコードの生成を開始および終了するときに発生します。 |
| <a name="imp-lib-output"></a>IMP_LIB_OUTPUT | Type | 簡易イベント |
|  | Parents | [リンカー](#linker) |
|  | Children | なし |
|  | プロパティ | - インポート ライブラリ出力ファイルへの絶対パス。 |
|  | クラスのキャプチャ | [シンプルイベント](cpp-event-data-types/simple-event.md)<br/>[ファイル出力](cpp-event-data-types/file-output.md)<br/>[インプリブ出力](cpp-event-data-types/imp-lib-output.md) |
|  | 説明 | リンカーの出力の 1 つがインポート ライブラリである場合に発生します。 |
| <a name="lib-output"></a>LIB_OUTPUT | Type | 簡易イベント |
|  | Parents | [リンカー](#linker) |
|  | Children | なし |
|  | プロパティ | - スタティック ライブラリ出力ファイルへの絶対パス。 |
|  | クラスのキャプチャ | [シンプルイベント](cpp-event-data-types/simple-event.md)<br/>[ファイル出力](cpp-event-data-types/file-output.md)<br/>[リブアウトプット](cpp-event-data-types/lib-output.md) |
|  | 説明 | リンカーの出力の 1 つが静的ライブラリである場合に発生します。 |
| <a name="linker"></a>リンカー | Type | アクティビティ |
|  | Parents | なし |
|  | Children | [COMMAND_LINE](#command-line)<br/>[ENVIRONMENT_VARIABLE](#environment-variable)<br/>[EXECUTABLE_IMAGE_OUTPUT](#executable-image-output)<br/>[EXP_OUTPUT](#exp-output)<br/>[FILE_INPUT](#file-input)<br/>[IMP_LIB_OUTPUT](#imp-lib-output)<br/>[LIB_OUTPUT](#lib-output)<br/>[パス1](#pass1)<br/>[パス2](#pass2) |
|  | プロパティ | - リンカーバージョン<br/>- 作業ディレクトリ<br/>- 呼び出された*リンク.exe*への絶対パス |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[[呼び出し]](cpp-event-data-types/invocation.md)<br/>[リンカー](cpp-event-data-types/linker.md) |
|  | 説明 | *link.exe*の呼び出しの開始と停止時に発生します。 |
| <a name="ltcg"></a>Ltcg | Type | アクティビティ |
|  | Parents | [パス1](#pass1) |
|  | Children | [C2_DLL](#c2-dll) |
|  | プロパティ | なし |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[Ltcg](cpp-event-data-types/ltcg.md) |
|  | 説明 | リンク時のコード生成の開始と終了で発生します。 |
| <a name="obj-output"></a>OBJ_OUTPUT | Type | 簡易イベント |
|  | Parents | [コンパイラ](#compiler) |
|  | Children | なし |
|  | プロパティ | - *.obj*出力ファイルへの絶対パス |
|  | クラスのキャプチャ | [シンプルイベント](cpp-event-data-types/simple-event.md)<br/>[ファイル出力](cpp-event-data-types/file-output.md)<br/>[出力](cpp-event-data-types/obj-output.md) |
|  | 説明 | *cl.exe*によって生成される *.obj*出力ごとに 1 回発生します。 |
| <a name="opt-icf"></a>OPT_ICF | Type | アクティビティ |
|  | Parents | [パス1](#pass1) |
|  | Children | なし |
|  | プロパティ | なし |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[オプティフ](cpp-event-data-types/opt-icf.md) |
|  | 説明 | 同一の COMDAT 折りたたみ (/OPT:ICF) リンカー最適化の開始と停止で発生します。 |
| <a name="opt-lbr"></a>OPT_LBR | Type | アクティビティ |
|  | Parents | [パス1](#pass1) |
|  | Children | なし |
|  | プロパティ | なし |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[オプトLBR](cpp-event-data-types/opt-lbr.md) |
|  | 説明 | 長い分岐 (/OPT:LBR) リンカー最適化の開始と停止で発生します。 |
| <a name="opt-ref"></a>OPT_REF | Type | アクティビティ |
|  | Parents | [パス1](#pass1) |
|  | Children | なし |
|  | プロパティ | なし |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[オプトレフ](cpp-event-data-types/opt-ref.md) |
|  | 説明 | 参照されていない関数とデータ消去 (/OPT:REF) リンカーの最適化の開始と停止で発生します。 |
| <a name="pass1"></a>パス1 | Type | アクティビティ |
|  | Parents | [リンカー](#linker) |
|  | Children | [Ltcg](#ltcg)<br/>[OPT_ICF](#opt-icf)<br/>[OPT_LBR](#opt-lbr)<br/>[OPT_REF](#opt-ref) |
|  | プロパティ | なし |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[パス1](cpp-event-data-types/pass1.md) |
|  | 説明 | リンカーのパス 1 の開始と停止で発生します。 |
| <a name="pass2"></a>パス2 | Type | アクティビティ |
|  | Parents | [リンカー](#linker) |
|  | Children | なし |
|  | プロパティ | なし |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[パス2](cpp-event-data-types/pass2.md) |
|  | 説明 | リンカーのパス 2 の開始と停止で発生します。 |
| <a name="pre-ltcg-opt-ref"></a>PRE_LTCG_OPT_REF | Type | アクティビティ |
|  | Parents | [パス1](#pass1) |
|  | Children | なし |
|  | プロパティ | なし |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[プレエルトCGオプトレフ](cpp-event-data-types/pre-ltcg-opt-ref.md) |
|  | 説明 | 参照されていない関数とデータ (/OPT:REF) を除去するリンカー最適化パスの開始と停止時に発生します。 これは、リンク時のコード生成前に行われます。 |
| <a name="symbol-name"></a>SYMBOL_NAME | Type | 簡易イベント |
|  | Parents | [C1_DLL](#c1-dll) |
|  | Children | なし |
|  | プロパティ | - タイプキー<br/> - タイプの名前 |
|  | クラスのキャプチャ | [シンプルイベント](cpp-event-data-types/simple-event.md)<br/>[シンボル名](cpp-event-data-types/symbol-name.md) |
|  | 説明 | テンプレートのインスタンス化に関係するすべての型に対して、フロントエンド パスの最後に 1 回発生します。 キーは型の数値識別子で、名前はそのテキスト表現です。 タイプ キーは、分析対象のトレース内で一意です。 ただし、異なるコンパイラのフロントエンド パスから渡される異なるキーは、同じ型を指している可能性があります。 異なるコンパイラ フロントエンド パス間で型を比較するには、その名前を使用する必要があります。 SYMBOL_NAMEイベントは、すべてのテンプレートのインスタンス化が行われた後、コンパイラのフロントエンド パスの最後に出力されます。 |
| <a name="template-instantiation"></a>TEMPLATE_INSTANTIATION | Type | アクティビティ |
|  | Parents | [C1_DLL](#c1-dll)<br/>[FRONT_END_FILE](#front-end-file)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Children | [TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | プロパティ | - 特殊な型のキー<br/>- プライマリ テンプレートの種類のキー<br/>- インスタンス化されたテンプレートの種類 |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[テンプレートのインスタンス化](cpp-event-data-types/template-instantiation.md) |
|  | 説明 | テンプレートのインスタンス化の先頭と末尾で発生します。 プライマリ テンプレートの型 (`vector`など) がインスタンス化され、特殊な型 (`std::vector<int>`など) が生成されます。 両方のタイプに対してキーが与えられます。 キーを型の名前に変換するには[、SYMBOL_NAME](#symbol-name)イベントを使用します。 タイプ キーは、分析対象のトレース内で一意です。 ただし、異なるコンパイラのフロントエンド パスから渡される異なるキーは、同じ型を指している可能性があります。 異なるコンパイラ フロントエンド パス間で型を比較するには、シンボル名を使用する必要があります。 このイベントは再帰的です。 再帰は、フロントエンドが入れ子になったテンプレートをインスタンス化している場合に発生します。 |
| <a name="thread"></a>スレッド | Type | アクティビティ |
|  | Parents | [CODE_GENERATION](#code-generation)<br/>[TOP_DOWN](#top-down) |
|  | Children | [関数](#function) |
|  | プロパティ | なし |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[スレッド](cpp-event-data-types/thread.md) |
|  | 説明 | コンパイラのバックエンド スレッドの実行の開始と終了で発生します。 中断中のスレッドは終了と見なされます。 起こされているスレッドは開始済みと見なされます。 |
| <a name="top-down"></a>TOP_DOWN | Type | アクティビティ |
|  | Parents | [WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Children | [関数](#function)<br/>[スレッド](#thread) |
|  | プロパティ | なし |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[トップダウン](cpp-event-data-types/top-down.md) |
|  | 説明 | プログラム分析全体のトップダウン パスの開始と停止で発生します。 |
| <a name="whole-program-analysis"></a>WHOLE_PROGRAM_ANALYSIS | Type | アクティビティ |
|  | Parents | [C2_DLL](#c2-dll) |
|  | Children | [BOTTOM_UP](#bottom-up)<br/>[TOP_DOWN](#top-down) |
|  | プロパティ | なし |
|  | クラスのキャプチャ | [アクティビティ](cpp-event-data-types/activity.md)<br/>[プログラム分析全体](cpp-event-data-types/whole-program-analysis.md) |
|  | 説明 | リンク時コード生成のプログラム全体分析フェーズの開始と停止時に発生します。 |

::: moniker-end
