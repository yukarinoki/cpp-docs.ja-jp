---
title: MakeDynamicReloggerGroup
description: C++ Build Insights SDK MakeDynamicReloggerGroup 関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeDynamicReloggerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6bfa5bfbe8a61148f925ba185fccc035fd44d02d
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920269"
---
# <a name="makedynamicreloggergroup"></a>MakeDynamicReloggerGroup

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`MakeDynamicReloggerGroup` 関数は、動的リロガー グループを作成するために使用されます。 リロガー グループのメンバーは、トレース内のすべてのイベントが処理されるまで、左から右に 1 つずつイベントを受け取ります。

## <a name="syntax"></a>構文

```cpp
auto MakeDynamicReloggerGroup(std::vector<IRelogger*> reloggers);

auto MakeDynamicReloggerGroup(std::vector<std::shared_ptr<IRelogger>> reloggers);

auto MakeDynamicReloggerGroup(std::vector<std::unique_ptr<IRelogger>> reloggers);
```

### <a name="parameters"></a>パラメーター

*reloggers*\
動的リロガー グループに含まれる [IRelogger](../other-types/irelogger-class.md) ポインターのベクター。 これらのポインターには、生、`std::unique_ptr`、または `std::shared_ptr` を使用できます。 継承関係のため、[IAnalyzer](../other-types/ianalyzer-class.md) ポインターは `IRelogger` ポインターとも見なされます。

### <a name="return-value"></a>戻り値

動的リロガー グループ。 戻り値を取得するには、 **`auto`** キーワードを使用します。

## <a name="remarks"></a>Remarks

静的リロガー グループとは異なり、動的リロガー グループのメンバーは、コンパイル時に既知である必要はありません。 プログラムの入力、またはコンパイル時には不明な他の値に基づいて、実行時にリロガー グループのメンバーを選択できます。 静的リロガー グループとは異なり、動的リロガー グループ内の [`IRelogger`](../other-types/irelogger-class.md) ポインターにはポリモーフィックな動作があり、仮想関数の呼び出しは正しくディスパッチされます。 この柔軟性により、イベント処理時間が遅くなる可能性があります。 リロガー グループのすべてのメンバーがコンパイル時にわかっていて、ポリモーフィックな動作が必要ない場合は、静的リロガー グループの使用を検討します。 静的リロガー グループを使用するには、代わりに [`MakeStaticReloggerGroup`](make-static-relogger-group.md) を呼び出します。

動的リロガー グループを、静的リロガー グループ内にカプセル化することができます。 そのアドレスを [`MakeStaticReloggerGroup`](make-static-relogger-group.md) に渡します。 静的リロガー グループのみを受け入れる [`Relog`](relog.md) などの関数に動的リロガー グループを渡す場合は、この手法を使用します。

::: moniker-end
