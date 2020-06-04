---
title: RELOG_CALLBACKS構造
description: C++ ビルド インサイト SDK RELOG_CALLBACKS構造参照。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 60e7db81a48731090a23b82332704a79a51e97df
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328974"
---
# <a name="relog_callbacks-structure"></a>RELOG_CALLBACKS構造

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`RELOG_CALLBACKS`構造体は[、RELOG_DESCRIPTOR](relog-descriptor-struct.md)オブジェクトを初期化するときに使用されます。 Windows イベント トレース (ETW) トレースの再ロギング中に呼び出す関数を指定します。

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

|  |  |
|--|--|
| `OnStartActivity` | アクティビティ開始イベントを処理するために呼び出されます。 |
| `OnStopActivity` | アクティビティ停止イベントを処理するために呼び出されます。 |
| `OnSimpleEvent` | 単純なイベントを処理するために呼び出されます。 |
| `OnTraceInfo` | 再ロギングパスの先頭で一度呼び出され`OnBeginReloggingPass`、後に呼び出されます。 |
| `OnBeginRelogging` | 再ログのパスが開始される前に、再ロギング セッションを開始するときに呼び出されます。 |
| `OnEndRelogging` | 再ログパスが終了した後、再ロギング セッションを終了するときに呼び出されます。 |
| `OnBeginReloggingPass` | イベントを処理する前に、再ロギング パスを開始するときに呼び出されます。 |
| `OnEndReloggingPass` | すべてのイベントを処理した後、再ログ パスを終了するときに呼び出されます。 |

## <a name="remarks"></a>解説

構造体のすべてのメンバーは`RELOG_CALLBACKS`、有効な関数を指している必要があります。 受け入れられた関数シグネチャの詳細については[、「OnRelogEventFunc](on-relog-event-func-typedef.md)、[オントレースインフォファンク](on-trace-info-func-typedef.md)、および[オントレースエンドパスファンク](on-begin-end-pass-func-typedef.md)」を参照してください。

::: moniker-end
