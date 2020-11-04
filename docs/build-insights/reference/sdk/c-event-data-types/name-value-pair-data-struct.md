---
title: NAME_VALUE_PAIR_DATA 構造体
description: C++ Build Insights SDK の NAME_VALUE_PAIR_DATA 構造体のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- NAME_VALUE_PAIR_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: bab9f7ccedc4a94478d50863f2fae248722468e2
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923544"
---
# <a name="name_value_pair_data-structure"></a>NAME_VALUE_PAIR_DATA 構造体

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`NAME_VALUE_PAIR_DATA` 構造体は、名前と値のペアを表します。

## <a name="syntax"></a>構文

```cpp
typedef struct NAME_VALUE_PAIR_DATA_TAG
{
    const wchar_t*      Name;
    const wchar_t*      Value;
} NAME_VALUE_PAIR_DATA;
```

## <a name="members"></a>メンバー

| 名前 | [説明] |
|--|--|
| `Name` | 名前。 |
| `Value` | 値。 |

::: moniker-end
