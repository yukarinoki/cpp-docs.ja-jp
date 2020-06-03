---
title: コードジェネレーション クラス
description: C++ ビルド インサイト SDK コードジェネレーション クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CodeGeneration
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 27149d60cc6970843ef2ecccbaf25472f002e35f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325067"
---
# <a name="codegeneration-class"></a>コードジェネレーション クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`CodeGeneration`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [CODE_GENERATION](../event-table.md#code-generation)イベントに一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class CodeGeneration : public Activity
{
public:
    CodeGeneration(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

クラスには、[その Activity](activity.md)基本クラスから継承された`CodeGeneration`メンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[コードジェネレーション](#code-generation)

## <a name="codegeneration"></a><a name="code-generation"></a>コードジェネレーション

```cpp
CodeGeneration(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[CODE_GENERATION](../event-table.md#code-generation)イベント。

::: moniker-end
