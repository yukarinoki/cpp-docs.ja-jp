---
title: コマンド ライン クラス
description: C++ ビルド インサイト SDK コマンド ライン クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CommandLine
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b35d688acf06579cc27f2fee053ef58032e204e0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325058"
---
# <a name="commandline-class"></a>コマンド ライン クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`CommandLine`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [COMMAND_LINE](../event-table.md#command-line)イベントに一致させるために使用します。

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

[クラスには、SimpleEvent](simple-event.md)基本クラスから継承されたメンバーと`CommandLine`共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[コマンドライン](#command-line)

### <a name="functions"></a>関数

[Value](#value)

## <a name="commandline"></a><a name="command-line"></a>コマンドライン

```cpp
CommandLine(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[COMMAND_LINE](../event-table.md#command-line)イベント。

## <a name="value"></a><a name="value"></a> の値

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>戻り値

コマンド ラインを含む文字列。 この値には、応答ファイルから取得された引数、および環境変数 (CL、CL、\_\_リンク、LINK\_など\_) から取得された引数が含まれます。

::: moniker-end
