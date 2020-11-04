---
title: MakeDynamicAnalyzerGroup
description: C++ Build Insights SDK MakeDynamicAnalyzerGroup 関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeDynamicAnalyzerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4a10c175cf41bb0e867a9211a11595c8abaca18a
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920282"
---
# <a name="makedynamicanalyzergroup"></a>MakeDynamicAnalyzerGroup

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`MakeDynamicAnalyzerGroup` 関数は、動的アナライザー グループを作成するために使用されます。 アナライザー グループのメンバーは、トレース内のすべてのイベントが分析されるまで、左から右に 1 つずつイベントを受け取ります。

## <a name="syntax"></a>構文

```cpp
auto MakeDynamicAnalyzerGroup(std::vector<IAnalyzer*> analyzers);

auto MakeDynamicAnalyzerGroup(std::vector<std::shared_ptr<IAnalyzer>> analyzers);

auto MakeDynamicAnalyzerGroup(std::vector<std::unique_ptr<IAnalyzer>> analyzers);
```

### <a name="parameters"></a>パラメーター

*analyzers*\
動的アナライザー グループに含まれる [IAnalyzer](../other-types/ianalyzer-class.md) ポインターのベクター。 これらのポインターには、生、`std::unique_ptr`、または `std::shared_ptr` を使用できます。

### <a name="return-value"></a>戻り値

動的アナライザー グループ。 戻り値を取得するには、 **`auto`** キーワードを使用します。

## <a name="remarks"></a>Remarks

静的アナライザー グループとは異なり、動的アナライザー グループのメンバーは、コンパイル時に既知である必要はありません。 プログラムの入力、またはコンパイル時には不明な他の値に基づいて、実行時にアナライザー グループのメンバーを選択できます。 静的アナライザー グループとは異なり、動的アナライザー グループ内の [`IAnalyzer`](../other-types/ianalyzer-class.md) ポインターにはポリモーフィックな動作があり、仮想関数の呼び出しは正しくディスパッチされます。 この柔軟性により、イベント処理時間が遅くなる可能性があります。 アナライザー グループのすべてのメンバーがコンパイル時にわかっていて、ポリモーフィックな動作が必要ない場合は、静的アナライザー グループの使用を検討します。 静的アナライザー グループを使用するには、代わりに [`MakeStaticAnalyzerGroup`](make-static-analyzer-group.md) を呼び出します。

動的アナライザー グループを、静的アナライザー グループ内にカプセル化することができます。 これを行うには、そのアドレスを [`MakeStaticAnalyzerGroup`](make-static-analyzer-group.md) に渡します。 静的アナライザー グループのみを受け入れる [`Analyze`](analyze.md) などの関数に動的アナライザー グループを渡す場合は、この手法を使用します。

::: moniker-end
