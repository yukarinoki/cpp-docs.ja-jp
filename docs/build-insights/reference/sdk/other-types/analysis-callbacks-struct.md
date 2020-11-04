---
title: ANALYSIS_CALLBACKS 構造体
description: C++ Build Insights SDK ANALYSIS_CALLBACKS 構造体のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3fae97370ff9366ffc2fbd8d046a73c30125e554
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919931"
---
# <a name="analysis_callbacks-structure"></a>ANALYSIS_CALLBACKS 構造体

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`ANALYSIS_CALLBACKS` 構造体は、[ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) または [RELOG_DESCRIPTOR](relog-descriptor-struct.md) オブジェクトを初期化するときに使用され、 Event Tracing for Windows (ETW) トレースの分析または再ログ中に呼び出す関数を指定します。

## <a name="syntax"></a>構文

```cpp
typedef struct ANALYSIS_CALLBACKS_TAG
{
    OnAnalysisEventFunc     OnStartActivity;
    OnAnalysisEventFunc     OnStopActivity;
    OnAnalysisEventFunc     OnSimpleEvent;
    OnTraceInfoFunc         OnTraceInfo;
    OnBeginEndPassFunc      OnBeginAnalysis;
    OnBeginEndPassFunc      OnEndAnalysis;
    OnBeginEndPassFunc      OnBeginAnalysisPass;
    OnBeginEndPassFunc      OnEndAnalysisPass;
} ANALYSIS_CALLBACKS;
```

## <a name="members"></a>メンバー

| 名前 | [説明] |
|--|--|
| `OnStartActivity` | アクティビティの開始イベントを処理するために呼び出されます。 |
| `OnStopActivity` | アクティビティの停止イベントを処理するために呼び出されます。 |
| `OnSimpleEvent` | 簡易イベントを処理するために呼び出されます。 |
| `OnTraceInfo` | 分析セッションの場合、各分析パスの開始時に呼び出されます。 再ログ セッションの場合、各分析パスの開始時に呼び出され、再ログ パスの開始時に再度呼び出されます。 この関数は、OnBeginAnalysisPass が呼び出された後にのみ呼び出されます。 |
| `OnBeginAnalysis` | 分析セッションの場合、分析パスが開始される前に呼び出されます。 再ログ セッションの場合、分析フェーズが開始される前に 2 回 (再ログ セッションの開始を通知するために 1 回、分析フェーズの開始を通知するためにもう 1 回) 呼び出されます。 |
| `OnEndAnalysis` | 分析セッションの場合、この関数は、すべての分析パスが終了した後に呼び出されます。 再ログ セッションの場合、この関数は、分析フェーズのすべての分析パスが終了したときに呼び出されます。 その後、再ログ パスが終了した後に再度呼び出されます。 |
| `OnBeginAnalysisPass` | 任意のイベントを処理する前に、分析パスまたは再ログ パスの開始時に呼び出されます。 |
| `OnEndAnalysisPass` | すべてのイベントを処理した後、分析パスまたは再ログ パスの終了時に呼び出されます。 |

## <a name="remarks"></a>注釈

再ログ セッションの分析フェーズは、再ログ セッションの一部と見なされ、複数の分析パスが含まれる場合があります。 このため、`OnBeginAnalysis` は、再ログ セッションの開始時に連続して 2 回呼び出されます。 `OnEndAnalysis` は、再ログ フェーズを開始する前に、分析フェーズの終了時に呼び出され、再ログ フェーズの終了時にもう 1 回呼び出されます。 再ログ フェーズには、常に単一の再ログ パスが含まれます。

アナライザーは、再ログ セッションの分析フェーズと再ログ フェーズの両方に含めることができます。 これらのアナライザーでは、OnBeginAnalysis と `OnEndAnalysis` の呼び出しペアを追跡することにより、現在進行中のフェーズを特定できます。 `OnEndAnalysis` 呼び出しのない 2 回の `OnBeginAnalysis` 呼び出しは、分析フェーズが進行中であることを意味します。 2 回の `OnBeginAnalysis` 呼び出しと 1 回の `OnEndAnalysis` 呼び出しは、再ログ フェーズが進行中であることを意味します。 2 回の OnBeginAnalysis 呼び出しと 2 回の `OnEndAnalysis` 呼び出しは、両方のフェーズが終了したことを意味します。

`ANALYSIS_CALLBACKS` 構造体のすべてのメンバーは、有効な関数を指す必要があります。 許容される関数シグネチャの詳細については、「[OnAnalysisEventFunc](on-analysis-event-func-typedef.md)」、「[OnTraceInfoFunc](on-trace-info-func-typedef.md)」、「[OnBeginEndPassFunc](on-begin-end-pass-func-typedef.md)」を参照してください。

::: moniker-end
