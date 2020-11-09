---
title: C1DLL クラス
description: C++ Build Insights SDK の C1DLL クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- C1DLL
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a8f1f6fdaf9a2c16e07fa5096cfcb585f8c3d9f2
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920842"
---
# <a name="c1dll-class"></a>C1DLL クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`C1DLL` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [C1_DLL](../event-table.md#c1-dll) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class C1DLL : public Activity
{
public:
    C1DLL(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

その基底クラス [Activity](activity.md) から継承されたメンバーに加えて、`C1DLL` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[C1DLL](#c1-dll)

## <a name="c1dll"></a><a name="c1-dll"></a> C1DLL

```cpp
C1DLL(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[C1_DLL](../event-table.md#c1-dll) イベント。

::: moniker-end
