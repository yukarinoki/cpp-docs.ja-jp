---
title: インライン ファイルを指定する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, inline files
- inline files [C++], specifying NMAKE
- files [C++], inline
ms.assetid: 393eccfb-3fc9-4bac-a30c-8ac8d221cca3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2c0d85436aef5ed48c0a8787f8bce330bf6d3e96
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380106"
---
# <a name="specifying-an-inline-file"></a>インライン ファイルの指定
2 つの山かっこを指定 (<<) コマンドで、 *filename*が表示されます。 山かっこでは、マクロの展開をすることはできません。  
  
## <a name="syntax"></a>構文  
  
```  
<<[filename]  
```  
  
## <a name="remarks"></a>コメント  
 コマンドを実行すると、山かっこが置き換え*filename*、指定した場合または (nmake の) によって生成された一意の名前。 指定した場合*filename*スペースまたはタブせず山かっこを従う必要があります。パスが許可されます。 拡張子がが必須かまたはと見なされません。 場合*filename*を指定すると、現在のファイルを作成または指定したディレクトリは、既存のすべてを上書きする名前のファイル以外の場合はそれ以外の場合、TMP ディレクトリに作成されます (または、現在のディレクトリ場合、TMP 環境変数定義されていません)。 場合は、以前*filename*は、再利用 (nmake の) は、前のファイルを置き換えます。  
  
## <a name="see-also"></a>関連項目  
 [メイクファイルのインライン ファイル](../build/inline-files-in-a-makefile.md)