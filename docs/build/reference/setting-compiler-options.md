---
title: コンパイラ オプションの設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- compiler options, setting
- cl.exe compiler, setting options
ms.assetid: 4b079f5b-0017-4124-aad6-0d2b58e427e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 322d4add32aca1c57b45a601e4704b2ec5d99a02
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375807"
---
# <a name="setting-compiler-options"></a>コンパイラ オプションの設定
C および C++ コンパイラ オプションは、開発環境またはコマンド ラインで設定できます。  
  
## <a name="in-the-development-environment"></a>開発環境での指定  
 内の各プロジェクトのコンパイラ オプションを設定することができます、**プロパティ ページ** ダイアログ ボックス。 左のペインで選択**構成プロパティ**、 **C/C++** コンパイラ オプションのカテゴリを選択します。 各コンパイラ オプションのトピックで、開発環境でオプションを設定する方法と、そのオプションがどこにあるかを説明します。 参照してください[コンパイラ オプション](../../build/reference/compiler-options.md)完全な一覧についてはします。  
  
## <a name="outside-the-development-environment"></a>開発環境以外での指定  
 コンパイラ (CL.exe) オプションは、次のいずれかで設定できます。  
  
-   [コマンドラインで](../../build/reference/compiler-command-line-syntax.md)  
  
-   [コマンド ファイル](../../build/reference/cl-command-files.md)  
  
-   [環境変数 CL](../../build/reference/cl-environment-variables.md)  
  
 環境変数 CL で指定したオプションは、CL を起動するたびに使用されます。 環境変数 CL またはコマンド ラインでコマンド ファイルを指定すると、そのコマンド ファイルに指定されているオプションが使用されます。 コマンド ラインまたは環境変数 CL ではオプションとファイル名を 1 行しか指定できませんが、コマンド ファイルでは複数行指定できます。  
  
 コンパイラ オプションは、"左から右" に処理されます。オプションが競合する場合は、最後の、つまり一番右のオプションが優先されます。 CL とコマンド ラインが競合した場合は、コマンド ラインが優先されます。環境変数 CL の処理後にコマンド ラインが処理されるからです。  
  
## <a name="additional-compiler-topics"></a>コンパイラに関するその他のトピック  
  
-   [高速コンパイル](../../build/reference/fast-compilation.md)  
  
-   [リンカーを呼び出す CL](../../build/reference/cl-invokes-the-linker.md)  
  
## <a name="see-also"></a>関連項目  
 [C/C++ ビルドのリファレンス](../../build/reference/c-cpp-building-reference.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)