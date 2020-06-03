---
title: リンカーパスクラス
description: C++ ビルド インサイト SDK リンカーパス クラス リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LinkerPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2b0c5a02958560faeff30500543b6e6d4921ac52
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324614"
---
# <a name="linkerpass-class"></a>リンカーパスクラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`LinkerPass`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) このイベントは[、PASS1](../event-table.md#pass1)または[PASS2](../event-table.md#pass2)イベントと一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class LinkerPass : public Activity
{
public:
    LinkerPass(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

クラスには、[その Activity](activity.md)基本クラスから継承された`LinkerPass`メンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[リンカーパス](#linker-pass)

## <a name="linkerpass"></a><a name="linker-pass"></a>リンカーパス

```cpp
LinkerPass(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[PASS1](../event-table.md#pass1)または[PASS2](../event-table.md#pass2)イベント。

::: moniker-end
