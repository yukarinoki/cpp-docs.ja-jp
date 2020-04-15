---
title: オプトレフクラス
description: C++ ビルド インサイト SDK OptRef クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OptRef
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: dca8cc62eed4b7136f88ed5ba6a1a168b2de56c3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324445"
---
# <a name="optref-class"></a>オプトレフクラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`OptRef`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [OPT_REF](../event-table.md#opt-ref)イベントに一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class OptRef : public Activity
{
public:
    OptRef(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

クラスには、[その Activity](activity.md)基本クラスから継承された`OptRef`メンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[オプトレフ](#opt-ref)

## <a name="optref"></a><a name="opt-ref"></a>オプトレフ

```cpp
OptRef(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[OPT_REF](../event-table.md#opt-ref)イベント。

::: moniker-end
