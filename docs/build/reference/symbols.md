---
description: 詳細情報:/記号
title: /SYMBOLS
ms.date: 09/05/2018
f1_keywords:
- /symbols
helpviewer_keywords:
- symbols, dumping
- public symbols
- symbols, displaying COFF symbol table
- symbol tables
- SYMBOLS dumpbin option
- /SYMBOLS dumpbin option
- -SYMBOLS dumpbin option
ms.assetid: 34bcae90-4561-4c77-a80c-065508dec39a
ms.openlocfilehash: f0cc213a8b37f99e0cb80f6df88967e4eb5204b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230147"
---
# <a name="symbols"></a>/SYMBOLS

```
/SYMBOLS
```

このオプションを選択すると、COFF シンボルテーブルが表示されます。 シンボルテーブルは、すべてのオブジェクトファイルに存在します。 COFF シンボルテーブルは、/DEBUG にリンクされている場合にのみ、イメージファイルに表示されます。

/SYMBOLS. の出力の説明を次に示します。 /記号の出力の意味に関する追加情報については、「winnt.h」 (IMAGE_SYMBOL と IMAGE_AUX_SYMBOL)、または COFF のドキュメントを参照してください。

次のサンプルダンプを指定します。

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

## <a name="remarks"></a>解説

シンボル番号で始まる行の説明を次に示します。ユーザーに関連する情報が含まれている列について説明します。

- 最初の3桁の数値は、シンボルのインデックス/数値です。

- 3番目の列に MBF 発注書 *x* が含まれている場合は、オブジェクトファイルのそのセクションにシンボルが定義されます。 ただし、UNDEF が出現する場合は、そのオブジェクトで定義されていないため、他の場所で解決する必要があります。

- 5番目の列 (Static、External) は、シンボルがそのオブジェクト内でのみ表示されるか、またはパブリック (外部参照可能) であるかを示します。 静的なシンボルである _sym は、パブリックシンボル _sym にリンクされません。これらは、_sym という名前の関数の2つの異なるインスタンスです。

番号付きの行の最後の列は、修飾されたシンボルと装飾されていないシンボル名です。

[/GL](gl-whole-program-optimization.md) コンパイラ オプションで生成したファイルで使用できるのは、[/HEADERS](headers.md) DUMPBIN オプションだけです。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](dumpbin-options.md)
