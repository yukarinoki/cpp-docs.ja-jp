---
title: TraceInfo クラス
description: C++ Build Insights SDK の TraceInfo クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TraceInfo
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b772cc13981720c73238e56a561ca92144775cb4
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922916"
---
# <a name="traceinfo-class"></a>TraceInfo クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`TraceInfo` クラスは、分析または再ログ記録の対象のトレースに関する有用なプロパティにアクセスするために使用されます。

## <a name="syntax"></a>構文

```cpp
class TraceInfo
{
public:
    TraceInfo(const TRACE_INFO_DATA& data);

    const unsigned long& LogicalProcessorCount() const;

    const long long& TickFrequency() const;
    const long long& StartTimestamp() const;
    const long long& StopTimestamp() const;

    std::chrono::nanoseconds Duration() const;
};
```

## <a name="remarks"></a>解説

トレース全体で経過したティック数を得るには、`StopTimestamp` から `StartTimestamp` を減算します。 得られた結果を時間単位に変換するには `TickFrequency` を使用します。 ティック数を時間に変換する例については、[EVENT_DATA](../c-event-data-types/event-data-struct.md)に関する記事を参照してください。

ティック数を自分で変換したくない場合は、`TraceInfo` クラスで、トレース時間をナノ秒単位で返すメンバー関数が提供されています。 この値を他の時間単位に変換するには、C++ の標準 `chrono` ライブラリを使用します。

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

[TraceInfo](#trace-info)

### <a name="functions"></a>機能

[Duration](#duration)
[LogicalProcessorCount](#logical-processor-count)
[StartTimestamp](#start-timestamp)
[StopTimestamp](#stop-timestamp)
[TickFrequency](#tick-frequency)

## <a name="duration"></a><a name="duration"></a> Duration

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>戻り値

アクティビティの継続時間 (ナノ秒単位)。

## <a name="logicalprocessorcount"></a><a name="logical-processor-count"></a> LogicalProcessorCount

```cpp
const unsigned long& LogicalProcessorCount() const;
```

### <a name="return-value"></a>戻り値

トレースが収集されたコンピューター上の論理プロセッサの数。

## <a name="starttimestamp"></a><a name="start-timestamp"></a> StartTimestamp

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>戻り値

トレースが開始された時刻にキャプチャされたティック値。

## <a name="stoptimestamp"></a><a name="stop-timestamp"></a> StopTimestamp

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>戻り値

トレースが停止された時刻にキャプチャされたティック値。

## <a name="tickfrequency"></a><a name="tick-frequency"></a> TickFrequency

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>戻り値

ティック単位で計測された期間を評価するときに使用する、1 秒あたりのティック数。

## <a name="traceinfo"></a><a name="trace-info"></a> TraceInfo

```cpp
TraceInfo(const TRACE_INFO_DATA& data);
```

### <a name="parameters"></a>パラメーター

*data*\
トレースに関する情報が格納されているデータ。

::: moniker-end
