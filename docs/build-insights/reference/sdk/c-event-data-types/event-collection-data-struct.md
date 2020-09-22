---
title: EVENT_COLLECTION_DATA 構造体
description: C++ Build Insights SDK の EVENT_COLLECTION_DATA 構造体のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EVENT_COLLECTION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 58be46d31af154bfe7ecef5c440092eaafdcbb0f
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90039600"
---
# <a name="event_collection_data-structure"></a>EVENT_COLLECTION_DATA 構造体

::: moniker range="<=vs-2015"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=vs-2017"

`EVENT_COLLECTION_DATA` 構造体は [EVENT_DATA](event-data-struct.md) 要素の配列を表します。

## <a name="syntax"></a>構文

```cpp
typedef struct EVENT_COLLECTION_DATA_TAG
{
    unsigned int            Count;
    const EVENT_DATA*       Elements;

} EVENT_COLLECTION_DATA;
```

## <a name="members"></a>メンバー

| 名前 | [説明] |
|--|--|
| `Count` | 配列内の `EVENT_DATA` 要素の数。 |
| `Elements` | 配列における最初の `EVENT_DATA` 要素のポインター。 |

::: moniker-end
