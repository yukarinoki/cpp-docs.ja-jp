---
title: 'チュートリアル: コマンドラインでの C プログラムをコンパイルします。'
ms.custom: conceptual
ms.date: 04/25/2019
helpviewer_keywords:
- command-line applications [C++], C programs
- Visual C, compiling
- compiling programs [C++]
- C program compiling [C++]
ms.assetid: 7e74cc2d-54b1-49de-b7ad-d3ae6b39ab8d
ms.openlocfilehash: 03876ba47270252caa21d7e2994a4f8321a6d59e
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877198"
---
# <a name="walkthrough-compile-a-c-program-on-the-command-line"></a>チュートリアル: コマンドラインでの C プログラムをコンパイルします。

Visual C には、完全な Windows デスクトップ アプリケーション、モバイル アプリは、基本的なコンソール プログラムから作成するすべてのものを使用できる C コンパイラが含まれています。

このチュートリアルは、basic、「こんにちは, World」を作成する方法を示します-エディターでテキストを使用して C プログラムをスタイル設定し、それをコマンドラインでコンパイルします。 場合は、コマンドラインで C で作業する場合ではなくを参照してください。[チュートリアル。コマンド ラインでのネイティブ C++ プログラムのコンパイル](walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)」を参照してください。 コマンドラインを使用する代わりに、Visual Studio IDE を再試行してくださいを参照してくださいしたい場合[チュートリアル。プロジェクトとソリューション (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md)または[C++ デスクトップ開発用 Visual Studio IDE を使用して](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)します。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを完了するには、必要がありますまたはインストールしたか、Visual Studio と、オプションの Visual C コンポーネント Build Tools for Visual Studio。

Visual Studio は、多くの言語とプラットフォームの全機能装備のエディター、リソース マネージャー、デバッガー、およびコンパイラをサポートする強力な統合開発環境です。 これらの機能とをダウンロードして無料の Visual Studio Community edition など、Visual Studio をインストールする方法についてを参照してください。 [Visual Studio のインストール](/visualstudio/install/install-visual-studio)します。

Visual Studio のバージョンの Visual Studio の Build Tools は、のみコマンド ライン ツールセット、コンパイラ、ツール、および C および C++ プログラムの構築に必要なライブラリをインストールします。 ビルド環境に最適なまたはと比較的高速インストールを実行します。 コマンド ライン ツールセットのみをインストールするには、Visual Studio からの Build Tools をダウンロード、 [Visual Studio のダウンロード](https://visualstudio.microsoft.com/downloads/)ページし、インストーラーを実行します。

C または C++ プログラムを作成するには、コマンドラインで、前に、ツールがインストールされているし、コマンドラインからアクセスできることを確認する必要があります。 Visual C には、コマンド ライン ツール、ヘッダー、および使用するライブラリを検索する環境の複雑な要件があります。 **普通のコマンド プロンプト ウィンドウで、Visual C を使用することはできません**準備なし。 必要があります、*開発者コマンド プロンプト*ウィンドウで、これは通常のコマンド プロンプト ウィンドウを持つすべての必要な環境変数を設定します。 さいわい、Visual C では、コマンド ライン ビルドを設定する環境の開発者コマンド プロンプトを起動するためのショートカットをインストールします。 残念ながら、開発者コマンド プロンプトのショートカットとされている名前は、ほぼすべてのバージョンの Visual C とに異なるバージョンの Windows で異なる。 最初のチュートリアル タスクを使用する適切なショートカットを検索します。

> [!NOTE]
> 開発者コマンド プロンプトのショートカットは、コンパイラおよびツール、および必要なヘッダーとライブラリによって正しいパスを自動的に設定します。 これらの値の一部は、ビルド構成ごとに異なります。 必要がありますこれらの環境値自分で設定した場合は、ショートカットのいずれかを使用しないでください。 詳細については、次を参照してください。[コマンド ライン ビルドのパスと環境変数を設定する](setting-the-path-and-environment-variables-for-command-line-builds.md)します。 ビルド環境は複雑なため、開発者コマンド プロンプト ショートカットを使用して、独自に構築する代わりを強くお勧めします。

これらの手順は、使用して Visual Studio のバージョンによって異なります。 続行する前にバージョン セレクターで、左上のこのページが正しく設定されていることを確認します。

::: moniker range="vs-2019"

## <a name="open-a-developer-command-prompt-in-visual-studio-2019"></a>Visual Studio 2019 で開発者コマンド プロンプトを開く

Windows 10 に Visual Studio 2019 をインストールした場合、スタート メニューを開きし、下へスクロールしとを開く、 **Visual Studio 2019**フォルダー (Visual Studio 2019 アプリではありません)。 選択**開発者コマンド プロンプト for VS 2019**コマンド プロンプト ウィンドウを開きます。

別のバージョンの Windows を使用している場合は、[スタート] メニューでは、ファイルの場所か、開発者コマンド プロンプトのショートカットが含まれる Visual Studio ツール フォルダーのページを開始します。 「開発者コマンド プロンプト」を検索し、Visual Studio のインストールされているバージョンと一致するものを選択して、Windows 検索機能を使用することもできます。 ショートカットを使用して、コマンド プロンプト ウィンドウを開きます。

::: moniker-end

::: moniker range="vs-2017"

## <a name="open-a-developer-command-prompt-in-visual-studio-2017"></a>Visual Studio 2017 で、開発者コマンド プロンプトを開く

Windows 10 に Visual Studio 2017 をインストールした場合、スタート メニューを開きし、下へスクロールしとを開く、 **Visual Studio 2017**フォルダー (Visual Studio 2017 のアプリとは異なる)。 選択**開発者コマンド プロンプト for VS 2017**コマンド プロンプト ウィンドウを開きます。

別のバージョンの Windows を実行している場合は、[スタート] メニューでは、ファイルの場所か、開発者コマンド プロンプトのショートカットが含まれる Visual Studio ツール フォルダーのページを開始します。 「開発者コマンド プロンプト」を検索し、Visual Studio のインストールされているバージョンと一致するものを選択して、Windows 検索機能を使用することもできます。 ショートカットを使用して、コマンド プロンプト ウィンドウを開きます。

::: moniker-end

::: moniker range="vs-2015"

## <a name="open-a-developer-command-prompt-in-visual-studio-2015"></a>Visual Studio 2015 で、開発者コマンド プロンプトを開く

Windows 10 に Microsoft Visual C Build Tools 2015 をインストールした場合は、開く、**開始**] メニューの [下へスクロールして開く、 **Visual C Build Tools**フォルダー。 選択**Visual C 2015 x86 Native Tools コマンド プロンプト**コマンド プロンプト ウィンドウを開きます。

別のバージョンの Windows を実行している場合は、[スタート] メニューでは、ファイルの場所か、開発者コマンド プロンプトのショートカットが含まれる Visual Studio ツール フォルダーのページを開始します。 「開発者コマンド プロンプト」を検索し、Visual Studio のインストールされているバージョンと一致するものを選択して、Windows 検索機能を使用することもできます。 ショートカットを使用して、コマンド プロンプト ウィンドウを開きます。
   
::: moniker-end


次に、Visual C の開発者コマンド プロンプトが正しく設定されていることを確認します。 コマンド プロンプト ウィンドウで、入力`cl`し、出力は次ようなコードのことを確認します。

```Output
C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
Copyright (C) Microsoft Corporation.  All rights reserved.

usage: cl [ option... ] filename... [ /link linkoption... ]
```

現在のディレクトリまたは Visual C と更新プログラムがインストールされている任意のバージョンに応じて、バージョン番号の相違がある可能性があります。 上記の出力が表示される内容のような場合は、コマンドラインでの C または C++ プログラムを作成する準備ができました。

> [!NOTE]
> 「'Cl' は、内部または外部コマンド、操作可能なプログラムまたはバッチ ファイルとしては認識されません"など、エラーが発生した場合エラー C1034 またはエラー LNK1104 を実行すると、 **cl**コマンドを使用するか、開発者コマンド プロンプトを使用しない、またはVisual C のインストールに問題があります。 続行するには、この問題を修正する必要があります。

開発者コマンド プロンプトのショートカットを見つけられない場合、または入力すると、エラー メッセージが表示された場合`cl`、Visual C インストール問題がある可能性があります。 Visual Studio 2017 を使用している場合は、後で再インストールしてください、**によるデスクトップ開発C++**  Visual Studio インストーラーのワークロード。 詳細については、次を参照してください。 [Visual Studio で C++ のインストール サポート](vscpp-step-0-installation.md)します。 またはからのビルド ツールを再インストール、 [Visual Studio のダウンロード](https://visualstudio.microsoft.com/downloads/)ページ。 を接続しない次のセクションにはこれまでです。 インストールして、Visual Studio のトラブルシューティングの詳細については、次を参照してください。 [Visual Studio のインストール](/visualstudio/install/install-visual-studio)します。

> [!NOTE]
> によって、コンピューターとシステムのセキュリティ構成の Windows のバージョンを右クリックすると、開発者コマンド プロンプト ショートカットのショートカット メニューを開き、選択し、必要があります**管理者として実行**に正常にビルドして、このチュートリアルで作成するプログラムを実行します。

## <a name="create-a-c-source-file-and-compile-it-on-the-command-line"></a>C ソース ファイルを作成し、コマンドラインでコンパイル

1. 開発者コマンド プロンプト ウィンドウで次のように入力します。 `cd c:\` 、c: ドライブのルートに現在の作業ディレクトリを変更します。 次に、入力`md c:\simple`ディレクトリを作成し、入力`cd c:\simple`をそのディレクトリに変更します。 このディレクトリは、ソース ファイルとコンパイル済みのプログラムに保持されます。

1. 入力`notepad simple.c`開発者コマンド プロンプトでします。 メモ帳アラート ダイアログ ボックスが表示されたら、次のように選択します。**はい**作業ディレクトリに新しい simple.c ファイルを作成します。

1. メモ帳で、次のコード行を入力します。

    ```C
    #include <stdio.h>

    int main()
    {
        printf("Hello, World! This is a native C program compiled on the command line.\n");
        return 0;
    }
    ```

1. メモ帳のメニュー バー、**ファイル** > **保存**simple.c を作業ディレクトリに保存します。

1. 開発者コマンド プロンプト ウィンドウに切り替えます。 入力`dir`c:\simple のディレクトリの内容を一覧表示するコマンド プロンプトでします。 ように、ディレクトリのリストにソース ファイル simple.c が表示されます。

    ```Output
    C:\simple>dir
     Volume in drive C has no label.
     Volume Serial Number is CC62-6545

     Directory of C:\simple

    10/02/2017  03:46 PM    <DIR>          .
    10/02/2017  03:46 PM    <DIR>          ..
    10/02/2017  03:36 PM               143 simple.c
                   1 File(s)            143 bytes
                   2 Dir(s)  514,900,566,016 bytes free

    ```

   日付とその他の詳細については、コンピューターに異なります。 ソース コード ファイルが見つからない場合 simple.c は、作成した c:\simple のディレクトリに変更したかどうかを確認し、メモ帳でこのディレクトリにソース ファイルを保存することを確認します。 また、.c ファイル名拡張子を .txt という拡張子ではないと、ソース コードを保存したことを確認します。

1. プログラムをコンパイルするには、次のように入力します。`cl simple.c`開発者コマンド プロンプトでします。

   Simple.exe、コンパイラによって表示される出力情報の行で、実行可能プログラム名を確認できます。

    ```Output
    c:\simple>cl simple.c
    Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
    Copyright (C) Microsoft Corporation.  All rights reserved.

    simple.c
    Microsoft (R) Incremental Linker Version 14.10.25017.0
    Copyright (C) Microsoft Corporation.  All rights reserved.

    /out:simple.exe
    simple.obj
    ```

   > [!NOTE]
   > 「'Cl' は、内部または外部コマンド、操作可能なプログラムまたはバッチ ファイルとしては認識されません"など、エラーが発生した場合エラー C1034 またはエラー LNK1104、開発者コマンド プロンプトが正しくセットアップされていません。 この問題を解決する方法についてに戻り、**開発者コマンド プロンプトを開き**セクション。

   > [!NOTE]
   > 別のコンパイラまたはリンカーのエラーまたは警告が発生した場合、エラーを修正し、保存およびコンパイラをもう一度実行するソース コードを確認します。 特定のエラーについては、このページの上部にある検索ボックスを使用して、エラー番号を検索します。

1. プログラムを実行するには、次のように入力します。`simple`コマンド プロンプトでします。

   プログラムは、次のテキストを表示して終了します。

    ```Output
    Hello, World! This is a native C program compiled on the command line.
    ```

   これで、コンパイルし、コマンドラインを使用して C プログラムを実行します。

## <a name="next-steps"></a>次の手順

この「こんにちは, World」の例は、単純な C プログラムを取得できます。 実際のプログラムがあるヘッダー ファイルと複数のソース ファイルは、ライブラリでは、リンクし、有益な処理を実行します。

このチュートリアルで示したサンプル コードを入力する代わりに C# コードをビルドするのに手順を使用できます。 別の場所に表示されている多くの C コード サンプル プログラムを構築することもできます。 追加のソース コード ファイルのあるプログラムをコンパイルするには、コマンドラインですべてのようにそれらを入力します。

`cl file1.c file2.c file3.c`

コンパイラは、file1.exe と呼ばれるプログラムを出力します。 Program1.exe に名前を変更するには、追加、 [/out](reference/out-output-file-name.md)リンカー オプション。

`cl file1.c file2.c file3.c /link /out:program1.exe`

複数のプログラミングのミスを自動的にキャッチするをお勧めするかを使用してコンパイルして、 [/W3](reference/compiler-option-warning-level.md)または[/W4](reference/compiler-option-warning-level.md)警告レベル オプション。

`cl /W4 file1.c file2.c file3.c /link /out:program1.exe`

コンパイラ (cl.exe) はその他の多くのオプションをビルド、最適化、デバッグ、適用し、コードを分析することができます。 クイック一覧は、次のように入力します。`cl /?`開発者コマンド プロンプトでします。 コンパイル、リンクを別々 にし、およびより複雑なビルド シナリオでリンカー オプションの適用もできます。 コンパイラとリンカー オプション、使用状況の詳細については、次を参照してください。 [c/c++ ビルドのリファレンス](reference/c-cpp-building-reference.md)します。

構成して、コマンドラインでより複雑なプロジェクトをビルドする NMAKE やメイクファイル、MSBuild とプロジェクト ファイルを使用できます。 これらのツールの使用に関する詳細については、次を参照してください。 [NMAKE リファレンス](reference/nmake-reference.md)と[MSBuild](msbuild-visual-cpp.md)します。

C および C++ 言語は似ていますが、同じではありません。 Microsoft C/C++コンパイラ (MSVC) では、単純なルールを使用して、コードをコンパイルするときに使用する言語を決定します。 既定では、MSVC コンパイラは C ソース コード、.c で終わるすべてのファイルと C++ ソース コードとして .cpp で終わるすべてのファイルを扱います。 C 非依存のファイル名拡張子としてすべてのファイルを処理するコンパイラが使用して、 [/Tc](reference/tc-tp-tc-tp-specify-source-file-type.md)コンパイラ オプション。

MSVC は、ISO C99 標準と互換性のある厳密に準拠していないです。 ほとんどの場合、移植可能な C コードはコンパイルし、想定どおりに実行します。 Visual C では、ISO c11 変更のほとんどをサポートしていません。 特定のライブラリの関数と POSIX 関数名は、MSVC で非推奨とされます。 関数がサポートされますが、優先名が変更されました。 詳細については、次を参照してください。 [CRT のセキュリティ機能](../c-runtime-library/security-features-in-the-crt.md)と[コンパイラの警告 (レベル 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)します。

## <a name="see-also"></a>関連項目

[チュートリアル: 標準 C++ プログラム (C++) の作成](../windows/walkthrough-creating-a-standard-cpp-program-cpp.md)<br/>
[C 言語リファレンス](../c-language/c-language-reference.md)<br/>
[プロジェクトおよびビルド システム](projects-and-build-systems-cpp.md)<br/>
[互換性](../c-runtime-library/compatibility.md)
