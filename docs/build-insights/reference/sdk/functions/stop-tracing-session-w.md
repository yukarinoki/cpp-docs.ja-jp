---
title: StopTracingSessionW
description: C++ Build Insights SDK の StopTracingSessionW 関数のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopTracingSessionW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 116d76b83f93e126bcb5dfc0d3f9b76d45df89fe
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919944"
---
# <a name="stoptracingsessionw"></a>StopTracingSessionW

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`StopTracingSessionW` 関数により、実行中のトレース セッションが停止されて、生のトレース ファイルが生成されます。 生のトレース ファイルを [Analyze](analyze.md)、[AnalzeA](analyze-a.md)、[AnalyzeW](analyze-w.md) 関数に渡して、分析セッションを開始できます。 また、生のトレース ファイルを [Relog](relog.md)、[RelogA](relog-a.md)、[RelogW](relog-w.md) 関数に渡して、再ログ記録セッションを開始できます。 `StopTracingSessionW` を呼び出す実行可能ファイルには管理者権限が必要です。

## <a name="syntax"></a>構文

```cpp
enum RESULT_CODE StopTracingSessionW(
    const wchar_t*              sessionName,
    const char*                 outputLogFile,
    TRACING_SESSION_STATISTICS* statistics);
```

### <a name="parameters"></a>パラメーター

*sessionName*\
停止するトレース セッションの名前。 [StartTracingSession](start-tracing-session.md)、[StartTracingSessionA](start-tracing-session-a.md)、[StartTracingSessionW](start-tracing-session-w.md) に渡したものと同じセッション名を使用します。

*outputLogFile*\
生のトレースを保存する必要がある最終的な出力ログ ファイルへのパス。

*statistics*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) オブジェクトへのポインター。 `StopTracingSessionW` によって、戻る前に、このオブジェクトのトレース コレクション統計情報が書き込まれます。

### <a name="return-value"></a>戻り値

[RESULT_CODE](../other-types/result-code-enum.md) 列挙型の結果コード。

::: moniker-end
