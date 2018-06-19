---
title: 複数のインライン ファイル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inline files, multiple NMAKE
- multiple inline files
- NMAKE program, inline files
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ee9be15f029c0aaab3ca4bc47fb183e1499c2e2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368214"
---
# <a name="multiple-inline-files"></a>複数のインライン ファイル
コマンドは、1 つ以上のインライン ファイルを作成できます。  
  
## <a name="syntax"></a>構文  
  
```  
  
      command << <<  
inlinetext  
<<[KEEP | NOKEEP]  
inlinetext  
<<[KEEP | NOKEEP]  
```  
  
## <a name="remarks"></a>コメント  
 各ファイルに対して、1 つまたは複数の行のインライン テキストが続く、区切り記号を表す終了行を指定します。 最初のファイルの区切り線を次の行に 2 番目のファイルのテキストを開始します。  
  
## <a name="see-also"></a>関連項目  
 [メイクファイルのインライン ファイル](../build/inline-files-in-a-makefile.md)