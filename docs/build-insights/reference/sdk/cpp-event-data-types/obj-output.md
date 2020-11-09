---
title: ObjOutput クラス
description: C++ Build Insights SDK の ObjOutput クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ObjOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5c88ed6f1faa307d90a73104d3183adc8e50c542
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923063"
---
# <a name="objoutput-class"></a>ObjOutput クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`ObjOutput` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [OBJ_OUTPUT](../event-table.md#obj-output) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class ObjOutput : public FileOutput
{
public:
    ObjOutput(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

その基底クラス [FileOutput](file-output.md) から継承されたメンバーに加えて、`ObjOutput` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[ObjOutput](#obj-output)

## <a name="objoutput"></a><a name="obj-output"></a> ObjOutput

```cpp
ObjOutput(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[OBJ_OUTPUT](../event-table.md#obj-output) イベント。

::: moniker-end
