---
title: FILE_DATA 構造体
description: C++ Build Insights SDK の FILE_DATA 構造体のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1a03c2c47be82fac2ee036a632e4df775f6c4f5f
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923599"
---
# <a name="file_data-structure"></a>FILE_DATA 構造体

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`FILE_DATA` 構造体はファイルの入力または出力を表します。

## <a name="syntax"></a>構文

```cpp
typedef struct FILE_DATA_TAG
{
    const wchar_t*      Path;
    int                 TypeCode;

} FILE_DATA;
```

## <a name="members"></a>メンバー

| 名前 | [説明] |
|--|--|
| `Path` | ファイルの絶対パス |
| `TypeCode` | ファイルの種類を表すコード。 詳細については、[FILE_TYPE_CODE](file-type-code-enum.md) に関するページを参照してください。 |

::: moniker-end
