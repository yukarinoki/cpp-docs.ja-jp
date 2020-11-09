---
title: ForceInlinee クラス
description: C++ Build Insights SDK の ForceInlinee クラスのリファレンスです。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ForceInlinee
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 53fff7b6cfd37ba3e3211dd072c1ce3386d00fda
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920672"
---
# <a name="forceinlinee-class"></a>ForceInlinee クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`ForceInlinee` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [FORCE_INLINEE](../event-table.md#force-inlinee) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class ForceInlinee : public SimpleEvent
{
public:
    ForceInlinee(const RawEvent& event);

    const char*             Name() const;
    const unsigned short&   Size() const;
};
```

## <a name="members"></a>メンバー

その基底クラス [SimpleEvent](simple-event.md) から継承されたメンバーに加えて、`ForceInlinee` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[ForceInlinee](#force-inlinee)

### <a name="functions"></a>機能

[Name](#name)
[Size](#size)

## <a name="forceinlinee"></a><a name="force-inlinee"></a> ForceInlinee

```cpp
ForceInlinee(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[FORCE_INLINEE](../event-table.md#force-inlinee) イベント。

## <a name="name"></a><a name="name"></a> Name

```cpp
const char* Name() const;
```

### <a name="return-value"></a>戻り値

強制インライン化関数の名前。UTF-8 でエンコードされます。

## <a name="size"></a><a name="size"></a> サイズ

```cpp
const unsigned short& Size() const;
```

### <a name="return-value"></a>戻り値

強制インライン化関数のサイズ。中間命令数として表されます。

::: moniker-end
