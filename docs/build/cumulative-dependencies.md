---
title: 累積的な依存関係 |Microsoft Docs
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
ms.openlocfilehash: 5a66b153a52da06cca14845b9a58fcef0f42676d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725713"
---
# <a name="cumulative-dependencies"></a>依存関係の追加

ターゲットが繰り返し発生する場合は、依存関係を記述ブロックで累積されます。

たとえば、この、ルールの設定

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

1 つ記述ブロックで複数の依存関係の行で複数のターゲットとして評価されます、個別の記述ブロックでそれぞれ指定されましたが、依存関係の最後の行ではありません。 ターゲットでコマンド ブロックを使用しないでください。 (Nmake の) は、このようなターゲットの推論規則を使用しようとします。

たとえば、この、ルールの設定

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