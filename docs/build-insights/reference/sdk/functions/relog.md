---
title: Relog
description: C++ ビルド インサイト SDK リログ関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Relog
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 28b290d2bf2880ce2f534fa1cd91750890e2fead
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323776"
---
# <a name="relog"></a>Relog

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`Relog`関数は、Windows イベント・トレース (ETW) トレースから MSVC イベントを読み取り、新しい変更された ETW トレースに書き込むために使用されます。

## <a name="syntax"></a>構文

```cpp
template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE Relog(
    const char*                                   inputLogFile,
    const char*                                   outputLogFile,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);

template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE Relog(
    const wchar_t*                                inputLogFile,
    const wchar_t*                                outputLogFile,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);
```

### <a name="parameters"></a>パラメーター

*グループメンバー*\
このパラメーターは常に推定されます。

*トレロガーグループメンバー*\
このパラメーターは常に推定されます。

*入力ログファイル*\
イベントの読み取りを行う入力 ETW トレース。

*出力ログファイル*\
新しいイベントを書き込むファイル。

*分析パスの数*\
入力トレースで実行する解析パスの数。 トレースは、指定されたアナライザー グループを 1 回、分析パスごとに渡されます。

*フラグ*\
ログに記録されたトレースに保持するシステム ETW イベントを指定するビットマスク。 詳細については、「 [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](../other-types/relog-retention-system-event-flags-constants.md)」を参照してください。

*アナライザグループ*\
再ロギング セッションの分析フェーズで使用されるアナライザー グループ。 [アナライザー グループ](make-static-analyzer-group.md)を作成するには、呼び出します。 [から](make-dynamic-analyzer-group.md)取得した動的アナライザー グループを使用するには、まずアドレスをに渡すことによって静的アナライザー グループ内にカプセル`MakeStaticAnalyzerGroup`化します。

*リロガーグループ*\
*outputLogFile*で指定されたトレース ファイルにイベントを再ログするリロガー グループ。 リ[ロガー グループ](make-static-relogger-group.md)を作成するには、呼び出します。 [MakeDynamicReloggerGroup](make-dynamic-relogger-group.md)から取得した動的リロガー グループを使用するには、まずアドレスを渡すことによって静的リロガー グループ内`MakeStaticReloggerGroup`にカプセル化します。

### <a name="return-value"></a>戻り値

[RESULT_CODE](../other-types/result-code-enum.md)列挙型からの結果コード。

### <a name="remark"></a>注記

入力トレースはアナライザー グループ*番号OfAnalysisPasss*時間を通過します。 パスを再ロギングする場合、同様のオプションはありません。 トレースは、すべての分析パスが完了した後、リロガーグループを一度だけトラフ渡します。

リロガー クラス内からの CPU サンプルのようなシステム イベントの再ロギングはサポートされていません。 出力トレースに保持するシステム イベントを決定するには、システムイベント*RetentionFlags*パラメーターを使用します。

::: moniker-end
