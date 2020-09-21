---
title: INVOCATION_VERSION_DATA 構造体
description: C++ Build Insights SDK INVOCATION_VERSION_DATA 構造体のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_VERSION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ec54c560dd408dc3beecbc20eaac69d389c7ec37
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041560"
---
# <a name="invocation_version_data-structure"></a>INVOCATION_VERSION_DATA 構造体

::: moniker range="<=vs-2015"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=vs-2017"

`INVOCATION_VERSION_DATA` 構造体は、整数値のグループとしてバージョン番号を表します。

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

| 名前 | [説明] |
|--|--|
| `VersionMajor` | バージョンのメジャー番号。 |
| `VersionMinor` | バージョンのマイナー番号。 |
| `BuildNumberMajor` | ビルドのメジャー番号。 |
| `BuildNumberMinor` | ビルドのマイナー番号。 |

::: moniker-end
