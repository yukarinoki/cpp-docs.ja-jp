---
title: 複数のターゲット
ms.date: 11/04/2016
helpviewer_keywords:
- makefiles, targets
- multiple targets in NMAKE
- targets, multiple in NMAKE
- NMAKE program, targets
ms.assetid: b609a179-0b9f-4b08-9930-998047588ae0
ms.openlocfilehash: 2762e458781e3a95f478ea3477fc8ef02f9196fb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50645061"
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