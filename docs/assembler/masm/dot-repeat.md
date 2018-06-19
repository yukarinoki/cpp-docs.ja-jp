---
title: .REPEAT | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .REPEAT
dev_langs:
- C++
helpviewer_keywords:
- .REPEAT directive
ms.assetid: cb8ad8c6-587b-42f9-a0ad-b5316a24918c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41e3dadaa95cb4bf0ca4a17af32332d5b5471245
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32052451"
---
# <a name="repeat"></a>.REPEAT
ブロックの実行を繰り返し表示されるコードを生成*ステートメント*まで`condition`は true になります。 [.UNTILCXZ](../../assembler/masm/dot-untilcxz.md)の置き換えられる可能性がありますが true になる CX が 0、[です。まで](../../assembler/masm/dot-until.md)です。 `condition`は省略可能**です。UNTILCXZ**です。  
  
## <a name="syntax"></a>構文  
  
```  
  
   .REPEAT  
statements  
.UNTIL condition  
```  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)