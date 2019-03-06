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
ms.openlocfilehash: 94009670329887a0b8a35e7b8b36996a84c7faa6
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417503"
---
# <a name="imports-dumpbin"></a>/IMPORTS (DUMPBIN)

```
/IMPORTS[:file]
```

このオプションは、Dll の一覧を表示します (どちらも静的にリンクされていると[遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)) からこれらの各 Dll を実行可能ファイルまたは DLL を個別にインポートされるすべてインポートします。

省略可能な`file`仕様では、のみ、その DLL のインポートが表示されることを指定できます。 例:

```
dumpbin /IMPORTS:msvcrt.dll
```

## <a name="remarks"></a>Remarks

このオプションによって表示される出力は、 [/exports](../../build/reference/dash-exports.md)出力します。

のみ、 [/HEADERS](../../build/reference/headers.md) DUMPBIN オプションがで生成されたファイルで使用できる、 [/GL](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプション。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](../../build/reference/dumpbin-options.md)
