---
title: 列挙TRANSLATION_UNIT_PASS_CODE
description: C++ ビルド インサイト SDK TRANSLATION_UNIT_PASS_CODE列挙型参照。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRANSLATION_UNIT_PASS_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b0162d7e53bb7ee7035b94a6b640f6db87cd8b8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325285"
---
# <a name="translation_unit_pass_code-enum"></a>列挙TRANSLATION_UNIT_PASS_CODE

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

列挙`TRANSLATION_UNIT_PASS_CODE`型。

## <a name="members"></a>メンバー

| 名前 | [値] | 説明 |
|--|--|--|
| `TRANSLATION_UNIT_PASS_CODE_FRONT_END` | 0 (0x0000000) | ソース コードを解析し、中間言語に変換するフロントエンド パス。 |
| `TRANSLATION_UNIT_PASS_CODE_BACK_END` | 1 (0x00000001) | 中間言語を最適化し、それをマシンコードに変換するバックエンドパス。 |

## <a name="remarks"></a>解説

C SDK 関数で使用されます。

::: moniker-end
