---
title: TRACE_INFO_DATA構造
description: C++ ビルド インサイト SDK TRACE_INFO_DATA構造リファレンスです。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACE_INFO_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 70ae17a376f79cad7a669d81e482f551afd0ec62
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325279"
---
# <a name="trace_info_data-structure"></a>TRACE_INFO_DATA構造

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`TRACE_INFO_DATA`構造体は、分析または再ログに記録されるトレースを記述します。

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

|  |  |
|--|--|
| `LogicalProcessorCount` | トレースが収集されたコンピューター上の論理プロセッサの数。 |
| `TickFrequency` | ティック単位で測定された期間を評価するときに使用する 1 秒あたりのティック数。 |
| `StartTimestamp` | このフィールドは、トレースの開始時にキャプチャされたティック値に設定されます。 |
| `StopTimestamp` | このフィールドは、トレースが停止された時点でキャプチャされたティック値に設定されます。 |

## <a name="remarks"></a>解説

[`StartTimestamp`から`StopTimestamp`] を指定して、トレース全体で経過したティック数を取得します。 結果`TickFrequency`の値を時間単位に変換するために使用します。 ティックを時間単位に変換する例については[、「EVENT_DATA」](event-data-struct.md)を参照してください。

::: moniker-end
