---
title: Activity クラス
description: C++ ビルド インサイト SDK アクティビティ クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Activity
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2ea04150aec9c0b2366d97e6e4c15de557a4f47c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325244"
---
# <a name="activity-class"></a>Activity クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`Activity`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 任意のアクティビティ イベントに一致させるために使用します。 イベント[テーブル](../event-table.md)を参照して、クラスで一致できるすべてのイベント`Activity`を確認します。

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

クラス内のいくつかのメンバー関数`Activity`は、ティック数を返します。 C++ ビルドインサイトは、ティックのソースとして Windows のパフォーマンス カウンターを使用します。 ティック数は、秒などの時間単位に変換するためにティック頻度と共に使用する必要があります。 Event`TickFrequency`基本クラスで使用できる[Event](event.md)メンバー関数は、ティックの頻度を取得するために呼び出されるかもしれません。 [EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example)ページには、ティックを時間単位に変換する例が表示されます。

自分でティックを時間単位に変換しない場合、`Activity`クラスは時間の値をナノ秒単位で返すメンバー関数を提供します。 標準の C++`chrono`ライブラリを使用して、他の時間単位に変換します。

## <a name="members"></a>メンバー

[Event](event.md)基本クラスから継承されたメンバーと共に`Activity`、クラスには次のメンバーが含まれます。

### <a name="constructor"></a>Constructor

[アクティビティ](#activity)

### <a name="functions"></a>関数

[CPUティック](#cpu-ticks)\
[CPUタイム](#cpu-time)\
[期間](#duration)\
[排他的なCPUティック](#exclusive-cpu-ticks)\
[排他 CPU タイム](#exclusive-cpu-time)\
[エクスクルーシブ期間](#exclusive-duration)\
[エクスクルーシブ・デュレーション・ティック](#exclusive-duration-ticks)\
[エクスクルーシブウォールクロックタイム責任](#exclusive-wall-clock-time-responsibility)\
[排他的なウォールクロックタイム責任ティック](#exclusive-wall-clock-time-responsibility-ticks)\
[スタートタイムスタンプ](#start-timestamp)\
[ストップタイムスタンプ](#stop-timestamp)\
[ウォールクロックタイム責任](#wall-clock-time-responsibility)\
[ウォールクロックタイム責任ティック](#wall-clock-time-responsibility-ticks)

## <a name="activity"></a><a name="activity"></a> の利用状況

```cpp
Activity(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
任意のアクティビティ イベント。

## <a name="cputicks"></a><a name="cpu-ticks"></a>CPUティック

```cpp
const long long& CPUTicks() const;
```

### <a name="return-value"></a>戻り値

このアクティビティ中に発生した CPU ティックの数。 CPU ティックは、通常のティックとは異なります。 CPU ティックは、CPU がアクティビティ内のコードを実行している場合にのみカウントされます。 アクティビティに関連付けられたスレッドがスリープ状態の場合、CPU ティックはカウントされません。

## <a name="cputime"></a><a name="cpu-time"></a>CPUタイム

```cpp
std::chrono::nanoseconds CPUTime()() const;
```

### <a name="return-value"></a>戻り値

このアクティビティ内で CPU がコードを実行していた時間。 子アクティビティが別々のスレッドで実行される場合、この値はアクティビティの期間よりも長くなることがあります。 値はナノ秒単位で返されます。

## <a name="duration"></a><a name="duration"></a>期間

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>戻り値

アクティビティの時間 (ナノ秒単位)。

## <a name="exclusivecputicks"></a><a name="exclusive-cpu-ticks"></a>排他的なCPUティック

```cpp
const long long& ExclusiveCPUTicks() const;
```

### <a name="return-value"></a>戻り値

[CPUTicks](#cpu-ticks)と同じですが、子アクティビティで発生した CPU ティックは含まれません。

## <a name="exclusivecputime"></a><a name="exclusive-cpu-time"></a>排他 CPU タイム

```cpp
std::chrono::nanoseconds ExclusiveCPUTime() const;
```

### <a name="return-value"></a>戻り値

[CPUTime](#cpu-time)と同じですが、子アクティビティの CPU 時間は含まれません。

## <a name="exclusiveduration"></a><a name="exclusive-duration"></a>エクスクルーシブ期間

```cpp
std::chrono::nanoseconds ExclusiveDuration() const;
```

### <a name="return-value"></a>戻り値

アクティビティの期間 (子アクティビティに費やされた時間は含まない)

## <a name="exclusivedurationticks"></a><a name="exclusive-duration-ticks"></a>エクスクルーシブ・デュレーション・ティック

```cpp
const long long& ExclusiveDurationTicks() const;
```

### <a name="return-value"></a>戻り値

子アクティビティで発生したティックの数を除き、このアクティビティで発生したティックの数。

## <a name="exclusivewallclocktimeresponsibility"></a><a name="exclusive-wall-clock-time-responsibility"></a>エクスクルーシブウォールクロックタイム責任

```cpp
std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
```

### <a name="return-value"></a>戻り値

[は、子](#wall-clock-time-responsibility)アクティビティのウォールクロックタイム責任と同じですが、ウォールクロック時間の責任は含まれていません。

## <a name="exclusivewallclocktimeresponsibilityticks"></a><a name="exclusive-wall-clock-time-responsibility-ticks"></a>排他的なウォールクロックタイム責任ティック

```cpp
const long long& ExclusiveWallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>戻り値

[ウォールクロックタイム責任ティックと](#wall-clock-time-responsibility-ticks)同じですが、子アクティビティのウォールクロック時間の責任ティックは含まれていません。

## <a name="starttimestamp"></a><a name="start-timestamp"></a>スタートタイムスタンプ

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>戻り値

アクティビティの開始時にキャプチャされたティック値。

## <a name="stoptimestamp"></a><a name="stop-timestamp"></a>ストップタイムスタンプ

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>戻り値

アクティビティが停止した時点でキャプチャされたティック値。

## <a name="wallclocktimeresponsibility"></a><a name="wall-clock-time-responsibility"></a>ウォールクロックタイム責任

```cpp
std::chrono::nanoseconds WallClockTimeResponsibility() const;
```

### <a name="return-value"></a>戻り値

この活動のウォールクロック時間の責任(ナノ秒単位)。 ウォールクロック時間責任の意味の詳細については、「[ウォールクロックタイムレニシアルティック」](#wall-clock-time-responsibility-ticks)を参照してください。

## <a name="wallclocktimeresponsibilityticks"></a><a name="wall-clock-time-responsibility-ticks"></a>ウォールクロックタイム責任ティック

```cpp
const long long& WallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>戻り値

このアクティビティの全体的なウォール クロック時間への貢献度を表すティック数。 ウォールクロックの時間責任ティックは、通常のティックとは異なります。 ウォールクロック時間の責任ティックは、アクティビティ間の並列性を考慮に入れます。 2 つの並列アクティビティの時間は 50 ティックで、開始時間と停止時間は同じです。 この場合、両方とも 25 ティックのウォールクロック時間の責任が割り当てられます。

::: moniker-end
