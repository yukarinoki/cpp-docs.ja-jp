---
title: クラスを出力します。
description: C++ ビルド インサイト SDK インプリブアウトプレンプクラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ImpLibOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 98905dfe75484e98e14a0fa575e75fe3ab284559
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324698"
---
# <a name="impliboutput-class"></a>クラスを出力します。

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`ImpLibOutput`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output)イベントに一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class ImpLibOutput : public FileOutput
{
public:
    ImpLibOutput(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

クラスには、[その FileOutput](file-output.md)基本クラスから継承された`ImpLibOutput`メンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[インプリブ出力](#imp-lib-output)

## <a name="impliboutput"></a><a name="imp-lib-output"></a>インプリブ出力

```cpp
ImpLibOutput(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[IMP_LIB_OUTPUT](../event-table.md#imp-lib-output)イベント。

::: moniker-end
