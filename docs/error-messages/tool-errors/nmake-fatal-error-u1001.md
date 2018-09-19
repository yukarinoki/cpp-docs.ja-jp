---
title: NMAKE の致命的なエラー U1001 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1001
dev_langs:
- C++
helpviewer_keywords:
- U1001
ms.assetid: 5d7da559-6cbd-44d6-848c-aaf54cae0d1a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e4e465af5b4fa22c5f0ba5a9e01ebde0a7ee89e9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068144"
---
# <a name="nmake-fatal-error-u1001"></a>NMAKE の致命的なエラー U1001

構文エラー: 無効な文字 'character' でマクロ

特定の文字は、マクロが表示されますが、文字、数字、またはアンダー スコアではありません。

このエラーは、マクロの展開で不足している、コロンで発生することができます。

```
syntax error : illegal character '=' in macro
```