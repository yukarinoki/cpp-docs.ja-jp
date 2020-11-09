---
title: RawEvent クラス
description: C++ Build Insights SDK の RawEvent クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RawEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1cf96e1b8eadaf1de9fe2cf565a993f3bcafe358
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920464"
---
# <a name="rawevent-class"></a>RawEvent クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`RawEvent` クラスは、[EventStack](event-stack.md) の一般的なイベントを表すために使用されます。

## <a name="syntax"></a>構文

```cpp
class RawEvent
{
public:
    RawEvent(const EVENT_DATA& event);

    const unsigned short&        EventId() const;
    const unsigned long long&    EventInstanceId() const;
    const long long&             TickFrequency() const;
    const long long&             StartTimestamp() const;
    const long long&             StopTimestamp() const;
    const long long&             ExclusiveDurationTicks() const;
    const long long&             CPUTicks() const;
    const long long&             ExclusiveCPUTicks() const;
    const long long&             WallClockTimeResponsibilityTicks() const;
    const long long&             ExclusiveWallClockTimeResponsibilityTicks() const;
    const void*                  Data() const;
    const unsigned long&         ProcessId() const;
    const unsigned long&         ThreadId() const;
    const unsigned short&        ProcessorIndex() const;
    const char*                  EventName() const;
    const wchar_t*               EventWideName() const;

    std::chrono::nanoseconds Duration() const;
    std::chrono::nanoseconds ExclusiveDuration() const;
    std::chrono::nanoseconds CPUTime() const ;
    std::chrono::nanoseconds ExclusiveCPUTime() const;
    std::chrono::nanoseconds WallClockTimeResponsibility() const;
    std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
};
```

## <a name="remarks"></a>解説

`RawEvent` クラスのいくつかのメンバー関数からは、ティック数が返されます。 C++ Build Insights では、ティックのソースとして Window のパフォーマンス カウンターが使用されます。 ティック数をティック周波数と共に使用して、秒などの時間単位に変換する必要があります。 `TickFrequency` メンバー関数を呼び出して、ティック周波数を取得できます。 ティック数を時間単位に変換する方法の例については、[EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example) に関するページを参照してください。

ティック数を自分で変換したくない場合は、`RawEvent` クラスに、時間の値をナノ秒単位で返すメンバー関数が用意されています。 ナノ秒単位を他の時間単位に変換するには、C++ の標準 `chrono` ライブラリを使用します。

## <a name="members"></a>メンバー

### <a name="constructor"></a>コンストラクター

