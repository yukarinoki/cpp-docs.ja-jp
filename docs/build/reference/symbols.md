---
title: -SYMBOLS |Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /symbols
dev_langs:
- C++
helpviewer_keywords:
- symbols, dumping
- public symbols
- symbols, displaying COFF symbol table
- symbol tables
- SYMBOLS dumpbin option
- /SYMBOLS dumpbin option
- -SYMBOLS dumpbin option
ms.assetid: 34bcae90-4561-4c77-a80c-065508dec39a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8759ac9ae4de33862c8f0fa698faecc7b14ff1e7
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703236"
---
# <a name="symbols"></a>/SYMBOLS

```
/SYMBOLS
```

このオプションは、COFF シンボル テーブルを表示します。 シンボル テーブルは、すべてのオブジェクト ファイルに存在します。 COFF シンボル テーブルは、/DEBUG にリンクされている場合にのみ、イメージ ファイルに表示されます。

/SYMBOLS の出力の説明を次に示します。 /SYMBOLS 出力の意味については、winnt.h (IMAGE_SYMBOL および IMAGE_AUX_SYMBOL) または COFF ドキュメントではあります。

次のサンプルのダンプを指定します。

```
Dump of file main.obj
File Type: COFF OBJECT

COFF SYMBOL TABLE
000 00000000 DEBUG    notype       Filename     | .file
    main.cpp
002 000B1FDB ABS      notype       Static       | @comp.id
003 00000000 SECT1    notype       Static       | .drectve
    Section length     26, #relocs    0, #linenums    0, checksum 722C964F
005 00000000 SECT2    notype       Static       | .text
    Section length     23, #relocs    1, #linenums    0, checksum 459FF65F, selection    1 (pick no duplicates)
007 00000000 SECT2    notype ()    External     | _main
008 00000000 UNDEF    notype ()    External     | ?MyDump@@YAXXZ (void __cdecl MyDump(void))

String Table Size = 0x10 bytes

  Summary

         26 .drectve
         23 .text
```

## <a name="remarks"></a>Remarks

シンボルの番号で始まる行を次の説明では、ユーザーに関連する情報を含む列について説明します。

- 最初の 3 桁の数字は、シンボルのインデックス/数です。

- 3 番目の列には、セクターが含まれている場合*x*シンボルがオブジェクト ファイルのセクションで定義されています。 そのオブジェクトで定義されていないと、別の場所を解決する必要があります UNDEF が表示された場合。

- (静的、外部) の 5 番目の列は、シンボルが、そのオブジェクト内でのみ表示されるかどうかがパブリックかどうかを示します (表示されている外部)。 _Sym とのスタティック シンボルは、パブリック シンボル _sym; にリンクはありません。_sym という名前の関数の 2 つの異なるインスタンスになります。

番号付きの行の最後の列は、シンボル名は、装飾形式し非装飾します。

のみ、 [/HEADERS](../../build/reference/headers.md) DUMPBIN オプションがで生成されたファイルで使用できる、 [/GL](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプション。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](../../build/reference/dumpbin-options.md)