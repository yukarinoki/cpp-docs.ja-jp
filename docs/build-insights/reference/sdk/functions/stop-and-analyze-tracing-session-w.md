---
title: StopAndAnalyzeTracingSessionW
description: C++ Build Insights SDK の StopAndAnalyzeTracingSessionW 関数のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndAnalyzeTracingSessionW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e353e9d0038fcd764a9c4d03170f0a3c949bc43d
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919983"
---
# <a name="stopandanalyzetracingsessionw"></a>StopAndAnalyzeTracingSessionW

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`StopAndAnalyzeTracingSessionW` 関数により、実行中のトレース セッションが停止されて、結果のトレースが一時ファイルに保存されます。 その後、その一時ファイルを入力として使用して、分析セッションが直ちに開始されます。 この関数を呼び出す実行可能ファイルには、管理者権限が必要です。

## <a name="syntax"></a>構文

```cpp
enum RESULT_CODE StopAndAnalyzeTracingSessionW(
    const wchar_t*              sessionName,
    TRACING_SESSION_STATISTICS* statistics,
    const ANALYSIS_DESCRIPTOR*  analysisDescriptor);
```

### <a name="parameters"></a>パラメーター

*sessionName*\
停止するトレース セッションの名前。 [StartTracingSession](start-tracing-session.md)、[StartTracingSessionA](start-tracing-session-a.md)、[StartTracingSessionW](start-tracing-session-w.md) に渡したものと同じセッション名を使用します。

*statistics*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) オブジェクトへのポインター。 `StopAndAnalyzeTracingSessionW` によって、戻る前に、このオブジェクトのトレース コレクション統計情報が書き込まれます。

*analysisDescriptor*\
[ANALYSIS_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) オブジェクトへのポインター。 `StopAndAnalyzeTracingSessionW` によって開始される分析セッションを構成するには、このオブジェクトを使用します。

### <a name="return-value"></a>戻り値

[RESULT_CODE](../other-types/result-code-enum.md) 列挙型の結果コード。

::: moniker-end
