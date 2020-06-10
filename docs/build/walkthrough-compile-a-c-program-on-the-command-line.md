---
title: 'チュートリアル: コマンド ラインでの C プログラムのコンパイル'
ms.custom: conceptual
ms.date: 04/25/2019
helpviewer_keywords:
- command-line applications [C++], C programs
- Visual C, compiling
- compiling programs [C++]
- C program compiling [C++]
ms.assetid: 7e74cc2d-54b1-49de-b7ad-d3ae6b39ab8d
ms.openlocfilehash: d807fa75b32b515c2222fec9ea9d070266303e33
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335260"
---
# <a name="walkthrough-compile-a-c-program-on-the-command-line"></a>チュートリアル: コマンド ラインでの C プログラムのコンパイル

Visual C++ に含まれる C コンパイラを使用して、基本的なコンソール プログラムから、完全な Windows デスクトップ アプリケーションやモバイル アプリまで、あらゆるものを作成できます。

このチュートリアルでは、テキスト エディターを使用して基本的な "Hello, World" スタイルの C++ プログラムを作成した後、それをコマンド ラインでコンパイルする方法を示しします。 コマンド ラインで C++ を使用する場合は、「[チュートリアル: コマンド ラインでのネイティブ C++ プログラムのコンパイル](walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)」を参照してください。 コマンド ラインではなく Visual Studio IDE を試したい場合は、「[チュートリアル: プロジェクトとソリューションの使用 (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md)」または「[C++ デスクトップ開発のための Visual Studio IDE の使用](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)」を参照してください。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを最後まで行うには、Visual Studio とオプションの Visual C++ コンポーネント、または Build Tools for Visual Studio が、インストールされている必要があります。

Visual Studio は強力な統合開発環境であり、あらゆる機能を備えたエディター、リソース マネージャー、デバッガー、およびさまざまな言語とプラットフォームに対応したコンパイラがサポートされています。 無料の Visual Studio Community エディションなど、これらの機能と、Visual Studio をダウンロードしてインストールする方法については、「[Visual Studio のインストール](/visualstudio/install/install-visual-studio)」を参照してください。

Visual Studio の Build Tools for Visual Studio バージョンでは、C と C++ のプログラムをビルドするために必要なコマンド ライン ツールセット、コンパイラ、ツール、ライブラリのみがインストールされます。 ビルド ラボやクラスルームの演習に最適であり、比較的短時間でインストールできます。 コマンド ライン ツールセットのみをインストールするには、[Visual Studio のダウンロード](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019) ページから Build Tools for Visual Studio をダウンロードして、インストーラを実行します。 Visual Studio インストーラーで、 **[C++ Build Tools]** ワークロードを選択して、 **[インストール]** を選択します。

C または C++ のプログラムをコマンド ラインでビルドするには、その前に、ツールがインストールされていて、コマンド ラインからアクセスできることを確認しておく必要があります。 Visual C++ の場合、コマンド ライン環境で使用されるツール、ヘッダー、ライブラリを検出するには、複雑な要件があります。 何も準備を行わずに、**そのままのコマンド プロンプト ウィンドウで Visual C++ を使用することはできません**。 "*開発者コマンド プロンプト*" ウィンドウが必要です。これは、必要な環境変数がすべて設定されている通常のコマンド プロンプト ウィンドウです。 さいわい、Visual C++ では、コマンド ライン ビルド用の環境のセットアップが含まれる開発者コマンド プロンプトを起動するためのショートカットが、自動的にインストールされます。 残念ながら、開発者コマンド プロンプトのショートカットの名前とそれがある場所は、Visual C++ のほぼすべてのバージョンと Windows のバージョンで異なります。 チュートリアルでの最初のタスクは、使用する適切なショートカットを見つけることです。

> [!NOTE]
> 開発者コマンド プロンプトのショートカットを使用すると、コンパイラとツールおよび必要なヘッダーとライブラリに対する正しいパスが、自動的に設定されます。 これらの値の一部は、ビルド構成ごとに異なります。 いずれかのショートカットを使用しない場合は、これらの環境値を自分で設定する必要があります。 詳細については、[コマンド ライン ビルドのパスと環境変数の設定](setting-the-path-and-environment-variables-for-command-line-builds.md)に関するページを参照してください。 ビルド環境は複雑なので、自分で構築するのではなく、開発者コマンド プロンプトのショートカットを使用することを強くお勧めします。

手順は、使用している Visual Studio のバージョンによって異なります。 優先するバージョンの Visual Studio のドキュメントを表示するには、 **[バージョン]** セレクター コントロールを使用します。 このページの目次の一番上にあります。

::: moniker range="vs-2019"

## <a name="open-a-developer-command-prompt-in-visual-studio-2019"></a>Visual Studio 2019 で開発者コマンド プロンプトを開く

Windows 10 に Visual Studio 2019 がインストールされている場合は、[スタート] メニューを開き、下にスクロールして、(Visual Studio 2019 アプリではなく) **[Visual Studio 2019]** フォルダーを開きます。 **[開発者コマンド プロンプト for VS 2019]** を選択して、コマンド プロンプト ウィンドウを開きます。

別のバージョンの Windows を使用している場合は、[スタート] メニューまたは [スタート] ページで、開発者コマンド プロンプトのショートカットが含まれている Visual Studio Tools フォルダーを探します。 また、Windows の検索機能を使用して "開発者コマンド プロンプト" を検索し、インストールされている Visual Studio のバージョンに一致するものを選択することもできます。 ショートカットを使用してコマンド プロンプト ウィンドウを開きます。

::: moniker-end

::: moniker range="vs-2017"

## <a name="open-a-developer-command-prompt-in-visual-studio-2017"></a>Visual Studio 2017 で開発者コマンド プロンプトを開く

Windows 10 に Visual Studio 2017 がインストールされている場合は、[スタート] メニューを開き、下にスクロールして、(Visual Studio 2017 アプリではなく) **[Visual Studio 2017]** フォルダーを開きます。 **[開発者コマンド プロンプト for VS 2017]** を選択して、コマンド プロンプト ウィンドウを開きます。

別のバージョンの Windows を実行している場合は、[スタート] メニューまたは [スタート] ページで、開発者コマンド プロンプトのショートカットが含まれている Visual Studio Tools フォルダーを探します。 また、Windows の検索機能を使用して "開発者コマンド プロンプト" を検索し、インストールされている Visual Studio のバージョンに一致するものを選択することもできます。 ショートカットを使用してコマンド プロンプト ウィンドウを開きます。

::: moniker-end

::: moniker range="vs-2015"

## <a name="open-a-developer-command-prompt-in-visual-studio-2015"></a>Visual Studio 2015 で開発者コマンド プロンプトを開く

Windows 10 に Microsoft Visual C++ Build Tools 2015 がインストールされている場合は、 **[スタート]** メニューを開き、下にスクロールして、 **[Visual C++ Build Tools]** フォルダーを開きます。 **[Visual C++ 2015 x86 Native Tools Command Prompt]\(Visual C++ 2015 x86 Native Tools コマンドプロンプト\)** を選択して、コマンド プロンプト ウィンドウを開きます。

別のバージョンの Windows を実行している場合は、[スタート] メニューまたは [スタート] ページで、開発者コマンド プロンプトのショートカットが含まれている Visual Studio Tools フォルダーを探します。 また、Windows の検索機能を使用して "開発者コマンド プロンプト" を検索し、インストールされている Visual Studio のバージョンに一致するものを選択することもできます。 ショートカットを使用してコマンド プロンプト ウィンドウを開きます。

::: moniker-end

次に、Visual C++ の開発者コマンド プロンプトが正しくセットアップされていることを確認します。 コマンド プロンプト ウィンドウで「`cl`」と入力し、出力が次のようになることを確認します。

```Output
C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
Copyright (C) Microsoft Corporation.  All rights reserved.

usage: cl [ option... ] filename... [ /link linkoption... ]
```

インストールされている Visual C++ のバージョンと更新プログラムによっては、現在のディレクトリまたはバージョン番号が異なる場合があります。 上記と似た出力が表示される場合は、コマンド ラインで C または C++ のプログラムをビルドする準備ができています。

> [!NOTE]
> **cl** コマンドを実行すると、"'cl' は、内部コマンドまたは外部コマンド、操作可能なプログラムまたはバッチ ファイルとして認識されていません"、エラー C1034、エラー LNK1104 などのエラーが発生する場合は、開発者コマンド プロンプトを使用していないか、または Visual C++ のインストールに何らかの問題があります。 続けるには、この問題を解決する必要があります。

開発者コマンド プロンプトのショートカットが見つからない場合、または `cl` を入力するとエラー メッセージが表示される場合は、Visual C++ のインストールに問題がある可能性があります。 Visual Studio 2017 以降を使用している場合は、Visual Studio インストーラーで **C++ によるデスクトップ開発**ワークロードを再インストールしてみます。 詳細については、「[Visual Studio での C++ サポートのインストール](vscpp-step-0-installation.md)」を参照してください。 または、[Visual Studio のダウンロード](https://visualstudio.microsoft.com/downloads/) ページから Build Tools を再インストールします。 この作業が終わるまで、次のセクションに進まないでください。 Visual Studio のインストールとトラブルシューティングの詳細については、「[Visual Studio のインストール](/visualstudio/install/install-visual-studio)」を参照してください。

> [!NOTE]
> コンピューターの Windows のバージョンおよびシステムのセキュリティ構成によっては、このチュートリアルに従って作成するアプリケーションを正常にビルドして実行するために、開発者コマンド プロンプト ショートカットを右クリックしてショートカット メニューを開き、 **[管理者として実行]** を選択することが必要な場合があります。

## <a name="create-a-c-source-file-and-compile-it-on-the-command-line"></a>C のソース ファイルを作成してコマンド ラインでコンパイルする

1. 開発者コマンド プロンプト ウィンドウで「`cd c:\`」と入力して、現在の作業ディレクトリを C: ドライブのルートに変更します。 次に、「`md c:\simple`」と入力してディレクトリを作成し、「`cd c:\simple`」と入力してそのディレクトリに変更します。 このディレクトリに、ソース ファイルとコンパイル済みプログラムが保持されます。

1. 開発者コマンド プロンプトで「`notepad simple.c`」と入力します。 メモ帳の警告ダイアログ ボックスが表示されたら **[はい]** を選択して、作業ディレクトリに新しい simple.c ファイルを作成します。

1. メモ帳で、次のコード行を入力します。

    ```C
    #include <stdio.h>

    int main()
    {
        printf("Hello, World! This is a native C program compiled on the command line.\n");
        return 0;
    }
    ```

1. メモ帳のメニュー バーで **[ファイル]**  >  **[保存]** を選択して、作業ディレクトリに simple.c を保存します。

1. 開発者コマンド プロンプト ウィンドウに戻ります。 コマンド プロンプトで「`dir`」と入力して、c:\simple ディレクトリの内容の一覧を表示します。 次のように、ディレクトリの内容の一覧にソース ファイル simple.c が表示されるはずです。

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

   日付と他の詳細は使用しているコンピューターによって異なります。 ソース コード ファイル simple.c が表示されない場合は、作成した c:\simple ディレクトリに切り替えたことを確認し、メモ帳で、ソース ファイルをこのディレクトリに保存したことを確認します。 また、保存したソース コードのファイル名拡張子が、.txt ではなく .c であることを確認します。

1. プログラムをコンパイルするには、開発者コマンド プロンプトで「`cl simple.c`」と入力します。

   実行可能プログラムの名前 simple.exe は、コンパイラによって表示される出力情報の行で確認できます。

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
   > "'cl' は、内部コマンドまたは外部コマンド、操作可能なプログラムまたはバッチ ファイルとして認識されていません"、エラー C1034、エラー LNK1104 などのエラーが発生する場合は、開発者コマンド プロンプトが正しくセットアップされていません。 この問題を解決する方法については、「**開発者コマンド プロンプトを開く**」セクションを再確認してください。

   > [!NOTE]
   > これとは異なるコンパイラ エラー、リンカー エラー、または警告が発生する場合は、ソース コードを確認してエラーを修正し、保存してからコンパイラを再度実行します。 特定のエラーの詳細については、このページの先頭にある検索ボックスを使用して、エラー番号を検索してください。

1. プログラムを実行するには、コマンド プロンプトで「`simple`」と入力します。

   プログラムは、次のテキストを表示して終了します。

    ```Output
    Hello, World! This is a native C program compiled on the command line.
    ```

   これで、コマンド ラインを使用した C プログラムのコンパイルと実行が完了しました。

## <a name="next-steps"></a>次の手順

この "Hello, World" の例は、C プログラムでできる最も簡単なことです。 実際のプログラムには、ヘッダー ファイルや多くのソース ファイル、ライブラリへのリンク、役に立つ機能があります。

このチュートリアルの手順を使用すれば、示されているサンプル コードを入力する代わりに、独自の C コードを作成できます。 他の場所で見つかる多くの C コード サンプル プログラムをビルドすることもできます。 追加のソース コード ファイルがあるプログラムをコンパイルするには、次のようにコマンド ラインですべてを入力します。

`cl file1.c file2.c file3.c`

コンパイラでは、file1.exe というプログラムが出力されます。 名前を program1.exe に変更するには、[/out](reference/out-output-file-name.md) リンカー オプションを追加します。

`cl file1.c file2.c file3.c /link /out:program1.exe`

また、さらに多くのプログラミングの誤りが自動的にキャッチされるよう、[/W3](reference/compiler-option-warning-level.md) または [/W4](reference/compiler-option-warning-level.md) の警告レベル オプションを使用してコンパイルすることをお勧めします。

`cl /W4 file1.c file2.c file3.c /link /out:program1.exe`

コンパイラ cl.exe には他にも多くのオプションがあり、コードのビルド、最適化、デバッグ、分析に適用できます。 簡単に一覧を見るには、開発者コマンド プロンプトで「`cl /?`」と入力します。 また、さらに複雑なビルド シナリオでは、コンパイルとリンクを別々に行い、リンカー オプションを適用することもできます。 コンパイラとリンカーのオプションと使用方法の詳細については、「[C/C++ ビルドのリファレンス](reference/c-cpp-building-reference.md)」を参照してください。

NMAKE とメイクファイル、または MSBuild とプロジェクト ファイルを使用すると、さらに複雑なプロジェクトをコマンド ラインで構成し、ビルドすることができます。 これらのツールの使用方法の詳細については、「[NMAKE リファレンス](reference/nmake-reference.md)」および「[MSBuild](msbuild-visual-cpp.md)」を参照してください。

C 言語と C++ 言語は似ていますが、同じではありません。 Microsoft C/C++ コンパイラ (MSVC) では、簡単なルールを使用して、コードをコンパイルするときに使用する言語が決定されます。 既定の MSVC コンパイラでは、末尾が .c のファイルはすべて C ソース コードとして扱われ、末尾が .cpp のファイルはすべて C++ ソース コードとして扱われます。 ファイル名拡張子に関係なくコンパイラですべてのファイルが C として扱われるように強制するには、[/Tc](reference/tc-tp-tc-tp-specify-source-file-type.md) コンパイラ オプションを使用します。

MSVC は ISO C99 標準と互換性がありますが、厳密には準拠していません。 ほとんどの場合、移植可能な C コードは予期されるとおりにコンパイルされて実行されます。 Visual C++ では、ISO C11 でのほとんどの変更がサポートされていません。 一部のライブラリ関数と POSIX 関数名は、MSVC では非推奨になっています。 関数はサポートされていますが、推奨される名前は変更されています。 詳細については、「[CRT のセキュリティ機能](../c-runtime-library/security-features-in-the-crt.md)」と「[コンパイラ警告 (レベル 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)」を参照してください。

## <a name="see-also"></a>関連項目

[チュートリアル: 標準 C++ プログラム (C++) の作成](../windows/walkthrough-creating-a-standard-cpp-program-cpp.md)<br/>
[C 言語リファレンス](../c-language/c-language-reference.md)<br/>
[プロジェクトおよびビルド システム](projects-and-build-systems-cpp.md)<br/>
[互換性](../c-runtime-library/compatibility.md)
