---
title: EVENT_COLLECTION_DATA構造
description: C++ ビルド インサイト SDK EVENT_COLLECTION_DATA構造リファレンスです。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EVENT_COLLECTION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 88ba39ede8c86f47c2e6458332ae005eddc06fda
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325693"
---
# <a name="event_collection_data-structure"></a>EVENT_COLLECTION_DATA構造

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

構造体`EVENT_COLLECTION_DATA`は[、EVENT_DATA](event-data-struct.md)要素の配列を記述します。

## <a name="syntax"></a>構文

```cpp
typedef struct EVENT_COLLECTION_DATA_TAG
{
    unsigned int            Count;
    const EVENT_DATA*       Elements;

} EVENT_COLLECTION_DATA;
```

## <a name="members"></a>メンバー

|  |  |
|--|--|
| `Count` | 配列内の`EVENT_DATA`要素の数。 |
| `Elements` | 配列の最初`EVENT_DATA`の要素へのポインター。 |

::: moniker-end
