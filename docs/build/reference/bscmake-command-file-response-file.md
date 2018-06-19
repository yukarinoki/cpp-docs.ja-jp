---
title: BSCMAKE コマンド ファイル (応答ファイル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- BSCMAKE, response file
- BSCMAKE, command file
- response files, BSCMAKE
- command files, BSCMAKE
- response files
- command files
ms.assetid: abdffeea-35c7-4f2d-8c17-7d0d80bac314
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a879306078c52e0ad11d29f1786a2e55c2480d2f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369566"
---
# <a name="bscmake-command-file-response-file"></a>BSCMAKE コマンド ファイル (応答ファイル)
コマンド ファイル内のコマンド ライン入力の一部またはすべてを指定することができます。 次の構文を使用してコマンド ファイルを指定します。  
  
```  
BSCMAKE @filename  
```  
  
 1 つのコマンド ファイルが許可されているとします。 パスを指定することができます*filename*です。 前に*filename*で、アット マーク (@)。 BSCMAKE では、拡張機能を想定しません。 追加を指定できます*sbrfiles*後のコマンド ラインで*filename*です。 コマンド ファイルは、コマンドラインで指定する場合と同じ順序では、BSCMAKE への入力を含むテキスト ファイルです。 コマンドラインの引数 1 つ以上のスペース、タブ、または改行文字で区切ります。  
  
 次のコマンドは、BSCMAKE コマンド ファイルの使用を呼び出します。  
  
```  
BSCMAKE @prog1.txt  
```  
  
 サンプルのコマンド ファイルを次に示します。  
  
```  
/n /v /o main.bsc /El  
/S (  
toolbox.h  
verdate.h c:\src\inc\screen.h  
)  
file1.sbr file2.sbr file3.sbr file4.sbr  
```  
  
## <a name="see-also"></a>関連項目  
 [BSCMAKE リファレンス](../../build/reference/bscmake-reference.md)