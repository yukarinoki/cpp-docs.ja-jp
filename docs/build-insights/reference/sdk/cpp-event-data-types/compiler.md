---
title: コンパイラ クラス
description: C++ ビルド インサイト SDK コンパイラ クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Compiler
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9b0a2622c4bc0bc19d7222977fe24c060ee8709e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325023"
---
# <a name="compiler-class"></a>コンパイラ クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`Compiler`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) この関数は[、COMPILER](../event-table.md#compiler)イベントと一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class Compiler : public Invocation
{
public:
    Compiler(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

[クラスには、継承](invocation.md)されたメンバーが Invocation 基本クラス`Compiler`から継承されたメンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[コンパイラ](#compiler)

## <a name="compiler"></a><a name="compiler"></a>コンパイラ

```cpp
Compiler(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[コンパイラ](../event-table.md#compiler)イベント。

::: moniker-end
