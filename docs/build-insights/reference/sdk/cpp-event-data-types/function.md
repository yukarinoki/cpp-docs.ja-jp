---
title: Function クラス
description: C++ Build Insights SDK の Function クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Function
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 874477b9ca31095bfcf4ba3c7a6fd220dc073415
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920646"
---
# <a name="function-class"></a>Function クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`Function` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [FUNCTION](../event-table.md#function) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class Function : public Activity
{
public:
    Function(const RawEvent& event);

    const char* Name() const;
};
```

## <a name="members"></a>メンバー

その基底クラス [Activity](activity.md) から継承されたメンバーに加えて、`Function` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[Function](#function)

### <a name="functions"></a>関数

[名前](#name)

## <a name="function"></a><a name="function"></a> Function

```cpp
Function(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[FUNCTION](../event-table.md#function) イベント。

## <a name="name"></a><a name="name"></a> Name

```cpp
const char* Name() const;
```

### <a name="return-value"></a>戻り値

関数の名前。UTF-8 でエンコードされます。

::: moniker-end
