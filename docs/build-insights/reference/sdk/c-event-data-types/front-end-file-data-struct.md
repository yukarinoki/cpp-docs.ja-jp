---
title: FRONT_END_FILE_DATA構造
description: C++ ビルド インサイト SDK FRONT_END_FILE_DATA構造リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FRONT_END_FILE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7fb6b6fff4f309a3539a290f279d1e31cb1ed76b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325547"
---
# <a name="front_end_file_data-structure"></a>FRONT_END_FILE_DATA構造

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`FRONT_END_FILE_DATA`構造体は、コンパイラのフロントエンドによるファイルの処理を記述します。

## <a name="syntax"></a>構文

```cpp
typedef struct FRONT_END_FILE_DATA_TAG
{
    const char*         Path;

} FRONT_END_FILE_DATA;
```

## <a name="members"></a>メンバー

|  |  |
|--|--|
| `Path` | ファイルの絶対パスは UTF-8 でエンコードされています。 |

::: moniker-end
