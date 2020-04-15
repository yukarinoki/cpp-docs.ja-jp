---
title: メイクアップスタティックアナライザグループ
description: C++ ビルド インサイト SDK メイクスタティックアナライザグループ関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeStaticAnalyzerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 72f7f5d7a408436902394451a52dd66efe1d93f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323942"
---
# <a name="makestaticanalyzergroup"></a>メイクアップスタティックアナライザグループ

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`MakeStaticAnalyzerGroup`関数は、[分析](analyze.md)や[再ログ](relog.md)などの関数に渡すことができる静的アナライザーグループを作成するために使用されます。 アナライザー グループのメンバは、トレース内のすべてのイベントが分析されるまで、イベントを左から右に 1 つずつ受け取ります。

## <a name="syntax"></a>構文

```cpp
template <typename... TAnalyzerPtrs>
auto MakeStaticAnalyzerGroup(TAnalyzerPtrs... analyzers);
```

### <a name="parameters"></a>パラメーター

*Tアナライザー*\
このパラメーターは常に推定されます。

*アナライザー*\
静的アナライザー グループに含まれる[IAnalyzer](../other-types/ianalyzer-class.md)ポインターのパラメーター パック。 これらのポインターは、生、 `std::unique_ptr`、または`std::shared_ptr`、 です。

### <a name="return-value"></a>戻り値

静的アナライザー グループ。 **auto**キーワードを使用して、戻り値を取得します。

## <a name="remarks"></a>解説

動的アナライザーグループとは異なり、静的アナライザーグループのメンバーはコンパイル時に認識されている必要があります。 さらに、静的アナライザー グループには、ポリモーフィックな動作を持たない[IAnalyzer](../other-types/ianalyzer-class.md)ポインターが含まれています。 静的アナライザー グループを使用して Windows イベント トレース (ETW) トレースを`IAnalyzer`分析する場合、インターフェイスへの呼び出しは常にアナライザー グループ メンバーによって直接ポイントされたオブジェクトに解決されます。 この柔軟性の低下には、イベント処理時間が短縮される可能性があります。 コンパイル時にアナライザー グループのメンバーが認識できない場合、または`IAnalyzer`ポインターに対してポリモーフィックな動作が必要な場合は、動的アナライザー グループの使用を検討してください。 動的アナライザー グループを使用するには、代わりに[メイクダイナミック アナライザグループを](make-static-analyzer-group.md)呼び出します。

::: moniker-end
