---
title: 依存関係の追加
ms.date: 11/04/2016
helpviewer_keywords:
- dependencies, cumulative
- cumulative dependencies in NMAKE
- dependencies
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
ms.openlocfilehash: de0a9649be8f0dae58f45d8980d2df610ff2febe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294084"
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

[ターゲット](targets.md)
