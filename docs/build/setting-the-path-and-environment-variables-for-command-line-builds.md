---
title: コマンド ライン ビルドのパスと環境変数を設定します。
ms.custom: conceptual
ms.date: 05/06/2019
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
ms.openlocfilehash: 30dadf365186ae74144a3225889c08eedfb89b47
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65217601"
---
# <a name="set-the-path-and-environment-variables-for-command-line-builds"></a>コマンド ライン ビルドのパスと環境変数を設定します。

Microsoft C++ (MSVC) コマンド ライン ビルド ツールのインストールとビルド構成のカスタマイズされたいくつかの環境変数を必要とします。 Visual Studio インストーラーでは、C++ ワークロードをインストール、カスタマイズされたコマンド ファイル、または必要な環境変数を設定するバッチ ファイルが作成されます。 インストーラーは、これらのコマンド ファイルを使用して開発者コマンド プロンプト ウィンドウを開く Windows [スタート] メニューのショートカットを作成します。 特定の環境変数を設定するこれらのショートカットは、構成をビルドします。 コマンド ライン ツールを使用するには、これらのショートカットのいずれかを行うことができます。 または、プレーンなコマンド プロンプト ウィンドウを開きますして自分でビルド構成の環境を設定するカスタム コマンド ファイルのいずれかを実行します。 詳細については、次を参照してください。[コマンドラインから MSVC ツールセットを使用して](building-on-the-command-line.md)します。

MSVC コマンド ライン ツールは PATH、TMP、INCLUDE、LIB、および LIBPATH 環境変数を使用し、インストールされているツール、プラットフォーム、および Sdk に固有の他の環境変数を使用しても。 簡単な Visual Studio のインストールも 20 以上の環境変数を設定できます。 これらの環境変数の値は、インストールされ、選択したビルドの構成に固有製品の更新プログラムやアップグレードによって変更できるため、強くお勧め開発者コマンド プロンプトのショートカットまたはのいずれかを使用すること、Windows 環境で自分で設定するのではなく、それらを設定するコマンド ファイルをカスタマイズします。

開発者コマンド プロンプトのショートカットがどの環境変数の設定を表示するには、SET コマンドを使用することができます。 普通のコマンド プロンプト ウィンドウを開き、基準の SET コマンドの出力をキャプチャします。 開発者コマンド プロンプト ウィンドウを開き、比較の SET コマンドの出力をキャプチャします。 Visual Studio IDE に組み込まれているものなどの差分ツールを環境変数を比較し、開発者コマンド プロンプトで何が設定されていることができます。 コンパイラとリンカーで使用される特定の環境変数の詳細については、次を参照してください。[環境変数 CL](reference/cl-environment-variables.md)します。

> [!NOTE]
>  いくつかのコマンド ライン ツールまたはツール オプションには、管理者のアクセス許可がある場合があります。 使用して開発者コマンド プロンプト ウィンドウを開くことをお勧めときに使用する、アクセス許可の問題がある場合、**管理者として実行**オプション。 Windows 10 では、右クリックしてショートカット メニューを開き、コマンド プロンプト ウィンドウを選択し、**詳細**、**管理者として実行**します。

## <a name="see-also"></a>関連項目

[コマンド ラインから MSVC ツールセットを使用する](building-on-the-command-line.md)<br/>
[MSVC リンカーのリファレンス](reference/linking.md)<br/>
[MSVC リンカー オプション](reference/linker-options.md)<br/>
[MSVC コンパイラ リファレンス](reference/compiling-a-c-cpp-program.md)<br/>
[MSVC コンパイラ オプション](reference/compiler-options.md)
