---
title: クラスを出力します。
description: C++ ビルド インサイト SDK LibOutput クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LibOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: fda7b471759a9c49937214bb2176473226668776
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324623"
---
# <a name="liboutput-class"></a>クラスを出力します。

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`LibOutput`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [LIB_OUTPUT](../event-table.md#lib-output)イベントに一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class LibOutput : public FileOutput
{
public:
    LibOutput(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

クラスには、[その FileOutput](file-output.md)基本クラスから継承された`LibOutput`メンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[リブアウトプット](#lib-output)

## <a name="liboutput"></a><a name="lib-output"></a>リブアウトプット

```cpp
LibOutput(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[LIB_OUTPUT](../event-table.md#lib-output)イベント。

::: moniker-end
