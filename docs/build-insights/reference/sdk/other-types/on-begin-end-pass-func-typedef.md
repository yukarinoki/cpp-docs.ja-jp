---
title: OnBeginEndPassFunc typedef
description: C++ Build Insights SDK OnBeginEndPassFunc typedef のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnBeginEndPassFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2a97ae792392e5cc0dc83bab00a92d05609a4815
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922491"
---
# <a name="onbeginendpassfunc-typedef"></a>OnBeginEndPassFunc typedef

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`OnBeginEndPassFunc` typedef は、[ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) 構造体と [RELOG_CALLBACKS](relog-callbacks-struct.md) 構造体で使用される関数シグネチャの 1 つです。

## <a name="syntax"></a>構文

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnBeginEndPassFunc)(
    void*                           callbackContext);
```

## <a name="members"></a>メンバー

| 名前 | 説明 |
|--|--|
| `callbackContext` |  |

::: moniker-end