[RawEvent](#raw-event)

### <a name="functions"></a>機能

[CPUTicks](#cpu-ticks)\
[CPUTime](#cpu-time)\
[データ](#data)\
[Duration](#duration)\
[EventId](#event-id)
[EventInstanceId](#event-instance-id)
[EventName](#event-name)\
[EventWideName](#event-wide-name)\
[ExclusiveCPUTicks](#exclusive-cpu-ticks)\
[ExclusiveCPUTime](#exclusive-cpu-time)\
[ExclusiveDuration](#exclusive-duration)\
[ExclusiveDurationTicks](#exclusive-duration-ticks)\
[ExclusiveWallClockTimeResponsibility](#exclusive-wall-clock-time-responsibility)\
[ExclusiveWallClockTimeResponsibilityTicks](#exclusive-wall-clock-time-responsibility-ticks)\
[ProcessId](#process-id)\
[ProcessorIndex](#processor-index)\
[StartTimestamp](#start-timestamp)\
[StopTimestamp](#stop-timestamp)\
[ThreadId](#thread-id)\
[TickFrequency](#tick-frequency)\
[WallClockTimeResponsibility](#wall-clock-time-responsibility)\
[WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks)

## <a name="rawevent"></a><a name="raw-event"></a> RawEvent

```cpp
RawEvent(const EVENT_DATA& data);
```

### <a name="parameters"></a>パラメーター

*event*\
イベントのデータ。

## <a name="cputicks"></a><a name="cpu-ticks"></a> CPUTicks

```cpp
const long long& CPUTicks() const;
```

### <a name="return-value"></a>戻り値

このアクティビティの間に発生した CPU ティックの数。 CPU ティックは、通常のティックとは異なります。 CPU ティックは、アクティビティ内のコードが CPU によって実行されている場合にのみカウントされます。 アクティビティに関連付けられているスレッドがスリープ状態のときには、CPU ティックはカウントされません。

## <a name="cputime"></a><a name="cpu-time"></a> CPUTime

```cpp
std::chrono::nanoseconds CPUTime()() const;
```

### <a name="return-value"></a>戻り値

CPU がこのアクティビティ内でコードを実行していた時間の長さ。 子アクティビティが別のスレッドで実行される場合、この値はアクティビティの期間より長くなる可能性があります。 値はナノ秒単位で返されます。

## <a name="data"></a><a name="data"></a> Data

```cpp
const void* Data() const;
```

### <a name="return-value"></a>戻り値

このイベントに含まれる追加データへのポインター。 このフィールドを解釈する方法の詳細については、[EVENT_DATA](../c-event-data-types/event-data-struct.md) に関する記事を参照してください。

## <a name="duration"></a><a name="duration"></a> Duration

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>戻り値

アクティビティの継続時間 (ナノ秒単位)。

## <a name="eventid"></a><a name="event-id"></a> EventId

```cpp
const unsigned short& EventId() const;
```

### <a name="return-value"></a>戻り値

イベントの種類を識別する番号。 イベント識別子の一覧については、[EVENT_ID](../c-event-data-types/event-id-enum.md) に関する記事をご覧ください。

## <a name="eventinstanceid"></a><a name="event-instance-id"></a> EventInstanceId

```cpp
const unsigned long long& EventInstanceId() const;
```

### <a name="return-value"></a>戻り値

トレース内のイベントを一意に識別する番号。 この値は、同じトレースを複数回分析またはログに再記録しても変わりません。 この値を使用して、同じトレースに対する複数の分析パスまたは再ログ記録パスで同じイベントを識別します。

## <a name="eventname"></a><a name="event-name"></a> EventName

```cpp
const char* EventName() const;
```

### <a name="return-value"></a>戻り値

[EventId](#event-id) によって示されるイベントの種類の名前が含まれる ANSI 文字列。

## <a name="eventwidename"></a><a name="event-wide-name"></a> EventWideName

```cpp
const wchar_t* EventWideName() const;
```

### <a name="return-value"></a>戻り値

[EventId](#event-id) によって示されるイベントの種類の名前が含まれるワイド文字列。

## <a name="exclusivecputicks"></a><a name="exclusive-cpu-ticks"></a> ExclusiveCPUTicks

```cpp
const long long& ExclusiveCPUTicks() const;
```

### <a name="return-value"></a>戻り値

[CPUTicks](#cpu-ticks) と同じですが、子アクティビティで発生した CPU ティック数は含まれません。

## <a name="exclusivecputime"></a><a name="exclusive-cpu-time"></a> ExclusiveCPUTime

```cpp
std::chrono::nanoseconds ExclusiveCPUTime() const;
```

### <a name="return-value"></a>戻り値

子アクティビティの CPU 時間が含まれない点を除いて、[CPUTime](#cpu-time) と同じです。

## <a name="exclusiveduration"></a><a name="exclusive-duration"></a> ExclusiveDuration

```cpp
std::chrono::nanoseconds ExclusiveDuration() const;
```

### <a name="return-value"></a>戻り値

アクティビティの継続時間 (ナノ秒単位)。子アクティビティで費やされた時間は含まれません。

## <a name="exclusivedurationticks"></a><a name="exclusive-duration-ticks"></a> ExclusiveDurationTicks

```cpp
const long long& ExclusiveDurationTicks() const;
```

### <a name="return-value"></a>戻り値

このアクティビティで発生したティックの数。子アクティビティで発生したティックの数は除きます。

## <a name="exclusivewallclocktimeresponsibility"></a><a name="exclusive-wall-clock-time-responsibility"></a> ExclusiveWallClockTimeResponsibility

```cpp
std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
```

### <a name="return-value"></a>戻り値

[WallClockTimeResponsibility](#wall-clock-time-responsibility) と同じですが、子アクティビティのウォール クロック時間責任は含まれません。

## <a name="exclusivewallclocktimeresponsibilityticks"></a><a name="exclusive-wall-clock-time-responsibility-ticks"></a> ExclusiveWallClockTimeResponsibilityTicks

```cpp
const long long& ExclusiveWallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>戻り値

[WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks) と同じですが、子アクティビティのウォール クロック時間責任ティック数は含まれません。

## <a name="processid"></a><a name="process-id"></a> ProcessId

```cpp
const unsigned long& ProcessId() const;
```

### <a name="return-value"></a>戻り値

イベントが発生したプロセスの識別子。

## <a name="processorindex"></a><a name="processor-index"></a> ProcessorIndex

```cpp
const unsigned short& ProcessorIndex() const;
```

### <a name="return-value"></a>戻り値

イベントが発生した論理プロセッサに対する 0 から始まるインデックス。

## <a name="starttimestamp"></a><a name="start-timestamp"></a> StartTimestamp

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>戻り値

アクティビティが開始した時刻にキャプチャされたティック値。

## <a name="stoptimestamp"></a><a name="stop-timestamp"></a> StopTimestamp

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>戻り値

アクティビティが停止した時刻にキャプチャされたティック値。

## <a name="threadid"></a><a name="thread-id"></a> ThreadId

```cpp
const unsigned long& ThreadId() const;
```

### <a name="return-value"></a>戻り値

イベントが発生したスレッドの識別子。

## <a name="tickfrequency"></a><a name="tick-frequency"></a> TickFrequency

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>戻り値

このイベントのティック単位で計測された期間を評価するときに使用する、1 秒あたりのティック数。

## <a name="wallclocktimeresponsibility"></a><a name="wall-clock-time-responsibility"></a> WallClockTimeResponsibility

```cpp
std::chrono::nanoseconds WallClockTimeResponsibility() const;
```

### <a name="return-value"></a>戻り値

このアクティビティのウォール クロック時間責任 (ナノ秒単位)。 ウォール クロック時間責任の詳細については、「[WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks)」を参照してください。

## <a name="wallclocktimeresponsibilityticks"></a><a name="wall-clock-time-responsibility-ticks"></a> WallClockTimeResponsibilityTicks

```cpp
const long long& WallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>戻り値

全体的なウォール クロック時間に対するこのアクティビティの影響を表すティック数。 実時間の責任ティックは、通常のティックとは異なります。 実時間の責任ティックでは、アクティビティ間の並列処理が考慮されます。 2 つの並列アクティビティが 50 ティックの期間を持ち、開始時刻と終了時刻が同じであるとします。 この場合、両方に 25 ティックのウォール クロック時間責任が割り当てられます。

::: moniker-end
