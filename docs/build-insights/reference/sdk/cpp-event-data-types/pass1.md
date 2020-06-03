---
title: パス1クラス
description: C++ ビルド インサイト SDK Pass1 クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Pass1
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 039c2cc92b8461009c235baa7e49484eb2a4f49f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324421"
---
# <a name="pass1-class"></a>パス1クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`Pass1`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [PASS1](../event-table.md#pass1)イベントと一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class Pass1 : public LinkerPass
{
public:
    Pass1(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

継承されたメンバーの基底クラスからの[継承](linker-pass.md)メンバーと共に`Pass1`、クラスには次のメンバーが含まれています。

### <a name="constructors"></a>コンストラクター

[パス1](#pass1)

## <a name="pass1"></a><a name="pass1"></a>パス1

```cpp
Pass1(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[PASS1](../event-table.md#pass1)イベント。

::: moniker-end
