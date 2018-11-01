---
title: /IMPORTS (DUMPBIN)
ms.date: 11/04/2016
f1_keywords:
- /imports
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
ms.openlocfilehash: 9367457a8e7f6be1f372244f8288a994eb777071
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613786"
---
# <a name="imports-dumpbin"></a>/IMPORTS (DUMPBIN)

```
/IMPORTS[:file]
```

このオプションは、Dll の一覧を表示します (どちらも静的にリンクされていると[遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)) からこれらの各 Dll を実行可能ファイルまたは DLL を個別にインポートされるすべてインポートします。

省略可能な`file`仕様では、のみ、その DLL のインポートが表示されることを指定できます。 例えば:

```
dumpbin /IMPORTS:msvcrt.dll
```

## <a name="remarks"></a>Remarks

このオプションによって表示される出力は、 [/exports](../../build/reference/dash-exports.md)出力します。

のみ、 [/HEADERS](../../build/reference/headers.md) DUMPBIN オプションがで生成されたファイルで使用できる、 [/GL](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプション。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](../../build/reference/dumpbin-options.md)