---
title: 複数のターゲット |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- makefiles, targets
- multiple targets in NMAKE
- targets, multiple in NMAKE
- NMAKE program, targets
ms.assetid: b609a179-0b9f-4b08-9930-998047588ae0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c1e072b5c831cecabaf1fd63034a0746b3e3419
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368188"
---
# <a name="multiple-targets"></a>複数のターゲット
(Nmake の) は、個別の記述ブロックでそれぞれ指定した場合と、単一の依存関係の複数のターゲットを評価します。  
  
 例えばこの。。。  
  
```Output  
bounce.exe leap.exe : jump.obj  
   echo Building...  
```  
  
 .. 評価結果。  
  
```Output  
bounce.exe : jump.obj  
   echo Building...  
leap.exe : jump.obj  
   echo Building...  
```  
  
## <a name="see-also"></a>関連項目  
 [ターゲット](../build/targets.md)