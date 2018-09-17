---
title: 推論規則の優先順位 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4f2e7ff55e935b7e425b552ba85f47f134c6b80
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725232"
---
# <a name="precedence-in-inference-rules"></a>推論規則の優先順位

推論規則が複数回定義されている場合 (nmake の) は、最も高い優先順位の定義を使用します。 次に、高いものから低い方への優先順位の順序を示します。

1. メイクファイルで定義された推論規則後続の定義は、優先順位を持ちます。

1. Tools.ini; で定義された推論規則後続の定義は、優先順位を持ちます。

1. 定義済みの推論のルール。

## <a name="see-also"></a>関連項目

[推論規則](../build/inference-rules.md)