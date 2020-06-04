---
title: 定数をRELOG_RETENTION_SYSTEM_EVENT_FLAGSする
description: C++ ビルドインサイト SDK RELOG_RETENTION_SYSTEM_EVENT_FLAGS定数のリファレンスです。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_RETENTION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7110f809a819357b31951c203c1fa6ac9fb9f42e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323471"
---
# <a name="relog_retention_system_event_flags-constants"></a>定数をRELOG_RETENTION_SYSTEM_EVENT_FLAGSする

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

定数`RELOG_RETENTION_SYSTEM_EVENT_FLAGS`は、ログに記録されたトレースに保持するシステム イベントを記述するために使用されます。 これらのフィールドを使用して[、RELOG_DESCRIPTOR](relog-descriptor-struct.md)構造体の`SystemEventsRetentionFlags`フィールドを初期化します。

## <a name="syntax"></a>構文

```cpp
static const unsigned long long
    RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES = 0x1ULL;

static const unsigned long long
    RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL         = 0xFFFFFFFFFFFFFFFFULL;
```

## <a name="members"></a>メンバー

|  |  |
|--|--|
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | 再ログされたトレースで CPU サンプル システム イベントを保持します。 |
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL` | すべてのシステム イベントを再ログトレースに保持します。 |

## <a name="remarks"></a>解説

::: moniker-end
