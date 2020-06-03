---
title: ボトムアップクラス
description: C++ ビルド インサイト SDK ボトムアップ クラス リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- BottomUp
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1cfe25aaa5736b9e2ba55a577e64958a6b9f113b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325216"
---
# <a name="bottomup-class"></a>ボトムアップクラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`BottomUp`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [BOTTOM_UP](../event-table.md#bottom-up)イベントに一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class BottomUp : public Activity
{
public:
    BottomUp(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

クラスには、[その Activity](activity.md)基本クラスから継承された`BottomUp`メンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[ボトムアップ](#bottom-up)

## <a name="bottomup"></a><a name="bottom-up"></a>ボトムアップ

```cpp
BottomUp(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[BOTTOM_UP](../event-table.md#bottom-up)イベント。

::: moniker-end
