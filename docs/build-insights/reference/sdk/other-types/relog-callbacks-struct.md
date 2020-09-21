---
title: RELOG_CALLBACKS 構造体
description: C++ Build Insights SDK RELOG_CALLBACKS 構造体のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 55f63b05691e3d729ee42ed21049669b94053559
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041433"
---
# <a name="relog_callbacks-structure"></a>RELOG_CALLBACKS 構造体

::: moniker range="<=vs-2015"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=vs-2017"

`RELOG_CALLBACKS` 構造体は、[RELOG_DESCRIPTOR](relog-descriptor-struct.md) オブジェクトを初期化するときに使用されます。 Event Tracing for Windows (ETW) トレースの再ログ記録中に呼び出す関数を指定します。

## <a name="syntax"></a>構文

```cpp
typedef struct RELOG_CALLBACKS_TAG
{
    OnRelogEventFunc        OnStartActivity;
    OnRelogEventFunc        OnStopActivity;
    OnRelogEventFunc        OnSimpleEvent;
    OnTraceInfoFunc         OnTraceInfo;
    OnBeginEndPassFunc      OnBeginRelogging;
    OnBeginEndPassFunc      OnEndRelogging;
    OnBeginEndPassFunc      OnBeginReloggingPass;
    OnBeginEndPassFunc      OnEndReloggingPass;
} RELOG_CALLBACKS;
```

## <a name="members"></a>メンバー

| 名前 | [説明] |
|--|--|
| `OnStartActivity` | アクティビティの開始イベントを処理するために呼び出されます。 |
| `OnStopActivity` | アクティビティの停止イベントを処理するために呼び出されます。 |
| `OnSimpleEvent` | 簡易イベントを処理するために呼び出されます。 |
| `OnTraceInfo` | `OnBeginReloggingPass` が呼び出された後に、再ログ記録パスの先頭で 1 回呼び出されます。 |
| `OnBeginRelogging` | 再ログ記録セッションの開始時、再ログ記録パスの開始前に呼び出されます。 |
| `OnEndRelogging` | 再ログ記録セッションの終了時、再ログ記録パスの終了後に呼び出されます。 |
| `OnBeginReloggingPass` | 再ログ記録パスの開始時、イベントの処理前に呼び出されます。 |
| `OnEndReloggingPass` | 再ログ記録パスの終了時、全イベントの処理後に呼び出されます。 |

## <a name="remarks"></a>注釈

`RELOG_CALLBACKS` 構造体のすべてのメンバーは、有効な関数を指す必要があります。 許容される関数シグネチャの詳細については、[OnRelogEventFunc](on-relog-event-func-typedef.md)、[OnTraceInfoFunc](on-trace-info-func-typedef.md)、[OnBeginEndPassFunc](on-begin-end-pass-func-typedef.md) に関するページを参照してください。

::: moniker-end
