---
description: 詳細情報:/LINENUMBERS
title: /LINENUMBERS
ms.date: 11/04/2016
f1_keywords:
- /linenumbers
helpviewer_keywords:
- LINENUMBERS dumpbin option
- line numbers
- -LINENUMBERS dumpbin option
- /LINENUMBERS dumpbin option
ms.assetid: 1681d582-2c2f-484e-9920-109959549055
ms.openlocfilehash: 9df3d88476a82466f86ec23147c9f8f35f9b3f1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191018"
---
# <a name="linenumbers"></a>/LINENUMBERS

```
/LINENUMBERS
```

## <a name="remarks"></a>解説

このオプションは、COFF 行番号を表示します。 行番号は、プログラムデータベース (/Zi)、C7 互換 (/Z7)、または行番号のみ (/Zd) でコンパイルされた場合、オブジェクトファイルに存在します。 実行可能ファイルまたは DLL には、デバッグ情報の生成 (/DEBUG) とリンクされている場合、COFF 行番号が含まれます。

[/GL](gl-whole-program-optimization.md) コンパイラ オプションで生成したファイルで使用できるのは、[/HEADERS](headers.md) DUMPBIN オプションだけです。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](dumpbin-options.md)
