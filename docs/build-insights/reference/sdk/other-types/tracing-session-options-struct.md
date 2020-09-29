---
title: TRACING_SESSION_OPTIONS 構造体
description: C++ Build Insights SDK の TRACING_SESSION_OPTIONS 構造体のリファレンスについて説明します。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_OPTIONS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f7c53abc14c4862ccb73f94acd2e325eb3d4a6fa
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742776"
---
# <a name="tracing_session_options-structure"></a>TRACING_SESSION_OPTIONS 構造体

::: moniker range="<=vs-2015"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=vs-2017"

`TRACING_SESSION_OPTIONS` 構造体は、[ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) または [RELOG_DESCRIPTOR](relog-descriptor-struct.md) 構造体を初期化するときに使用され、 トレースの収集中にキャプチャするイベントを表します。

## <a name="syntax"></a>構文

```cpp
typedef struct TRACING_SESSION_OPTIONS_TAG
{
    unsigned long long SystemEventFlags;
    unsigned long long MsvcEventFlags;

} TRACING_SESSION_OPTIONS;
```

## <a name="members"></a>メンバー

| 名前 | [説明] |
|--|--|
| `SystemEventFlags` | キャプチャするシステム イベントを表すビットマスク。 詳細については、[TRACING_SESSION_SYSTEM_EVENT_FLAGS](tracing-session-system-event-flags-constants.md) に関するページを参照してください。 |
| `MsvcEventFlags` | キャプチャする MSVC イベントを表すビットマスク。 詳細については、[TRACING_SESSION_MSVC_EVENT_FLAGS](tracing-session-msvc-event-flags-constants.md) に関するページを参照してください。 |

::: moniker-end
