---
title: コントロール列挙型クラス
description: C++ ビルド インサイト SDK 分析コントロール列挙型の参照。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalysisControl
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e9431f878390127f2cefbe8f0ee42ca509e147de
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323640"
---
# <a name="analysiscontrol-enum-class"></a>コントロール列挙型クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

enum`AnalysisControl`クラスは、分析セッションまたは再ロギング セッションのフローを制御するために使用されます。 IAnalyzer`AnalysisControl`または[IAnalyzer](ianalyzer-class.md)[IRelogger](irelogger-class.md)メンバー関数からコードを返して、次に何が起こるかを制御します。

## <a name="members"></a>メンバー

|  |  |
|--|--|
| `BLOCK` | 現在のイベントがアナライザまたはリロガー グループでさらに伝播しないようにします。 |
| `CANCEL` | 現在の分析セッションまたは再ロギング セッションをキャンセルします。 |
| `CONTINUE` | 現在の分析セッションまたは再ロギング セッションを通常どおり続行します。 現在のイベントを次のアナライザまたはリロガー グループ メンバーに伝播します。 |
| `FAILURE` | 現在の分析または再ロギング セッションをキャンセルし、エラーを通知します。 |

::: moniker-end
