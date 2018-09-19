---
title: -PDBALTPATH (別の PDB パスを使用) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /pdbaltpath
dev_langs:
- C++
helpviewer_keywords:
- .pdb files, path
- PDBALTPATH dumpbin option
- -PDBALTPATH dumpbin option
- /PDBALTPATH dumpbin option
- PDB files, path
ms.assetid: 72e200aa-e2c3-4ad8-b687-25528da1aaaf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72c494745fa33c8feeb4955f4542e9db5ed22307
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718390"
---
# <a name="pdbaltpath-use-alternate-pdb-path"></a>/PDBALTPATH (別の PDB パスを使用)

```
/PDBALTPATH:pdb_file_name
```

## <a name="arguments"></a>引数

*pdb_file_name*<br/>
.pdb ファイルのパスとファイル名です。

## <a name="remarks"></a>Remarks

このオプションを使って、コンパイルされたバイナリ ファイルにプログラム データベース (.pdb) ファイルの別の場所を提供します。 通常、リンカーは作成するバイナリの中に .pdb ファイルの場所を記録します。 このオプションを使って .pdb ファイルに異なるパスとファイル名を提供できます。 /PDBALTPATH で提供される情報は、実際の .pdb ファイルの場所や名前を変更するわけではなく、リンカーがバイナリ ファイルに書き込む情報を変更します。 これにより、ビルド コンピューターのファイル構造とは独立したパスを提供できます。 このオプションの 2 つの一般的な使用方法は、ネットワーク パスまたはパス情報のないファイルを提供することです。

値*pdb_file_name*は、任意の文字列、環境変数、または **% _PDB**します。 リンカーはなどを展開し、環境変数 **%systemroot%**、その値にします。 リンカーは、環境変数を定義します。 **% _PDB**と**展開**します。 **% _PDB**展開し、パス情報がない実際の .pdb ファイルのファイル名と**展開**は、生成された実行可能ファイルの拡張機能です。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](../../build/reference/dumpbin-options.md)<br/>
[/PDBPATH](../../build/reference/pdbpath.md)