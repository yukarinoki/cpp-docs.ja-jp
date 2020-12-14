---
description: 詳細情報:/pdtpath (別の PDB パスを使用)
title: /PDBALTPATH (別の PDB パスを使用)
ms.date: 11/04/2016
f1_keywords:
- /pdbaltpath
helpviewer_keywords:
- .pdb files, path
- PDBALTPATH dumpbin option
- -PDBALTPATH dumpbin option
- /PDBALTPATH dumpbin option
- PDB files, path
ms.assetid: 72e200aa-e2c3-4ad8-b687-25528da1aaaf
ms.openlocfilehash: f85a39fb4570773f01a98331e746f6b37b76c161
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226065"
---
# <a name="pdbaltpath-use-alternate-pdb-path"></a>/PDBALTPATH (別の PDB パスを使用)

```
/PDBALTPATH:pdb_file_name
```

## <a name="arguments"></a>引数

*pdb_file_name*<br/>
.pdb ファイルのパスとファイル名です。

## <a name="remarks"></a>解説

このオプションを使って、コンパイルされたバイナリ ファイルにプログラム データベース (.pdb) ファイルの別の場所を提供します。 通常、リンカーは作成するバイナリの中に .pdb ファイルの場所を記録します。 このオプションを使って .pdb ファイルに異なるパスとファイル名を提供できます。 /PDBALTPATH で提供される情報は、実際の .pdb ファイルの場所や名前を変更するわけではなく、リンカーがバイナリ ファイルに書き込む情報を変更します。 これにより、ビルド コンピューターのファイル構造とは独立したパスを提供できます。 このオプションの 2 つの一般的な使用方法は、ネットワーク パスまたはパス情報のないファイルを提供することです。

*Pdb_file_name* の値には、任意の文字列、環境変数、または **% _PDB%** を指定できます。 リンカーは、 **% SystemRoot%** などの環境変数をその値に拡張します。 リンカーは、環境変数 **% _PDB%** および **% _EXT%** を定義します。 **% _PDB%** は、パス情報を含まない実際の .pdb ファイルのファイル名に展開されます。% **_EXT%** は、生成された実行可能ファイルの拡張子です。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](dumpbin-options.md)<br/>
[/PDBPATH](pdbpath.md)
