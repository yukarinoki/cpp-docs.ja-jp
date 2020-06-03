---
title: クラス
description: クラスリファレンスを構築します。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndFileGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d2eebb650e59e750e5ebde74914dca5f0ef4779d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324772"
---
# <a name="frontendfilegroup-class"></a>クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`FrontEndFileGroup`は、[関数と一致イベント スタック](../functions/match-event-stack.md)と一致イベント[スタックInメンバー関数](../functions/match-event-stack-in-member-function.md)で使用されます。 [FRONT_END_FILE](../event-table.md#front-end-file)イベントのグループと一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class FrontEndFileGroup : public EventGroup<FrontEndFile>
{
public:
    FrontEndFileGroup(std::deque<FrontEndFile>&& group);
};
```

## <a name="members"></a>メンバー

クラスには、継承されたメンバーが[、その\<イベント グループ\>のフロント エンドファイル](event-group.md)基本クラスから継承されたメンバーと共に`FrontEndFileGroup`、次のメンバーが含まれています。

### <a name="constructors"></a>コンストラクター

[フロントエンドファイルグループ](#front-end-file-group)

## <a name="frontendfilegroup"></a><a name="front-end-file-group"></a>フロントエンドファイルグループ

```cpp
FrontEndFileGroup(std::deque<FrontEndFile>&& group);
```

### <a name="parameters"></a>パラメーター

*グループ*\
[FRONT_END_FILE](../event-table.md#front-end-file)イベントのグループ。

::: moniker-end
