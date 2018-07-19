---
title: 推論規則の優先順位 |Microsoft ドキュメント
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
ms.openlocfilehash: 36d462d4222cbfc143dd7487d4cb6b1b8bb3ba3b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368487"
---
# <a name="precedence-in-inference-rules"></a>推論規則の優先順位
推論規則は重複定義されて、NMAKE は最も高い優先順位の定義を使用します。 次に、最上位から最下位までの優先順位の順序を示します。  
  
1.  メイクファイルで定義された推論規則後続の定義では、優先順位があります。  
  
2.  Tools.ini; で定義された推論規則後続の定義では、優先順位があります。  
  
3.  定義済みの推論規則。  
  
## <a name="see-also"></a>関連項目  
 [推論規則](../build/inference-rules.md)