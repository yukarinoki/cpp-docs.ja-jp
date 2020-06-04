---
title: Thread クラス
description: C++ ビルド インサイト SDK スレッド クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Thread
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 397083c63f451b2d3fb8dad529adf73855af8644
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324195"
---
# <a name="thread-class"></a>Thread クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`Thread`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) この値は[、THREAD](../event-table.md#thread)イベントと一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class Thread : public Activity
{
public:
    Thread(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

クラスには、[その Activity](activity.md)基本クラスから継承された`Thread`メンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[スレッド](#thread)

## <a name="thread"></a><a name="thread"></a>スレッド

```cpp
Thread(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[THREAD](../event-table.md#thread)イベント。

::: moniker-end
