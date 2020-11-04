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
ms.openlocfilehash: ebed659ade4610b50ae06f2a32851522073a58d8
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923559"
---
# <a name="invocation_version_data-structure"></a>INVOCATION_VERSION_DATA 構造体

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

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
