---
title: StopAndAnalyzeTracingSession
description: C++ Build Insights SDK の StopAndAnalyzeTracingSession 関数のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndAnalyzeTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 81a8ce43ecedfa51874508193637969411ae52d6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922718"
---
# <a name="stopandanalyzetracingsession"></a>StopAndAnalyzeTracingSession

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`StopAndAnalyzeTracingSession` 関数により、実行中のトレース セッションが停止されて、結果のトレースが一時ファイルに保存されます。 その後、その一時ファイルを入力として使用して、分析セッションが直ちに開始されます。 この関数を呼び出す実行可能ファイルには、管理者権限が必要です。

## <a name="syntax"></a>構文

```cpp
template <typename... TAnalyzerGroupMembers>
RESULT_CODE StopAndAnalyzeTracingSession(
    const char*                                   sessionName,
    unsigned                                      numberOfAnalysisPasses,
    TRACING_SESSION_STATISTICS*                   statistics,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);

template <typename... TAnalyzerGroupMembers>
RESULT_CODE StopAndAnalyzeTracingSession(
    const wchar_t*                                sessionName,
    unsigned                                      numberOfAnalysisPasses,
    TRACING_SESSION_STATISTICS*                   statistics,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);
```

### <a name="parameters"></a>パラメーター

*sessionName*\
停止するトレース セッションの名前。 [StartTracingSession](start-tracing-session.md)、[StartTracingSessionA](start-tracing-session-a.md)、[StartTracingSessionW](start-tracing-session-w.md) に渡したものと同じセッション名を使用します。

*numberOfAnalysisPasses*\
トレースに対して実行する分析パスの数。 トレースは、指定されたアナライザー グループを通して、分析パスごとに 1 回渡されます。

*statistics*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) オブジェクトへのポインター。 `StopAndAnalyzeTracingSession` によって、戻る前に、このオブジェクトのトレース コレクション統計情報が書き込まれます。

*analyzerGroup*\
分析に使用するアナライザー グループ。 アナライザー グループを作成するには、[MakeStaticAnalyzerGroup](make-static-analyzer-group.md) を呼び出します。 [MakeDynamicAnalyzerGroup](make-dynamic-analyzer-group.md) から取得された動的アナライザー グループを使用する場合は、最初に、そのアドレスを `MakeStaticAnalyzerGroup` に渡すことによって、静的なアナライザー グループ内にそれをカプセル化します。

### <a name="return-value"></a>戻り値

[RESULT_CODE](../other-types/result-code-enum.md) 列挙型の結果コード。

::: moniker-end
