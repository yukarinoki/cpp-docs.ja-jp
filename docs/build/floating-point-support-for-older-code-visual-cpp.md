---
title: 旧形式のコードのための浮動小数点サポート (Visual C++)
ms.date: 11/04/2016
ms.assetid: a2a26b96-7bc2-418a-981a-51aa1a0294a2
ms.openlocfilehash: 2340a4d136dee3438a47ce06793ed9274035250d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509644"
---
# <a name="floating-point-support-for-older-code-visual-c"></a>旧形式のコードのための浮動小数点サポート (Visual C++)

MMX と浮動小数点スタック レジスタ (MM0-MM7/st0 を割り当てます-ST7) は、コンテキストの切り替えの間で保持されます。  これらのレジスタの明示的な呼び出し規約はありません。  これらのレジスタの使用は、カーネル モード コードで禁じられています。

## <a name="see-also"></a>関連項目

[呼び出し規則](../build/calling-convention.md)