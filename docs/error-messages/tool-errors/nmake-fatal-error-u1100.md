---
title: NMAKE の致命的なエラー U1100
ms.date: 11/04/2016
f1_keywords:
- U1100
helpviewer_keywords:
- U1100
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
ms.openlocfilehash: d5c62c1465bbb6463afbac2bc9ad5f4290473471
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193265"
---
# <a name="nmake-fatal-error-u1100"></a>NMAKE の致命的なエラー U1100

バッチルール ' rule ' のコンテキストではマクロ ' macroname ' は無効です

バッチモード規則のコマンドブロックが $ < ではない特殊なファイルマクロを直接または間接的に参照している場合、NMAKE はこのエラーを生成します。

$ < は、バッチモードルールで許可されている唯一のマクロです。
