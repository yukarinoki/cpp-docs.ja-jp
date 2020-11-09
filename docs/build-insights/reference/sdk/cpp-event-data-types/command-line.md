---
title: CommandLine クラス
description: C++ Build Insights SDK の CommandLine クラスのリファレンスです。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CommandLine
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5214f2970329510088184dc3092db66607f4d67e
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923338"
---
# <a name="commandline-class"></a>CommandLine クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`CommandLine` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [COMMAND_LINE](../event-table.md#command-line) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class CommandLine : public SimpleEvent
{
public:
    CommandLine(const RawEvent& event);

    const wchar_t* Value() const;
};
```

## <a name="members"></a>メンバー

その基底クラス [SimpleEvent](simple-event.md) から継承されたメンバーに加えて、`CommandLine` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[CommandLine](#command-line)

### <a name="functions"></a>機能

[Value](#value)

## <a name="commandline"></a><a name="command-line"></a> CommandLine

```cpp
CommandLine(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[COMMAND_LINE](../event-table.md#command-line) イベント。

## <a name="value"></a><a name="value"></a> 値

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>戻り値

コマンド ラインが格納されている文字列。 この値には、応答ファイルと、CL、\_CL\_、Link、\_LINK\_ などの環境変数から取得された引数が含まれます。

::: moniker-end
