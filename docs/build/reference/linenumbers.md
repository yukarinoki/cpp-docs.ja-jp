---
title: -LINENUMBERS |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /linenumbers
dev_langs:
- C++
helpviewer_keywords:
- LINENUMBERS dumpbin option
- line numbers
- -LINENUMBERS dumpbin option
- /LINENUMBERS dumpbin option
ms.assetid: 1681d582-2c2f-484e-9920-109959549055
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c9b969f51733d9eb4c45ac5609b42920765a7ad5
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704055"
---
# <a name="linenumbers"></a>/LINENUMBERS

```
/LINENUMBERS
```

## <a name="remarks"></a>Remarks

このオプションは、COFF 行番号を表示します。 C7 互換プログラム データベース (/Zi) でコンパイルされた場合に、行番号がオブジェクト ファイルに存在 (/Z7)、または行番号のみ (/Zd)。 実行可能ファイルまたは DLL が含まれています行 coff にはデバッグ情報の生成にリンクされている場合 (/debug)。

のみ、 [/HEADERS](../../build/reference/headers.md) DUMPBIN オプションがで生成されたファイルで使用できる、 [/GL](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプション。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](../../build/reference/dumpbin-options.md)