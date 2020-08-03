---
title: EVENT_DATA 構造体
description: C++ Build Insights SDK の EVENT_DATA 構造体のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EVENT_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ccba320a8bb9279b874fae2484c71af913253148
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229923"
---
# <a name="event_data-structure"></a>EVENT_DATA 構造体

::: moniker range="<=vs-2015"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=vs-2017"

`EVENT_DATA` 構造体によって、分析セッションまたは再ログ セッションから受信したイベントが表されます。 これらのセッションは、[Analyze](../functions/analyze.md)、[AnalyzeA](../functions/analyze-a.md)、[AnalyzeW](../functions/analyze-w.md)、[Relog](../functions/relog.md)、[RelogA](../functions/relog-a.md)、または [RelogW](../functions/relog-w.md) 関数を呼び出すことによって開始されます。

## <a name="syntax"></a>構文

```cpp
typedef struct EVENT_DATA_TAG
{
    unsigned short          EventId;
    unsigned long long      EventInstanceId;

    long long               TickFrequency;
    long long               StartTimestamp;
    long long               StopTimestamp;
    long long               ExclusiveDurationTicks;
    long long               CPUTicks;
    long long               ExclusiveCPUTicks;
    long long               WallClockTimeResponsibilityTicks;
    long long               ExclusiveWallClockTimeResponsibilityTicks;

    const void*             Data;

    unsigned long           ProcessId;
    unsigned long           ThreadId;
    unsigned short          ProcessorIndex;

    const char*             EventName;
    const wchar_t*          EventWideName;

} EVENT_DATA;
```

## <a name="members"></a>メンバー

|  |  |
|--|--|
| `EventId` | イベントを識別する番号です。 イベント識別子の一覧については、[EVENT_ID](event-id-enum.md) に関する記事をご覧ください。 |
| `EventInstanceId` | トレース内の現在のイベントを一意に識別する番号です。 この値は、同じトレースを複数回分析またはログに再記録しても変わりません。 このフィールドを使用して、同じトレースに対する複数の分析または再ログのパスから同じイベントを識別します。 |
| `TickFrequency` | ティック単位で計測された期間を評価するときに使用する、1 秒あたりのティック数。 |
| `StartTimestamp` | イベントが "*アクティビティ*" である場合、このフィールドは、アクティビティの開始時にキャプチャされたティック値に設定されます。 このイベントが "*シンプルなイベント*" である場合、このフィールドは、イベントの発生時にキャプチャされたティック値に設定されます。 |
| `StopTimestamp` | イベントが "*アクティビティ*" である場合、このフィールドは、アクティビティの停止時にキャプチャされたティック値に設定されます。 このアクティビティに対する停止イベントがまだ受信されていない場合、このフィールドは 0 に設定されます。 このイベントが "*シンプルなイベント*" である場合、このフィールドは 0 に設定されます。 |
| `ExclusiveDurationTicks` | このイベントが "*アクティビティ*" である場合、このフィールドは、このアクティビティで直接発生したティック数に設定されます。 子アクティビティで発生したティック数は除外されます。 "*シンプルなイベント*" の場合、このフィールドは 0 に設定されます。 |
| `CPUTicks` | このイベントが "*アクティビティ*" である場合、このフィールドは、このアクティビティの実行中に発生した CPU ティック数に設定されます。 CPU ティックは、通常のティックとは異なります。 CPU ティックは、アクティビティ内のコードが CPU によって実行されている場合にのみカウントされます。 アクティビティに関連付けられているスレッドがスリープ状態のときには、CPU ティックはカウントされません。 "*シンプルなイベント*" の場合、このフィールドは 0 に設定されます。 |
| `ExclusiveCPUTicks` | このフィールドは `CPUTicks` と同じ意味を持ちますが、子アクティビティで発生した CPU ティックは含まれません。 "*シンプルなイベント*" の場合、このフィールドは 0 に設定されます。 |
| `WallClockTimeResponsibilityTicks` | このイベントが "*アクティビティ*" である場合、このフィールドには、全体的な実時間に対するこのアクティビティの影響を表すティック数が設定されます。 実時間の責任ティックは、通常のティックとは異なります。 実時間の責任ティックでは、アクティビティ間の並列処理が考慮されます。 たとえば、2 つの並列アクティビティが 50 ティックの期間を持ち、開始時刻と終了時刻が同じであるとします。 この場合、両方に 25 ティックの実時間の責任が割り当てられます。 "*シンプルなイベント*" の場合、このフィールドは 0 に設定されます。 |
| `ExclusiveWallClockTimeResponsibilityTicks` | このフィールドは `WallClockTimeResponsibilityTicks` と同じ意味を持ちます。ただし、子アクティビティの実時間の責任ティックは含まれません。 "*シンプルなイベント*" の場合、このフィールドは 0 に設定されます。 |
| `Data` | イベントに格納されている追加データを示します。 示されているデータの型は、`EventId` フィールドによって異なります。 |
| `ProcessId` | イベントが発生したプロセスの識別子。 |
| `ThreadId` | イベントが発生したスレッドの識別子。 |
| `ProcessorIndex` | イベントが発生した (インデックスが 0 から始まる) CPU 番号。 |
| `EventName` | `EventId` によって識別されるエンティティの名前を含む ANSI 文字列。 |
| `EventWideName` | `EventId` によって識別されるエンティティの名前を含むワイド文字列。 |

