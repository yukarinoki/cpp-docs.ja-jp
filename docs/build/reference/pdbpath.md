---
title: -PDBPATH |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /pdbpath
dev_langs:
- C++
helpviewer_keywords:
- .pdb files, path
- -PDBPATH dumpbin option
- /PDBPATH dumpbin option
- PDBPATH dumpbin option
- PDB files, path
ms.assetid: ccf67dcd-0b23-4250-ad47-06c48acbe82b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 274c4a3742d99b1e4702ed332206b78dacebccbd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373669"
---
# <a name="pdbpath"></a>/PDBPATH
```  
/PDBPATH[:VERBOSE] filename  
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 *ファイル名*  
 対応する .pdb ファイルを検索する .dll または .exe ファイルの名前。  
  
 VERBOSE (省略可能)  
 .Pdb ファイルを検索しようとしてが行われる場所のすべてのディレクトリを報告します。  
  
## <a name="remarks"></a>コメント  
 同じパスをたどって、デバッガーが .pdb ファイルを検索してしまいますおよびレポートが存在する場合に指定されたファイルに対応する .pdb ファイルをコンピューターの検索が/PDBPATH *filename*です。  
  
 Visual Studio デバッガーを使用する場合、デバッガーが .pdb ファイルを使用してデバッグしているファイルの別のバージョンのあるという事実のという問題が発生する可能性があります。  
  
 /PDBPATH は次のパスに沿った .pdb ファイルを検索します。  
  
-   実行可能ファイルが存在する場所を確認してください。  
  
-   実行可能ファイルに書き込まれた PDB の場所を確認してください。 これは、イメージのリンク時に場所では通常です。  
  
-   Visual Studio IDE で構成されている検索パスを確認します。  
  
-   _NT_SYMBOL_PATH および _NT_ALT_SYMBOL_PATH パスに沿った、環境変数を確認します。  
  
-   Windows ディレクトリで確認してください。  
  
## <a name="see-also"></a>関連項目  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)   
 [/PDBALTPATH (別の PDB パスを使用)](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)