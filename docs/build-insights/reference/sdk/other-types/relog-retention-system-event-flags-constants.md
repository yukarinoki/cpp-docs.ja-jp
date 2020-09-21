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
ms.openlocfilehash: 5444c1a6b8799b1de8eea228211a5f2d6de638f8
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041407"
---
# <a name="relog_retention_system_event_flags-constants"></a>RELOG_RETENTION_SYSTEM_EVENT_FLAGS 定数

::: moniker range="<=vs-2015"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=vs-2017"

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
