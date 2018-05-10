---
title: プロトタイプ宣言されていない関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 34200b8c-5b52-4f0d-aff8-9f70d82868ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df159942832479807b2dfe2679e709292ff3f44b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="unprototyped-functions"></a>プロトタイプ宣言されていない関数
ない完全なプロトタイプ関数では、呼び出し元は、整数値として整数と浮動小数点値として渡します倍精度。 浮動小数点値の場合にのみ、整数レジスタと浮動小数点レジスタの両方値が含まれます、float 場合に、呼び出し先は、整数レジスタに値が必要です。  
  
```  
func1();  
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7  
   func1(2, 1.0, 7);  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [呼び出し規則](../build/calling-convention.md)