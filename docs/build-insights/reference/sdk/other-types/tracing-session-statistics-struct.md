---
title: TRACING_SESSION_STATISTICS 構造体
description: C++ Build Insights SDK の TRACING_SESSION_STATISTICS 構造体のリファレンスについて説明します。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_STATISTICS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c1db302d9e816591624f0fc63633351d32684097
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742763"
---
# <a name="tracing_session_statistics-structure"></a>TRACING_SESSION_STATISTICS 構造体

::: moniker range="<=vs-2015"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=vs-2017"

`TRACING_SESSION_STATISTICS` 構造体は、収集されたトレースでの統計を表します。 トレース セッションの終了時にそのフィールドが設定されます。

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

| 名前 | [説明] |
|--|--|
| `MSVCEventsLost` | 削除された MSVC イベントの数。 |
| `MSVCBuffersLost` | 削除された MSVC イベント バッファーの数。 |
| `SystemEventsLost` | 削除されたシステム イベントの数。 |
| `SystemBuffersLost` | 削除されたシステム イベント バッファーの数。 |

## <a name="remarks"></a>注釈

この構造体には、次の関数の呼び出し時にデータが入力されます。

- [StopTracingSession](../functions/stop-tracing-session.md)
- [StopTracingSessionA](../functions/stop-tracing-session-a.md)
- [StopTracingSessionW](../functions/stop-tracing-session-w.md)
- [StopAndAnalyzeTracingSession](../functions/stop-and-analyze-tracing-session.md)
- [StopAndAnalyzeTracingSessionA](../functions/stop-and-analyze-tracing-session-a.md)
- [StopAndAnalyzeTracingSessionW](../functions/stop-and-analyze-tracing-session-w.md)
- [StopAndRelogTracingSession](../functions/stop-and-relog-tracing-session.md)
- [StopAndRelogTracingSessionA](../functions/stop-and-relog-tracing-session-a.md)
- [StopAndRelogTracingSessionW](../functions/stop-and-relog-tracing-session-w.md)

::: moniker-end
