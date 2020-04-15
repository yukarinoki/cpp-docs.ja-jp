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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335260"
---
# <a name="walkthrough-compile-a-c-program-on-the-command-line"></a>チュートリアル: コマンド ラインでの C プログラムのコンパイル

Visual C++ には、基本的なコンソール プログラムから完全な Windows デスクトップ アプリケーション、モバイル アプリ、および多くを作成するために使用できる C コンパイラが含まれています。

このチュートリアルでは、テキスト エディターを使用して基本的な "Hello, World" スタイルの C プログラムを作成し、コマンド ラインでコンパイルする方法を示します。 コマンド ラインで C++ で作業する場合は、「[チュートリアル : コマンド ラインでネイティブ C++ プログラムをコンパイルする](walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)」を参照してください。 コマンド ラインを使用する代わりに Visual Studio IDE を試す場合は、「[チュートリアル: プロジェクトとソリューションの操作 (C++)」](../ide/walkthrough-working-with-projects-and-solutions-cpp.md)または「Visual Studio IDE for [C++ デスクトップ開発](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)」を参照してください。

## <a name="prerequisites"></a>前提条件

このチュートリアルを完了するには、Visual Studio と Visual C++ のオプション コンポーネント、または Visual Studio 用のビルド ツールをインストールしておく必要があります。

Visual Studio は、多くの言語とプラットフォーム向けのエディター、リソース マネージャー、デバッガー、およびコンパイラをサポートする強力な統合開発環境です。 これらの機能の詳細と、Visual Studio の無料のエディションを含む Visual Studio をダウンロードしてインストールする方法については、「 [Visual Studio](/visualstudio/install/install-visual-studio)のインストール 」を参照してください。

Visual Studio のビルド ツールでは、C および C++ プログラムをビルドするために必要なコマンド ライン ツールセット、コンパイラ、ツール、およびライブラリのみがインストールされます。 これは、ラボや教室の演習を構築するのに最適であり、比較的迅速にインストールします。 コマンド ライン ツールセットのみをインストールするには、Visual Studio のダウンロード ページから Visual Studio 用ビルド ツール[をダウンロード](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019)し、インストーラーを実行します。 Visual Studio インストーラーで **、C++ ビルド ツール**のワークロードを選択し、[**インストール**] を選択します。

コマンド ラインで C または C++ プログラムをビルドする前に、ツールがインストールされていること、およびコマンド ラインからアクセスできることを確認する必要があります。 Visual C++ には、コマンド ライン環境で使用するツール、ヘッダー、およびライブラリを検索するための複雑な要件があります。 **準備をせずに、コマンド プロンプト ウィンドウで Visual C++ を使用することはできません**。 必要なすべての環境変数が設定されている通常のコマンド プロンプト ウィンドウである *、開発者のコマンド*プロンプト ウィンドウが必要です。 さいわい、Visual C++ では、コマンド ライン ビルド用にセットアップされた環境を持つ開発者コマンド プロンプトを起動するためのショートカットがインストールされています。 残念ながら、開発者コマンド プロンプトのショートカットの名前と、そのショートカットの場所は、Visual C++ のほぼすべてのバージョンと Windows のバージョンによって異なります。 最初のチュートリアル タスクは、使用する適切なショートカットを見つけることです。

> [!NOTE]
> 開発者コマンド プロンプトのショートカットは、コンパイラとツール、および必要なヘッダーとライブラリの正しいパスを自動的に設定します。 これらの値の一部は、ビルド構成ごとに異なります。 ショートカットの 1 つを使用しない場合は、これらの環境値を自分で設定する必要があります。 詳細については、[コマンド ライン ビルドのパスと環境変数の設定](setting-the-path-and-environment-variables-for-command-line-builds.md)に関するページを参照してください。 ビルド環境は複雑であるため、独自のビルドではなく、開発者コマンド プロンプト ショートカットを使用することを強くお勧めします。

