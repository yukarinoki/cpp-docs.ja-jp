---
title: を使用します。
description: C++ ビルド インサイト SDK オントレースインフォファンク タイプ定義のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnTraceInfoFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b987d4db9852c2e52c148bb91015ad414c04d41b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329020"
---
# <a name="ontraceinfofunc-typedef"></a>を使用します。

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

typedef は`OnTraceInfoFunc`[、ANALYSIS_CALLBACKS](analysis-callbacks-struct.md)および[RELOG_CALLBACKS](relog-callbacks-struct.md)構造体で使用される関数シグネチャの 1 つです。

## <a name="syntax"></a>構文

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnTraceInfoFunc)(
    const TRACE_INFO_DATA*          traceInfo,
    void*                           callbackContext);
```

### <a name="parameters"></a>パラメーター

*トレース情報*\
現在分析または再ログされているトレースに関する情報を含む[TRACE_INFO_DATA](../c-event-data-types/trace-info-data-struct.md)オブジェクト。

*コールバックコンテキスト*\
このコールバックに設定されたコンテキスト値は[、ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md)または RELOG_DESCRIPTOR で行[われます](relog-descriptor-struct.md)。

### <a name="return-value"></a>戻り値

次に起こる処理を制御する[CALLBACK_CODE](callback-code-enum.md)値。

::: moniker-end
