---
title: OnAnalysisEventFunc typedef
description: C++ Build Insights SDK の OnAnalysisEventFunc typedef のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnAnalysisEventFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 069c89a01fa466e86986a821e5dd9d0b09f5c81a
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919788"
---
# <a name="onanalysiseventfunc-typedef"></a>OnAnalysisEventFunc typedef

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`OnAnalysisEventFunc` typedef は、[ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) 構造体で使用される関数シグネチャの 1 つです。

## <a name="syntax"></a>構文

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnAnalysisEventFunc)(
    const EVENT_COLLECTION_DATA*    eventStack,
    void*                           callbackContext);
```

### <a name="parameters"></a>パラメーター

*eventStack*\
現在のイベントのイベント スタック。 イベント スタックの詳細については、[イベント](../event-table.md)に関するページを参照してください。

*callbackContext*\
[ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) または [RELOG_DESCRIPTOR](relog-descriptor-struct.md) でこのコールバックに対して設定されたコンテキスト値。

### <a name="return-value"></a>戻り値

次に実行される必要があることを制御する [CALLBACK_CODE](callback-code-enum.md) 値。

::: moniker-end
