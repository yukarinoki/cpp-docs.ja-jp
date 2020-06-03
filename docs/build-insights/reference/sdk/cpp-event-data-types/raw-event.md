---
title: クラス
description: C++ ビルド インサイト SDK RawEvent クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RawEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 83629457ac3a0d1f991f6b084af2f3400612b2ac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324384"
---
# <a name="rawevent-class"></a>クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`RawEvent`は、[イベントスタック](event-stack.md)内の一般的なイベントを表すために使用されます。

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

クラス内のいくつかのメンバー関数`RawEvent`は、ティック数を返します。 C++ ビルドインサイトは、ティックのソースとして Windows のパフォーマンス カウンターを使用します。 ティック数は、秒のような時間単位に変換するためにティック周波数と一緒に使用する必要があります。 メンバー`TickFrequency`関数は、ティック周波数を取得するために呼び出されるかもしれません。 ティックを時間単位に変換する方法の例については[、EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example)ページを参照してください。

自分でティックを変換しない場合、`RawEvent`クラスは時間の値をナノ秒単位で返すメンバー関数を提供します。 標準の C++`chrono`ライブラリを使用して、ナノ秒を他の時間単位に変換します。

## <a name="members"></a>メンバー

### <a name="constructor"></a>Constructor

[生のイベント](#raw-event)

### <a name="functions"></a>関数

[CPUティック](#cpu-ticks)\
[CPUタイム](#cpu-time)\
[データ](#data)\
[期間](#duration)\
[EventId](#event-id)
[イベント](#event-instance-id)
[Id イベント名](#event-name)\
[イベントワイドネーム](#event-wide-name)\
[排他的なCPUティック](#exclusive-cpu-ticks)\
[排他 CPU タイム](#exclusive-cpu-time)\
[エクスクルーシブ期間](#exclusive-duration)\
[エクスクルーシブ・デュレーション・ティック](#exclusive-duration-ticks)\
[エクスクルーシブウォールクロックタイム責任](#exclusive-wall-clock-time-responsibility)\
[排他的なウォールクロックタイム責任ティック](#exclusive-wall-clock-time-responsibility-ticks)\
[プロセスId](#process-id)\
[プロセッサインデックス](#processor-index)\
[スタートタイムスタンプ](#start-timestamp)\
[ストップタイムスタンプ](#stop-timestamp)\
[Threadid](#thread-id)\
[ティック周波数](#tick-frequency)\
[ウォールクロックタイム責任](#wall-clock-time-responsibility)\
[ウォールクロックタイム責任ティック](#wall-clock-time-responsibility-ticks)

## <a name="rawevent"></a><a name="raw-event"></a>生のイベント

```cpp
RawEvent(const EVENT_DATA& data);
```

### <a name="parameters"></a>パラメーター

*イベント*\
イベントのデータ。

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

## <a name="data"></a><a name="data"></a>データ

```cpp
const void* Data() const;
```

### <a name="return-value"></a>戻り値

このイベントに含まれる追加データへのポインター。 このフィールドの解釈方法の詳細については[、「EVENT_DATA」](../c-event-data-types/event-data-struct.md)を参照してください。

## <a name="duration"></a><a name="duration"></a>期間

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>戻り値

アクティビティの時間 (ナノ秒単位)。

## <a name="eventid"></a><a name="event-id"></a>Eventid

```cpp
const unsigned short& EventId() const;
```

### <a name="return-value"></a>戻り値

イベントの種類を識別する数値。 イベント識別子の一覧については、「 [EVENT_ID](../c-event-data-types/event-id-enum.md)」 を参照してください。

## <a name="eventinstanceid"></a><a name="event-instance-id"></a>イベントインスタンスId

```cpp
const unsigned long long& EventInstanceId() const;
```

### <a name="return-value"></a>戻り値

トレース内のイベントを一意に識別する番号。 同じトレースを複数回分析または再ログしても、この値は変わりません。 この値を使用して、複数の分析または再ロギングパスで同じトレースを渡す場合に同じイベントを識別します。

## <a name="eventname"></a><a name="event-name"></a>Eventname

```cpp
const char* EventName() const;
```

### <a name="return-value"></a>戻り値

イベントタイプの名前を含む ANSI[文字列です。](#event-id)

## <a name="eventwidename"></a><a name="event-wide-name"></a>イベントワイドネーム

```cpp
const wchar_t* EventWideName() const;
```

### <a name="return-value"></a>戻り値

[EventId](#event-id)で識別されるイベントの種類の名前を含むワイド文字列。

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

## <a name="processid"></a><a name="process-id"></a>プロセスId

```cpp
const unsigned long& ProcessId() const;
```

### <a name="return-value"></a>戻り値

イベントが発生したプロセスの識別子。

## <a name="processorindex"></a><a name="processor-index"></a>プロセッサインデックス

```cpp
const unsigned short& ProcessorIndex() const;
```

### <a name="return-value"></a>戻り値

イベントが発生した論理プロセッサの 0 から始まるインデックス。

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

## <a name="threadid"></a><a name="thread-id"></a>Threadid

```cpp
const unsigned long& ThreadId() const;
```

### <a name="return-value"></a>戻り値

イベントが発生したスレッドの識別子。

## <a name="tickfrequency"></a><a name="tick-frequency"></a>ティック周波数

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>戻り値

このイベントのティック数で測定された期間を評価するときに使用する 1 秒あたりのティック数。

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