## <a name="remarks"></a>Remarks

`EVENT_DATA` の多くのフィールドには、ティック数が含まれています。 C++ Build Insights では、ティックのソースとして Window のパフォーマンス カウンターが使用されます。 ティック数は `TickFrequency` フィールドと共に使用して、秒などの適切な時間単位に変換する必要があります。 この変換の実行方法については、以下の例を参照してください。 `EVENT_DATA` には、アクティビティの通常のティック数を表すフィールドは含まれていません。 この値を取得するには、`StopTimestamp` から `StartTimestamp` を減算します。 `EVENT_DATA` は、C API ユーザーが使用することを意図した構造体です。 C++ API ユーザーの場合、[Event](../cpp-event-data-types/event.md) などのクラスによって、時間の変換が自動的に実行されます。

`EVENT_DATA` の `Data` フィールドの値は、その `EventId` フィールドの値によって異なります。 `Data` の値について、次の表で説明します。 次の表では、エンティティ識別子の一部が不足している場合があります。 その場合、`Data` フィールドは **`nullptr`** または 0 に設定されます。

| `EventId` の値 | `Data` が指す型 |
|--|--|
| `EVENT_ID_BACK_END_PASS` | [CL_PASS_DATA](cl-pass-data-struct.md) |
| `EVENT_ID_COMMAND_LINE` | `const wchar_t` |
| `EVENT_ID_COMPILER` | [INVOCATION_DATA](invocation-data-struct.md) |
| `EVENT_ID_ENVIRONMENT_VARIABLE` | [NAME_VALUE_PAIR_DATA](name-value-pair-data-struct.md) |
| `EVENT_ID_EXECUTABLE_IMAGE_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_EXP_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_FILE_INPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_FORCE_INLINE` | [FUNCTION_FORCE_INLINEE_DATA](function-force-inlinee-data-struct.md) |
| `EVENT_ID_FRONT_END_FILE` | [FRONT_END_FILE_DATA](front-end-file-data-struct.md) |
| `EVENT_ID_FRONT_END_PASS` | [CL_PASS_DATA](cl-pass-data-struct.md) |
| `EVENT_ID_FUNCTION` | [FUNCTION_DATA](function-data-struct.md) |
| `EVENT_ID_IMP_LIB_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_LIB_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_LINKER` | [INVOCATION_DATA](invocation-data-struct.md) |
| `EVENT_ID_OBJ_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_SYMBOL_NAME` | [SYMBOL_NAME_DATA](symbol-name-data-struct.md) |
| `EVENT_ID_TEMPLATE_INSTANTIATION` | [TEMPLATE_INSTANTIATION_DATA](template-instantiation-data-struct.md) |

## <a name="tick-conversion-example"></a>ティック変換の例

```cpp
//
// We have the elapsed number of ticks, along with the
// number of ticks per second. We use these values
// to convert to the number of elapsed microseconds.
// To guard against loss-of-precision, we convert
// to microseconds *before* dividing by ticks-per-second.
//

long long ConvertDurationToMicroseconds(const sruct EVENT_DATA& eventData)
{
    long long duration = eventData.StopTimestamp - eventData.StartTimestamp;
    long long duration *= 1000000;
    return duration / eventData.TickFrequency;
}
```

::: moniker-end
