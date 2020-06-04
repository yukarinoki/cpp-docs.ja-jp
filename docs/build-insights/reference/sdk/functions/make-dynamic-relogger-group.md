---
title: メイクダイナミックリロガーグループ
description: C++ ビルド インサイト SDK MakeDynamicReloggerGroup 関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeDynamicReloggerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f49e37f8e1a8b9ca9a800d20b2891a54453095ef
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323952"
---
# <a name="makedynamicreloggergroup"></a>メイクダイナミックリロガーグループ

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

関数`MakeDynamicReloggerGroup`は、動的リロガー グループを作成するために使用されます。 リロガー グループのメンバーは、トレース内のすべてのイベントが処理されるまで、左から右に 1 つずつイベントを受け取ります。

## <a name="syntax"></a>構文

```cpp
auto MakeDynamicReloggerGroup(std::vector<IRelogger*> reloggers);

auto MakeDynamicReloggerGroup(std::vector<std::shared_ptr<IRelogger>> reloggers);

auto MakeDynamicReloggerGroup(std::vector<std::unique_ptr<IRelogger>> reloggers);
```

### <a name="parameters"></a>パラメーター

*リロガー*\
動的リロガー グループに含まれる[IRelogger](../other-types/irelogger-class.md)ポインターのベクター。 これらのポインターは、生、 `std::unique_ptr`、または`std::shared_ptr`、 です。 [IAnalyzer](../other-types/ianalyzer-class.md)ポインターは、継承`IRelogger`関係のためにポインターとも見なされます。

### <a name="return-value"></a>戻り値

ダイナミックリロガーグループ。 **auto**キーワードを使用して、戻り値を取得します。

## <a name="remarks"></a>解説

静的リロガー グループとは異なり、動的リロガー グループのメンバーはコンパイル時に知られる必要はありません。 リロガー グループ メンバーは、プログラム入力に基づいて実行時に選択するか、コンパイル時に不明なその他の値に基づいて選択できます。 静的リロガーグループとは異なり、動的リロガーグループ内の[IRelogger](../other-types/irelogger-class.md)ポインタはポリモーフィックな動作を持ち、仮想関数の呼び出しは正しくディスパッチされます。 この柔軟性は、イベント処理時間が遅くなる可能性があります。 すべてのリロガー グループ メンバーがコンパイル時に既知の場合、およびポリモーフィックな動作が必要ない場合は、静的リロガー グループを使用することを検討してください。 静的リロガー グループを使用するには、代わりに[MakeStaticRelogger グループを](make-static-relogger-group.md)呼び出します。

動的リロガー グループは、静的リロガー グループ内にカプセル化できます。 そのアドレスを渡す[。](make-static-relogger-group.md) 動的リロガー グループを[Relog](relog.md)などの関数に渡す場合は、静的リロガー グループのみを受け入れるこの手法を使用します。

::: moniker-end
