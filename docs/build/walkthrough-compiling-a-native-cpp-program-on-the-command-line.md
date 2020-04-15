---
title: 'チュートリアル: コマンド ラインでのネイティブ C++ プログラムのコンパイル'
description: コマンド プロンプトから Microsoft C++ コンパイラを使用します。
ms.custom: conceptual
ms.date: 04/02/2020
helpviewer_keywords:
- native code [C++]
- Visual C++, native code
- compiling programs [C++]
- command-line applications [C++], native
ms.assetid: b200cfd1-0440-498f-90ee-7ecf92492dc0
ms.openlocfilehash: c24fdfdaef612059d5c2fbaaa58f10d83f5fe3a8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335231"
---
# <a name="walkthrough-compiling-a-native-c-program-on-the-command-line"></a>チュートリアル: コマンド ラインでのネイティブ C++ プログラムのコンパイル

Visual Studio には、コマンド ライン C コンパイラと C++ コンパイラが含まれています。 このツールを使用すると、基本的なコンソール アプリからユニバーサル Windows プラットフォーム アプリ、デスクトップ アプリ、デバイス ドライバー、および .NET コンポーネントまで、あらゆるものを作成できます。

このチュートリアルでは、テキスト エディターを使用して基本的な "Hello, World" 形式の C++ プログラムを作成し、コマンド ラインでコンパイルします。 コマンド ラインを使用する代わりに Visual Studio IDE を試す場合は、「[チュートリアル: プロジェクトとソリューションの操作 (C++)」](../ide/walkthrough-working-with-projects-and-solutions-cpp.md)または「Visual Studio IDE for [C++ デスクトップ開発](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)」を参照してください。

このチュートリアルでは、表示されている C++ プログラムを入力する代わりに、独自の C++ プログラムを使用できます。 または、別のヘルプ記事の C++ コード サンプルを使用できます。

## <a name="prerequisites"></a>前提条件

このチュートリアルを完了するには、Visual Studio と C++ ワークロードを**使用したオプションのデスクトップ開発**、または Visual Studio 用のコマンド ライン ビルド ツールをインストールしておく必要があります。

Visual Studio は*統合開発環境*(IDE) です。 多くの言語とプラットフォーム向けのエディタ、リソースマネージャー、デバッガ、コンパイラをサポートしています。 利用可能なバージョンには、無料の Visual Studio コミュニティ エディションが含まれ、すべてのバージョンで C および C++ の開発をサポートできます。 Visual Studio をダウンロードしてインストールする方法の詳細については、「Visual [Studio での C++ サポートのインストール](vscpp-step-0-installation.md)」を参照してください。

Visual Studio 用のビルド ツールでは、C および C++ プログラムをビルドするために必要なコマンド ライン コンパイラ、ツール、およびライブラリのみがインストールされます。 これは、ラボや教室の演習を構築するのに最適であり、比較的迅速にインストールします。 コマンド ライン ツールのみをインストールするには、Visual Studio のダウンロード ページで Visual Studio のビルド ツール[を探します](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019)。

コマンド ラインで C または C++ プログラムをビルドする前に、ツールがインストールされていることを確認し、コマンド ラインからアクセスできます。 Visual C++ には、コマンド ライン環境で使用するツール、ヘッダー、およびライブラリを検索するための複雑な要件があります。 **準備を行わずに、コマンド プロンプト ウィンドウで Visual C++ を使用することはできません**。 さいわい、Visual C++ では、コマンド ライン ビルド用にセットアップされた環境を持つ開発者コマンド プロンプトを起動するためのショートカットがインストールされています。 残念ながら、開発者コマンド プロンプトのショートカットの名前と、そのショートカットの場所は、Visual C++ のほぼすべてのバージョンと Windows のバージョンによって異なります。 最初のチュートリアル タスクは、使用する適切なタスクを見つけることです。

> [!NOTE]
> 開発者コマンド プロンプトのショートカットは、コンパイラとツール、および必要なヘッダーとライブラリの正しいパスを自動的に設定します。 通常の**コマンド プロンプト**ウィンドウを使用する場合は、これらの環境値を自分で設定する必要があります。 詳細については、[コマンド ライン ビルドのパスと環境変数の設定](setting-the-path-and-environment-variables-for-command-line-builds.md)に関するページを参照してください。 開発者用のコマンド プロンプト ショートカットを独自に作成する代わりに使用することをお勧めします。

### <a name="open-a-developer-command-prompt"></a>開発者コマンド プロンプトを開く

1. Windows 10 で Visual Studio 2017 以降をインストールしている場合は、[スタート] メニューを開き、[**すべてのアプリ**] を選択します。 下にスクロールして **、Visual Studio**アプリケーションではなく Visual Studio フォルダーを開きます。 **VS の開発者コマンド プロンプトを**選択して、コマンド プロンプト ウィンドウを開きます。

   Windows 10 に Visual C++ ビルド ツール 2015 をインストールしている場合は、[**スタート]** メニューを開き、[**すべてのアプリ**] を選択します。 下にスクロールして **、Visual C++ ビルド ツール**フォルダーを開きます。 **Visual C++ 2015 x86 ネイティブ ツール コマンド プロンプト**を選択して、コマンド プロンプト ウィンドウを開きます。

   Windows の検索機能を使用して"開発者コマンド プロンプト" を検索し、インストールされているバージョンの Visual Studio に一致するものを選択することもできます。 ショートカットを使用してコマンド プロンプト ウィンドウを開きます。

