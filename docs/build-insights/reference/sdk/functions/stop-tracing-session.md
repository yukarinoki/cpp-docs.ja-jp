---
title: セッションを停止します。
description: C++ ビルド インサイト SDK ストップトレースセッション関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c6c7a3c6ca47749491774cc3bcd97aae8aa663ea
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323526"
---
# <a name="stoptracingsession"></a>セッションを停止します。

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`StopTracingSession`関数は、進行中のトレース セッションを停止し、未処理のトレース ファイルを生成します。 ロー トレース ファイルは[、分析](analyze.md)[、AnalzeA、](analyze-a.md)および[AnalyzeW](analyze-w.md)関数に渡して、分析セッションを開始できます。 生のトレース ファイルは、[再ログ](relog.md)[、RelogA、](relog-a.md)および[RelogW](relog-w.md)関数に渡して、再ロギング セッションを開始することもできます。 呼び出`StopTracingSession`す実行可能ファイルには管理者権限が必要です。

## <a name="syntax"></a>構文

```cpp
inline RESULT_CODE StopTracingSession(
    const char*                 sessionName,
    const char*                 outputLogFile,
    TRACING_SESSION_STATISTICS* statistics);

inline RESULT_CODE StopTracingSession(
    const wchar_t*              sessionName
    const wchar_t*              outputLogFile,
    TRACING_SESSION_STATISTICS* statistics);
```

### <a name="parameters"></a>パラメーター

*Sessionname*\
停止するトレース セッションの名前。 [開始トレーシングセッション、開始トレーシングセッション](start-tracing-session.md)、または開始ト[レーシング](start-tracing-session-a.md)[セッションW](start-tracing-session-w.md)に渡されたものと同じセッション名を使用します。

*出力ログファイル*\
生のトレースを保存する必要がある最終出力ログ ファイルへのパス。

*統計*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md)オブジェクトへのポインター。 `StopTracingSession`このオブジェクトにトレース コレクションの統計情報を書き込む前に、このオブジェクトを返します。

### <a name="return-value"></a>戻り値

[RESULT_CODE](../other-types/result-code-enum.md)列挙型からの結果コード。

::: moniker-end
