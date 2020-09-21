---
title: INVOCATION_DATA 構造体
description: C++ Build Insights SDK INVOCATION_DATA 構造体のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 48b4c28d3c01d61a31343894312a54ba2ab17a70
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041641"
---
# <a name="invocation_data-structure"></a>INVOCATION_DATA 構造体

::: moniker range="<=vs-2015"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=vs-2017"

`INVOCATION_DATA` 構造体は、コンパイラまたはリンカーの呼び出しを表します。

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

| 名前 | [説明] |
|--|--|
| `MSVCToolCode` | 呼び出しの種類を識別するコード。 詳細については、[MSVC_TOOL_CODE](msvc-tool-code-enum.md) に関するページを参照してください。 |
| `ToolVersion` | 呼び出されたツールのバージョンを整数値として格納するオブジェクト。 |
| `ToolVersionString` | 呼び出されたツールのバージョンをテキスト形式で表します。 |
| `WorkingDirectory` | 呼び出し元のディレクトリ。 |
| `ToolPath` | 呼び出されたツールの絶対パス。 |

::: moniker-end
