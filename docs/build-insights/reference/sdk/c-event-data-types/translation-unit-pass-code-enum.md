---
title: TRANSLATION_UNIT_PASS_CODE 列挙型
description: C++ Build Insights SDK の TRANSLATION_UNIT_PASS_CODE 列挙型のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRANSLATION_UNIT_PASS_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 31f3e16ce6d9aa8c3c9db6cf9c11069dc3ec22fe
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920919"
---
# <a name="translation_unit_pass_code-enum"></a>TRANSLATION_UNIT_PASS_CODE 列挙型

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`TRANSLATION_UNIT_PASS_CODE` 列挙型。

## <a name="members"></a>メンバー

| 名前 | 値 | 説明 |
|--|--|--|
| `TRANSLATION_UNIT_PASS_CODE_FRONT_END` | 0 (0x00000000) | フロントエンド パス。ソース コードの解析と中間言語への変換が行われます。 |
| `TRANSLATION_UNIT_PASS_CODE_BACK_END` | 1 (0x00000001) | バックエンド パス。中間言語の最適化とマシン語コードへの変換が行われます。 |

## <a name="remarks"></a>注釈

C SDK 関数によって使用されます。

::: moniker-end
