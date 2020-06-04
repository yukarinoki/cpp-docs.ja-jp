---
title: 列挙型RESULT_CODE
description: C++ ビルド インサイト SDK RESULT_CODE列挙参照。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RESULT_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 62874e176c3f3e8f9df1ca64e7b593b7a0ef5c01
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323620"
---
# <a name="result_code-enum"></a>列挙型RESULT_CODE

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

列挙`RESULT_CODE`型は、成功条件と失敗条件を記述します。

## <a name="members"></a>メンバー

| 名前 | [値] | 説明 |
|--|--|--|
| `RESULT_CODE_SUCCESS` | 0 (0x0000000) | 操作に成功しました。 |
| `RESULT_CODE_FAILURE_ANALYSIS_ERROR` | 1 (0x00000001) | コールバック関数の 1 つは[、ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md)または[RELOG_DESCRIPTOR](relog-descriptor-struct.md)で値を`CALLBACK_CODE_ANALYSIS_FAILURE`返します。 この値は[、CALLBACK_CODE](callback-code-enum.md)列挙型のメンバーです。 |
| `RESULT_CODE_FAILURE_CANCELLED` | 2 (0x0000002) | コールバック関数の 1 つは[、ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md)または[RELOG_DESCRIPTOR](relog-descriptor-struct.md)で値を`CALLBACK_CODE_ANALYSIS_CANCEL`返します。 この値は[、CALLBACK_CODE](callback-code-enum.md)列挙型のメンバーです。 |
| `RESULT_CODE_FAILURE_INVALID_INPUT_LOG_FILE` | 3 (0x0000003) | 指定された Windows イベント トレース (ETW) トレースの入力が無効です。 |
| `RESULT_CODE_FAILURE_INVALID_OUTPUT_LOG_FILE` | 4 (0x0000004) | 指定された出力 ETW トレースが無効です。 |
| `RESULT_CODE_FAILURE_MISSING_ANALYSIS_CALLBACK` | 5 (0x0000005) | [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md)構造体が正しく初期化されませんでした。 |
| `RESULT_CODE_FAILURE_MISSING_RELOG_CALLBACK` | 6 (0x0000006) | [RELOG_CALLBACKS](relog-callbacks-struct.md)構造体が正しく初期化されませんでした。 |
| `RESULT_CODE_FAILURE_OPEN_INPUT_TRACE` | 7 (0x0000007) | 入力 ETW トレースを開けませんでした。 |
| `RESULT_CODE_FAILURE_PROCESS_TRACE` | 8 (0x0000008) | 入力 ETW トレースの処理中にエラーが発生しました。 |
| `RESULT_CODE_FAILURE_START_RELOGGER` | 9 (0x0000009) | 再ロギング セッションを開始しようとしたときにエラーが発生しました。 |
| `RESULT_CODE_FAILURE_DROPPED_EVENTS` | 10 (0x000000A) | 入力 ETW トレースに重要なイベントがありません。 |
| `RESULT_CODE_FAILURE_UNSUPPORTED_OS` | 11 (0x000000B) | サポートされていないバージョンの Windows で C++ ビルド インサイトを使用しています。 |
| `RESULT_CODE_FAILURE_INVALID_TRACING_SESSION_NAME` | 12 (0x000000C) | 指定されたセッション名が無効です。 |
| `RESULT_CODE_FAILURE_INSUFFICIENT_PRIVILEGES` | 13 (0x000000D) | この操作には管理者権限が必要です。 |
| `RESULT_CODE_FAILURE_GENERATE_GUID` | 14 (0x000000E) | GUID の生成中にエラーが発生しました。 |
| `RESULT_CODE_FAILURE_OBTAINING_TEMP_DIRECTORY` | 15 (0x000000F) | 一時ディレクトリ パスを確認中にエラーが発生しました。 |
| `RESULT_CODE_FAILURE_CREATE_TEMPORARY_DIRECTORY` | 16 (0x0000010) | 開始中のトレース セッション用の一時ディレクトリを作成中にエラーが発生しました。 |
| `RESULT_CODE_FAILURE_START_SYSTEM_TRACE` | 17 (0x0000011) | システム トレースを開始しようとしたときにエラーが発生しました。 |
| `RESULT_CODE_FAILURE_START_MSVC_TRACE` | 18 (0x00000012) | MSVC トレースを開始しようとしたときにエラーが発生しました。 |
| `RESULT_CODE_FAILURE_STOP_MSVC_TRACE` | 19 (0x00000013) | MSVC トレースを停止しようとしたときにエラーが発生しました。 |
| `RESULT_CODE_FAILURE_STOP_SYSTEM_TRACE` | 20 (0x00000014) | システム トレースを開始しようとしたときにエラーが発生しました。 |
| `RESULT_CODE_FAILURE_SESSION_DIRECTORY_RESOLUTION` | 21 (0x00000015) | トレースは停止されましたが、トレース セッションの一時ディレクトリが見つかりません。 |
| `RESULT_CODE_FAILURE_MSVC_TRACE_FILE_NOT_FOUND` | 22 (0x00000016) | 停止している MSVC トレースのトレース・ファイルが見つかりません。 |
| `RESULT_CODE_FAILURE_MERGE_TRACES` | 23 (0x00000017) | カーネル トレース コントロールを使用してトレースをマージするときにエラーが発生しました。 |
| `RESULT_CODE_FAILURE_UNKNOWN_ERROR` | 24 (0x00000018) | 不明なエラーが発生しました。 |

::: moniker-end