1. 次に、Visual C++ 開発者コマンド プロンプトが正しく設定されていることを確認します。 コマンド プロンプト ウィンドウで、`cl`次のように出力を入力して確認します。

   ```Output
   C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
   Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
   Copyright (C) Microsoft Corporation.  All rights reserved.

   usage: cl [ option... ] filename... [ /link linkoption... ]
   ```

   現在のディレクトリまたはバージョン番号に違いがある可能性があります。 これらの値は、Visual C++ のバージョンとインストールされている更新プログラムによって異なります。 上記の出力が表示と同様であれば、コマンド ラインで C または C++ プログラムをビルドする準備が整いました。

   > [!NOTE]
   > "'cl' が内部または外部コマンド、操作可能なプログラムまたはバッチ ファイルとして認識されない、コマンドを実行**`cl`** するとエラー LNK1104 などのエラーが発生した場合は、開発者コマンド プロンプトを使用していないか、Visual C++ のインストールに問題があります。 続行する前に、この問題を修正する必要があります。

   開発者のコマンド プロンプトのショートカットが見つからない場合、または を入力`cl`したときにエラー メッセージが表示される場合は、Visual C++ のインストールに問題がある可能性があります。 Visual C++ コンポーネントを再インストールするか、Visual C++ ビルド ツールを再インストールしてください。 コマンドが動作するまで、次のセクションに**`cl`** 進まないでください。 Visual C++ のインストールとトラブルシューティングの詳細については[、「Visual Studio](/visualstudio/install/install-visual-studio)のインストール」を参照してください。

   > [!NOTE]
   > コンピューター上の Windows のバージョンとシステム セキュリティ構成によっては、右クリックして開発者のコマンド プロンプトのショートカット メニューを開き、[**管理者として実行**] を選択して、このチュートリアルを実行して作成したプログラムを正常にビルドして実行する必要があります。

### <a name="create-a-visual-c-source-file-and-compile-it-on-the-command-line"></a>Visual C++ ソース ファイルを作成し、コマンド ラインでコンパイルする

1. 開発者のコマンド プロンプト ウィンドウで`md c:\hello`、ディレクトリを作成する場合に入力`cd c:\hello`し、そのディレクトリに変更する場合に入力します。 このディレクトリは、ソースファイルとコンパイル済みプログラムが作成される場所です。

1. コマンド`notepad hello.cpp`プロンプト ウィンドウに入力します。

   メモ帳でファイルを作成するように求められたら、[**はい**] を選択します。 この手順では、hello.cpp という名前のファイルにコードを入力できる空のメモ帳ウィンドウが開きます。

1. メモ帳に次のコード行を入力します。

   ```cpp
   #include <iostream>
   using namespace std;
   int main()
   {
       cout << "Hello, world, from Visual C++!" << endl;
   }
   ```

   このコードは、画面上にテキストの1行を書き込み、終了する単純なプログラムです。 エラーを最小限に抑えるには、このコードをコピーし、メモ帳に貼り付けます。

1. 作業内容を保存します。 メモ帳で、 **[ファイル]** メニューの **[保存]** を選びます。

   これで、コンパイル準備が整った C++ ソース ファイル hello.cpp が作成されました。

1. 開発者コマンド プロンプト ウィンドウに戻ります。 コマンド`dir`プロンプトで、c:\hello ディレクトリの内容を一覧表示します。 ディレクトリ一覧に、次のようなソース ファイル hello.cpp が表示されます。

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

   日付やその他の詳細は、コンピュータによって異なります。 ソース コード ファイル*hello.cpp*が表示されない場合は、作成した*\\c: hello*ディレクトリに変更したことを確認します。 メモ帳で、ソース ファイルをこのディレクトリに保存したことを確認します。 また、ソース コードに拡張子ではなくファイル名拡張子*`.cpp`* を*`.txt`* 付けて保存してください。

1. 開発者コマンド プロンプトで、プログラム`cl /EHsc hello.cpp`をコンパイルするために入力します。

   cl.exe コンパイラによって、コンパイルされたコードを含む .obj ファイルが生成され、リンカーが実行されて hello.exe という名前の実行可能プログラムが作成されます。 この名前は、コンパイラによって表示される出力情報の行に表示されます。 コンパイラの出力は次のようになります。

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
   > 「'cl'が内部または外部コマンド、操作可能なプログラムまたはバッチファイルとして認識されない」などのエラーが発生した場合、エラー C1034、またはエラー LNK1104 は、開発者コマンド プロンプトが正しく設定されていません。 この問題を解決する方法については、「**開発者コマンド プロンプトを開く**」セクションに戻ってください。

   > [!NOTE]
   > 別のコンパイラエラーまたはリンカーエラーまたは警告が表示された場合は、ソースコードを見直してエラーを修正し、保存してからコンパイラを再実行してください。 特定のエラーについては、この MSDN ページの検索ボックスを使用してエラー番号を探します。

