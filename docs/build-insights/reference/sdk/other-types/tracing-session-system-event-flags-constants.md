---
title: TRACING_SESSION_SYSTEM_EVENT_FLAGS 定数
description: C++ Build Insights SDK の TRACING_SESSION_SYSTEM_EVENT_FLAGS 定数のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 346c955355ffbc6c062a34bf928f16ccd3940154
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922373"
---
# <a name="tracing_session_system_event_flags-constants"></a>TRACING_SESSION_SYSTEM_EVENT_FLAGS 定数

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`TRACING_SESSION_SYSTEM_EVENT_FLAGS` 定数は、トレース中に収集するシステム イベントを表すために使用されます。 これらを使用して、[TRACING_SESSION_OPTIONS](tracing-session-options-struct.md) 構造体の `SystemEventFlags` フィールドを初期化します。

## <a name="syntax"></a>構文

```cpp
static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_CONTEXT      = 0x1ULL;

static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES  = 0x2ULL;

static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_ALL          = 0xFFFFFFFFFFFFFFFFULL;
```

## <a name="members"></a>メンバー

| 名前 | このフラグによって有効にされるイベント |
|--|--|
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CONTEXT` | このフラグは、明示的に指定されていなくても、C++ Build Insights SDK によって既定でアクティブにされます。 これにより、C++ Build Insights が正常に機能するために必要な基本的なシステム イベントが有効になります。 このフラグによって有効にされるイベントにより、プロセス、スレッド、およびイメージの読み込みに関する情報が提供されます。 これらのイベントを無効にすることはできません。 |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | CPU サンプル |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_ALL` | このフラグによって、すべてのシステム イベントがオンになります。 |

::: moniker-end
