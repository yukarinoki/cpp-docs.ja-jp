---
title: 分析
description: C++ ビルド インサイト SDK 分析関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyze
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 08b3643270cc785b3fbea36720d192b4a1473104
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324105"
---
# <a name="analyze"></a>分析

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`Analyze`関数は、C++ ビルドのトレース中に MSVC から取得した Windows イベント トレース (ETW) トレースを分析するために使用されます。 ETW トレース内のイベントは、呼び出し元によって提供されるアナライザー グループに順番に転送されます。 この関数は、イベント ストリームをアナライザ グループに複数回連続して転送できるマルチパス分析をサポートします。

## <a name="syntax"></a>構文

```cpp
template <typename... TAnalyzerGroupMembers>
RESULT_CODE Analyze(
    const char*                                   inputLogFile,
    unsigned                                      numberOfPasses,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);

template <typename... TAnalyzerGroupMembers>
RESULT_CODE Analyze(
    const wchar_t*                                inputLogFile,
    unsigned                                      numberOfPasses,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);
```

### <a name="parameters"></a>パラメーター

*グループメンバー*\
このパラメーターは常に推定されます。

*入力ログファイル*\
イベントの読み取りを行う入力 ETW トレース。

*パス数*\
入力トレースで実行する解析パスの数。 トレースは、指定されたアナライザー グループを 1 回、分析パスごとに渡されます。

*アナライザグループ*\
分析に使用されるアナライザー グループ。 [アナライザー グループ](make-static-analyzer-group.md)を作成するには、呼び出します。 [から](make-dynamic-analyzer-group.md)取得した動的アナライザー グループを使用するには、まずアドレスをに渡すことによって静的アナライザー グループ内にカプセル`MakeStaticAnalyzerGroup`化します。

### <a name="return-value"></a>戻り値

[RESULT_CODE](../other-types/result-code-enum.md)列挙型からの結果コード。

::: moniker-end
