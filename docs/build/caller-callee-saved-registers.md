---
title: 呼び出し元/呼び出し先保存済みレジスタ
ms.date: 11/04/2016
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
ms.openlocfilehash: f34fbfff8e6c61b5d568c073f6b7da2a12e34535
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654702"
---
# <a name="callercallee-saved-registers"></a>呼び出し元または呼び出し先保存済みレジスタ

揮発性と見なされ、考慮する必要があります RAX、RCX、RDX、R8、R9、R10、R11 レジスタが関数の呼び出しで破棄 (しない限り、それ以外の場合の安全性が証明可能なプログラム全体の最適化などの分析によって)。

RBX、RBP、RDI、RSI、RSP、R12、R13、R14、および R15 レジスタの不揮発性と見なされます保存する必要がありますや関数によって復元されるそれらを使用します。

## <a name="see-also"></a>関連項目

[呼び出し規則](../build/calling-convention.md)