---
title: BackEndPass クラス
description: C++ Build Insights SDK の BackEndPass クラスのリファレンスです。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- BackEndPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5438fb0ae27d07cbf3f9c7ee446cd12278b4777a
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920906"
---
# <a name="backendpass-class"></a>BackEndPass クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`BackEndPass` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [BACK_END_PASS](../event-table.md#back-end-pass) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class BackEndPass : public CompilerPass
{
public:
    BackEndPass(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

その基底クラス [CompilerPass](compiler-pass.md) から継承されたメンバーに加えて、`BackEndPass` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[BackEndPass](#back-end-pass)

## <a name="backendpass"></a><a name="back-end-pass"></a> BackEndPass

```cpp
BackEndPass(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[BACK_END_PASS](../event-table.md#back-end-pass) イベント。

::: moniker-end
