---
title: -PDBALTPATH (別の PDB パスを使用して) |Microsoft ドキュメント
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
ms.openlocfilehash: dec06c3d6a8a981a059f173700e716431acc53a7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="pdbaltpath-use-alternate-pdb-path"></a>/PDBALTPATH (別の PDB パスを使用)
```  
/PDBALTPATH:pdb_file_name  
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 *pdb_file_name*  
 .pdb ファイルのパスとファイル名です。  
  
## <a name="remarks"></a>コメント  
 このオプションを使って、コンパイルされたバイナリ ファイルにプログラム データベース (.pdb) ファイルの別の場所を提供します。 通常、リンカーは作成するバイナリの中に .pdb ファイルの場所を記録します。 このオプションを使って .pdb ファイルに異なるパスとファイル名を提供できます。 /PDBALTPATH で提供される情報は、実際の .pdb ファイルの場所や名前を変更するわけではなく、リンカーがバイナリ ファイルに書き込む情報を変更します。 これにより、ビルド コンピューターのファイル構造とは独立したパスを提供できます。 このオプションの 2 つの一般的な使用方法は、ネットワーク パスまたはパス情報のないファイルを提供することです。  
  
 値*pdb_file_name*は、任意の文字列、環境変数、または **% _PDB**です。 リンカーはなどを展開し、環境変数 **%systemroot%**、その値にします。 リンカーは環境変数を定義 **% _PDB**と**展開**です。 **% _PDB**パス情報がない実際の .pdb ファイルのファイル名と**展開**が生成された実行可能ファイルの拡張子。  
  
## <a name="see-also"></a>関連項目  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)   
 [/PDBPATH](../../build/reference/pdbpath.md)