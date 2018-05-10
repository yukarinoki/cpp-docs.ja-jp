---
title: コマンド ライン ビルドのパスと環境変数を設定 |Microsoft ドキュメント
ms.custom: conceptual
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- include
- Lib
- Path
dev_langs:
- C++
helpviewer_keywords:
- environment variables [C++]
- VCVARS32.bat file
- cl.exe compiler [C++], environment variables
- LINK tool [C++], environment variables
- PATH reserved word
- INCLUDE reserved word
- LINK tool [C++], path
- LIB environment variable
- compiling source code [C++], from command line
- environment variables [C++], CL compiler
ms.assetid: 99389528-deb5-43b9-b99a-03c8773ebaf4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b72f13fe25330b81a48d1447b707bdc4626ab3f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="set-the-path-and-environment-variables-for-command-line-builds"></a>コマンド ライン ビルドのパスと環境変数を設定します。

Visual C のコマンド ライン ビルド ツールではのインストールとビルド構成のカスタマイズされたいくつかの環境変数が必要です。 C++ のワークロードがインストールされている場合、[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]インストーラー、カスタマイズされたコマンド ファイルは、または作成、必要な環境変数を設定するバッチ ファイルです。 インストーラーは、これらのコマンド ファイルを使用して開発者コマンド プロンプト ウィンドウを開くには、[スタート] メニューのショートカットを作成します。 これらのショートカットを特定の環境変数を設定では、構成をビルドします。 コマンド ライン ツールを使用する場合は、これらのショートカットのいずれかを実行することができますしたりできますプレーンのコマンド プロンプト ウィンドウを開き、ビルド構成の環境を設定するカスタム コマンド ファイルのいずれかを実行します。 詳細については、次を参照してください。[コマンドラインで c/c++ コードをビルド](building-on-the-command-line.md)です。  
  
Visual C のコマンド ライン ツールは、PATH、TMP、INCLUDE、LIB、および LIBPATH 環境変数を使用し、インストール済みのツール、プラットフォーム、および Sdk に固有の他の環境変数を使用してもします。 単純なでも[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]インストールは 20 以上の環境変数を設定します。 これらの環境変数の値が、インストールされ、選択したビルド構成に固有、製品の更新プログラムやアップグレードによって変更できるため、強くお勧め開発者コマンド プロンプト ショートカットまたはのいずれかを使用して、コマンド ファイルを Windows 環境で自分で設定ではなく、それらの設定をカスタマイズします。 

開発者コマンド プロンプト ショートカットで設定されている環境変数を表示するには、SET コマンドを使用することができます。 標準のコマンド プロンプト ウィンドウを開き、基準の SET コマンドの出力をキャプチャします。 開発者コマンド プロンプト ウィンドウを開き、比較の SET コマンドの出力をキャプチャします。 など、Visual Studio IDE に組み込まれている 1 つの相違のツールを環境変数を比較し、新機能は、開発者コマンド プロンプトで設定を表示することができます。 コンパイラおよびリンカーで使用される特定の環境変数については、次を参照してください。[環境変数 CL](../build/reference/cl-environment-variables.md)と[環境変数 LINK](../build/reference/link-environment-variables.md)です。  
  
> [!NOTE]
>  いくつかのコマンド ライン ツールまたはツール オプションには、管理者のアクセス許可がある場合があります。 使用して開発者コマンド プロンプト ウィンドウを開くときに使用するアクセス許可の問題があれば、お勧め、**管理者として実行**オプション。 Windows 10 では、ショートカット メニューを開き、コマンド プロンプト ウィンドウを右クリックし、選択**詳細**、**管理者として実行**です。  
  
## <a name="see-also"></a>関連項目  

[コマンドラインで C/C++ コードをビルドします。](../build/building-on-the-command-line.md)   
[リンク](../build/reference/linking.md)   
[リンカー オプション](../build/reference/linker-options.md)   
[C/C++ プログラムのコンパイル](../build/reference/compiling-a-c-cpp-program.md)   
[コンパイラ オプション](../build/reference/compiler-options.md)