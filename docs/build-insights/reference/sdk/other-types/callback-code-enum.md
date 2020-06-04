---
title: 列挙CALLBACK_CODE
description: C++ ビルド インサイト SDK CALLBACK_CODE列挙型参照。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CALLBACK_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d0d3dcc70040f562cd40755188e545f709a807b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329187"
---
# <a name="callback_code-enum"></a>列挙CALLBACK_CODE

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

列挙`CALLBACK_CODE`型は、分析セッションまたは再ロギング セッションのフローを制御するために使用されます。 次に何が起こるかを制御するために[、ANALYSIS_CALLBACKS](analysis-callbacks-struct.md)または[RELOG_CALLBACKS](relog-callbacks-struct.md)の関数からCALLBACK_CODE値を返します。

## <a name="members"></a>メンバー

| 名前 | [値] | 説明 |
|--|--|--|
| `CALLBACK_CODE_ANALYSIS_SUCCESS` | 1 (0x00000001) | 現在の分析セッションまたは再ロギング セッションを通常どおり続行します。 |
| `CALLBACK_CODE_ANALYSIS_FAILURE` | 2 (0x0000002) | 現在の分析または再ロギング セッションをキャンセルし、エラーを通知します。 |
| `CALLBACK_CODE_ANALYSIS_CANCEL` | 4 (0x0000004) | 現在の分析セッションまたは再ロギング セッションをキャンセルします。 |

::: moniker-end
