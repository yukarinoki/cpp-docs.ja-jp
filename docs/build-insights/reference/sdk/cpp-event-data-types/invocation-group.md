---
title: クラスを呼び出します。
description: C++ ビルド インサイト SDK 呼び出しグループ クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InvocationGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ff5a73d5304a21c314c0fc5ce442e0ffc23b28fd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324690"
---
# <a name="invocationgroup-class"></a>クラスを呼び出します。

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`InvocationGroup`は、[関数と一致イベント スタック](../functions/match-event-stack.md)と一致イベント[スタックInメンバー関数](../functions/match-event-stack-in-member-function.md)で使用されます。 このキーワードを使用して[、COMPILER](../event-table.md#compiler)イベントと[LINKER](../event-table.md#linker)イベントの組み合わせを含むグループを照合します。

## <a name="syntax"></a>構文

```cpp
class InvocationGroup : public EventGroup<Invocation>
{
public:
    InvocationGroup(std::deque<Invocation>&& group);
};
```

## <a name="members"></a>メンバー

[クラスには、EventGroup\<呼び出し\>](event-group.md)基本クラスから継承`InvocationGroup`されたメンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[呼び出しグループ](#invocation-group)

## <a name="invocationgroup"></a><a name="invocation-group"></a>呼び出しグループ

```cpp
InvocationGroup(std::deque<Invocation>&& group);
```

### <a name="parameters"></a>パラメーター

*グループ*\
[コンパイラ](../event-table.md#compiler)イベントと[リンカー](../event-table.md#linker)イベントの組み合わせを含むグループ。

::: moniker-end
