---
title: .IF |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .IF
dev_langs:
- C++
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ab0e2fc510b4be8c5a9a8c0c3d0fb1c4347f0b9
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32053117"
---
# <a name="if"></a>.IF
テストするコードを生成`condition1`(たとえば、AX 7 >) を実行し、*ステートメント*その条件が true の場合。  
  
## <a name="syntax"></a>構文  
  
```  
  
   .IF condition1   
statements  
[[.ELSEIF condition2   
   statements]]  
[[.ELSE  
   statements]]  
.ENDIF  
```  
  
## <a name="remarks"></a>コメント  
 場合、[です。ELSE](../../assembler/masm/dot-else.md)元の条件が false であった場合、次のように、そのステートメントは実行されます。 実行時に、条件が評価されることに注意してください。  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)