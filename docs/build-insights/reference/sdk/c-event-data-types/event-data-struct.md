---
title: EVENT_DATA構造
description: C++ ビルド インサイト SDK EVENT_DATA構造リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EVENT_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 8ce396febe278c5e7c34fe170939c9522913f92a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325604"
---
# <a name="event_data-structure"></a>EVENT_DATA構造

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`EVENT_DATA`構造体は、分析セッションまたは再ロギング セッションから受信したイベントを記述します。 これらのセッションは、[分析](../functions/analyze.md)、[分析 A](../functions/analyze-a.md)、[分析 W](../functions/analyze-w.md)、[リローグ](../functions/relog.md)、[再ログ](../functions/relog-a.md)、 または[RelogW](../functions/relog-w.md)関数を呼び出すことによって開始されます。

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
| `EventId` | イベントを識別する番号。 イベント識別子の一覧については、「 [EVENT_ID](event-id-enum.md)」 を参照してください。 |
| `EventInstanceId` | トレース内の現在のイベントを一意に識別する番号。 同じトレースを複数回分析または再ログしても、この値は変わりません。 このフィールドを使用して、複数の分析または再ロギングパスで同じトレースを渡す場合に同じイベントを識別します。 |
| `TickFrequency` | ティック単位で測定された期間を評価するときに使用する 1 秒あたりのティック数。 |
| `StartTimestamp` | イベントが *[アクティビティ*] の場合、このフィールドはアクティビティの開始時にキャプチャされたティック値に設定されます。 このイベントが*単純イベント*の場合、このフィールドはイベント発生時にキャプチャされたティック値に設定されます。 |
| `StopTimestamp` | イベントが *[アクティビティ*] の場合、このフィールドはアクティビティが停止した時点でキャプチャされたティック値に設定されます。 このアクティビティの停止イベントがまだ受信されていない場合、このフィールドはゼロに設定されます。 このイベントが*単純イベント*の場合、このフィールドはゼロに設定されます。 |
| `ExclusiveDurationTicks` | このイベントが *[アクティビティ*] の場合、このフィールドは、このアクティビティで直接発生したティック数に設定されます。 子アクティビティで発生したティックの数は除外されます。 *単純なイベント*の場合、このフィールドは 0 に設定されています。 |
| `CPUTicks` | このイベントが *[アクティビティ*] の場合、このフィールドは、このアクティビティ中に発生した CPU ティックの数に設定されます。 CPU ティックは、通常のティックとは異なります。 CPU ティックは、CPU がアクティビティ内のコードを実行している場合にのみカウントされます。 アクティビティに関連付けられたスレッドがスリープ状態の場合、CPU ティックはカウントされません。 *単純なイベント*の場合、このフィールドは 0 に設定されています。 |
| `ExclusiveCPUTicks` | このフィールドは、子アクティビティで`CPUTicks`発生した CPU ティックが含まれていない点を除いて、 と同じ意味を持ちます。 *単純なイベント*の場合、このフィールドは 0 に設定されています。 |
| `WallClockTimeResponsibilityTicks` | このイベントが *[アクティビティ*] の場合、このフィールドは、このアクティビティが全体のウォール クロック時間に対する貢献度を表すティック数に設定されます。 ウォールクロックの時間責任ティックは、通常のティックとは異なります。 ウォールクロック時間の責任ティックは、アクティビティ間の並列性を考慮に入れます。 たとえば、2 つの並列アクティビティの期間が 50 ティックで、開始時間と終了時間が同じ場合があります。 この場合、両方とも 25 ティックの壁時計の時間責任が割り当てられます。 *単純なイベント*の場合、このフィールドは 0 に設定されています。 |
| `ExclusiveWallClockTimeResponsibilityTicks` | このフィールドは、子アクティビティの`WallClockTimeResponsibilityTicks`ウォールクロック時間の責任ティックが含まれていない点を除いて、 と同じ意味を持ちます。 *単純なイベント*の場合、このフィールドは 0 に設定されています。 |
| `Data` | イベントに格納されている追加データへのポイント。 フィールドによって、指し示されるデータの種類が`EventId`異なります。 |
| `ProcessId` | イベントが発生したプロセスの識別子。 |
| `ThreadId` | イベントが発生したスレッドの識別子。 |
| `ProcessorIndex` | イベントが発生したインデックスが 0 個の CPU 番号。 |
| `EventName` | で`EventId`識別されるエンティティの名前を含む ANSI 文字列。 |
| `EventWideName` | で`EventId`識別されるエンティティの名前を含むワイド文字列。 |

## <a name="remarks"></a>解説

の多くの`EVENT_DATA`フィールドにはティック数が含まれています。 C++ ビルドインサイトは、ウィンドウのパフォーマンス カウンターをティックのソースとして使用します。 ティック数は`TickFrequency`、秒などの適切な時間単位に変換するために、フィールドと一緒に使用する必要があります。 この変換を実行するには、以下の例を参照してください。 `EVENT_DATA`アクティビティの通常のティック数のフィールドは含まれていません。 この値を取得するには、 `StartTimestamp` `StopTimestamp`から減算します。 `EVENT_DATA`は、C API ユーザーが使用するための構造です。 C++ API ユーザーの場合[、Event](../cpp-event-data-types/event.md)のようなクラスは自動的に時間変換を行います。

フィールドの値は`EVENT_DATA``Data`、フィールド`EventId`の値によって異なります。 の値`Data`は、以下の表で説明します。 一部のエンティティ識別子は、次の表に含まれる可能性があります。 この場合、`Data`フィールドは 0 に`nullptr`設定されます。

| `EventId` 値 | 指定先の型`Data` |
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
