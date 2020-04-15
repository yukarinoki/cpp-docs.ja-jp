---
title: RELOG_DESCRIPTOR構造
description: C++ ビルド インサイト SDK RELOG_DESCRIPTOR構造リファレンスです。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c3aee49fe9f609ca37082693ddcfd5e838cc96a1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328937"
---
# <a name="relog_descriptor-structure"></a>RELOG_DESCRIPTOR構造

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`RELOG_DESCRIPTOR`構造体は[、RelogA](../functions/relog-a.md)関数および[RelogW](../functions/relog-w.md)関数と共に使用されます。 Windows のイベント トレース (ETW) トレースを再ログする方法について説明します。

## <a name="syntax"></a>構文

```cpp
typedef struct RELOG_DESCRIPTOR_TAG
{
    unsigned                NumberOfAnalysisPasses;
    ANALYSIS_CALLBACKS      AnalysisCallbacks;
    RELOG_CALLBACKS         RelogCallbacks;
    unsigned long long      SystemEventsRetentionFlags;
    void*                   AnalysisContext;
    void*                   RelogContext;
} RELOG_DESCRIPTOR;
```

## <a name="members"></a>メンバー

|  |  |
|--|--|
| `NumberOfAnalysisPasses` | 再ロギング セッションの分析フェーズ中に ETW トレースで実行する必要がある分析パスの数。 |
| `AnalysisCallbacks` | 再ロギング セッションの分析フェーズ中に呼び出す関数を指定する[ANALYSIS_CALLBACKS](analysis-callbacks-struct.md)オブジェクト。 |
| `RelogCallbacks` | 再ロギング セッションの再ロギング フェーズ中に呼び出す関数を指定する[RELOG_CALLBACKS](relog-callbacks-struct.md)オブジェクト。 |
| `SystemEventsRetentionFlags` | ログに記録されたトレースに保持するシステム ETW イベントを指定する[RELOG_RETENTION_SYSTEM_EVENT_FLAGS](relog-retention-system-event-flags-constants.md)ビットマスク。 |
| `AnalysisContext` | で指定されたすべてのコールバック関数に引数として渡されるユーザー指定のコンテキスト`AnalysisCallbacks` |
| `RelogContext` | で指定されたすべてのコールバック関数に引数として渡されるユーザー指定のコンテキスト`RelogCallbacks` |

## <a name="remarks"></a>解説

再ロギング セッション中の ETW イベントの再ロギングは、 で`RelogCallbacks`指定されたコールバック関数を通じてユーザーによって制御されます。 ただし、CPU サンプルなどのシステム ETW イベントは、これらのコールバック関数には転送されません。 `SystemEventsRetentionFlags`このフィールドを使用して、システム ETW イベントの再ロギングを制御します。

および`AnalysisCallbacks``RelogCallbacks`構造体は、非メンバー関数へのポインターのみを受け入れます。 この制限は、オブジェクト ポインタに設定することで回避できます。 このオブジェクト ポインタは、すべての非メンバー コールバック関数に引数として渡されます。 このポインターを使用して、メンバー以外のコールバック関数内からメンバー関数を呼び出します。

再ロギング セッションの分析フェーズは、常に再ロギング フェーズの前に実行されます。

::: moniker-end
