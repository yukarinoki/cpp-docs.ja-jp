---
title: StopAndRelogTracingSession
description: C++ Build Insights SDK の StopAndRelogTracingSession 関数のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d36dee1b16ca467d16b22587abe3ef34ee6ccb29
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919957"
---
# <a name="stopandrelogtracingsession"></a>StopAndRelogTracingSession

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`StopAndRelogTracingSession` 関数により、実行中のトレース セッションが停止されて、結果のトレースが一時ファイルに保存されます。 その後、その一時ファイルを入力として使用して、再ログ記録セッションが直ちに開始されます。 再ログ記録セッションによって生成された最終的な再ログ記録されたトレースが、呼び出し元によって指定されたファイルに保存されます。 この関数を呼び出す実行可能ファイルには、管理者権限が必要です。

## <a name="syntax"></a>構文

```cpp
template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE StopAndRelogTracingSession(
    const char*                                   sessionName,
    const char*                                   outputLogFile,
    TRACING_SESSION_STATISTICS*                   statistics,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);

template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE StopAndRelogTracingSession(
    const wchar_t*                                sessionName,
    const wchar_t*                                outputLogFile,
    TRACING_SESSION_STATISTICS*                   statistics,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);
```

### <a name="parameters"></a>パラメーター

*sessionName*\
停止するトレース セッションの名前。 [StartTracingSession](start-tracing-session.md)、[StartTracingSessionA](start-tracing-session-a.md)、[StartTracingSessionW](start-tracing-session-w.md) に渡したものと同じセッション名を使用します。

*outputLogFile*\
再ログ記録セッションによって生成される再ログ記録されたトレースを書き込むファイル。

*statistics*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) オブジェクトへのポインター。 `StopAndRelogTracingSession` によって、戻る前に、このオブジェクトのトレース コレクション統計情報が書き込まれます。

*numberOfAnalysisPasses*\
トレースに対して実行する分析パスの数。 トレースは、指定されたアナライザー グループを通して、分析パスごとに 1 回渡されます。

*systemEventsRetentionFlags*\
再記録されたトレースに保持するシステム ETW イベントを指定する [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](../other-types/relog-retention-system-event-flags-constants.md) ビットマスク。

*analyzerGroup*\
再ログ記録セッションの分析フェーズに使用されるアナライザー グループ。 アナライザー グループを作成するには、[MakeStaticAnalyzerGroup](make-static-analyzer-group.md) を呼び出します。 [MakeDynamicAnalyzerGroup](make-dynamic-analyzer-group.md) から取得された動的アナライザー グループを使用する場合は、最初に、そのアドレスを `MakeStaticAnalyzerGroup` に渡すことによって、静的なアナライザー グループ内にそれをカプセル化します。

*reloggerGroup*\
*outputLogFile* で指定されているトレース ファイルにイベントを再ログ記録するリロガー グループ。 リロガー グループを作成するには、[MakeStaticReloggerGroup](make-static-relogger-group.md) を呼び出します。 [MakeDynamicAnalyzerGroup](make-dynamic-relogger-group.md) から取得された動的リロガー グループを使用したい場合は、最初に、そのアドレスを `MakeStaticReloggerGroup` に渡すことによって、静的リロガー グループ内にそれをカプセル化します。

### <a name="return-value"></a>戻り値

[RESULT_CODE](../other-types/result-code-enum.md) 列挙型の結果コード。

### <a name="remarks"></a>注釈

入力トレースは、アナライザー グループを通して *numberOfAnalysisPasses* 回渡されます。 再ログ記録パスには同様のオプションはありません。 トレースは、すべての分析パスの完了後に、リロガー グループを通して 1 回だけ渡されます。

CPU サンプルなどのシステム イベントをリロガー クラス内から再ログ記録することはサポートされていません。 出力トレースに保持するシステム イベントを決定するには、 *systemEventsRetentionFlags* パラメーターを使用します。

::: moniker-end
