---
title: セッションを停止します。
description: C++ ビルド インサイト SDK ストップアンドログトレースセッション関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1f6f5af63d25504226707d977791430463374328
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323664"
---
# <a name="stopandrelogtracingsession"></a>セッションを停止します。

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`StopAndRelogTracingSession`関数は、進行中のトレース・セッションを停止し、結果のトレースを一時ファイルに保管します。 再ロギング セッションは、入力として一時ファイルを使用してすぐに開始されます。 再ロギング・セッションによって生成された最終再ログ・トレースは、呼び出し元によって指定されたファイルに保管されます。 この関数を呼び出す実行可能ファイルには、管理者権限が必要です。

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

*Sessionname*\
停止するトレース セッションの名前。 [開始トレーシングセッション、開始トレーシングセッション](start-tracing-session.md)、または開始ト[レーシング](start-tracing-session-a.md)[セッションW](start-tracing-session-w.md)に渡されたものと同じセッション名を使用します。

*出力ログファイル*\
再ロギング セッションによって生成された、再ログ済みトレースを書き込むファイル。

*統計*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md)オブジェクトへのポインター。 `StopAndRelogTracingSession`このオブジェクトにトレース コレクションの統計情報を書き込む前に、このオブジェクトを返します。

*分析パスの数*\
トレースで実行する解析パスの数。 トレースは、指定されたアナライザー グループを 1 回、分析パスごとに渡されます。

*フラグ*\
ログに記録されたトレースに保持するシステム ETW イベントを指定する[RELOG_RETENTION_SYSTEM_EVENT_FLAGS](../other-types/relog-retention-system-event-flags-constants.md)ビットマスク。

*アナライザグループ*\
再ロギング セッションの分析フェーズで使用されるアナライザー グループ。 [アナライザー グループ](make-static-analyzer-group.md)を作成するには、呼び出します。 [から](make-dynamic-analyzer-group.md)取得した動的アナライザー グループを使用する場合は、まずアドレスをに渡すことによって静的アナライザー グループ内にカプセル化`MakeStaticAnalyzerGroup`します。

*リロガーグループ*\
*outputLogFile*で指定されたトレース ファイルにイベントを再ログするリロガー グループ。 リ[ロガー グループ](make-static-relogger-group.md)を作成するには、呼び出します。 [MakeDynamicReloggerGroup](make-dynamic-relogger-group.md)から取得した動的リロガー グループを使用する場合は、まずアドレスを渡すことによって静的リロガー グループ内に`MakeStaticReloggerGroup`カプセル化します。

### <a name="return-value"></a>戻り値

[RESULT_CODE](../other-types/result-code-enum.md)列挙型からの結果コード。

### <a name="remarks"></a>解説

入力トレースはアナライザー グループ*番号OfAnalysisPasss*時間を通過します。 パスを再ロギングする場合、同様のオプションはありません。 トレースは、すべての分析パスが完了した後、リロガーグループを一度だけトラフ渡します。

リロガー クラス内からの CPU サンプルのようなシステム イベントの再ロギングはサポートされていません。 出力トレースに保持するシステム イベントを決定するには、システムイベント*RetentionFlags*パラメーターを使用します。

::: moniker-end
