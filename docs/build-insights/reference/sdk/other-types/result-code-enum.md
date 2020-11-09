---
title: RESULT_CODE 列挙型
description: C++ Build Insights SDK の RESULT_CODE 列挙型のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RESULT_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3d9d18d535d15d04a2e449bdbbf693364276a518
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922413"
---
# <a name="result_code-enum"></a>RESULT_CODE 列挙型

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`RESULT_CODE` 列挙型には、成功と失敗の条件が記述されています。

## <a name="members"></a>メンバー

| 名前 | 値 | 説明 |
|--|--|--|
| `RESULT_CODE_SUCCESS` | 0 (0x00000000) | 操作に成功しました。 |
| `RESULT_CODE_FAILURE_ANALYSIS_ERROR` | 1 (0x00000001) | [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) または [RELOG_DESCRIPTOR](relog-descriptor-struct.md) のコールバック関数の 1 つにより、`CALLBACK_CODE_ANALYSIS_FAILURE` 値が返されました。 この値は、[CALLBACK_CODE](callback-code-enum.md) 列挙型のメンバーです。 |
| `RESULT_CODE_FAILURE_CANCELLED` | 2 (0x00000002) | [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) または [RELOG_DESCRIPTOR](relog-descriptor-struct.md) のコールバック関数の 1 つにより、`CALLBACK_CODE_ANALYSIS_CANCEL` 値が返されました。 この値は、[CALLBACK_CODE](callback-code-enum.md) 列挙型のメンバーです。 |
| `RESULT_CODE_FAILURE_INVALID_INPUT_LOG_FILE` | 3 (0x00000003) | 指定されている入力 Event Tracing for Windows (ETW) トレースが無効です。 |
| `RESULT_CODE_FAILURE_INVALID_OUTPUT_LOG_FILE` | 4 (0x00000004) | 指定されている出力 ETW トレースが無効です。 |
| `RESULT_CODE_FAILURE_MISSING_ANALYSIS_CALLBACK` | 5 (0x00000005) | [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) 構造体が正しく初期化されませんでした。 |
| `RESULT_CODE_FAILURE_MISSING_RELOG_CALLBACK` | 6 (0x00000006) | [RELOG_CALLBACKS](relog-callbacks-struct.md) 構造体が正しく初期化されませんでした。 |
| `RESULT_CODE_FAILURE_OPEN_INPUT_TRACE` | 7 (0x00000007) | 入力 ETW トレースを開くことができませんでした。 |
| `RESULT_CODE_FAILURE_PROCESS_TRACE` | 8 (0x00000008) | 入力 ETW トレースの処理中にエラーが発生しました。 |
| `RESULT_CODE_FAILURE_START_RELOGGER` | 9 (0x00000009) | 再ログ記録セッションを開始しようとしたときに、エラーが発生しました。 |
| `RESULT_CODE_FAILURE_DROPPED_EVENTS` | 10 (0x0000000A) | 入力 ETW トレースに重要なイベントがありません。 |
| `RESULT_CODE_FAILURE_UNSUPPORTED_OS` | 11 (0x0000000B) | サポートされていないバージョンの Windows で C++ Build Insights を使用しています。 |
| `RESULT_CODE_FAILURE_INVALID_TRACING_SESSION_NAME` | 12 (0x0000000C) | 指定されたセッション名が無効です。 |
| `RESULT_CODE_FAILURE_INSUFFICIENT_PRIVILEGES` | 13 (0x0000000D) | この操作には管理者特権が必要です。 |
| `RESULT_CODE_FAILURE_GENERATE_GUID` | 14 (0x0000000E) | GUID の生成中にエラーが発生しました。 |
| `RESULT_CODE_FAILURE_OBTAINING_TEMP_DIRECTORY` | 15 (0x0000000F) | 一時ディレクトリ パスの決定中にエラーが発生しました。 |
| `RESULT_CODE_FAILURE_CREATE_TEMPORARY_DIRECTORY` | 16 (0x00000010) | 開始中のトレース セッション用に一時ディレクトリを作成しようとして、エラーが発生しました。 |
| `RESULT_CODE_FAILURE_START_SYSTEM_TRACE` | 17 (0x00000011) | システム トレースを開始しようとしたときに、エラーが発生しました。 |
| `RESULT_CODE_FAILURE_START_MSVC_TRACE` | 18 (0x00000012) | MSVC トレースを開始しようとしたときに、エラーが発生しました。 |
| `RESULT_CODE_FAILURE_STOP_MSVC_TRACE` | 19 (0x00000013) | MSVC トレースを停止しようとしたときに、エラーが発生しました。 |
| `RESULT_CODE_FAILURE_STOP_SYSTEM_TRACE` | 20 (0x00000014) | システム トレースを開始しようとしたときに、エラーが発生しました。 |
| `RESULT_CODE_FAILURE_SESSION_DIRECTORY_RESOLUTION` | 21 (0x00000015) | トレースは停止されましたが、トレース セッションの一時ディレクトリが見つかりません。 |
| `RESULT_CODE_FAILURE_MSVC_TRACE_FILE_NOT_FOUND` | 22 (0x00000016) | 停止されている MSVC トレースのトレース ファイルが見つかりません。 |
| `RESULT_CODE_FAILURE_MERGE_TRACES` | 23 (0x00000017) | カーネル トレース コントロールを使用してトレースをマージしているときに、エラーが発生しました。 |
| `RESULT_CODE_FAILURE_UNKNOWN_ERROR` | 24 (0x00000018) | 不明なエラーが発生しました。 |

::: moniker-end
