---
title: MxCsr |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4f3c229d-0862-4733-acc7-9ed7a0b870ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9df2225526c20463bdbd618322d031c3245d9493
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368627"
---
# <a name="mxcsr"></a>MxCsr
レジスタの状態には、MxCsr も含まれています。 呼び出し規約は、揮発性の部分と不揮発性部分にこのレジスタを分割します。 揮発性の部分から成る 6 つの状態フラグ、MXCSR [0:5]、6:15、MXCSR レジスタの残りの部分には、不揮発性と見なされます。  
  
 不揮発性の部分は、プログラム実行の開始時に、次の標準的な値に設定されます。  
  
```  
MXCSR[6]         : Denormals are zeros - 0  
MXCSR[7:12]      : Exception masks all 1's (all exceptions masked)  
MXCSR[13:14]   : Rounding  control - 0 (round to nearest)  
MXCSR[15]      : Flush to zero for masked underflow - 0 (off)  
```  
  
 MXCSR 内不揮発性のフィールドのいずれかを変更する呼び出し先が呼び出し元に返す前にそれらを復元する必要があります。 さらに、呼び出し元がこれらのフィールドのいずれかを変更する必要があります値に戻す、標準呼び出し先契約には、変更された値が必要ですがない限り、呼び出し先を呼び出す前にします。  
  
 これには、制御フラグの不揮発性に関する規則に 2 つの例外があります。  
  
-   指定された関数のドキュメント化の目的が、不揮発性 MxCsr の変更、関数にフラグを設定します。  
  
-   おそらくである場合は、プログラムが動作/手段でこれらの規則に違反しない、たとえば、プログラム全体の分析によって、プログラムと同じ結果をこれらの規則に違反するを修正します。  
  
 関数の境界を越えて MXCSR の揮発性の部分の状態に関する仮定は行われません、関数のドキュメントで説明されている場合を除き。  
  
## <a name="see-also"></a>関連項目  
 [呼び出し規則](../build/calling-convention.md)