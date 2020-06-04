---
title: イベントのイベントを処理する
description: C++ ビルド インサイト SDK OnRelogEventFunc タイプ定義のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnRelogEventFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2df8646d530c089b1239978d716b2b619a5b4b61
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329074"
---
# <a name="onrelogeventfunc-typedef"></a>イベントのイベントを処理する

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

typedef は`OnRelogEventFunc`[、RELOG_CALLBACKS](relog-callbacks-struct.md)構造体で使用される関数シグネチャの 1 つです。

## <a name="syntax"></a>構文

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnRelogEventFunc)(
    const EVENT_COLLECTION_DATA*    eventStack,
    const void*                     relogSession,
    void*                           callbackContext);
```

### <a name="parameters"></a>パラメーター

*イベントスタック*\
現在のイベントのイベント スタック。 イベント スタックの詳細については、「[イベント](../event-table.md)」を参照してください。

*セッションを再ログします。*\
[InjectEvent](../functions/inject-event.md)を呼び出すときに使用する再ロギング セッション ポインター。

*コールバックコンテキスト*\
このコールバックに設定されたコンテキスト値[は RELOG_DESCRIPTOR。](analysis-descriptor-struct.md)

### <a name="return-value"></a>戻り値

次に起こる処理を制御する[CALLBACK_CODE](callback-code-enum.md)値。

::: moniker-end
