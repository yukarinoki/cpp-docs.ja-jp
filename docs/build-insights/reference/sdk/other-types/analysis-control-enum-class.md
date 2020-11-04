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
ms.openlocfilehash: 0f4887d626c5e80a0afaa393e255f8ffedbd6b1f
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922621"
---
# <a name="analysiscontrol-enum-class"></a>AnalysisControl 列挙型クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`AnalysisControl` 列挙型クラスは、分析または再ログ記録セッションのフローを制御するために使用されます。 次に何が行われるかを制御するため、[IAnalyzer](ianalyzer-class.md) または [IRelogger](irelogger-class.md) メンバー関数から `AnalysisControl` コードが返されます。

## <a name="members"></a>メンバー

| 名前 | [説明] |
|--|--|
| `BLOCK` | アナライザーまたはリロガー グループにおける現在のイベントによるさらなる伝達を禁止します。 |
| `CANCEL` | 現在の分析か再ログ記録セッションをキャンセルします。 |
| `CONTINUE` | 現在の分析か再ログ記録セッションを通常どおり続けます。 次のアナライザーまたはリロガー グループ メンバーに現在のイベントを伝達します。 |
| `FAILURE` | 現在の分析または再ログ記録セッションをキャンセルし、エラーを信号で伝えます。 |

::: moniker-end