1. hello.exe プログラムを実行するには、コマンド プロンプトで `hello`と入力します。

   プログラムは、次のテキストを表示して終了します。

   ```Output
   Hello, world, from Visual C++!
   ```

   これで、コマンド ライン ツールを使用して C++ プログラムをコンパイルして実行しました。

## <a name="next-steps"></a>次のステップ

この「Hello, World」の例は、C++プログラムが得ることができるのと同じくらい簡単です。 現実世界のプログラムには、通常、ヘッダー ファイル、より多くのソース ファイル、およびライブラリへのリンクがあります。

このチュートリアルの手順を使用すると、サンプル コードを入力する代わりに独自の C++ コードを作成できます。 また、これらの手順を使用して、他の場所で見つけた多くの C++ コード サンプル プログラムをビルドすることもできます。 ソースコードを入れて、書き込み可能なディレクトリにアプリを構築できます。 既定では、Visual Studio IDE は、*ソース\\リポジトリ*サブフォルダーのユーザー フォルダーにプロジェクトを作成します。 古いバージョンでは、プロジェクトを*ドキュメント\\Visual \<Studio\\バージョン>* Projects* フォルダーに配置できます。

追加のソース コード ファイルを含むプログラムをコンパイルするには、コマンド ラインで次のようにすべて入力します。

`cl /EHsc file1.cpp file2.cpp file3.cpp`

コマンド`/EHsc`ライン オプションは、標準の C++ 例外処理動作を有効にするようにコンパイラに指示します。 このオプションを指定しないと、スローされた例外は破棄されていないオブジェクトやリソースのリークを引き起こす可能性があります。 詳細については、「[/EH (例外処理モデル)](reference/eh-exception-handling-model.md)」を参照してください。

追加のソース ファイルを指定すると、コンパイラは最初の入力ファイルを使用してプログラム名を作成します。 この場合、file1.exe というプログラムを出力します。 名前を program1.exe に変更するには[、/out](reference/out-output-file-name.md)リンカー オプションを追加します。

`cl /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

さらに、より多くのプログラミングミスを自動的にキャッチするために[、/W3](reference/compiler-option-warning-level.md)または[/W4](reference/compiler-option-warning-level.md)警告レベル オプションを使用してコンパイルすることをお勧めします。

`cl /W4 /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

コンパイラ cl.exe には、さらに多くのオプションがあります。 コードのビルド、最適化、デバッグ、および分析に適用できます。 クイック リストについては、開発者`cl /?`コマンド プロンプトで入力します。 さらに複雑なビルド シナリオで、個別にコンパイルおよびリンクし、リンカー オプションを適用することもできます。 コンパイラおよびリンカーのオプションと使用方法の詳細については[、「C/C++ のビルドリファレンス](reference/c-cpp-building-reference.md)」を参照してください。

NMAKE とメイクファイル、MSBuild とプロジェクト ファイル、または CMake を使用して、より複雑なプロジェクトをコマンド ラインで構成およびビルドできます。 これらのツールの使用方法の詳細については、「 [NMAKE リファレンス](reference/nmake-reference.md)、 [MSBuild](msbuild-visual-cpp.md)、および[CMake プロジェクトの Visual Studio でのプロジェクト](cmake-projects-in-visual-studio.md)の使用 」を参照してください。

C 言語と C++ 言語は似ていますが、同じではありません。 MSVC コンパイラは、単純な規則を使用して、コードのコンパイル時に使用する言語を決定します。 既定では、MSVC コンパイラは、最後に*`.c`* 終了するファイルを C ソース コードとして*`.cpp`* 扱い、最後に終了するファイルを C++ ソース コードとして扱います。 コンパイラですべてのファイルを C++ として扱うように強制するには[、/TP](reference/tc-tp-tc-tp-specify-source-file-type.md)コンパイラ オプションを使用します。

MSVC コンパイラには、ISO C99 標準に準拠する C ランタイム ライブラリ (CRT) が含まれていますが、小さな例外があります。 ポータブル コードは、通常、正常にコンパイルおよび実行されます。 一部の廃止されたライブラリ関数といくつかの POSIX 関数名は、MSVC コンパイラーによって非推奨になっています。 関数はサポートされていますが、優先名が変更されました。 詳細については、「 [CRT](../c-runtime-library/security-features-in-the-crt.md)および[コンパイラ警告 (レベル 3) C4996 の](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)セキュリティ機能」を参照してください。

## <a name="see-also"></a>関連項目

[C++ 言語リファレンス](../cpp/cpp-language-reference.md)<br/>
[プロジェクトおよびビルド システム](projects-and-build-systems-cpp.md)<br/>
[MSVC コンパイラ オプション](reference/compiler-options.md)
