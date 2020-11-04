---
title: FUNCTION_FORCE_INLINEE_DATA 構造体
description: C++ Build Insights SDK の FUNCTION_FORCE_INLINEE_DATA 構造体のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FUNCTION_FORCE_INLINEE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e9de87bdc4e5a1a3e25483f8ba1766609c7d7622
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923568"
---
# <a name="function_force_inlinee_data-structure"></a>FUNCTION_FORCE_INLINEE_DATA 構造体

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`FUNCTION_FORCE_INLINEE_DATA` 構造体は、強制インライン関数を表します。

## <a name="syntax"></a>構文

```cpp
typedef struct FUNCTION_FORCE_INLINEE_DATA_TAG
{
    const char*         Name;
    unsigned short      Size;

} FUNCTION_FORCE_INLINEE_DATA;
```

## <a name="members"></a>メンバー

| 名前 | [説明] |
|--|--|
| `Name` | UTF-8 でエンコードされる関数の名前。 |
| `Size` | 関数のサイズ。中間の命令の数として表現されます。 |

::: moniker-end
