---
title: EnvironmentVariable クラス
description: C++ Build Insights SDK の EnvironmentVariable クラスのリファレンスです。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EnvironmentVariable
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f707ab744aaf6097975ba9e189815df3c9f32266
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920764"
---
# <a name="environmentvariable-class"></a>EnvironmentVariable クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`EnvironmentVariable` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [ENVIRONMENT_VARIABLE](../event-table.md#environment-variable) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class EnvironmentVariable : public SimpleEvent
{
public:
    EnvironmentVariable(const RawEvent& event);

    const wchar_t* Name() const;
    const wchar_t* Value() const;
};
```

## <a name="members"></a>メンバー

その基底クラス [SimpleEvent](simple-event.md) から継承されたメンバーに加えて、`EnvironmentVariable` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[EnvironmentVariable](#environment-variable)

### <a name="functions"></a>機能

[Name](#name)
[Value](#value)

## <a name="environmentvariable"></a><a name="environment-variable"></a> EnvironmentVariable

```cpp
EnvironmentVariable(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[ENVIRONMENT_VARIABLE](../event-table.md#environment-variable) イベント。

## <a name="name"></a><a name="name"></a> Name

```cpp
const wchar_t Name() const;
```

### <a name="return-value"></a>戻り値

環境変数の名前。

## <a name="value"></a><a name="value"></a> 値

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>戻り値

環境変数の値。

::: moniker-end
