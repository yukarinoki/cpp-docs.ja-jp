---
title: CALLBACK_CODE 列挙型
description: C++ Build Insights SDK の CALLBACK_CODE 列挙型のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CALLBACK_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 146d191d0b642ad538f5a314016b41fdbdf26113
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922593"
---
# <a name="callback_code-enum"></a>CALLBACK_CODE 列挙型

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`CALLBACK_CODE` 列挙型は、分析または再ログ記録セッションのフローを制御するために使用されます。 次に行う必要があることを制御するため、[ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) または [RELOG_CALLBACKS](relog-callbacks-struct.md) の関数から CALLBACK_CODE の値が返されます。

## <a name="members"></a>メンバー

| 名前 | 値 | 説明 |
|--|--|--|
| `CALLBACK_CODE_ANALYSIS_SUCCESS` | 1 (0x00000001) | 現在の分析か再ログ記録セッションを通常どおり続けます。 |
| `CALLBACK_CODE_ANALYSIS_FAILURE` | 2 (0x00000002) | 現在の分析または再ログ記録セッションをキャンセルし、エラーを信号で伝えます。 |
| `CALLBACK_CODE_ANALYSIS_CANCEL` | 4 (0x00000004) | 現在の分析か再ログ記録セッションをキャンセルします。 |

::: moniker-end
