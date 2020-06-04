---
title: TRACING_SESSION_STATISTICS構造
description: C++ ビルド インサイト SDK TRACING_SESSION_OPTIONS構造体の参照。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_STATISTICS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 96cff3a231fd515ec1c52a048b8350a63ba46a39
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323375"
---
# <a name="tracing_session_statistics-structure"></a>TRACING_SESSION_STATISTICS構造

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`TRACING_SESSION_STATISTICS`構造体は、収集されたトレースに関する統計を記述します。 トレース セッションを停止するときに、そのフィールドが設定されます。

## <a name="syntax"></a>構文

```cpp
typedef struct TRACING_SESSION_STATISTICS_TAG
{
    unsigned long MSVCEventsLost;
    unsigned long MSVCBuffersLost;
    unsigned long SystemEventsLost;
    unsigned long SystemBuffersLost;

} TRACING_SESSION_STATISTICS;
```

## <a name="members"></a>メンバー

|  |  |
|--|--|
| `MSVCEventsLost` | ドロップされた MSVC イベントの数。 |
| `MSVCBuffersLost` | ドロップされた MSVC イベント・バッファーの数。 |
| `SystemEventsLost` | ドロップされたシステム イベントの数。 |
| `SystemBuffersLost` | ドロップされたシステム イベント バッファの数。 |

## <a name="remarks"></a>解説

この構造体は、次の関数を呼び出すときに設定されます。

- [セッションを停止します。](../functions/stop-tracing-session.md)
- [ストップトレースセッションA](../functions/stop-tracing-session-a.md)
- [ストップトレースセッションW](../functions/stop-tracing-session-w.md)
- [トレースセッションを停止して分析する](../functions/stop-and-analyze-tracing-session.md)
- [トレースセッションを停止して分析する](../functions/stop-and-analyze-tracing-session-a.md)
- [停止してトレースセッションを分析します。](../functions/stop-and-analyze-tracing-session-w.md)
- [セッションを停止します。](../functions/stop-and-relog-tracing-session.md)
- [ストップアンドログトレーシングセッション](../functions/stop-and-relog-tracing-session-a.md)
- [停止アンドログトレーシングセッション](../functions/stop-and-relog-tracing-session-w.md)

::: moniker-end
