---
title: MSVC_TOOL_CODE 列挙型
description: C++ Build Insights SDK の MSVC_TOOL_CODE 列挙型のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MSVC_TOOL_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4f539401f304d5d39983ec8f97cc8c99b19399d9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920958"
---
# <a name="msvc_tool_code-enum"></a>MSVC_TOOL_CODE 列挙型

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`MSVC_TOOL_CODE` 列挙型。

## <a name="members"></a>メンバー

| 名前 | 値 | 説明 |
|--|--|--|
| `MSVC_TOOL_CODE_CL` | 0 (0x00000000) | コンパイラ (cl.exe)。 |
| `MSVC_TOOL_CODE_LINK` | 1 (0x00000001) | リンカー (link.exe)。 |

## <a name="remarks"></a>注釈

C SDK 関数によって使用されます。

::: moniker-end
