---
title: ANALYSIS_CALLBACKS構造
description: C++ ビルド インサイト SDK ANALYSIS_CALLBACKS構造参照。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3c6de999b19657f999f884075ee53e21a4d2f2b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323506"
---
# <a name="analysis_callbacks-structure"></a>ANALYSIS_CALLBACKS構造

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`ANALYSIS_CALLBACKS`構造体は[、ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md)または[RELOG_DESCRIPTOR](relog-descriptor-struct.md)オブジェクトを初期化するときに使用されます。 Windows イベント トレース (ETW) トレースの分析または再ロギング中に呼び出す関数を指定します。

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

|  |  |
|--|--|
| `OnStartActivity` | アクティビティ開始イベントを処理するために呼び出されます。 |
| `OnStopActivity` | アクティビティ停止イベントを処理するために呼び出されます。 |
| `OnSimpleEvent` | 単純なイベントを処理するために呼び出されます。 |
| `OnTraceInfo` | 各分析パスの先頭で呼び出される分析セッションの場合。 各分析パスの先頭で呼び出され、再ロギング パスの先頭で再び呼び出される再ロギング セッションの場合。 この関数は、OnBeginAnalysisPass が呼び出された後にのみ呼び出されます。 |
| `OnBeginAnalysis` | 分析セッションの場合、解析パスが開始される前に呼び出されます。 再ロギング セッションの場合、分析フェーズが開始される前に 2 回呼び出されます。 |
| `OnEndAnalysis` | 分析セッションの場合、この関数は、すべての分析パスが終了した後に呼び出されます。 再ロギング・セッションの場合、この関数は分析フェーズのすべての分析パスが終了したときに呼び出されます。 その後、再ログパスが終了した後に再び呼び出されます。 |
| `OnBeginAnalysisPass` | イベントを処理する前に、分析パスまたは再ロギング パスを開始するときに呼び出されます。 |
| `OnEndAnalysisPass` | すべてのイベントを処理した後、分析パスまたは再ロギング パスを終了するときに呼び出されます。 |

## <a name="remarks"></a>解説

再ロギング セッションの分析フェーズは、再ロギング セッションの一部と見なされ、複数の分析パスを含めることができます。 このため、`OnBeginAnalysis`再ロギング セッションの開始時に 2 回連続して呼び出されます。 `OnEndAnalysis`は、再ロギングフェーズを開始する前に、分析フェーズの最後に呼び出され、再ロギングフェーズの最後にもう一度呼び出されます。 再ログフェーズには、常に 1 つの再ロギング パスが含まれます。

アナライザーは、再ロギング セッションの分析フェーズと再ロギング フェーズの両方に参加する可能性があります。 これらのアナライザーは、OnBeginAnalysis と呼び出し`OnEndAnalysis`のペアを追跡することによって、現在進行中のフェーズを特定できます。 コール`OnBeginAnalysis`を行わない`OnEndAnalysis`2 つのコールは、分析フェーズが進行中であることを意味します。 2`OnBeginAnalysis`つの呼`OnEndAnalysis`び出しと 1 つの呼び出しは、再ログフェーズが進行中であることを意味します。 2 つの OnBeginAnalysis と 2 つの`OnEndAnalysis`呼び出しは、両方のフェーズが終了した場合を意味します。

構造体のすべてのメンバーは`ANALYSIS_CALLBACKS`、有効な関数を指している必要があります。 受け入れられた関数シグネチャの詳細については、「を参照してください[。](on-analysis-event-func-typedef.md) [OnTraceInfoFunc](on-trace-info-func-typedef.md) [OnBeginEndPassFunc](on-begin-end-pass-func-typedef.md)

::: moniker-end
