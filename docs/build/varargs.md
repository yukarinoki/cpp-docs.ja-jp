---
title: Varargs |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: aac0c54b-0a2d-4a22-b1de-ee41381a3eb1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e7b71cd426bc89570f9d394f3e38dc7a002f6e8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="varargs"></a>vararg
パラメーターが varargs (たとえば、省略記号引数) を使用して指定された場合、基本的には、通常のパラメーターを渡すでは以降の 5 番目の引数に書き込むときに含めが適用されます。 再度、アドレスを与えるダンプ引数に、呼び出し先の責任です。 浮動小数点値の場合にのみ、整数と浮動小数点レジスタの両方値が含まれます、float 場合に、呼び出し先は、整数レジスタに値が必要です。  
  
## <a name="see-also"></a>関連項目  
 [呼び出し規則](../build/calling-convention.md)