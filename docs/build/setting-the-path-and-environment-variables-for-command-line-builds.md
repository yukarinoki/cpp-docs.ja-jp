---
description: '詳細情報: コマンド ライン ビルドのためのパスと環境変数を設定する'
title: コマンド ライン ビルドのためのパスと環境変数を設定する
ms.custom: conceptual
ms.date: 07/24/2019
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
ms.openlocfilehash: 3accc1cf56b86822298e1f1298bcae7d41c28332
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275387"
---
# <a name="set-the-path-and-environment-variables-for-command-line-builds"></a>コマンド ライン ビルドのためのパスと環境変数を設定する

Microsoft C++ (MSVC) のコマンド ライン ビルド ツールには、インストールとビルド構成に合わせてカスタマイズされたいくつかの環境変数が必要です。 Visual Studio インストーラーによって C++ のワークロードがインストールされるときに、必要な環境変数を設定するカスタマイズされたコマンド ファイル (バッチ ファイル) が作成されます。 その後、インストーラーでは、これらのコマンド ファイルを使用して、Windows の [スタート] メニューで開発者コマンド プロンプト ウィンドウを開くためのショートカットが作成されます。 これらのショートカットでは、特定のビルド構成に対する環境変数が設定されます。 コマンド ライン ツールを使用するときは、これらのショートカットのいずれかを実行するか、標準のコマンド プロンプト ウィンドウを開き、いずれかのカスタム コマンド ファイルを実行して自分でビルド構成環境を設定することができます。 詳細については、「[コマンド ラインから MSVC ツールセットを使用する](building-on-the-command-line.md)」を参照してください。 コマンド ファイルを標準のコマンド プロンプトで使用するには、「[開発者コマンド ファイルの場所](building-on-the-command-line.md#developer_command_file_locations)」セクションを参照してください。

MSVC コマンド ライン ツールでは、PATH、TMP、INCLUDE、LIB、LIBPATH の各環境変数が使用され、インストールされているツール、プラットフォーム、SDK に固有の他の環境変数も使用されます。 Visual Studio の単純なインストールでも、20 以上の環境変数が設定される場合があります。 これらの環境変数の値は、インストールと選択されているビルド構成に固有であり、製品の更新プログラムまたはアップグレードによって変更される可能性があるため、Windows 環境で自分で設定するのではなく、開発者コマンド プロンプトのショートカットまたはカスタマイズされたコマンド ファイルの 1 つを使用して、設定することを強くお勧めします。

開発者コマンド プロンプトのショートカットによって設定されている環境変数を確認するには、SET コマンドを使用します。 標準のコマンド プロンプト ウィンドウを開き、ベースラインとして SET コマンドの出力をキャプチャします。 開発者コマンド プロンプト ウィンドウを開き、比較のために SET コマンドの出力をキャプチャします。 Visual Studio IDE に組み込まれているもののような差分ツールは、環境変数を比較し、開発者コマンド プロンプトによって設定される内容を確認するのに役立ちます。 コンパイラとリンカーで使用される固有の環境変数の詳細については、「[環境変数 CL](reference/cl-environment-variables.md)」を参照してください。

> [!NOTE]
> コマンド ライン ツールまたはツールのオプションによっては、管理者アクセス許可が必要になる場合があります。 それらを使用するとアクセス許可の問題が発生する場合は、 **[管理者として実行]** オプションを使用して開発者コマンド プロンプト ウィンドウを開くことをお勧めします。 Windows 10 では、右クリックしてコマンド プロンプト ウィンドウのショートカット メニューを開き、 **[詳細]** 、 **[管理者として実行]** の順に選択します。

## <a name="see-also"></a>関連項目

[コマンド ラインから MSVC ツールセットを使用する](building-on-the-command-line.md)<br/>
[MSVC リンカーのリファレンス](reference/linking.md)<br/>
[MSVC リンカー オプション](reference/linker-options.md)<br/>
[MSVC コンパイラ リファレンス](reference/compiling-a-c-cpp-program.md)<br/>
[MSVC コンパイラ オプション](reference/compiler-options.md)
