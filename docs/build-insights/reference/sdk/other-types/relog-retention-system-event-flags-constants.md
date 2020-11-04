---
title: RELOG_RETENTION_SYSTEM_EVENT_FLAGS 定数
description: C++ Build Insights SDK RELOG_RETENTION_SYSTEM_EVENT_FLAGS 定数のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_RETENTION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e0144835568dab12c8593fe8fbfa820f6cde7647
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919733"
---
# <a name="relog_retention_system_event_flags-constants"></a>RELOG_RETENTION_SYSTEM_EVENT_FLAGS 定数

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`RELOG_RETENTION_SYSTEM_EVENT_FLAGS` 定数は、再ログ記録トレースに保持するシステム イベントを表すために使用されます。 これを使用し、[RELOG_DESCRIPTOR](relog-descriptor-struct.md) 構造の `SystemEventsRetentionFlags` フィールドを初期化します。

## <a name="syntax"></a>構文

```cpp
static const unsigned long long
    RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES = 0x1ULL;

static const unsigned long long
    RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL         = 0xFFFFFFFFFFFFFFFFULL;
```

## <a name="members"></a>メンバー

| 名前 | [説明] |
|--|--|
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | 再ログ記録トレースに CPU サンプル システム イベントを保持します。 |
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL` | 再ログ記録トレースにすべてのシステム イベントを保持します。 |

## <a name="remarks"></a>注釈

::: moniker-end
