---
title: 呼び出し元/呼び出し先保存済みレジスタ |Microsoft Docs
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
ms.openlocfilehash: e8e877387dbb5b0be865e11017a3ac71a0c38faa
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707656"
---
# <a name="callercallee-saved-registers"></a>呼び出し元または呼び出し先保存済みレジスタ

揮発性と見なされ、考慮する必要があります RAX、RCX、RDX、R8、R9、R10、R11 レジスタが関数の呼び出しで破棄 (しない限り、それ以外の場合の安全性が証明可能なプログラム全体の最適化などの分析によって)。

RBX、RBP、RDI、RSI、RSP、R12、R13、R14、および R15 レジスタの不揮発性と見なされます保存する必要がありますや関数によって復元されるそれらを使用します。

## <a name="see-also"></a>関連項目

[呼び出し規則](../build/calling-convention.md)