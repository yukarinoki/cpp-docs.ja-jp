---
title: 古いコード (Visual C) の浮動小数点サポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a2a26b96-7bc2-418a-981a-51aa1a0294a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd7cbf955fbf795d06d9cd2448d0736dc435f3b5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367161"
---
# <a name="floating-point-support-for-older-code-visual-c"></a>旧形式のコードのための浮動小数点サポート (Visual C++)
MMX および浮動小数点スタック レジスタ (MM0-MM7/st0 を割り当てます-ST7) は、コンテキストの切り替えの間で保持されます。  これらのレジスタの明示的な呼び出し規則はありません。  これらのレジスタの使用は、カーネル モード コードで禁じられています。  
  
## <a name="see-also"></a>関連項目  
 [呼び出し規則](../build/calling-convention.md)