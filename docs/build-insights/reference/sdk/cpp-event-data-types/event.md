---
title: イベント クラス
description: C++ Build Insights SDK の Event クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Event
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7dd96ffa3518c58e1b18312bb4fe2c36df26bd67
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923296"
---
# <a name="event-class"></a>イベント クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`Event` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 任意のイベントと照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class Event
{
public:
    Event(const RawEvent& event);

    const unsigned short&        EventId() const;
    const unsigned long long&    EventInstanceId() const;
    const long long&             TickFrequency() const;
    const long long&             Timestamp() const;
    const unsigned long&         ProcessId() const;
    const unsigned long&         ThreadId() const;
    const unsigned short&        ProcessorIndex() const;
    const char*                  EventName() const;
    const wchar_t*               EventWideName() const;
};
```

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

[Event](#entity)

### <a name="functions"></a>機能

[Data](#data)
[EventId](#event-id)\
[EventInstanceId](#event-instance-id)\
[EventName](#event-name)\
[EventWideName](#event-wide-name)\
[ProcessId](#process-id)\
[ProcessorIndex](#processor-index)\
[ThreadId](#thread-id)\
[TickFrequency](#tick-frequency)\
[Timestamp](#timestamp)

## <a name="event"></a><a name="entity"></a> イベント

```cpp
Event(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
任意のイベント。

## <a name="data"></a><a name="data"></a> Data

```cpp
const void* Data() const;
```

### <a name="return-value"></a>戻り値

このイベントに含まれる追加データへのポインター。 このフィールドを解釈する方法の詳細については、[EVENT_DATA](../c-event-data-types/event-data-struct.md) に関する記事を参照してください。

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

[EventId](#event-id) によって示されるイベントの名前が含まれるワイド文字列。

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

## <a name="timestamp"></a><a name="timestamp"></a> Timestamp

```cpp
const long long& Timestamp() const;
```

### <a name="return-value"></a>戻り値

イベントがアクティビティである場合、この関数からは、アクティビティの開始時にキャプチャされたティック値が返されます。 簡易イベントの場合は、この関数からは、イベントが発生したときにキャプチャされたティック値が返されます。

::: moniker-end
