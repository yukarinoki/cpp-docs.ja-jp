---
title: パス2クラス
description: C++ ビルド インサイト SDK Pass2 クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Pass2
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 89b775c60b1d136c33dbaf2c4e39f247be7bb0bc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324400"
---
# <a name="pass2-class"></a>パス2クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`Pass2`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) このイベントは[、PASS2](../event-table.md#pass2)イベントと一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class Pass2 : public LinkerPass
{
public:
    Pass2(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

継承されたメンバーの基底クラスからの[継承](linker-pass.md)メンバーと共に`Pass2`、クラスには次のメンバーが含まれています。

### <a name="constructors"></a>コンストラクター

[パス2](#pass2)

## <a name="pass2"></a><a name="pass2"></a>パス2

```cpp
Pass2(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[PASS2](../event-table.md#pass2)イベント。

::: moniker-end
