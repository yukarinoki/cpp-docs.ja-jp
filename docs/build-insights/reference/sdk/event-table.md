---
title: 'C++ Build Insights SDK: イベント テーブル'
description: Visual Studio C++ Build Insights SDK のイベント リファレンス
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Events
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6b1cf6871329fcce3166495e173360a88ac38ee0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224215"
---
# <a name="c-build-insights-sdk-event-table"></a>C++ Build Insights SDK: イベント テーブル

::: moniker range="<=vs-2015"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=vs-2017"

## <a name="compiler-events"></a>コンパイラ イベント

[COMPILER](#compiler)\
[COMMAND_LINE](#command-line)\
[ENVIRONMENT_VARIABLE](#environment-variable)\
[FILE_INPUT](#file-input)\
[OBJ_OUTPUT](#obj-output)\
[FRONT_END_PASS](#front-end-pass)\
[BACK_END_PASS](#back-end-pass)

## <a name="compiler-front-end-events"></a>コンパイラ フロントエンド イベント

[C1_DLL](#c1-dll)\
[FRONT_END_FILE](#front-end-file)\
[TEMPLATE_INSTANTIATION](#template-instantiation)\
[SYMBOL_NAME](#symbol-name)

## <a name="compiler-back-end-events"></a>コンパイラ バックエンド イベント

[C2_DLL](#c2-dll)\
[WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis)\
[TOP_DOWN](#top-down)\
[BOTTOM_UP](#bottom-up)\
[CODE_GENERATION](#code-generation)\
[THREAD](#thread)\
[FUNCTION](#function)\
[FORCE_INLINEE](#force-inlinee)

## <a name="linker-events"></a>リンカー イベント

[LINKER](#linker)\
[COMMAND_LINE](#command-line)\
[ENVIRONMENT_VARIABLE](#environment-variable)\
[FILE_INPUT](#file-input)\
[EXECUTABLE_IMAGE_OUTPUT](#executable-image-output)\
[EXP_OUTPUT](#exp-output)\
[IMP_LIB_OUTPUT](#imp-lib-output)\
[LIB_OUTPUT](#lib-output)\
[PASS1](#pass1)\
[PRE_LTCG_OPT_REF](#pre-ltcg-opt-ref)\
[LTCG](#ltcg)\
[OPT_REF](#opt-ref)\
[OPT_ICF](#opt-icf)\
[OPT_LBR](#opt-lbr)\
[PASS2](#pass2)

## <a name="event-table"></a>イベント テーブル

| event | プロパティ | 説明 |
|--|--|--|
| <a name="back-end-pass"></a> BACK_END_PASS | 種類 | アクティビティ |
|  | Parents | [COMPILER](#compiler) |
|  | Children | [C2_DLL](#c2-dll) |
|  | プロパティ | - 入力ソース ファイルへの絶対パス<br/>- 出力オブジェクト ファイルへの絶対パス |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[CompilerPass](cpp-event-data-types/compiler-pass.md)<br/>[BackEndPass](cpp-event-data-types/back-end-pass.md) |
|  | 説明 | コンパイラのバックエンド パスの開始時と停止時に発生します。 このパスでは、解析された C/C++ ソース コードの最適化と、マシン コードへの変換が行われます。 |
| <a name="bottom-up"></a> BOTTOM_UP | 種類 | アクティビティ |
|  | Parents | [WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Children | None |
|  | プロパティ | None |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[BottomUp](cpp-event-data-types/bottom-up.md) |
|  | 説明 | プログラム全体の分析のボトムアップ パスの開始時と停止時に発生します。 |
| <a name="c1-dll"></a> C1_DLL | 種類 | アクティビティ |
|  | Parents | [FRONT_END_PASS](#front-end-pass) |
|  | Children | [FRONT_END_FILE](#front-end-file)<br/>[SYMBOL_NAME](#symbol-name)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | プロパティ | None |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[C1DLL](cpp-event-data-types/c1-dll.md) |
|  | 説明 | *c1.dll* または *c1xx.dll* の呼び出しの開始時と停止時に発生します。 これらの DLL は、コンパイラの C および C++ フロントエンドです。 これらは、コンパイラ ドライバー (*cl.exe*) によってのみ呼び出されます。 |
| <a name="c2-dll"></a> C2_DLL | 種類 | アクティビティ |
|  | Parents | [BACK_END_PASS](#back-end-pass)<br/>[LTCG](#ltcg) |
|  | Children | [CODE_GENERATION](#code-generation)<br/>[WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | プロパティ | None |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[C2DLL](cpp-event-data-types/c2-dll.md) |
|  | 説明 | *c2.dll* の呼び出しの開始時と停止時に発生します。 この DLL は、コンパイラのバックエンドです。 コンパイラ ドライバー (*cl.exe*) によって呼び出されます。 また、リンク時のコード生成が使用されるときにも、リンカーによって (*link.exe*) 呼び出されます。 |
| <a name="code-generation"></a> CODE_GENERATION | 種類 | アクティビティ |
|  | Parents | [C2_DLL](#c2-dll) |
|  | Children | [FUNCTION](#function)<br/>[THREAD](#thread) |
|  | プロパティ | None |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[CodeGeneration](cpp-event-data-types/code-generation.md) |
|  | 説明 | バックエンドのコード生成フェーズの開始時と停止時に発生します。 |
| <a name="command-line"></a> COMMAND_LINE | 種類 | 簡易イベント |
|  | Parents | [COMPILER](#compiler)<br/>[LINKER](#linker) |
|  | Children | None |
|  | プロパティ | - *cl.exe* または *link.exe* を呼び出すために使用されたコマンド ライン |
|  | キャプチャ クラス | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[CommandLine](cpp-event-data-types/command-line.md) |
|  | 説明 | コンパイラとリンカーによるコマンド ラインの評価が完了すると発生します。 評価されるコマンド ラインには、応答ファイルを介して渡された *cl.exe* と *link.exe* のすべてのパラメーターが含まれます。 また、CL、\_CL\_、LINK、\_LINK\_ などの環境変数を介して渡された *cl.exe* および *link.exe* へのパラメーターも含まれます。 |
| <a name="compiler"></a> COMPILER | 種類 | アクティビティ |
|  | Parents | None |
|  | Children | [BACK_END_PASS](#back-end-pass)<br/>[COMMAND_LINE](#command-line)<br/>[ENVIRONMENT_VARIABLE](#environment-variable)<br/>[FILE_INPUT](#file-input)<br/>[OBJ_OUTPUT](#obj-output)<br/>[FRONT_END_PASS](#front-end-pass) |
|  | プロパティ | - コンパイラのバージョン<br/>- 作業ディレクトリ<br/>- 呼び出された *cl.exe* への絶対パス |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[[呼び出し]](cpp-event-data-types/invocation.md)<br/>[Compiler](cpp-event-data-types/compiler.md) |
|  | 説明 | *cl.exe* の呼び出しの開始時と停止時に発生します。 |
| <a name="environment-variable"></a> ENVIRONMENT_VARIABLE | 種類 | 簡易イベント |
|  | Parents | [COMPILER](#compiler)<br/>[LINKER](#linker) |
|  | Children | None |
|  | プロパティ | - 環境変数の名前<br/>- 環境変数の値。 |
|  | キャプチャ クラス | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[EnvironmentVariable](cpp-event-data-types/environment-variable.md) |
|  | 説明 | *cl.exe* または *link.exe* が呼び出されたときに、既存のすべての環境変数に対して 1 回発生します。 |
| <a name="executable-image-output"></a> EXECUTABLE_IMAGE_OUTPUT | 種類 | 簡易イベント |
|  | Parents | [LINKER](#linker) |
|  | Children | None |
|  | プロパティ | - DLL または実行可能な出力ファイルへの絶対パス。 |
|  | キャプチャ クラス | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileOutput](cpp-event-data-types/file-output.md)<br/>[ExecutableImageOutput](cpp-event-data-types/executable-image-output.md) |
|  | 説明 | リンカーの入力の 1 つが DLL または実行可能イメージ ファイルの場合に発生します。 |
| <a name="exp-output"></a> EXP_OUTPUT | 種類 | 簡易イベント |
|  | Parents | [LINKER](#linker) |
|  | Children | None |
|  | プロパティ | - *.exp* 出力ファイルへの絶対パス。 |
|  | キャプチャ クラス | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileOutput](cpp-event-data-types/file-output.md)<br/>[ExpOutput](cpp-event-data-types/exp-output.md) |
|  | 説明 | リンカーの出力の 1 つが *.exp* ファイルである場合に発生します。 |
| <a name="file-input"></a> FILE_INPUT | 種類 | 簡易イベント |
|  | Parents | [COMPILER](#compiler)<br/>[LINKER](#linker) |
|  | Children | None |
|  | プロパティ | - 入力ファイルへの絶対パス<br/>- 入力ファイルの種類 |
|  | キャプチャ クラス | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileInput](cpp-event-data-types/file-input.md) |
|  | 説明 | *cl.exe* または *link.exe* の入力を通知するために発生します。 |
| <a name="force-inlinee"></a> FORCE_INLINEE | 種類 | 簡易イベント |
|  | Parents | [FUNCTION](#function) |
|  | Children | None |
|  | プロパティ | - 強制インライン化関数の名前。<br/>- 中間命令数として表される、強制インライン化関数のサイズ。 |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[ForceInlinee](cpp-event-data-types/force-inlinee.md) |
|  | 説明 | **`__forceinline`** キーワードを使用することにより、関数が別の関数に強制インライン化されると発生します。 |
| <a name="front-end-file"></a> FRONT_END_FILE | 種類 | アクティビティ |
|  | Parents | [C1_DLL](#c1-dll)<br/>[FRONT_END_FILE](#front-end-file) |
|  | Children | [FRONT_END_FILE](#front-end-file)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | プロパティ | - ファイルへの絶対パス。 |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[FrontEndFile](cpp-event-data-types/front-end-file.md) |
|  | 説明 | コンパイラ フロントエンドによるファイルの処理が開始および停止したときに発生します。 このイベントは再帰的です。 再帰は、フロントエンドでインクルード ファイルが解析されると発生します。 |
| <a name="front-end-pass"></a> FRONT_END_PASS | 種類 | アクティビティ |
|  | Parents | [COMPILER](#compiler) |
|  | Children | [C1_DLL](#c1-dll) |
|  | プロパティ | - 入力ソース ファイルへの絶対パス<br/>- 出力オブジェクト ファイルへの絶対パス |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[CompilerPass](cpp-event-data-types/compiler-pass.md)<br/>[FrontEndPass](cpp-event-data-types/front-end-pass.md) |
|  | 説明 | コンパイラのフロントエンド パスの開始時と停止時に発生します。 このパスでは、C/C++ ソース コードの解析と、中間言語への変換が行われます。 |
| <a name="function"></a> FUNCTION | 種類 | アクティビティ |
|  | Parents | [CODE_GENERATION](#code-generation)<br/>[THREAD](#thread)<br/>[TOP_DOWN](#top-down) |
|  | Children | [FORCE_INLINEE](#force-inlinee) |
|  | プロパティ | - 関数の名前 |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[Function](cpp-event-data-types/function.md) |
|  | 説明 | 関数のコードの生成の開始時と停止時に発生します。 |
| <a name="imp-lib-output"></a> IMP_LIB_OUTPUT | 種類 | 簡易イベント |
|  | Parents | [LINKER](#linker) |
|  | Children | None |
|  | プロパティ | - インポート ライブラリの出力ファイルへの絶対パス。 |
|  | キャプチャ クラス | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileOutput](cpp-event-data-types/file-output.md)<br/>[ImpLibOutput](cpp-event-data-types/imp-lib-output.md) |
|  | 説明 | リンカーの出力の 1 つがインポート ライブラリである場合に発生します。 |
| <a name="lib-output"></a> LIB_OUTPUT | 種類 | 簡易イベント |
|  | Parents | [LINKER](#linker) |
|  | Children | None |
|  | プロパティ | - スタティック ライブラリ出力ファイルへの絶対パス。 |
|  | キャプチャ クラス | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileOutput](cpp-event-data-types/file-output.md)<br/>[LibOutput](cpp-event-data-types/lib-output.md) |
|  | 説明 | リンカーの出力の 1 つがスタティック ライブラリである場合に発生します。 |
| <a name="linker"></a> LINKER | 種類 | アクティビティ |
|  | Parents | None |
|  | Children | [COMMAND_LINE](#command-line)<br/>[ENVIRONMENT_VARIABLE](#environment-variable)<br/>[EXECUTABLE_IMAGE_OUTPUT](#executable-image-output)<br/>[EXP_OUTPUT](#exp-output)<br/>[FILE_INPUT](#file-input)<br/>[IMP_LIB_OUTPUT](#imp-lib-output)<br/>[LIB_OUTPUT](#lib-output)<br/>[PASS1](#pass1)<br/>[PASS2](#pass2) |
|  | プロパティ | - リンカーのバージョン<br/>- 作業ディレクトリ<br/>- 呼び出された *link.exe* への絶対パス |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[[呼び出し]](cpp-event-data-types/invocation.md)<br/>[リンカー](cpp-event-data-types/linker.md) |
|  | 説明 | *link.exe* の呼び出しの開始時と停止時に発生します。 |
| <a name="ltcg"></a> LTCG | 種類 | アクティビティ |
|  | Parents | [PASS1](#pass1) |
|  | Children | [C2_DLL](#c2-dll) |
|  | プロパティ | None |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[LTCG](cpp-event-data-types/ltcg.md) |
|  | 説明 | リンク時のコード生成の開始時と停止時に発生します。 |
| <a name="obj-output"></a> OBJ_OUTPUT | 種類 | 簡易イベント |
|  | Parents | [COMPILER](#compiler) |
|  | Children | None |
|  | プロパティ | - *.obj* 出力ファイルへの絶対パス |
|  | キャプチャ クラス | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileOutput](cpp-event-data-types/file-output.md)<br/>[ObjOutput](cpp-event-data-types/obj-output.md) |
|  | 説明 | *cl.exe* によって生成されるすべての *.obj* 出力に対して 1 回発生します。 |
| <a name="opt-icf"></a> OPT_ICF | 種類 | アクティビティ |
|  | Parents | [PASS1](#pass1) |
|  | Children | None |
|  | プロパティ | None |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[OptICF](cpp-event-data-types/opt-icf.md) |
|  | 説明 | 同じ COMDAT フォールド (/OPT:ICF) のリンカー最適化の開始時と停止時に発生します。 |
| <a name="opt-lbr"></a> OPT_LBR | 種類 | アクティビティ |
|  | Parents | [PASS1](#pass1) |
|  | Children | None |
|  | プロパティ | None |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[OptLBR](cpp-event-data-types/opt-lbr.md) |
|  | 説明 | 長い分岐 (/OPT:LBR) のリンカー最適化の開始時と停止時に発生します。 |
| <a name="opt-ref"></a> OPT_REF | 種類 | アクティビティ |
|  | Parents | [PASS1](#pass1) |
|  | Children | None |
|  | プロパティ | None |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[OptRef](cpp-event-data-types/opt-ref.md) |
|  | 説明 | 参照されていない関数とデータの削除 (/OPT:REF) のリンカー最適化の開始時と停止時に発生します。 |
| <a name="pass1"></a> PASS1 | 種類 | アクティビティ |
|  | Parents | [LINKER](#linker) |
|  | Children | [LTCG](#ltcg)<br/>[OPT_ICF](#opt-icf)<br/>[OPT_LBR](#opt-lbr)<br/>[OPT_REF](#opt-ref) |
|  | プロパティ | None |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[Pass1](cpp-event-data-types/pass1.md) |
|  | 説明 | リンカーのパス 1 の開始時と停止時に発生します。 |
| <a name="pass2"></a> PASS2 | 種類 | アクティビティ |
|  | Parents | [LINKER](#linker) |
|  | Children | None |
|  | プロパティ | None |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[Pass2](cpp-event-data-types/pass2.md) |
|  | 説明 | リンカーのパス 2 の開始時と停止時に発生します。 |
| <a name="pre-ltcg-opt-ref"></a> PRE_LTCG_OPT_REF | 種類 | アクティビティ |
|  | Parents | [PASS1](#pass1) |
|  | Children | None |
|  | プロパティ | None |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[PreLTCGOptRef](cpp-event-data-types/pre-ltcg-opt-ref.md) |
|  | 説明 | 参照されていない関数とデータを除去する (/OPT:REF) リンカー最適化パスの開始時と停止時に発生します。 リンク時コード生成の前に行われます。 |
| <a name="symbol-name"></a> SYMBOL_NAME | 種類 | 簡易イベント |
|  | Parents | [C1_DLL](#c1-dll) |
|  | Children | None |
|  | プロパティ | - 型のキー<br/> - 型の名前 |
|  | キャプチャ クラス | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[SymbolName](cpp-event-data-types/symbol-name.md) |
|  | 説明 | フロントエンド パスの最後で、テンプレートのインスタンス化に含まれるすべての型に対して 1 回発生します。 キーは型の数値識別子であり、名前はテキスト表現です。 型のキーは、分析対象のトレース内で一意です。 ただし、異なるコンパイラ フロントエンド パスから受け取る異なるキーで、同じ型が示されている場合があります。 異なるコンパイラ フロントエンド パスの間で型を比較するには、その名前を使用する必要があります。 SYMBOL_NAME イベントは、すべてのテンプレートのインスタンス化が行われた後で、コンパイラ フロントエンド パスの最後に生成されます。 |
| <a name="template-instantiation"></a> TEMPLATE_INSTANTIATION | 種類 | アクティビティ |
|  | Parents | [C1_DLL](#c1-dll)<br/>[FRONT_END_FILE](#front-end-file)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Children | [TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | プロパティ | - 特殊な型のキー<br/>- プライマリ テンプレートの型のキー<br/>- インスタンス化されたテンプレートの種類 |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[TemplateInstantiation](cpp-event-data-types/template-instantiation.md) |
|  | 説明 | テンプレートのインスタンス化の開始時と終了時に発生します。 プライマリ テンプレート型 (`vector` など) がインスタンス化され、結果として特殊な型 (`std::vector<int>` など) になります。 キーは両方の型に対して与えられます。 キーを型の名前に変換するには、[SYMBOL_NAME](#symbol-name) イベントを使用します。 型のキーは、分析対象のトレース内で一意です。 ただし、異なるコンパイラ フロントエンド パスから受け取る異なるキーで、同じ型が示されている場合があります。 異なるコンパイラ フロントエンド パスの間で型を比較するには、シンボルの名前を使用する必要があります。 このイベントは再帰的です。 再帰は、フロントエンドによって入れ子になったテンプレートがインスタンス化されると発生する場合があります。 |
| <a name="thread"></a> THREAD | 種類 | アクティビティ |
|  | Parents | [CODE_GENERATION](#code-generation)<br/>[TOP_DOWN](#top-down) |
|  | Children | [FUNCTION](#function) |
|  | プロパティ | None |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[スレッド](cpp-event-data-types/thread.md) |
|  | 説明 | コンパイラ バックエンドのスレッド実行の開始時と終了時に発生します。 中断されたスレッドは、終了されたものと見なされます。 再開されたスレッドは、開始されたものと見なされます。 |
| <a name="top-down"></a> TOP_DOWN | 種類 | アクティビティ |
|  | Parents | [WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Children | [FUNCTION](#function)<br/>[THREAD](#thread) |
|  | プロパティ | None |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[TopDown](cpp-event-data-types/top-down.md) |
|  | 説明 | プログラムの分析のトップダウン パス全体の開始時と停止時に発生します。 |
| <a name="whole-program-analysis"></a> WHOLE_PROGRAM_ANALYSIS | 種類 | アクティビティ |
|  | Parents | [C2_DLL](#c2-dll) |
|  | Children | [BOTTOM_UP](#bottom-up)<br/>[TOP_DOWN](#top-down) |
|  | プロパティ | None |
|  | キャプチャ クラス | [アクティビティ](cpp-event-data-types/activity.md)<br/>[WholeProgramAnalysis](cpp-event-data-types/whole-program-analysis.md) |
|  | 説明 | リンク時コード生成のプログラム全体の分析フェーズの開始時と停止時に発生します。 |

::: moniker-end
