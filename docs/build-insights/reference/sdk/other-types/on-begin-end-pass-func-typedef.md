---
title: タイプデフ
description: C++ ビルド インサイト SDK オンビエンドパスファンク タイプ定義リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnBeginEndPassFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3b3fc453245a47463c29ceeb30dfdc48c79aef35
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329087"
---
# <a name="onbeginendpassfunc-typedef"></a>タイプデフ

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

typedef は`OnBeginEndPassFunc`[、ANALYSIS_CALLBACKS](analysis-callbacks-struct.md)および[RELOG_CALLBACKS](relog-callbacks-struct.md)構造体で使用される関数シグネチャの 1 つです。

## <a name="syntax"></a>構文

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnBeginEndPassFunc)(
    void*                           callbackContext);
```

## <a name="members"></a>メンバー

|  |  |
|--|--|
| `callbackContext` |  |

::: moniker-end
