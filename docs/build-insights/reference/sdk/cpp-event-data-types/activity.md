---
title: Activity クラス
description: C++ Build Insights SDK の Activity クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Activity
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ce7e4083411f1654064ca4628d10a767c7be1b7f
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923398"
---
# <a name="activity-class"></a>Activity クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`Activity` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 任意のアクティビティと照合するために使用します。 `Activity` クラスで照合できるすべてのイベントを見るには、[イベント テーブル](../event-table.md)に関する記事を参照してください。

## <a name="syntax"></a>構文

```cpp
class Activity : public Event
{
public:
    Activity(const RawEvent& event);

    const long long& StartTimestamp() const;
    const long long& StopTimestamp() const;
    const long long& ExclusiveDurationTicks() const;
    const long long& CPUTicks() const;
    const long long& ExclusiveCPUTicks() const;
    const long long& WallClockTimeResponsibilityTicks() const;
    const long long& ExclusiveWallClockTimeResponsibilityTicks() const;

    std::chrono::nanoseconds Duration() const;
    std::chrono::nanoseconds ExclusiveDuration() const;
    std::chrono::nanoseconds CPUTime() const ;
    std::chrono::nanoseconds ExclusiveCPUTime() const;
    std::chrono::nanoseconds WallClockTimeResponsibility() const;
    std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
};
```

## <a name="remarks"></a>解説

`Activity` クラスのいくつかのメンバー関数からは、ティック数が返されます。 C++ Build Insights では、ティックのソースとして Window のパフォーマンス カウンターが使用されます。 ティック数をティック周波数と共に使用して、秒などの時間単位に変換する必要があります。 [Event](event.md) 基底クラスで使用できる `TickFrequency` メンバー関数を呼び出して、ティック周波数を取得することができます。 [EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example) に関するページには、ティックを時間単位に変換する例が示されています。

ティック数を時間単位に自分で変換したくない場合は、`Activity` クラスに、時間の値をナノ秒単位で返すメンバー関数が用意されています。 それを他の時間単位に変換するには、C++ の標準 `chrono` ライブラリを使用します。

## <a name="members"></a>メンバー

基底クラス [Event](event.md) から継承されたメンバーに加えて、`Activity` クラスには以下のメンバーが含まれます。

### <a name="constructor"></a>コンストラクター

[アクティビティ](#activity)

### <a name="functions"></a>機能

[CPUTicks](#cpu-ticks)\
[CPUTime](#cpu-time)\
[Duration](#duration)\
[ExclusiveCPUTicks](#exclusive-cpu-ticks)\
[ExclusiveCPUTime](#exclusive-cpu-time)\
[ExclusiveDuration](#exclusive-duration)\
[ExclusiveDurationTicks](#exclusive-duration-ticks)\
[ExclusiveWallClockTimeResponsibility](#exclusive-wall-clock-time-responsibility)\
[ExclusiveWallClockTimeResponsibilityTicks](#exclusive-wall-clock-time-responsibility-ticks)\
[StartTimestamp](#start-timestamp)\
[StopTimestamp](#stop-timestamp)\
[WallClockTimeResponsibility](#wall-clock-time-responsibility)\
[WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks)

## <a name="activity"></a><a name="activity"></a> の利用状況

```cpp
Activity(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
任意のアクティビティ イベント。

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

## <a name="duration"></a><a name="duration"></a> Duration

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>戻り値

アクティビティの継続時間 (ナノ秒単位)。

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
