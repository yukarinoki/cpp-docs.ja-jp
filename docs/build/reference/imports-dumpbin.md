---
description: 詳細情報:/IMPORTS (DUMPBIN)
title: /IMPORTS (DUMPBIN)
ms.date: 11/04/2016
f1_keywords:
- /imports
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
ms.openlocfilehash: 86c428280bbca3a4957f7d7a0a640482607547de
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199793"
---
# <a name="imports-dumpbin"></a>/IMPORTS (DUMPBIN)

```
/IMPORTS[:file]
```

このオプションを選択 [すると、](linker-support-for-delay-loaded-dlls.md)実行可能ファイルまたは dll にインポートされる dll の一覧と、これらの各 dll からのすべての個別のインポートが表示されます。

省略可能な `file` 指定を使用すると、その DLL のみのインポートが表示されるように指定できます。 次に例を示します。

```
dumpbin /IMPORTS:msvcrt.dll
```

## <a name="remarks"></a>解説

このオプションによって表示される出力は、 [/エクスポート](dash-exports.md) 出力に似ています。

[/GL](gl-whole-program-optimization.md) コンパイラ オプションで生成したファイルで使用できるのは、[/HEADERS](headers.md) DUMPBIN オプションだけです。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](dumpbin-options.md)
