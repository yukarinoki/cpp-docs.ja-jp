---
title: 定数をTRACING_SESSION_SYSTEM_EVENT_FLAGSする
description: C++ ビルド インサイト SDK TRACING_SESSION_SYSTEM_EVENT_FLAGS定数のリファレンスです。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 264d697cc905eb6b44c8ec7de835a552976f0eb8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323271"
---
# <a name="tracing_session_system_event_flags-constants"></a>定数をTRACING_SESSION_SYSTEM_EVENT_FLAGSする

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`TRACING_SESSION_SYSTEM_EVENT_FLAGS`定数は、トレース中に収集するシステム イベントを記述するために使用されます。 [TRACING_SESSION_OPTIONS](tracing-session-options-struct.md)構造体の`SystemEventFlags`フィールドを初期化するために使用します。

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

| 名前 | このフラグによって有効になるイベント |
|--|--|
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CONTEXT` | このフラグは、明示的に指定されていない場合でも、C++ ビルドインサイト SDK によって既定でアクティブ化されます。 これにより、C++ ビルド インサイトで必要な基本的なシステム イベントが正しく機能します。 このフラグによって有効になるイベントは、プロセス、スレッド、およびイメージの読み込みに関する情報を提供します。 これらのイベントを無効にすることはできません。 |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | CPU サンプル |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_ALL` | このフラグは、すべてのシステム イベントをオンにします。 |

::: moniker-end
