---
title: ANALYSIS_DESCRIPTOR 構造体
description: C++ Build Insights SDK の ANALYSIS_DESCRIPTOR 構造体のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ec2d0a76618d6ff2cf0e7fdff7e360a4fd2e0174
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919853"
---
# <a name="analysis_descriptor-structure"></a>ANALYSIS_DESCRIPTOR 構造体

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`ANALYSIS_DESCRIPTOR` 構造体は [AnalyzeA](../functions/analyze-a.md) 関数と [AnalyzeW](../functions/analyze-w.md) 関数と共に使用されます。 ここでは、Windows イベント トレーシング (ETW) を分析する方法について説明します。

## <a name="syntax"></a>構文

```cpp
typedef struct ANALYSIS_DESCRIPTOR_TAG
{
    unsigned                NumberOfPasses;
    ANALYSIS_CALLBACKS      Callbacks;
    void*                   Context;
} ANALYSIS_DESCRIPTOR;
```

## <a name="members"></a>メンバー

| 名前 | [説明] |
|--|--|
| `NumberOfPasses` | ETW トレースで実行される分析パスの数。 |
| `Callbacks` | 分析セッション中に呼び出す関数を指定する [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) オブジェクト。 |
| `Context` | `Callbacks` で指定されたすべてのコールバック関数に引数として渡されるユーザー指定のコンテキスト |

## <a name="remarks"></a>注釈

`Callbacks` 構造体は、非メンバー関数へのポインターのみを受け入れます。 この制限は、`Context` をオブジェクト ポインターに設定することによって回避できます。 このオブジェクト ポインターは、すべての非メンバー コールバック関数に引数として渡されます。 メンバー関数を非メンバー コールバック関数内から呼び出すには、このポインターを使用します。

::: moniker-end
