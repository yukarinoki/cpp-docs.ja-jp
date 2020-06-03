---
title: NAME_VALUE_PAIR_DATA構造
description: C++ ビルド インサイト SDK NAME_VALUE_PAIR_DATA構造リファレンスです。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- NAME_VALUE_PAIR_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4a0bf8e8ba32d94d30a56d0ef26ca4ed0c9b0711
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325353"
---
# <a name="name_value_pair_data-structure"></a>NAME_VALUE_PAIR_DATA構造

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

構造体`NAME_VALUE_PAIR_DATA`は、名前と値のペアを記述します。

## <a name="syntax"></a>構文

```cpp
typedef struct NAME_VALUE_PAIR_DATA_TAG
{
    const wchar_t*      Name;
    const wchar_t*      Value;
} NAME_VALUE_PAIR_DATA;
```

## <a name="members"></a>メンバー

|  |  |
|--|--|
| `Name` | 名前です。 |
| `Value` | 値。 |

::: moniker-end
