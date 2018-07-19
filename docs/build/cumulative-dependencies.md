---
title: 依存関係の |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dependencies, cumulative
- cumulative dependencies in NMAKE
- dependencies
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d502912a8aeee2e6b3782e7795f44238386e1dba
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366976"
---
# <a name="cumulative-dependencies"></a>依存関係の追加
ターゲットが繰り返し発生する場合は、依存関係を記述ブロックで累積されます。  
  
 たとえば、このルールをセット、  
  
```Output  
bounce.exe : jump.obj  
bounce.exe : up.obj  
   echo Building bounce.exe...  
```  
  
 この評価されます。  
  
```Output  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
```  
  
 説明が 1 つのブロック内の複数の依存関係行の複数のターゲットは、個別の記述ブロック内で指定された各は、依存関係の最後の行に含まれていないターゲットがコマンドのブロックを使用しないかのように評価されます。 (Nmake の) は、このような対象に対して推論規則を使用しようとします。  
  
 たとえば、このルールをセット、  
  
```Output  
leap.exe bounce.exe : jump.obj  
bounce.exe climb.exe : up.obj  
   echo Building bounce.exe...  
```  
  
 この評価されます。  
  
```Output  
  
leap.exe : jump.obj  
# invokes an inference rule  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
climb.exe : up.obj  
   echo Building bounce.exe...  
```  
  
## <a name="see-also"></a>関連項目  
 [ターゲット](../build/targets.md)