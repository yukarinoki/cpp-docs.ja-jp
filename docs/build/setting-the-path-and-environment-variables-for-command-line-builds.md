---
title: コマンド ライン ビルドのパスと環境変数を設定する
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
ms.openlocfilehash: aeafe806e5d29b89c243586974814aa7cfc16d1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335583"
---
# <a name="set-the-path-and-environment-variables-for-command-line-builds"></a>コマンド ライン ビルドのパスと環境変数を設定する

Microsoft C++ (MSVC) コマンド ライン ビルド ツールでは、インストールおよびビルド構成用にカスタマイズされた複数の環境変数が必要です。 Visual Studio インストーラーによって C++ ワークロードがインストールされると、必要な環境変数を設定するカスタマイズされたコマンド ファイルまたはバッチ ファイルが作成されます。 インストーラは、次に、これらのコマンド ファイルを使用して、Windows の [スタート] メニューのショートカットを作成し、開発者のコマンド プロンプト ウィンドウを開きます。 これらのショートカットは、特定のビルド構成の環境変数を設定します。 コマンド ライン ツールを使用する場合は、これらのショートカットのいずれかを実行するか、またはプレーンなコマンド プロンプト ウィンドウを開いてカスタム コマンド ファイルのいずれかを実行して、ビルド構成環境を自分で設定します。 詳細については、コマンド[ラインから MSVC ツールセットを使用するを](building-on-the-command-line.md)参照してください。 コマンド ファイルをプレーンコマンド プロンプトで使用するには、「[開発者コマンド ファイルの場所](building-on-the-command-line.md#developer_command_file_locations)」セクションを参照してください。

MSVC コマンド ライン ツールは、PATH、TMP、INCLUDE、LIB、および LIBPATH 環境変数を使用し、インストールされているツール、プラットフォーム、SDK に固有のその他の環境変数も使用します。 Visual Studio をインストールする単純な場合でも、20 以上の環境変数を設定できます。 これらの環境変数の値は、インストール環境とビルド構成の選択に固有のもので、製品の更新またはアップグレードによって変更できるため、開発者用のコマンド プロンプト ショートカットまたはカスタマイズされたコマンド ファイルのいずれかを使用して、Windows 環境で設定する代わりに、設定することを強くお勧めします。

開発者のコマンド プロンプト ショートカットによって設定された環境変数を確認するには、SET コマンドを使用します。 プレーンなコマンド プロンプト ウィンドウを開き、ベースラインの SET コマンドの出力をキャプチャします。 開発者コマンド プロンプト ウィンドウを開き、比較のために SET コマンドの出力をキャプチャします。 Visual Studio IDE に組み込まれているような相違ツールは、環境変数を比較し、開発者コマンド プロンプトで設定された内容を確認するのに役立ちます。 コンパイラおよびリンカーで使用される特定の環境変数については[、CL 環境変数](reference/cl-environment-variables.md)を参照してください。

> [!NOTE]
> コマンド ライン ツールやツール オプションによっては、管理者権限が必要な場合があります。 アクセス許可の問題がある場合は、**管理者として実行**オプションを使用して開発者のコマンド プロンプト ウィンドウを開くをお勧めします。 Windows 10 では、右クリックしてコマンド プロンプト ウィンドウのショートカット メニューを開き、[**その他]、[****管理者として実行**] の順に選択します。

## <a name="see-also"></a>関連項目

[コマンド ラインから MSVC ツールセットを使用する](building-on-the-command-line.md)<br/>
[MSVC リンカーのリファレンス](reference/linking.md)<br/>
[MSVC リンカー オプション](reference/linker-options.md)<br/>
[MSVC コンパイラ リファレンス](reference/compiling-a-c-cpp-program.md)<br/>
[MSVC コンパイラ オプション](reference/compiler-options.md)
