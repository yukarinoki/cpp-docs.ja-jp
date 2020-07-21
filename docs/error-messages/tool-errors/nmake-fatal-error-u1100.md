---
title: NMAKE の致命的なエラー U1100
description: Microsoft NMAKE の致命的なエラー U1100 の原因の説明。
ms.date: 07/17/2020
f1_keywords:
- U1100
helpviewer_keywords:
- U1100
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
ms.openlocfilehash: f908514469a6c9fdb53df3b2bded1b30bddc5a41
ms.sourcegitcommit: 00af3df3331854b23693ee844e5e7c10c8b05a90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "86491389"
---
# <a name="nmake-fatal-error-u1100"></a>NMAKE の致命的なエラー U1100

> バッチルール '*rule-name*' のコンテキストではマクロ '*macro name*' は無効です

このエラーは、バッチモード規則のコマンドブロックが、ではない特殊なファイルマクロを直接または間接的に参照している場合に、NMAKE によって生成さ `$<` れます。

`$<`バッチモード規則で許可されている唯一のマクロはです。

Batch ルールでの NMAKE マクロの詳細については、「[特殊な nmake マクロ](../../build/reference/special-nmake-macros.md)」を参照してください。
