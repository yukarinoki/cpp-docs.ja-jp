---
description: 詳細情報:/PDBPATH
title: /PDBPATH
ms.date: 11/04/2016
f1_keywords:
- /pdbpath
helpviewer_keywords:
- .pdb files, path
- -PDBPATH dumpbin option
- /PDBPATH dumpbin option
- PDBPATH dumpbin option
- PDB files, path
ms.assetid: ccf67dcd-0b23-4250-ad47-06c48acbe82b
ms.openlocfilehash: 41207d7cfce3d72ecb9517d9ad3af8bcd3f901d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226052"
---
# <a name="pdbpath"></a>/PDBPATH

```
/PDBPATH[:VERBOSE] filename
```

### <a name="parameters"></a>パラメーター

*filename*<br/>
一致する .pdb ファイルを検索する .dll ファイルまたは .exe ファイルの名前です。

**: VERBOSE**<br/>
Optional.Pdb ファイルを検索しようとしたすべてのディレクトリを報告します。

## <a name="remarks"></a>解説

/PDBPATH は、デバッガーが .pdb ファイルを検索するのと同じパスでコンピューターを検索し、ファイル *名* に指定されたファイルに対応する .pdb ファイルがある場合はそれを報告します。

Visual Studio デバッガーを使用すると、デバッグ中のファイルの別のバージョンの .pdb ファイルがデバッガーで使用されていることが原因で問題が発生する可能性があります。

/PDBPATH は、次のパスに従って .pdb ファイルを検索します。

- 実行可能ファイルが存在する場所を確認します。

- 実行可能ファイルに書き込まれた PDB の場所を確認します。 通常、これはイメージがリンクされた時点の場所です。

- Visual Studio IDE で構成された検索パスに従って確認します。

- _NT_SYMBOL_PATH 環境変数と _NT_ALT_SYMBOL_PATH 環境変数のパスに沿って確認します。

- Windows ディレクトリをチェックインします。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](dumpbin-options.md)<br/>
[/Pdtpath (別の PDB パスを使用)](pdbaltpath-use-alternate-pdb-path.md)
