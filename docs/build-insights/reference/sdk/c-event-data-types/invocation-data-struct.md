---
title: INVOCATION_DATA構造
description: C++ ビルド インサイト SDK INVOCATION_DATA構造参照。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4e1f428facac413d7a4a5c059452dd8cdb07be4c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325483"
---
# <a name="invocation_data-structure"></a>INVOCATION_DATA構造

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`INVOCATION_DATA`構造体は、コンパイラまたはリンカー呼び出しを記述します。

## <a name="syntax"></a>構文

```cpp
typedef struct INVOCATION_DATA_TAG
{
    int                         MSVCToolCode;

    INVOCATION_VERSION_DATA     ToolVersion;

    const char*                 ToolVersionString;
    const wchar_t*              WorkingDirectory;
    const wchar_t*              ToolPath;

} INVOCATION_DATA;
```

## <a name="members"></a>メンバー

|  |  |
|--|--|
| `MSVCToolCode` | 呼び出しの型を識別するコード。 詳細については、「 [MSVC_TOOL_CODE](msvc-tool-code-enum.md)」を参照してください。 |
| `ToolVersion` | 呼び出されたツールのバージョンを整数値のグループとして格納するオブジェクト。 |
| `ToolVersionString` | 呼び出されたツールのバージョンをテキスト形式で記述します。 |
| `WorkingDirectory` | 呼び出しが行われたディレクトリ。 |
| `ToolPath` | 呼び出されたツールの絶対パス。 |

::: moniker-end
