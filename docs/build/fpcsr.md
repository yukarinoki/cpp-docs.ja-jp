---
title: FpCsr |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: dff95d5d-7589-4432-82db-64b459c24352
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9defb41a026b32acb4375185f14c903788b91a23
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="fpcsr"></a>FpCsr
レジスタの状態も含まれますは x87 FPU 制御ワードです。 呼び出し規約では、このレジスタを不揮発性によって決まります。  
  
 X87 FPU 制御ワードのレジスタの開始時に、次の標準的な値に設定されているプログラムの実行。  
  
```  
FPCSR[0:6]: Exception masks all 1's (all exceptions masked)  
FPCSR[7]: Reserved - 0  
FPCSR[8:9]: Precision Control - 10B (double precision)  
FPCSR[10:11]: Rounding  control - 0 (round to nearest)  
FPCSR[12]: Infinity control - 0 (not used)  
```  
  
 FPCSR 内のフィールドのいずれかを変更する呼び出し先が呼び出し元に返す前にそれらを復元する必要があります。 さらに、呼び出し元がこれらのフィールドのいずれかを変更する必要があります値に戻す、標準呼び出し先契約には、変更された値が必要ですがない限り、呼び出し先を呼び出す前にします。  
  
 これには、制御フラグの不揮発性に関する規則に 2 つの例外があります。  
  
1.  ここで指定された関数の文書化されている目的は、不揮発性 FpCsr を変更する関数にフラグを設定します。  
  
2.  おそらくである場合は、プログラムが動作/手段でこれらの規則に違反しない、たとえば、プログラム全体の分析によって、プログラムと同じ結果をこれらの規則に違反するを修正します。  
  
## <a name="see-also"></a>関連項目  
 [呼び出し規則](../build/calling-convention.md)