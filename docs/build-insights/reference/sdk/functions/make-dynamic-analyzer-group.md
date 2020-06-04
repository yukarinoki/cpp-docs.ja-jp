---
title: メイクダイナミックアナライザグループ
description: C++ ビルド インサイト SDK メイクダイナミックアナライザグループ関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeDynamicAnalyzerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 148eeea41f29ac6dd75653feed7f3f3f8c301911
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323957"
---
# <a name="makedynamicanalyzergroup"></a>メイクダイナミックアナライザグループ

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`MakeDynamicAnalyzerGroup`関数は、動的アナライザー・グループを作成するために使用されます。 アナライザー グループのメンバは、トレース内のすべてのイベントが分析されるまで、イベントを左から右に 1 つずつ受け取ります。

## <a name="syntax"></a>構文

```cpp
auto MakeDynamicAnalyzerGroup(std::vector<IAnalyzer*> analyzers);

auto MakeDynamicAnalyzerGroup(std::vector<std::shared_ptr<IAnalyzer>> analyzers);

auto MakeDynamicAnalyzerGroup(std::vector<std::unique_ptr<IAnalyzer>> analyzers);
```

### <a name="parameters"></a>パラメーター

*アナライザー*\
動的アナライザー グループに含まれる[IAnalyzer](../other-types/ianalyzer-class.md)ポインターのベクトル。 これらのポインターは、生、 `std::unique_ptr`、または`std::shared_ptr`、 です。

### <a name="return-value"></a>戻り値

動的アナライザー グループ。 **auto**キーワードを使用して、戻り値を取得します。

## <a name="remarks"></a>解説

静的アナライザー グループとは異なり、動的アナライザー グループのメンバーはコンパイル時に認識する必要はありません。 実行時に、プログラム入力に基づいてアナライザー グループ メンバーを選択するか、コンパイル時に不明なその他の値に基づいて選択できます。 静的アナライザー グループとは異なり、動的アナライザ グループ内の[IAnalyzer](../other-types/ianalyzer-class.md)ポインターはポリモーフィックな動作を持ち、仮想関数呼び出しは正しくディスパッチされます。 この柔軟性は、イベント処理時間が遅くなる可能性があります。 すべてのアナライザ グループ メンバーがコンパイル時に既知であり、ポリモーフィックな動作が必要ない場合は、静的アナライザー グループの使用を検討してください。 静的アナライザー グループを使用するには、代わりに[を](make-static-analyzer-group.md)呼び出します。

動的アナライザーグループは、静的アナライザーグループ内にカプセル化できます。 アドレスを[渡](make-static-analyzer-group.md)すことによって行われます。 この手法を使用して、静的アナライザー グループのみを受け入れる[Analyze](analyze.md)などの関数に動的アナライザー グループを渡します。

::: moniker-end
