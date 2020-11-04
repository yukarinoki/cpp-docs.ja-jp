---
title: FUNCTION_DATA 構造体
description: C++ Build Insights SDK FUNCTION_DATA 構造体のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FUNCTION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 42dcb5a8633f0b7a6cb2fbee8a227cd3f00e2572
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920997"
---
# <a name="function_data-structure"></a>FUNCTION_DATA 構造体

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`FUNCTION_DATA` 構造体は関数を表します。

## <a name="syntax"></a>構文

```cpp
typedef struct FUNCTION_DATA_TAG
{
    const char*         Name;

} FUNCTION_DATA;
```

## <a name="members"></a>メンバー

| 名前 | [説明] |
|--|--|
| `Name` | UTF-8 でエンコードされる関数の名前。 |

::: moniker-end
