---
title: InvocationGroup クラス
description: C++ Build Insights SDK の InvocationGroup クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InvocationGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1a8d4786a228ab25551ee36ce22637d44dc07307
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920633"
---
# <a name="invocationgroup-class"></a>InvocationGroup クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`InvocationGroup` クラスは、[MatchEventStack](../functions/match-event-stack.md) および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [COMPILER](../event-table.md#compiler) イベントと [LINKER](../event-table.md#linker) イベントの組み合わせを含むグループを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class InvocationGroup : public EventGroup<Invocation>
{
public:
    InvocationGroup(std::deque<Invocation>&& group);
};
```

## <a name="members"></a>メンバー

その基底クラス [EventGroup\<Invocation\>](event-group.md) から継承されたメンバーに加えて、`InvocationGroup` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[InvocationGroup](#invocation-group)

## <a name="invocationgroup"></a><a name="invocation-group"></a> InvocationGroup

```cpp
InvocationGroup(std::deque<Invocation>&& group);
```

### <a name="parameters"></a>パラメーター

*group*\
[COMPILER](../event-table.md#compiler) イベントと [LINKER](../event-table.md#linker) イベントの組み合わせを含むグループ。

::: moniker-end
