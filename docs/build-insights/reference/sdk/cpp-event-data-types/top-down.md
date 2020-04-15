---
title: トップダウンクラス
description: C++ ビルド インサイト SDK トップダウン クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TopDown
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7c0c957fa17daaec34710debeda634192c63d1da
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324209"
---
# <a name="topdown-class"></a>トップダウンクラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`TopDown`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [TOP_DOWN](../event-table.md#top-down)イベントに一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class TopDown : public Activity
{
public:
    TopDown(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

クラスには、[その Activity](activity.md)基本クラスから継承された`TopDown`メンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[トップダウン](#top-down)

## <a name="topdown"></a><a name="top-down"></a>トップダウン

```cpp
TopDown(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[TOP_DOWN](../event-table.md#top-down)イベント。

::: moniker-end
