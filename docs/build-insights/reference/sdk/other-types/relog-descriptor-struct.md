---
title: RELOG_DESCRIPTOR 構造体
description: C++ Build Insights SDK の RELOG_DESCRIPTOR 構造体のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9b3c870998ce4f9ca55fb5bcc23ba66a1af46558
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922442"
---
# <a name="relog_descriptor-structure"></a>RELOG_DESCRIPTOR 構造体

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`RELOG_DESCRIPTOR` 構造体は、[RelogA](../functions/relog-a.md) および [RelogW](../functions/relog-w.md) 関数と共に使用されます。 ここでは、Windows イベント トレーシング (ETW) を再記録する方法について説明します。

## <a name="syntax"></a>構文

```cpp
typedef struct RELOG_DESCRIPTOR_TAG
{
    unsigned                NumberOfAnalysisPasses;
    ANALYSIS_CALLBACKS      AnalysisCallbacks;
    RELOG_CALLBACKS         RelogCallbacks;
    unsigned long long      SystemEventsRetentionFlags;
    void*                   AnalysisContext;
    void*                   RelogContext;
} RELOG_DESCRIPTOR;
```

## <a name="members"></a>メンバー

| 名前 | [説明] |
|--|--|
| `NumberOfAnalysisPasses` | 再記録セッションの分析フェーズ中に ETW トレースで実行される分析パスの数。 |
| `AnalysisCallbacks` | 再記録セッションの分析フェーズ中に呼び出す関数を指定する [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) オブジェクト。 |
| `RelogCallbacks` | 再記録セッションの再記録フェーズ中に呼び出す関数を指定する [RELOG_CALLBACKS](relog-callbacks-struct.md) オブジェクト。 |
| `SystemEventsRetentionFlags` | 再記録されたトレースに保持するシステム ETW イベントを指定する [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](relog-retention-system-event-flags-constants.md) ビットマスク。 |
| `AnalysisContext` | `AnalysisCallbacks` で指定されたすべてのコールバック関数に引数として渡されるユーザー指定のコンテキスト |
| `RelogContext` | `RelogCallbacks` で指定されたすべてのコールバック関数に引数として渡されるユーザー指定のコンテキスト |

## <a name="remarks"></a>注釈

再記録セッション中の ETW イベントの再記録は、`RelogCallbacks` で指定されたコールバック関数を介してユーザーによって制御されます。 ただし、CPU サンプルなどのシステム ETW イベントは、これらのコールバック関数に転送されません。 システム ETW イベントの再記録を制御するには、`SystemEventsRetentionFlags` フィールドを使用します。

`AnalysisCallbacks` および `RelogCallbacks` の構造体は、非メンバー関数へのポインターのみを受け入れます。 この制限は、オブジェクト ポインターに設定することによって回避できます。 このオブジェクト ポインターは、すべての非メンバー コールバック関数に引数として渡されます。 メンバー関数を非メンバー コールバック関数内から呼び出すには、このポインターを使用します。

再記録セッションの分析フェーズは、常に再記録フェーズの前に実行されます。

::: moniker-end
