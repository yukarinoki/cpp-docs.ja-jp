---
title: LinkerGroup クラス
description: C++ Build Insights SDK の LinkerGroup クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LinkerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 8a818cf7524405d4e2f29a1987e93b77371607cc
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923115"
---
# <a name="linkergroup-class"></a>LinkerGroup クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`LinkerGroup` クラスは、[MatchEventStack](../functions/match-event-stack.md) および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [LINKER](../event-table.md#linker) イベントのグループを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class LinkerGroup : public EventGroup<Linker>
{
public:
    LinkerGroup(std::deque<Linker>&& group);
};
```

## <a name="members"></a>メンバー

その基底クラス [EventGroup\<Linker\>](event-group.md) から継承されたメンバーに加えて、`LinkerGroup` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[LinkerGroup](#linker-group)

## <a name="linkergroup"></a><a name="linker-group"></a> LinkerGroup

```cpp
LinkerGroup(std::deque<Linker>&& group);
```

### <a name="parameters"></a>パラメーター

*group*\
[LINKER](../event-table.md#linker) イベントのグループ。

::: moniker-end
