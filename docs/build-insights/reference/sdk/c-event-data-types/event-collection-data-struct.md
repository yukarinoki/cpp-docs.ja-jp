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
ms.openlocfilehash: 17daaa6feb784c501d180a982cd4ad2b405ccf67
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921088"
---
# <a name="event_collection_data-structure"></a>EVENT_COLLECTION_DATA 構造体

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

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
