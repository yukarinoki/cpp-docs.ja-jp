---
title: 呼び出し元の呼び出し先保存済みレジスタ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f65e88c8609d6a2097e9e54c3f52cbd27dce36d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366797"
---
# <a name="callercallee-saved-registers"></a>呼び出し元または呼び出し先保存済みレジスタ
関数の呼び出しでは揮発性と見なされ、考慮すべき RAX、RCX、RDX、R8、R9、R10、R11 レジスタが破棄されます (しない限り、それ以外の場合の安全性の立証可能なプログラム全体の最適化などの分析で)。  
  
 レジスタ RBX、RBP、RDI、RSI、RSP、R12、R13、R14、および R15 不揮発性と見なされます保存する必要がありますや関数によって復元されるそれらを使用します。  
  
## <a name="see-also"></a>関連項目  
 [呼び出し規則](../build/calling-convention.md)