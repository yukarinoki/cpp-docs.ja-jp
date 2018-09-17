---
title: IMPORTS (DUMPBIN) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /imports
dev_langs:
- C++
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5b3b1e3a74fea278bc142d02f793308b6b0e054
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713571"
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