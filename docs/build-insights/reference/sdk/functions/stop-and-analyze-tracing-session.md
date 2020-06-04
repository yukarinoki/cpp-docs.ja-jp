---
title: トレースセッションを停止して分析する
description: C++ ビルド インサイト SDK StopAndAnalyze トレースセッション関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndAnalyzeTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9c9bd4a092c22dfcdfb6d463b74207ec11ee6d64
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323700"
---
# <a name="stopandanalyzetracingsession"></a>トレースセッションを停止して分析する

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`StopAndAnalyzeTracingSession`関数は、進行中のトレース・セッションを停止し、結果のトレースを一時ファイルに保管します。 分析セッションは、その後、入力として一時ファイルを使用してすぐに開始されます。 この関数を呼び出す実行可能ファイルには、管理者権限が必要です。

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

*Sessionname*\
停止するトレース セッションの名前。 [開始トレーシングセッション、開始トレーシングセッション](start-tracing-session.md)、または開始ト[レーシング](start-tracing-session-a.md)[セッションW](start-tracing-session-w.md)に渡されたものと同じセッション名を使用します。

*分析パスの数*\
トレースで実行する解析パスの数。 トレースは、指定されたアナライザー グループを 1 回、分析パスごとに渡されます。

*統計*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md)オブジェクトへのポインター。 `StopAndAnalyzeTracingSession`このオブジェクトにトレース コレクションの統計情報を書き込む前に、このオブジェクトを返します。

*アナライザグループ*\
分析に使用されるアナライザー グループ。 [アナライザー グループ](make-static-analyzer-group.md)を作成するには、呼び出します。 [から](make-dynamic-analyzer-group.md)取得した動的アナライザー グループを使用する場合は、まずアドレスをに渡すことによって静的アナライザー グループ内にカプセル化`MakeStaticAnalyzerGroup`します。

### <a name="return-value"></a>戻り値

[RESULT_CODE](../other-types/result-code-enum.md)列挙型からの結果コード。

::: moniker-end
