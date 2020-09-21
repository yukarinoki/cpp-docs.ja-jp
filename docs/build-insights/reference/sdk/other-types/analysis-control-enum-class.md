---
title: AnalysisControl 列挙型クラス
description: C++ Build Insights SDK AnalysisControl 列挙型参照。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalysisControl
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a7b7fc0ce404f414b3ec07449bdc110d578fa101
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90042018"
---
# <a name="analysiscontrol-enum-class"></a>AnalysisControl 列挙型クラス

::: moniker range="<=vs-2015"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=vs-2017"

`AnalysisControl` 列挙型クラスは、分析または再ログ記録セッションのフローを制御するために使用されます。 次に何が行われるかを制御するため、[IAnalyzer](ianalyzer-class.md) または [IRelogger](irelogger-class.md) メンバー関数から `AnalysisControl` コードが返されます。

## <a name="members"></a>メンバー

| 名前 | [説明] |
|--|--|
| `BLOCK` | アナライザーまたはリロガー グループにおける現在のイベントによるさらなる伝達を禁止します。 |
| `CANCEL` | 現在の分析か再ログ記録セッションをキャンセルします。 |
| `CONTINUE` | 現在の分析か再ログ記録セッションを通常どおり続けます。 次のアナライザーまたはリロガー グループ メンバーに現在のイベントを伝達します。 |
| `FAILURE` | 現在の分析または再ログ記録セッションをキャンセルし、エラーを信号で伝えます。 |

::: moniker-end
