---
title: SYMBOL_NAME_DATA構造
description: C++ ビルド インサイト SDK SYMBOL_NAME_DATA構造リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SYMBOL_NAME_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1217572f20a772fde629533d6ab170c14dc5b5e0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325335"
---
# <a name="symbol_name_data-structure"></a>SYMBOL_NAME_DATA構造

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`SYMBOL_NAME_DATA`構造体は、コンパイラのフロントエンド シンボルを記述します。

## <a name="syntax"></a>構文

```cpp
typedef struct SYMBOL_NAME_DATA_TAG
{
    unsigned long long  Key;
    const char*         Name;

} SYMBOL_NAME_DATA;
```

## <a name="members"></a>メンバー

|  |  |
|--|--|
| `Key` | シンボルのキー。 この値は、分析されるトレース内で一意です。 |
| `Name` | シンボルの名前。 |

## <a name="remarks"></a>解説

2 つの異なるコンパイラ のフロントエンド パスから来るシンボルは、同じ名前を持つことができますが、別のキーを持つことができます。 この場合、シンボル名を使用して、2 つの型が同じかどうかを判断します。

::: moniker-end
