---
title: SymbolName クラス
description: C++ Build Insights SDK の SymbolName クラスのリファレンスです。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SymbolName
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a749d95b3812df8b1cc0cd7d2da037e98467cefc
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920477"
---
# <a name="symbolname-class"></a>SymbolName クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`SymbolName` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [SYMBOL_NAME](../event-table.md#symbol-name) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class SymbolName : public SimpleEvent
{
public:
    SymbolName(const RawEvent& event);

    const unsigned long long&  Key() const;
    const char*                Name() const;
};
```

## <a name="members"></a>メンバー

その基底クラス [SimpleEvent](simple-event.md) から継承されたメンバーに加えて、`SymbolName` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[SymbolName](#symbol-name)

### <a name="functions"></a>機能

[Key](#key)
[Name](#name)

## <a name="key"></a><a name="key"></a> Key

```cpp
const unsigned long long& Key() const;
```

### <a name="return-value"></a>戻り値

この記号によって表される型の数値識別子。 この識別子は、コンパイラのフロントエンド パス内で一意です。

## <a name="name"></a><a name="name"></a> Name

```cpp
const char* Name() const;
```

### <a name="return-value"></a>戻り値

シンボルによって表される型の名前。UTF-8 でエンコードされます。

## <a name="symbolname"></a><a name="symbol-name"></a> SymbolName

```cpp
SymbolName(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[SYMBOL_NAME](../event-table.md#symbol-name) イベント。

::: moniker-end
