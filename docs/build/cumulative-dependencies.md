---
title: 依存関係の追加
ms.date: 11/04/2016
helpviewer_keywords:
- dependencies, cumulative
- cumulative dependencies in NMAKE
- dependencies
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
ms.openlocfilehash: 7ac1e164d1edc8d0aec26e268b3013c5b760672b
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57416879"
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
