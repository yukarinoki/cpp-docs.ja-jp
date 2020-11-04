---
title: CL_PASS_DATA 構造体
description: C++ Build Insights SDK の CL_PASS_DATA 構造体のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CL_PASS_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 24e524b802a124f38043f3b69afed7f1aa9cd156
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923654"
---
# <a name="cl_pass_data-structure"></a>CL_PASS_DATA 構造体

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`CL_PASS_DATA` 構造体はコンパイル パスを表します。

## <a name="syntax"></a>構文

```cpp
typedef struct CL_PASS_DATA_TAG
{
    int                         TranslationUnitPassCode;
    const wchar_t*              InputSourcePath;
    const wchar_t*              OutputObjectPath;

} CL_PASS_DATA;
```

## <a name="members"></a>メンバー

| 名前 | [説明] |
|--|--|
| `TranslationUnitPassCode` | 実行されているコンパイル パスを識別するコード。 詳細については、[TRANSLATION_UNIT_PASS_CODE](translation-unit-pass-code-enum.md) に関するページを参照してください。 |
| `InputSourcePath` | このコンパイル パスが実行されている C または C++ のソース ファイル。 |
| `OutputObjectPath` | コンパイラによって生成されているオブジェクト ファイル。 |

::: moniker-end