これらの手順は、使用している Visual Studio のバージョンによって異なります。 Visual Studio の優先バージョンのドキュメントを表示するには、**バージョン**セレクター コントロールを使用します。 このページの目次の上部に表示されます。

::: moniker range="vs-2019"

## <a name="open-a-developer-command-prompt-in-visual-studio-2019"></a>Visual Studio 2019 で開発者コマンド プロンプトを開く

Windows 10 で Visual Studio 2019 をインストールしている場合は、[スタート] メニューを開き、下にスクロールして**Visual Studio 2019 フォルダー (Visual Studio 2019**アプリではない) を開きます。 **VS 2019 の開発者コマンド プロンプト**を選択して、コマンド プロンプト ウィンドウを開きます。

別のバージョンの Windows を使用している場合は、[スタート] メニューまたは [スタート] ページで、開発者コマンド プロンプトのショートカットを含む Visual Studio ツール フォルダーを探します。 Windows の検索機能を使用して"開発者コマンド プロンプト" を検索し、インストールされているバージョンの Visual Studio に一致するものを選択することもできます。 ショートカットを使用してコマンド プロンプト ウィンドウを開きます。

::: moniker-end

::: moniker range="vs-2017"

## <a name="open-a-developer-command-prompt-in-visual-studio-2017"></a>Visual Studio 2017 で開発者コマンド プロンプトを開く

Windows 10 で Visual Studio 2017 をインストールしている場合は、[スタート] メニューを開き、下にスクロールして**Visual Studio 2017 フォルダー (Visual Studio 2017**アプリではない) を開きます。 **VS 2017 の開発者コマンド プロンプト**を選択して、コマンド プロンプト ウィンドウを開きます。

別のバージョンの Windows を実行している場合は、[スタート] メニューまたは [スタート] ページで、開発者コマンド プロンプトのショートカットを含む Visual Studio ツール フォルダーを探します。 Windows の検索機能を使用して"開発者コマンド プロンプト" を検索し、インストールされているバージョンの Visual Studio に一致するものを選択することもできます。 ショートカットを使用してコマンド プロンプト ウィンドウを開きます。

::: moniker-end

::: moniker range="vs-2015"

## <a name="open-a-developer-command-prompt-in-visual-studio-2015"></a>Visual Studio 2015 で開発者コマンド プロンプトを開く

Windows 10 で Microsoft Visual C++ ビルド ツール 2015 をインストールしている場合は、[**スタート]** メニューを開き、下にスクロールして **[Visual C++ ビルド ツール]** フォルダーを開きます。 **Visual C++ 2015 x86 ネイティブ ツール コマンド プロンプト**を選択して、コマンド プロンプト ウィンドウを開きます。

別のバージョンの Windows を実行している場合は、[スタート] メニューまたは [スタート] ページで、開発者コマンド プロンプトのショートカットを含む Visual Studio ツール フォルダーを探します。 Windows の検索機能を使用して"開発者コマンド プロンプト" を検索し、インストールされているバージョンの Visual Studio に一致するものを選択することもできます。 ショートカットを使用してコマンド プロンプト ウィンドウを開きます。

::: moniker-end

次に、Visual C++ 開発者コマンド プロンプトが正しく設定されていることを確認します。 コマンド プロンプト ウィンドウで、`cl`次のように出力を入力して確認します。

```Output
C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
Copyright (C) Microsoft Corporation.  All rights reserved.

usage: cl [ option... ] filename... [ /link linkoption... ]
```

Visual C++ のバージョンやインストールされている更新プログラムによっては、現在のディレクトリ番号やバージョン番号が異なる場合があります。 上記の出力が表示と同様であれば、コマンド ラインで C または C++ プログラムをビルドする準備が整いました。

> [!NOTE]
> "'cl' が内部または外部コマンド、操作可能なプログラムまたはバッチ ファイルとして認識されない、プログラムまたはバッチ ファイルとして認識されないエラー **、cl**コマンドを実行するとエラー LNK1104 などのエラーが発生した場合は、開発者コマンド プロンプトを使用していないか、Visual C++ のインストールに問題があります。 続行する前に、この問題を修正する必要があります。

