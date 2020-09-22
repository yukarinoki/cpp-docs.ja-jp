---
title: TRACE_INFO_DATA 構造体
description: C++ Build Insights SDK の TRACE_INFO_DATA 構造体のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACE_INFO_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 38683ff2c5c5165b5fe2a1969ccf80fbfca3693f
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040458"
---
# <a name="trace_info_data-structure"></a>TRACE_INFO_DATA 構造体

::: moniker range="<=vs-2015"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=vs-2017"

`TRACE_INFO_DATA` 構造体は、分析または再ログ記録されているトレースを説明するものです。

## <a name="syntax"></a>構文

```cpp
typedef struct TRACE_INFO_DATA_TAG
{
    unsigned long           LogicalProcessorCount;
    long long               TickFrequency;
    long long               StartTimestamp;
    long long               StopTimestamp;

} TRACE_INFO_DATA;
```

## <a name="members"></a>メンバー

| 名前 | [説明] |
|--|--|
| `LogicalProcessorCount` | トレースが収集されたコンピューター上の論理プロセッサの数。 |
| `TickFrequency` | ティック単位で計測された期間を評価するときに使用する、1 秒あたりのティック数。 |
| `StartTimestamp` | このフィールドは、トレースの開始時にキャプチャされたティック値に設定されます。 |
| `StopTimestamp` | このフィールドは、トレースの停止時にキャプチャされたティック値に設定されます。 |

## <a name="remarks"></a>注釈

トレース全体で経過したティック数を得るには、`StopTimestamp` から `StartTimestamp` を差し引きます。 得られた結果を時間単位に変換するには `TickFrequency` を使用します。 ティックを時間単位に変換する例については、[EVENT_DATA](event-data-struct.md) に関するページを参照してください。

::: moniker-end
