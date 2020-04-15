---
title: リンカークラス
description: C++ ビルド インサイト SDK リンカー クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Linker
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e5d4c0c3841377fc2e029c23d5cbbd076c8029cc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324596"
---
# <a name="linker-class"></a>リンカークラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`Linker`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [リンカー](../event-table.md#linker) ・イベントと一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class Linker : public Invocation
{
public:
    Linker(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

[クラスには、継承](invocation.md)されたメンバーが Invocation 基本クラス`Linker`から継承されたメンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[リンカー](#linker)

## <a name="linker"></a><a name="linker"></a>リンカー

```cpp
Linker(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[リンカー](../event-table.md#linker) ・イベント。

::: moniker-end
