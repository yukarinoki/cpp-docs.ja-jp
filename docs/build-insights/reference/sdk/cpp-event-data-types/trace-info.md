---
title: クラス
description: C++ ビルド インサイト SDK トレース情報 クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TraceInfo
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 75d53937e3999f5692dee0ecf419e0ce5f49a274
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324171"
---
# <a name="traceinfo-class"></a>クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`TraceInfo`クラスは、分析または再ログに記録されるトレースに関する有用なプロパティにアクセスするために使用されます。

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

`StartTimestamp` from`StopTimestamp`を減算して、トレース全体で経過したティック数を取得します。 結果`TickFrequency`の値を時間単位に変換するために使用します。 ティックを時間に変換する例については、「 [EVENT_DATA](../c-event-data-types/event-data-struct.md)」 を参照してください。

自分でティックを変換しない場合、`TraceInfo`クラスはナノ秒単位でトレース期間を返すメンバー関数を提供します。 標準の C++`chrono`ライブラリを使用して、この値を他の時間単位に変換します。

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

[トレース情報](#trace-info)

### <a name="functions"></a>関数

[期間](#duration)
[論理プロセッサカウント](#logical-processor-count)
[開始タイムスタンプ](#start-timestamp)
[ストップタイムスタンプ](#stop-timestamp)
[ティック周波数](#tick-frequency)

## <a name="duration"></a><a name="duration"></a>期間

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>戻り値

アクティビティの時間 (ナノ秒単位)。

## <a name="logicalprocessorcount"></a><a name="logical-processor-count"></a>論理プロセッサ数

```cpp
const unsigned long& LogicalProcessorCount() const;
```

### <a name="return-value"></a>戻り値

トレースが収集されたコンピューター上の論理プロセッサの数。

## <a name="starttimestamp"></a><a name="start-timestamp"></a>スタートタイムスタンプ

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>戻り値

トレースの開始時にキャプチャされたティック値。

## <a name="stoptimestamp"></a><a name="stop-timestamp"></a>ストップタイムスタンプ

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>戻り値

トレースが停止された時点でキャプチャされたティック値。

## <a name="tickfrequency"></a><a name="tick-frequency"></a>ティック周波数

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>戻り値

ティック単位で測定された期間を評価するときに使用する 1 秒あたりのティック数。

## <a name="traceinfo"></a><a name="trace-info"></a>トレース情報

```cpp
TraceInfo(const TRACE_INFO_DATA& data);
```

### <a name="parameters"></a>パラメーター

*データ*\
トレースに関する情報を含むデータ。

::: moniker-end
