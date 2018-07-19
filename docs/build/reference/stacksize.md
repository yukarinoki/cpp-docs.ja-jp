---
title: STACKSIZE |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- STACKSIZE
dev_langs:
- C++
helpviewer_keywords:
- STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b2093762b3c6f21d319c53a85da5ec5b430a1fd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376248"
---
# <a name="stacksize"></a>STACKSIZE
スタック サイズをバイト単位で設定します。  
  
```  
STACKSIZE reserve[,commit]  
```  
  
## <a name="remarks"></a>コメント  
 スタックを設定すると同等の方法は、[スタック割り当て](../../build/reference/stack-stack-allocations.md)(/stack) オプション。 このオプションは、詳細については、ドキュメントを参照してください、*予約*と`commit`引数。  
  
 このオプションは、Dll への影響を与えません。  
  
## <a name="see-also"></a>関連項目  
 [モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)