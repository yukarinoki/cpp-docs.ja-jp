---
title: 'チュートリアル: コマンドラインでネイティブ C++ プログラムのコンパイル'
description: 使用して、MicrosoftC++コマンド プロンプトからコンパイラ。
ms.custom: conceptual
ms.date: 04/23/2019
helpviewer_keywords:
- native code [C++]
- Visual C++, native code
- compiling programs [C++]
- command-line applications [C++], native
ms.assetid: b200cfd1-0440-498f-90ee-7ecf92492dc0
ms.openlocfilehash: 64300c8683dd5d1c40638ba7d50acfca6abc40c0
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65217713"
---
# <a name="walkthrough-compiling-a-native-c-program-on-the-command-line"></a>チュートリアル: コマンドラインでネイティブ C++ プログラムのコンパイル

Visual Studio が含まれていますが、コマンド ラインC++コンパイラ基本的なコンソール アプリからユニバーサル Windows プラットフォーム アプリ、デスクトップ アプリ、デバイス ドライバー、および .NET コンポーネントへのすべての作成に使用できます。

このチュートリアルでは、"Hello, World"の基本的な作成-エディターでテキストを使用して C++ プログラムのスタイル設定し、それをコマンドラインでコンパイルします。 コマンドラインを使用する代わりに、Visual Studio IDE を再試行してくださいを参照してくださいしたい場合[チュートリアル。プロジェクトとソリューション (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md)または[C++ デスクトップ開発用 Visual Studio IDE を使用して](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)します。

このチュートリアルでは、表示されている Visual C++ プログラムを入力する代わりに独自の Visual C++ プログラムを使用するか、別のヘルプ記事の Visual C++ コード サンプルを使用できます。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを完了する必要がありますがインストールした Visual Studio と省略可能な**C++ によるデスクトップ開発**ワークロード、または Visual Studio のコマンド ライン ビルド ツール。

Visual Studio は、多くの言語とプラットフォームの全機能装備のエディター、リソース マネージャー、デバッガー、およびコンパイラをサポートする強力な統合開発環境 (IDE) です。 C と C++ の開発をサポートするように、ダウンロードして無料の Visual Studio Community edition など、Visual Studio をインストールする方法については、次を参照してください。 [Visual Studio で C++ のインストール サポート](vscpp-step-0-installation.md)します。

For Visual Studio Build Tools は、コマンド ライン コンパイラ、ツール、および C および C++ プログラムをビルドする必要があるライブラリのみをインストールします。 ビルド環境に最適なまたはと比較的高速インストールを実行します。 コマンド ライン ツールのみをインストールするには、探して Build Tools for Visual Studio、 [Visual Studio のダウンロード](https://visualstudio.microsoft.com/downloads/)ページ。

C または C++ プログラムを作成するには、コマンドラインで、前に、ツールがインストールされているし、コマンドラインからアクセスできることを確認する必要があります。 Visual C には、コマンド ライン ツール、ヘッダー、および使用するライブラリを検索する環境の複雑な要件があります。 **普通のコマンド プロンプト ウィンドウで、Visual C を使用することはできません**準備作業を実行しなくてもします。 さいわい、Visual C では、コマンド ライン ビルドを設定する環境のある開発者コマンド プロンプトを起動するためのショートカットをインストールします。 残念ながら、開発者コマンド プロンプトのショートカットとされている名前は、ほぼすべてのバージョンの Visual C とに異なるバージョンの Windows で異なる。 最初のチュートリアル タスクでは、使用する適切なものを見つけることです。

> [!NOTE]
> 開発者コマンド プロンプトのショートカットは、コンパイラおよびツール、および必要なヘッダーとライブラリによって正しいパスを自動的に設定します。 必要がありますこれらの環境値自分で設定した場合は、通常を使用する**コマンド プロンプト**ウィンドウ。 詳細については、次を参照してください。[コマンド ライン ビルドのパスと環境変数を設定する](setting-the-path-and-environment-variables-for-command-line-builds.md)します。 独自に構築する代わりに、開発者コマンド プロンプト ショートカットを使用することをお勧めします。

### <a name="open-a-developer-command-prompt"></a>開発者コマンド プロンプトを開きます

1. Visual Studio 2017 または後で Windows 10 をインストールする場合、[スタート] メニューを開くし、選択**すべてのアプリ**します。 スクロール ダウンして開く、 **Visual Studio**フォルダー (Visual Studio アプリケーションではありません)。 選択**開発者コマンド プロンプト for VS**コマンド プロンプト ウィンドウを開きます。

   Windows 10 に Microsoft Visual C Build Tools 2015 をインストールした場合は、開く、**開始**メニュー選択**すべてのアプリ**。 スクロール ダウンして開く、 **Visual C Build Tools**フォルダー。 選択**Visual C 2015 x86 Native Tools コマンド プロンプト**コマンド プロンプト ウィンドウを開きます。

   「開発者コマンド プロンプト」を検索し、Visual Studio のインストールされているバージョンと一致するものを選択して、Windows 検索機能を使用することもできます。 ショートカットを使用して、コマンド プロンプト ウィンドウを開きます。

1. 次に、Visual C の開発者コマンド プロンプトが正しく設定されていることを確認します。 コマンド プロンプト ウィンドウで、入力`cl`し、出力は次ようなコードのことを確認します。

   ```Output
   C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
   Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
   Copyright (C) Microsoft Corporation.  All rights reserved.

   usage: cl [ option... ] filename... [ /link linkoption... ]
   ```

   現在のディレクトリまたは Visual C と更新プログラムがインストールされている任意のバージョンに応じて、バージョン番号の相違がある可能性があります。 上記の出力が表示される内容のような場合は、コマンドラインでの C または C++ プログラムを作成する準備ができました。

   > [!NOTE]
   > 「'Cl' は、内部または外部コマンド、操作可能なプログラムまたはバッチ ファイルとしては認識されません"など、エラーが発生した場合エラー C1034 またはエラー LNK1104 を実行すると、 **cl**コマンドを使用するか、開発者コマンド プロンプトを使用しない、またはVisual C のインストールに問題があります。 続行するには、この問題を修正する必要があります。

   開発者コマンド プロンプトのショートカットを見つけられない場合、または入力すると、エラー メッセージが表示された場合`cl`、Visual C インストール問題がある可能性があります。 Visual Studio で、Visual C コンポーネントを再インストールを再試行してください。 または、Microsoft Visual C Build Tools を再インストールします。 を接続しない次のセクションにはこれまでです。 インストールして、Visual C のトラブルシューティングの詳細については、次を参照してください。 [Visual Studio のインストール](/visualstudio/install/install-visual-studio)します。

   > [!NOTE]
   > によって、コンピューターとシステムのセキュリティ構成の Windows のバージョンを右クリックすると、開発者コマンド プロンプト ショートカットのショートカット メニューを開き、選択し、必要があります**管理者として実行**に正常にビルドして、このチュートリアルで作成するプログラムを実行します。

### <a name="create-a-visual-c-source-file-and-compile-it-on-the-command-line"></a>Visual C ソース ファイルを作成し、コマンドラインでコンパイル

1. 開発者コマンド プロンプト ウィンドウで次のように入力します。`md c:\hello`ディレクトリを作成し、入力`cd c:\hello`をそのディレクトリに変更します。 このディレクトリでソース ファイルと、コンパイル済みプログラムを作成します。

1. 入力`notepad hello.cpp`コマンド プロンプト ウィンドウでします。

   選択**はい**メモ帳がファイルを作成することを要求するときにします。 この手順では、hello.cpp という名前のファイルに、コードを入力するための準備ができて、メモ帳の空白ウィンドウを開きます。

1. メモ帳で、次のコード行を入力します。

   ```cpp
   #include <iostream>
   using namespace std;
   void main()
   {
       cout << "Hello, world, from Visual C++!" << endl;
   }
   ```

   このコードは、画面上の 1 つの行のテキストを入力し、終了する単純なプログラムです。 エラーを最小限に抑えるには、このコードをコピーし、メモ帳に貼り付けます。

1. 作業内容を保存します。 メモ帳で、 **[ファイル]** メニューの **[保存]** を選びます。

   これで、作成した、C++ソース ファイルをコンパイルする準備ができて hello.cpp します。

1. 開発者コマンド プロンプト ウィンドウに切り替えます。 入力`dir`c:\hello ディレクトリの内容を一覧表示するコマンド プロンプトでします。 ように、ディレクトリのリストにソース ファイル hello.cpp が表示されます。

   ```Output
   c:\hello>dir
    Volume in drive C has no label.
    Volume Serial Number is CC62-6545

    Directory of c:\hello

   05/24/2016  05:36 PM    <DIR>          .
   05/24/2016  05:36 PM    <DIR>          ..
   05/24/2016  05:37 PM               115 hello.cpp
                  1 File(s)            115 bytes
                  2 Dir(s)  571,343,446,016 bytes free

   ```

   日付とその他の詳細については、コンピューターに異なります。 ソース コード ファイルが見つからない場合 hello.cpp は作成した c:\hello ディレクトリに変更したかどうかを確認し、メモ帳でこのディレクトリにソース ファイルを保存することを確認します。 また、.cpp ファイル名拡張子を .txt という拡張子ではないと、ソース コードを保存したことを確認します。

1. 開発者コマンド プロンプトで次のように入力します。`cl /EHsc hello.cpp`プログラムをコンパイルします。

   cl.exe コンパイラによって、コンパイルされたコードを含む .obj ファイルが生成され、リンカーが実行されて hello.exe という名前の実行可能プログラムが作成されます。 この名前は、コンパイラによって表示される出力情報の行に表示されます。 コンパイラの出力は、ようになります。

   ```Output
   c:\hello>cl /EHsc hello.cpp
   Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
   Copyright (C) Microsoft Corporation.  All rights reserved.

   hello.cpp
   Microsoft (R) Incremental Linker Version 14.10.25017.0
   Copyright (C) Microsoft Corporation.  All rights reserved.

   /out:hello.exe
   hello.obj
   ```

   > [!NOTE]
   > 「'Cl' は、内部または外部コマンド、操作可能なプログラムまたはバッチ ファイルとしては認識されません"など、エラーが発生した場合エラー C1034 またはエラー LNK1104、開発者コマンド プロンプトが正しくセットアップされていません。 この問題を解決する方法についてに戻り、**開発者コマンド プロンプトを開き**セクション。

   > [!NOTE]
   > 別のコンパイラまたはリンカーのエラーまたは警告が発生した場合、エラーを修正し、保存およびコンパイラをもう一度実行するソース コードを確認します。 特定のエラーについては、この MSDN のページで、検索ボックスを使用して、エラー番号を検索します。

1. hello.exe プログラムを実行するには、コマンド プロンプトで `hello`と入力します。

   プログラムは、次のテキストを表示して終了します。

   ```Output
   Hello, world, from Visual C++!
   ```

   これで、コンパイルし、コマンド ライン ツールを使用して、C++ プログラムを実行します。

## <a name="next-steps"></a>次の手順

この"Hello, World"の例は、単純な C++ プログラムを取得できます。 実際のプログラムがあるヘッダー ファイルと複数のソース ファイルは、ライブラリでは、リンクし、有益な処理を実行します。

このチュートリアルで示したサンプル コードを入力する代わりに独自の C++ コードをビルドするのに手順を使用できます。 別の場所に表示されている多くの C++ コード サンプル プログラムを構築することもできます。 ソース コードを配置し、任意の書き込み可能なディレクトリでのアプリを構築できます。 既定では、Visual Studio IDE は、という名前の Visual Studio のバージョンの Visual Studio フォルダーのプロジェクト サブフォルダーに、ドキュメント フォルダー内にプロジェクトを作成します。

追加のソース コード ファイルのあるプログラムをコンパイルするには、コマンドラインですべてのようにそれらを入力します。

`cl /EHsc file1.cpp file2.cpp file3.cpp`

`/EHsc` は、コンパイラに対して C++ 例外処理を有効化するよう指示するコマンド ライン オプションです。 詳細については、「[/EH (例外処理モデル)](reference/eh-exception-handling-model.md)」を参照してください。

追加のソース ファイルを指定するときに、コンパイラは最初の入力ファイルを使用して、プログラム名を作成します。 この場合、file1.exe と呼ばれるプログラムを出力します。 Program1.exe に名前を変更するには、追加、 [/out](reference/out-output-file-name.md)リンカー オプション。

`cl /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

複数のプログラミングのミスを自動的にキャッチするをお勧めするかを使用してコンパイルして、 [/W3](reference/compiler-option-warning-level.md)または[/W4](reference/compiler-option-warning-level.md)警告レベル オプション。

`cl /W4 /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

コンパイラ (cl.exe) はその他の多くのオプションをビルド、最適化、デバッグ、適用し、コードを分析することができます。 クイック一覧は、次のように入力します。`cl /?`開発者コマンド プロンプトでします。 コンパイル、リンクを別々 にし、およびより複雑なビルド シナリオでリンカー オプションの適用もできます。 コンパイラとリンカー オプション、使用状況の詳細については、次を参照してください。 [c/c++ ビルドのリファレンス](reference/c-cpp-building-reference.md)します。

構成して、コマンドラインでより複雑なプロジェクトをビルドする NMAKE やメイクファイル、MSBuild とプロジェクト ファイルを使用できます。 これらのツールの使用に関する詳細については、次を参照してください。 [NMAKE リファレンス](reference/nmake-reference.md)と[MSBuild](msbuild-visual-cpp.md)します。

C および C++ 言語は似ていますが、同じではありません。 MSVC コンパイラでは、単純なルールを使用して、コードをコンパイルするときに使用する言語を決定します。 既定では、MSVC コンパイラは C ソース コード、.c で終わるすべてのファイルと C++ ソース コードとして .cpp で終わるすべてのファイルを扱います。 C++ ファイル名拡張子に非依存としてすべてのファイルを処理するコンパイラが使用して、 [/TC](reference/tc-tp-tc-tp-specify-source-file-type.md)コンパイラ オプション。

MSVC コンパイラには、ISO C99 標準と互換性が厳密に準拠していない C ランタイム ライブラリ (CRT) が含まれています。 ほとんどの場合、移植可能なコードはコンパイルし、想定どおりに実行します。 Visual C は、ISO c11 CRT の変更の一部をサポートしていません。 MSVC コンパイラでは、特定のライブラリの関数と POSIX 関数名は非推奨します。 関数がサポートされますが、優先名が変更されました。 詳細については、次を参照してください。 [CRT のセキュリティ機能](../c-runtime-library/security-features-in-the-crt.md)と[コンパイラの警告 (レベル 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)します。

## <a name="see-also"></a>関連項目

[C++ 言語リファレンス](../cpp/cpp-language-reference.md)<br/>
[プロジェクトおよびビルド システム](projects-and-build-systems-cpp.md)<br/>
[MSVC コンパイラ オプション](reference/compiler-options.md)
