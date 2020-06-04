---
title: ANALYSIS_DESCRIPTOR構造
description: C++ ビルド インサイト SDK ANALYSIS_DESCRIPTOR構造参照。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1de7f2a5bc3f02a327daaecf8c2cebc44687ba43
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323608"
---
# <a name="analysis_descriptor-structure"></a>ANALYSIS_DESCRIPTOR構造

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`ANALYSIS_DESCRIPTOR`構造は[、AnalyzeA](../functions/analyze-a.md)関数および[AnalyzeW](../functions/analyze-w.md)関数で使用されます。 Windows イベント トレース (ETW) トレースの分析方法について説明します。

## <a name="syntax"></a>構文

```cpp
typedef struct ANALYSIS_DESCRIPTOR_TAG
{
    unsigned                NumberOfPasses;
    ANALYSIS_CALLBACKS      Callbacks;
    void*                   Context;
} ANALYSIS_DESCRIPTOR;
```

## <a name="members"></a>メンバー

|  |  |
|--|--|
| `NumberOfPasses` | ETW トレースで実行する必要がある分析パスの数。 |
| `Callbacks` | 分析セッション中に呼び出す関数を指定する[ANALYSIS_CALLBACKS](analysis-callbacks-struct.md)オブジェクト。 |
| `Context` | で指定されたすべてのコールバック関数に引数として渡される、ユーザー指定のコンテキスト`Callbacks` |

## <a name="remarks"></a>解説

構造体`Callbacks`は、非メンバー関数へのポインターのみを受け入れます。 この制限は、オブジェクト ポインタに`Context`設定することで回避できます。 このオブジェクト ポインタは、すべての非メンバー コールバック関数に引数として渡されます。 このポインターを使用して、メンバー以外のコールバック関数内からメンバー関数を呼び出します。

::: moniker-end
