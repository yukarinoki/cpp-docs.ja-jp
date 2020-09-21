---
title: SYMBOL_NAME_DATA 構造体
description: C++ Build Insights SDK の SYMBOL_NAME_DATA 構造体のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SYMBOL_NAME_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d234c6c225eff87a0eecd98fa5ff60bf92db97f5
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041914"
---
# <a name="symbol_name_data-structure"></a>SYMBOL_NAME_DATA 構造体

::: moniker range="<=vs-2015"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=vs-2017"

`SYMBOL_NAME_DATA` 構造体はコンパイラ フロントエンド シンボルを表します。

## <a name="syntax"></a>構文

```cpp
typedef struct SYMBOL_NAME_DATA_TAG
{
    unsigned long long  Key;
    const char*         Name;

} SYMBOL_NAME_DATA;
```

## <a name="members"></a>メンバー

| 名前 | [説明] |
|--|--|
| `Key` | シンボルのキー。 この値は分析対象のトレース内で一意です。 |
| `Name` | シンボルの名前。 |

## <a name="remarks"></a>注釈

2 つの異なるコンパイラ フロントエンド パスから受け取るシンボルに同じ名前が付いていても、キーが異なることがあります。 その場合、シンボル名を利用し、2 つの種類が同じかどうかを判断します。

::: moniker-end
