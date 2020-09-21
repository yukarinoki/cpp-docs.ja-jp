---
title: FRONT_END_FILE_DATA 構造体
description: C++ Build Insights SDK の FRONT_END_FILE_DATA 構造体のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FRONT_END_FILE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c2519bfd478776f54cee59ba08b83ea00b96beff
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041758"
---
# <a name="front_end_file_data-structure"></a>FRONT_END_FILE_DATA 構造体

::: moniker range="<=vs-2015"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=vs-2017"

`FRONT_END_FILE_DATA` 構造体は、コンパイラ フロント エンドによるファイルの処理を表します。

## <a name="syntax"></a>構文

```cpp
typedef struct FRONT_END_FILE_DATA_TAG
{
    const char*         Path;

} FRONT_END_FILE_DATA;
```

## <a name="members"></a>メンバー

| 名前 | [説明] |
|--|--|
| `Path` | UTF-8 でエンコードされるファイルの絶対パス。 |

::: moniker-end
