---
title: リロガーグループを作成します。
description: C++ ビルド インサイト SDK MakeStaticReloggerグループ関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeStaticReloggerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 75b638537cb8e0cdeeb5476a3f5277e8e90d9baf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323913"
---
# <a name="makestaticreloggergroup"></a>リロガーグループを作成します。

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

関数`MakeStaticReloggerGroup`は[、Relog](relog.md)などの関数に渡すことができる静的なリロガー グループを作成するために使用されます。 リロガー グループのメンバーは、トレース内のすべてのイベントが処理されるまで、左から右に 1 つずつイベントを受け取ります。

## <a name="syntax"></a>構文

```cpp
template <typename... TReloggerPtrs>
auto MakeStaticReloggerGroup(TReloggerPtrs... reloggers);
```

### <a name="parameters"></a>パラメーター

*トレーロガープター*\
このパラメーターは常に推定されます。

*リロガー*\
静的リロガー グループに含まれている[IRelogger](../other-types/irelogger-class.md)ポインターのパラメーター パック。 これらのポインターは、生、 `std::unique_ptr`、または`std::shared_ptr`、 です。 [IAnalyzer](../other-types/ianalyzer-class.md)ポインターは、継承`IRelogger`関係のためにポインターとも見なされます。

### <a name="return-value"></a>戻り値

静的リロガー グループ。 **auto**キーワードを使用して、戻り値を取得します。

## <a name="remarks"></a>解説

動的リロガー グループとは異なり、静的リロガー グループのメンバーはコンパイル時に認識されている必要があります。 さらに、静的リロガー グループには、ポリモーフィックな動作を持たない[IRelogger](../other-types/irelogger-class.md)ポインターが含まれています。 静的リロガー グループを使用して Windows (ETW) トレースのイベント トレースを分析`IRelogger`する場合、インターフェイスへの呼び出しは常にリロガー グループ メンバーによって直接指すオブジェクトに解決されます。 この柔軟性の低下には、イベント処理時間が短縮される可能性があります。 リロガー グループのメンバーがコンパイル時に認識できない場合、またはポインターに多態的な動作が`IRelogger`必要な場合は、動的リロガー グループを使用することを検討してください。 代わりに[MakeDynamicReloggerGroup](make-dynamic-relogger-group.md)を呼び出して動的リロガー グループを使用できます。

::: moniker-end
