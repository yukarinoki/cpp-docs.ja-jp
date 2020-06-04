---
title: リンカーグループクラス
description: C++ ビルド インサイト SDK リンカーグループ クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LinkerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c59d62938e5bd7b839ad12a321a03510e708e0fd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324655"
---
# <a name="linkergroup-class"></a>リンカーグループクラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`LinkerGroup`は、[関数と一致イベント スタック](../functions/match-event-stack.md)と一致イベント[スタックInメンバー関数](../functions/match-event-stack-in-member-function.md)で使用されます。 このイベントは[、LINKER](../event-table.md#linker)イベントのグループと一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class LinkerGroup : public EventGroup<Linker>
{
public:
    LinkerGroup(std::deque<Linker>&& group);
};
```

## <a name="members"></a>メンバー

[クラスには\<、EventGroup リンカー\>](event-group.md)基本クラスから継承されたメンバーと共に`LinkerGroup`、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[リンカーグループ](#linker-group)

## <a name="linkergroup"></a><a name="linker-group"></a>リンカーグループ

```cpp
LinkerGroup(std::deque<Linker>&& group);
```

### <a name="parameters"></a>パラメーター

*グループ*\
[リンカー](../event-table.md#linker) ・イベントのグループ。

::: moniker-end
