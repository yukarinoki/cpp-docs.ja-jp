---
title: INVOCATION_VERSION_DATA構造
description: C++ ビルド インサイト SDK INVOCATION_VERSION_DATA構造参照。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_VERSION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1211b4eb999fd63767af71c6884d7d20d6920df0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325472"
---
# <a name="invocation_version_data-structure"></a>INVOCATION_VERSION_DATA構造

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`INVOCATION_VERSION_DATA`構造体は、バージョン番号を整数値のグループとして記述します。

## <a name="syntax"></a>構文

```cpp
typedef struct INVOCATION_VERSION_DATA_TAG
{
    unsigned short VersionMajor;
    unsigned short VersionMinor;
    unsigned short BuildNumberMajor;
    unsigned short BuildNumberMinor;

} INVOCATION_VERSION_DATA;
```

## <a name="members"></a>メンバー

|  |  |
|--|--|
| `VersionMajor` | バージョンのメジャー番号。 |
| `VersionMinor` | バージョンのマイナー番号。 |
| `BuildNumberMajor` | ビルドのメジャー番号。 |
| `BuildNumberMinor` | ビルドのマイナー番号。 |

::: moniker-end
