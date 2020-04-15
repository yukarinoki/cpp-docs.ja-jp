---
title: TRACING_SESSION_OPTIONS構造
description: C++ ビルド インサイト SDK TRACING_SESSION_OPTIONS構造体の参照。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_OPTIONS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5aeb6299aea8dc0661b9469ee524e7aa4d010aca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323428"
---
# <a name="tracing_session_options-structure"></a>TRACING_SESSION_OPTIONS構造

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`TRACING_SESSION_OPTIONS`構造体は[、ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md)または[RELOG_DESCRIPTOR](relog-descriptor-struct.md)構造を初期化するときに使用されます。 トレースの収集中にキャプチャするイベントについて説明します。

## <a name="syntax"></a>構文

```cpp
typedef struct TRACING_SESSION_OPTIONS_TAG
{
    unsigned long long SystemEventFlags;
    unsigned long long MsvcEventFlags;

} TRACING_SESSION_OPTIONS;
```

## <a name="members"></a>メンバー

|  |  |
|--|--|
| `SystemEventFlags` | キャプチャするシステム イベントを記述するビットマスク。 詳細については[、「TRACING_SESSION_SYSTEM_EVENT_FLAGS」](tracing-session-system-event-flags-constants.md)を参照してください。 |
| `MsvcEventFlags` | キャプチャする MSVC イベントを記述するビットマスク。 詳細については、「 [TRACING_SESSION_MSVC_EVENT_FLAGS](tracing-session-msvc-event-flags-constants.md)」を参照してください。 |

::: moniker-end
