---
title: C2DLL クラス
description: C++ Build Insights SDK の C2DLL クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- C2DLL
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 81aa4722d918646a0275099879bfee567ebc8f22
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923374"
---
# <a name="c2dll-class"></a>C2DLL クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`C2DLL` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [C2_DLL](../event-table.md#c2-dll) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class C2DLL : public Activity
{
public:
    C2DLL(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

その基底クラス [Activity](activity.md) から継承されたメンバーに加えて、`C2DLL` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[C2DLL](#c2-dll)

## <a name="c2dll"></a><a name="c2-dll"></a> C2DLL

```cpp
C2DLL(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[C2_DLL](../event-table.md#c2-dll) イベント。

::: moniker-end
