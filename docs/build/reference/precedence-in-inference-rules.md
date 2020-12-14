---
description: 詳細については、「推論規則の優先順位」を参照してください。
title: 推論規則の優先順位
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
ms.openlocfilehash: b56d01cce63aaaac92e011630e45bcf43e7fe0b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225909"
---
# <a name="precedence-in-inference-rules"></a>推論規則の優先順位

推論規則が多重定義されている場合、NMAKE は最も優先順位の高い定義を使用します。 次の一覧は、優先順位の高い順を示しています。

1. メイクファイルで定義されている推論規則後の定義が優先されます。

1. Tools.ini で定義された推論規則後の定義が優先されます。

1. 定義済みの推論規則。

## <a name="see-also"></a>関連項目

[推論規則](inference-rules.md)