開発者のコマンド プロンプトのショートカットが見つからない場合、または を入力`cl`したときにエラー メッセージが表示される場合は、Visual C++ のインストールに問題がある可能性があります。 Visual Studio 2017 以降を使用している場合は、Visual Studio インストーラーで**C++ ワークロードを使用してデスクトップ開発**を再インストールしてみてください。 詳細については、「 [Visual Studio での C++ サポートのインストール](vscpp-step-0-installation.md)」を参照してください。 または[、Visual Studio](https://visualstudio.microsoft.com/downloads/)のダウンロード ページからビルド ツールを再インストールします。 これが動作するまで次のセクションに進まないでください。 インストールと Visual Studio のトラブルシューティングの詳細については[、「Visual Studio](/visualstudio/install/install-visual-studio)のインストール」を参照してください。

> [!NOTE]
> コンピューター上の Windows のバージョンとシステム セキュリティ構成によっては、右クリックして開発者のコマンド プロンプトのショートカット メニューを開き、[**管理者として実行**] を選択して、このチュートリアルを実行して作成したプログラムを正常にビルドして実行する必要があります。

## <a name="create-a-c-source-file-and-compile-it-on-the-command-line"></a>C ソース ファイルを作成し、コマンド ラインでコンパイルする

1. 開発者コマンド プロンプト ウィンドウで、`cd c:\`現在の作業ディレクトリを C: ドライブのルートに変更する場合に入力します。 次に、`md c:\simple`ディレクトリを作成する場合に入力し`cd c:\simple`、そのディレクトリに変更する場合に入力します。 このディレクトリには、ソースファイルとコンパイル済みプログラムが格納されます。

1. 開発者`notepad simple.c`コマンド プロンプトで入力します。 表示されるメモ帳の警告ダイアログで、[**はい**] を選択して作業ディレクトリに新しい simple.c ファイルを作成します。

1. メモ帳に次のコード行を入力します。

    ```C
    #include <stdio.h>

    int main()
    {
        printf("Hello, World! This is a native C program compiled on the command line.\n");
        return 0;
    }
    ```

1. メモ帳のメニュー バーで、[**ファイルの** > **保存**] を選択して、simple.c を作業ディレクトリに保存します。

1. 開発者コマンド プロンプト ウィンドウに戻ります。 コマンド`dir`プロンプトで、c:\simple ディレクトリの内容を一覧表示します。 ディレクトリ一覧に、次のようなソース ファイル simple.c が表示されます。

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

   日付やその他の詳細は、コンピュータによって異なります。 ソース コード ファイル simple.c が表示されない場合は、作成した c:\simple ディレクトリに変更したことを確認し、メモ帳で、ソース ファイルをこのディレクトリに保存したことを確認します。 また、.txt 拡張子ではなく、.c ファイル名拡張子を持つソース コードを保存していることを確認します。

1. プログラムをコンパイルするには、開発者`cl simple.c`コマンド プロンプトで入力します。

   コンパイラが表示する出力情報の行に、実行可能プログラム名 simple.exe が表示されます。

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
   > 「'cl'が内部または外部コマンド、操作可能なプログラムまたはバッチファイルとして認識されない」などのエラーが発生した場合、エラー C1034、またはエラー LNK1104 は、開発者コマンド プロンプトが正しく設定されていません。 この問題を解決する方法については、「**開発者コマンド プロンプトを開く**」セクションに戻ってください。

   > [!NOTE]
   > 別のコンパイラエラーまたはリンカーエラーまたは警告が表示された場合は、ソースコードを見直してエラーを修正し、保存してからコンパイラを再実行してください。 特定のエラーについては、このページの上部にある検索ボックスを使用してエラー番号を探します。

1. プログラムを実行するには、コマンド`simple`プロンプトで入力します。

   プログラムは、次のテキストを表示して終了します。

    ```Output
    Hello, World! This is a native C program compiled on the command line.
    ```

   これで、コマンド ラインを使用して C プログラムをコンパイルして実行しました。

## <a name="next-steps"></a>次のステップ

この「こんにちは、世界」の例は、Cプログラムが得ることができるのと同じくらい簡単です。 実際のプログラムには、ヘッダー ファイルとソース ファイルが増え、ライブラリにリンクされ、便利な作業が行われます。

このチュートリアルの手順を使用すると、サンプル コードを入力する代わりに独自の C コードを作成できます。 また、他の場所で見つけた多くの C コード サンプル プログラムをビルドすることもできます。 追加のソース コード ファイルを含むプログラムをコンパイルするには、コマンド ラインで次のようにすべて入力します。

`cl file1.c file2.c file3.c`

コンパイラは、file1.exe というプログラムを出力します。 名前を program1.exe に変更するには[、/out](reference/out-output-file-name.md)リンカー オプションを追加します。

`cl file1.c file2.c file3.c /link /out:program1.exe`

さらに、より多くのプログラミングミスを自動的にキャッチするために[、/W3](reference/compiler-option-warning-level.md)または[/W4](reference/compiler-option-warning-level.md)警告レベル オプションを使用してコンパイルすることをお勧めします。

`cl /W4 file1.c file2.c file3.c /link /out:program1.exe`

コンパイラ cl.exe には、コードのビルド、最適化、デバッグ、および分析に適用できるオプションが多数あります。 クイック リストについては、開発者`cl /?`コマンド プロンプトで入力します。 さらに複雑なビルド シナリオで、個別にコンパイルおよびリンクし、リンカー オプションを適用することもできます。 コンパイラおよびリンカーのオプションと使用方法の詳細については[、「C/C++ のビルドリファレンス](reference/c-cpp-building-reference.md)」を参照してください。

NMAKE とメイクファイル、または MSBuild ファイルとプロジェクト ファイルを使用して、より複雑なプロジェクトをコマンド ラインで構成およびビルドできます。 これらのツールの使用方法の詳細については、「 [NMAKE リファレンス](reference/nmake-reference.md)」および「 [MSBuild](msbuild-visual-cpp.md)」を参照してください。

C 言語と C++ 言語は似ていますが、同じではありません。 Microsoft C/C++ コンパイラ (MSVC) では、単純な規則を使用して、コードのコンパイル時に使用する言語を決定します。 既定では、MSVC コンパイラは、.c で終わるすべてのファイルを C ソース コードとして扱い、.cpp で終わるすべてのファイルを C++ ソース コードとして扱います。 コンパイラがすべてのファイルを C 非依存ファイル拡張子として扱うように強制するには[、/Tc](reference/tc-tp-tc-tp-specify-source-file-type.md)コンパイラ オプションを使用します。

MSVC は ISO C99 規格と互換性がありますが、厳密には準拠していません。 ほとんどの場合、ポータブル C コードは、予想どおりにコンパイルされ、実行されます。 Visual C++ では、ISO C11 のほとんどの変更はサポートされません。 一部のライブラリー関数および POSIX 関数名は MSVC によって非推奨です。 関数はサポートされていますが、優先名が変更されました。 詳細については、「 [CRT](../c-runtime-library/security-features-in-the-crt.md)および[コンパイラ警告 (レベル 3) C4996 の](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)セキュリティ機能」を参照してください。

## <a name="see-also"></a>関連項目

[チュートリアル: 標準 C++ プログラム (C++) の作成](../windows/walkthrough-creating-a-standard-cpp-program-cpp.md)<br/>
[C 言語リファレンス](../c-language/c-language-reference.md)<br/>
[プロジェクトおよびビルド システム](projects-and-build-systems-cpp.md)<br/>
[互換性](../c-runtime-library/compatibility.md)
