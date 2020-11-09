---
title: StopAndRelogTracingSessionA
description: C++ Build Insights SDK の StopAndRelogTracingSessionA 関数のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSessionA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: de69ca379c6f0ef46e23d2b4a78c72518e997572
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919970"
---
# <a name="stopandrelogtracingsessiona"></a>StopAndRelogTracingSessionA

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`StopAndRelogTracingSessionA` 関数により、実行中のトレース セッションが停止されて、結果のトレースが一時ファイルに保存されます。 その後、その一時ファイルを入力として使用して、再ログ記録セッションが直ちに開始されます。 再ログ記録セッションによって生成された最終的な再ログ記録されたトレースが、呼び出し元によって指定されたファイルに保存されます。 この関数を呼び出す実行可能ファイルには、管理者権限が必要です。

## <a name="syntax"></a>構文

```cpp
enum RESULT_CODE StopAndRelogTracingSessionA(
    const char*                 sessionName,
    const char*                 outputLogFile,
    TRACING_SESSION_STATISTICS* statistics,
    const RELOG_DESCRIPTOR*     relogDescriptor);
```

### <a name="parameters"></a>パラメーター

*sessionName*\
停止するトレース セッションの名前。 [StartTracingSession](start-tracing-session.md)、[StartTracingSessionA](start-tracing-session-a.md)、[StartTracingSessionW](start-tracing-session-w.md) に渡したものと同じセッション名を使用します。

*outputLogFile*\
再ログ記録セッションによって生成される再ログ記録されたトレースを書き込むファイル。

*statistics*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) オブジェクトへのポインター。 `StopAndRelogTracingSessionA` によって、戻る前に、このオブジェクトのトレース コレクション統計情報が書き込まれます。

*analysisDescriptor*\
[RELOG_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) オブジェクトへのポインター。 `StopAndRelogTracingSessionA` によって開始される再ログ記録セッションを構成するには、このオブジェクトを使用します。

### <a name="return-value"></a>戻り値

[RESULT_CODE](../other-types/result-code-enum.md) 列挙型の結果コード。

::: moniker-end
