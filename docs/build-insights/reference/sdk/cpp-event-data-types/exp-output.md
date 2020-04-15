---
title: クラス
description: C++ ビルド インサイト SDK ExpOutput クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ExpOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4c8c5f2f260596c444df7841c2a3e0c65f5163f7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324817"
---
# <a name="expoutput-class"></a>クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`ExpOutput`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [EXP_OUTPUT](../event-table.md#exp-output)イベントに一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class ExpOutput : public FileOutput
{
public:
    ExpOutput(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

クラスには、[その FileOutput](file-output.md)基本クラスから継承された`ExpOutput`メンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[出力](#exp-output)

## <a name="expoutput"></a><a name="exp-output"></a>出力

```cpp
ExpOutput(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[EXP_OUTPUT](../event-table.md#exp-output)イベント。

::: moniker-end
