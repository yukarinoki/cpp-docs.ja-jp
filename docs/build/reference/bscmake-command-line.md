---
title: BSCMAKE コマンドライン |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- BSCMAKE, command line
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7866d2960acdd89c3015470ef3971307ba162cd3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369498"
---
# <a name="bscmake-command-line"></a>BSCMAKE コマンド ライン
BSCMAKE を実行するには、次のコマンドライン構文を使用します。  
  
```  
BSCMAKE [options] sbrfiles  
```  
  
 オプションでのみ使用できます、`options`コマンド ラインでフィールドです。  
  
 *Sbrfiles*フィールドは、コンパイラやアセンブラーによって作成された 1 つ以上の .sbr ファイルを指定します。 スペースまたはタブでは、.sbr ファイルの名前を区切ります。 拡張子を指定する必要があります。既定値はありません。 ファイル名は、パスを指定して、オペレーティング システムのワイルドカードを使用することができます (* と?) です。  
  
 インクリメンタル ビルドで、最初のビルドに含まれていない新しい .sbr ファイルを指定できます。 すべてのコントリビューションをブラウザー情報ファイルに保持する場合は、.bsc ファイルの作成に使用された元 (ファイルの切り捨てを含む) すべての .sbr ファイルを指定する必要があります。 .Sbr ファイルを省略すると、ブラウザー情報ファイルにそのファイルの金額が削除されます。  
  
 フル ビルドの切り捨てられた .sbr ファイルを指定しません。 フル ビルドには、すべての指定した .sbr ファイルからの協力が必要です。 フル ビルドを実行する前に、プロジェクトを再コンパイルし、空のファイルで新しい .sbr ファイルを作成します。  
  
 次のコマンドは、3 つの .sbr ファイルから MAIN.bsc という名前のファイルをビルドするを実行します。  
  
```  
BSCMAKE main.sbr file1.sbr file2.sbr  
```  
  
 関連情報については、次を参照してください。 [BSCMAKE コマンド ファイル](../../build/reference/bscmake-command-file-response-file.md)と[BSCMAKE オプション](../../build/reference/bscmake-options.md)です。  
  
## <a name="see-also"></a>関連項目  
 [BSCMAKE リファレンス](../../build/reference/bscmake-reference.md)