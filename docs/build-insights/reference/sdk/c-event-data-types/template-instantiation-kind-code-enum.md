---
title: TEMPLATE_INSTANTIATION_KIND_CODE 列挙型
description: C++ Build Insights SDK の TEMPLATE_INSTANTIATION_KIND_CODE 列挙型のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TEMPLATE_INSTANTIATION_KIND_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2ee85af4e3d7f19b1b5dc9163dab6090f5ce4e42
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920945"
---
# <a name="template_instantiation_kind_code-enum"></a>TEMPLATE_INSTANTIATION_KIND_CODE 列挙型

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`TEMPLATE_INSTANTIATION_KIND_CODE` 列挙型。

## <a name="members"></a>メンバー

| 名前 | 値 | 説明 |
|--|--|--|
| `TEMPLATE_INSTANTIATION_KIND_CODE_CLASS` | 0 (0x00000000) | クラス テンプレートのインスタンス化。 |
| `TEMPLATE_INSTANTIATION_KIND_CODE_FUNCTION` | 1 (0x00000001) | 関数テンプレートのインスタンス化。 |
| `TEMPLATE_INSTANTIATION_KIND_CODE_VARIABLE` | 2 (0x00000002) | constexpr 変数のインスタンス化。 |
| `TEMPLATE_INSTANTIATION_KIND_CODE_CONCEPT` | 3 (0x00000003) | 概念テンプレートのインスタンス化。 |

## <a name="remarks"></a>注釈

::: moniker-end
