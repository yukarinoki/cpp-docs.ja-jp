---
title: TRACING_SESSION_OPTIONS 構造体
description: C++ Build Insights SDK の TRACING_SESSION_OPTIONS 構造体のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_OPTIONS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c8a248d884b5232fbc5332db1a68533220ef2fab
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041264"
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
