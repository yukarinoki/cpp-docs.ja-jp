---
title: FILE_DATA構造
description: C++ ビルド インサイト SDK FILE_DATA構造参照。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6b7b0129c54fa4b1d5285bafb38761da45bab4e5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325587"
---
# <a name="file_data-structure"></a>FILE_DATA構造

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`FILE_DATA`構造体は、ファイルの入出力を記述します。

## <a name="syntax"></a>構文

```cpp
typedef struct FILE_DATA_TAG
{
    const wchar_t*      Path;
    int                 TypeCode;

} FILE_DATA;
```

## <a name="members"></a>メンバー

|  |  |
|--|--|
| `Path` | ファイルの絶対パス |
| `TypeCode` | ファイルの種類を記述するコード。 詳細については、「 [FILE_TYPE_CODE](file-type-code-enum.md)」を参照してください。 |

::: moniker-end
