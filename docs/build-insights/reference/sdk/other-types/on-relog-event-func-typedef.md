---
title: OnRelogEventFunc typedef
description: C++ Build Insights SDK の OnRelogEventFunc typedef のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnRelogEventFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ed639ab59b900f97d29dc69240e45b2f52f2f3b3
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919749"
---
# <a name="onrelogeventfunc-typedef"></a>OnRelogEventFunc typedef

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`OnRelogEventFunc` typedef は、[RELOG_CALLBACKS](relog-callbacks-struct.md) 構造体で使用される関数シグネチャの 1 つです。

## <a name="syntax"></a>構文

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnRelogEventFunc)(
    const EVENT_COLLECTION_DATA*    eventStack,
    const void*                     relogSession,
    void*                           callbackContext);
```

### <a name="parameters"></a>パラメーター

*eventStack*\
現在のイベントのイベント スタック。 イベント スタックの詳細については、[イベント](../event-table.md)に関するページを参照してください。

*relogSession*\
[InjectEvent](../functions/inject-event.md) を呼び出すときに使用する再ログ記録セッション ポインター。

*callbackContext*\
[RELOG_DESCRIPTOR](analysis-descriptor-struct.md) でこのコールバックに対して設定されたコンテキスト値。

### <a name="return-value"></a>戻り値

次に実行される必要があることを制御する [CALLBACK_CODE](callback-code-enum.md) 値。

::: moniker-end
