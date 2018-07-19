---
title: 共用体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- union
dev_langs:
- C++
helpviewer_keywords:
- UNION directive
ms.assetid: 52504abf-7dc1-47c5-944c-b886803a0c6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 71a2d7644e14903d2c4a9c4191ce54c8fea14849
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057670"
---
# <a name="union"></a>UNION
1 つまたは複数のデータ型の共用体を宣言します。 *Fielddeclarations*有効なデータの定義をする必要があります。 省略、[終了](../../assembler/masm/ends-masm.md)*名前*ラベルの上に入れ子になった**共用体**定義します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      name   
      UNION [[alignment]] [[, NONUNIQUE]]  
   fielddeclarations  
[[name]] ENDS  
```  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)