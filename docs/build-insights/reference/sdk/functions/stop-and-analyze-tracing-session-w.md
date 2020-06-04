---
title: 停止してトレースセッションを分析します。
description: C++ ビルド インサイト SDK StopAndAnalyze トレースセッション関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndAnalyzeTracingSessionW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2f5f232c3e58c66bc36099d954d97a8f945187ef
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323715"
---
# <a name="stopandanalyzetracingsessionw"></a>停止してトレースセッションを分析します。

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`StopAndAnalyzeTracingSessionW`関数は、進行中のトレース・セッションを停止し、結果のトレースを一時ファイルに保管します。 分析セッションは、その後、入力として一時ファイルを使用してすぐに開始されます。 この関数を呼び出す実行可能ファイルには、管理者権限が必要です。

## <a name="syntax"></a>構文

```cpp
enum RESULT_CODE StopAndAnalyzeTracingSessionW(
    const wchar_t*              sessionName,
    TRACING_SESSION_STATISTICS* statistics,
    const ANALYSIS_DESCRIPTOR*  analysisDescriptor);
```

### <a name="parameters"></a>パラメーター

*Sessionname*\
停止するトレース セッションの名前。 [開始トレーシングセッション、開始トレーシングセッション](start-tracing-session.md)、または開始ト[レーシング](start-tracing-session-a.md)[セッションW](start-tracing-session-w.md)に渡されたものと同じセッション名を使用します。

*統計*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md)オブジェクトへのポインター。 `StopAndAnalyzeTracingSessionW`このオブジェクトにトレース コレクションの統計情報を書き込む前に、このオブジェクトを返します。

*分析記述子*\
[ANALYSIS_DESCRIPTOR](../other-types/analysis-descriptor-struct.md)オブジェクトへのポインター。 によって開始される分析セッションを構成するには、このオブジェクトを使用`StopAndAnalyzeTracingSessionW`します。

### <a name="return-value"></a>戻り値

[RESULT_CODE](../other-types/result-code-enum.md)列挙型からの結果コード。

::: moniker-end
