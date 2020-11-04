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
ms.openlocfilehash: 98ac234b702ef2c73a5c8d90ee6bf4dc59349ed6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920971"
---
# <a name="invocation_data-structure"></a>INVOCATION_DATA 構造体

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

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
