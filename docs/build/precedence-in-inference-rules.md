---
title: 推論規則の優先順位
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
ms.openlocfilehash: 30dee54c99115c076f7662bafb8aa22d97f234fa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548734"
---
# <a name="precedence-in-inference-rules"></a>推論規則の優先順位

推論規則が複数回定義されている場合 (nmake の) は、最も高い優先順位の定義を使用します。 次に、高いものから低い方への優先順位の順序を示します。

1. メイクファイルで定義された推論規則後続の定義は、優先順位を持ちます。

1. Tools.ini; で定義された推論規則後続の定義は、優先順位を持ちます。

1. 定義済みの推論のルール。

## <a name="see-also"></a>関連項目

[推論規則](../build/inference-rules.md)