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
ms.openlocfilehash: 488faf80fc073d5bd41712f66bd263e4043f978e
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923583"
---
# <a name="front_end_file_data-structure"></a>FRONT_END_FILE_DATA 構造体

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

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
