---
title: イベント クラス
description: C++ ビルド インサイト SDK イベント クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Event
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 25d58f642a1c314e48ddff62553394bcc65e4717
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324964"
---
# <a name="event-class"></a>イベント クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`Event`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 任意のイベントに一致させるために使用します。

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

[イベント](#entity)

### <a name="functions"></a>関数

[データ](#data)
[イベント ID](#event-id)\
[イベントインスタンスId](#event-instance-id)\
[Eventname](#event-name)\
[イベントワイドネーム](#event-wide-name)\
[プロセスId](#process-id)\
[プロセッサインデックス](#processor-index)\
[Threadid](#thread-id)\
[ティック周波数](#tick-frequency)\
[Timestamp](#timestamp)

## <a name="event"></a><a name="entity"></a> イベント

```cpp
Event(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
任意のイベント。

## <a name="data"></a><a name="data"></a>データ

```cpp
const void* Data() const;
```

### <a name="return-value"></a>戻り値

このイベントに含まれる追加データへのポインター。 このフィールドの解釈方法の詳細については[、「EVENT_DATA」](../c-event-data-types/event-data-struct.md)を参照してください。

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

[で](#event-id)識別されるイベントの名前を含むワイド文字列。

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

## <a name="timestamp"></a><a name="timestamp"></a>タイムスタンプ

```cpp
const long long& Timestamp() const;
```

### <a name="return-value"></a>戻り値

イベントがアクティビティの場合、この関数はアクティビティの開始時にキャプチャされたティック値を返します。 単純なイベントの場合、この関数はイベント発生時にキャプチャされたティック値を返します。

::: moniker-end
