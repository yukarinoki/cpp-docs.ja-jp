---
title: OnTraceInfoFunc typedef
description: C++ Build Insights SDK の OnTraceInfoFunc typedef のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnTraceInfoFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4aaa865fd0f907a67179e7ee967f23a9827b0026
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922471"
---
# <a name="ontraceinfofunc-typedef"></a>OnTraceInfoFunc typedef

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`OnTraceInfoFunc` typedef は、[ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) 構造体と [RELOG_CALLBACKS](relog-callbacks-struct.md) 構造体で使用される関数シグネチャの 1 つです。

## <a name="syntax"></a>構文

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnTraceInfoFunc)(
    const TRACE_INFO_DATA*          traceInfo,
    void*                           callbackContext);
```

### <a name="parameters"></a>パラメーター

*traceInfo*\
現在分析または再ログ記録が行われているトレースに関する情報が格納される [TRACE_INFO_DATA](../c-event-data-types/trace-info-data-struct.md) オブジェクト。

*callbackContext*\
[ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) または [RELOG_DESCRIPTOR](relog-descriptor-struct.md) でこのコールバックに対して設定されたコンテキスト値。

### <a name="return-value"></a>戻り値

次に実行される必要があることを制御する [CALLBACK_CODE](callback-code-enum.md) 値。

::: moniker-end
