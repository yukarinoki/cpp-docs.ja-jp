---
title: 環境変数 LINK |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- variables, environment
- LINK tool [C++], environment variables
- LIB environment variable
- environment variables [C++], LINK
ms.assetid: 9a3d3291-0cc4-4a7d-9d50-80e351b90708
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 076e427e50520651f30cde20c764ff1124a6f953
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372699"
---
# <a name="link-environment-variables"></a>環境変数 LINK

LINK ツールでは、次の環境変数を使用します。  
  
-   リンクおよび\_リンク\_定義されている場合、します。 定義されている引数およびリンク ツールを先頭にオプションと引数の環境変数 LINK に定義されているオプションを追加し、\_リンク\_環境変数を処理する前にコマンドライン引数。  
  
-   LIB。定義されている場合。 LINK ツールは、オブジェクト、ライブラリ、またはコマンド ラインでまたはを指定したその他のファイルを検索するときに LIB パスを使用、 [/base](../../build/reference/base-base-address.md)オプション。 また、オブジェクトで指定された .pdb ファイルを検索するときにも LIB パスを使用します。 LIB 変数では、複数のパスをセミコロンで区切って指定できます。 1 つのパスは Visual C++ インストールの \lib サブディレクトリを示す必要があります。  
  
-   PATH。ツールが CVTRES を実行する必要があり、LINK 自身と同じディレクトリ内にこのファイルが見つからない場合  (LINK では、.res ファイルをリンクするために CVTRES を必要とします)。PATH は Visual C++ インストールの \bin サブディレクトリを示す必要があります。  
  
-   TMP。OMF ファイルまたは .res ファイルをリンクするときのディレクトリを指定します。  
  
## <a name="see-also"></a>関連項目  

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
[リンカー オプション](../../build/reference/linker-options.md)   
[コマンドラインでの C/C++ コードのビルド](../../build/building-on-the-command-line.md)  
[コマンド ライン ビルドのパスと環境変数の設定](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)
