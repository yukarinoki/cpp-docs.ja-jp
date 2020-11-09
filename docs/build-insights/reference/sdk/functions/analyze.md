---
title: 分析
description: C++ Build Insights SDK の Analyze 関数のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyze
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5e593b690231adf6f04161f9c3ff6aef3217f9ef
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920321"
---
# <a name="analyze"></a>分析

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`Analyze` 関数は、C++ ビルドのトレース中に MSVC から取得した Event Tracing for Windows (ETW) トレースを分析するために使用されます。 ETW トレースのイベントは、呼び出し元によって提供されるアナライザー グループに順次転送されます。 この関数では複数パスの分析がサポートされており、イベント ストリームをアナライザー グループに続けて複数回転送できます。

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

*TAnalyzerGroupMembers*\
このパラメーターは常に推測されます。

*inputLogFile*\
イベントの読み取り元の入力 ETW トレース。

*numberOfPasses*\
入力トレースに対して実行する分析パスの数。 トレースは、指定されたアナライザー グループを通して、分析パスごとに 1 回渡されます。

*analyzerGroup*\
分析に使用するアナライザー グループ。 アナライザー グループを作成するには、[MakeStaticAnalyzerGroup](make-static-analyzer-group.md) を呼び出します。 [MakeDynamicAnalyzerGroup](make-dynamic-analyzer-group.md) から取得された動的アナライザー グループを使用するには、最初に、そのアドレスを `MakeStaticAnalyzerGroup` に渡すことによって、静的なアナライザー グループ内にそれをカプセル化します。

### <a name="return-value"></a>戻り値

[RESULT_CODE](../other-types/result-code-enum.md) 列挙型の結果コード。

::: moniker-end
