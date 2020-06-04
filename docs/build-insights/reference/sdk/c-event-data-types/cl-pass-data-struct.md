---
title: CL_PASS_DATA構造
description: C++ ビルド インサイト SDK CL_PASS_DATA構造リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CL_PASS_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b0a41e59068ade285f1ffa1a9ce13734ef5f1f32
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325710"
---
# <a name="cl_pass_data-structure"></a>CL_PASS_DATA構造

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`CL_PASS_DATA`構造体は、コンパイル パスを記述します。

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

|  |  |
|--|--|
| `TranslationUnitPassCode` | 実行されるコンパイル パスを識別するコード。 詳細については、「 [TRANSLATION_UNIT_PASS_CODE](translation-unit-pass-code-enum.md)」を参照してください。 |
| `InputSourcePath` | このコンパイル パスが実行される C または C++ ソース ファイル。 |
| `OutputObjectPath` | コンパイラによって生成されるオブジェクト ファイル。 |

::: moniker-end
