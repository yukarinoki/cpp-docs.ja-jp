---
title: 'チュートリアル: コマンド ラインでのネイティブ C++ プログラムのコンパイル'
description: コマンド プロンプトから Microsoft の C++ コンパイラを使用します。
ms.custom: conceptual
ms.date: 04/02/2020
helpviewer_keywords:
- native code [C++]
- Visual C++, native code
- compiling programs [C++]
- command-line applications [C++], native
ms.assetid: b200cfd1-0440-498f-90ee-7ecf92492dc0
ms.openlocfilehash: 8af104598f56aa6c8eb5a9a87905324700da3d37
ms.sourcegitcommit: 31a443c9998cf5cfbaff00fcf815b133f55b2426
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "86373672"
---
# <a name="walkthrough-compiling-a-native-c-program-on-the-command-line"></a>チュートリアル: コマンド ラインでのネイティブ C++ プログラムのコンパイル

Visual Studio には、C と C++ のコマンド ライン コンパイラが付属しています。 それを使用すると、基本的なコンソール アプリからユニバーサル Windows プラットフォーム アプリ、デスクトップ アプリ、デバイス ドライバー、.NET コンポーネントまで、あらゆるものを作成できます。

このチュートリアルでは、テキスト エディターを使用して基本的な "Hello, World" スタイルの C++ プログラムを作成した後、それをコマンド ラインでコンパイルします。 コマンド ラインではなく Visual Studio IDE を試したい場合は、「[チュートリアル: プロジェクトとソリューションの使用 (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md)」または「[C++ デスクトップ開発のための Visual Studio IDE の使用](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)」を参照してください。

このチュートリアルでは、示されているものを入力する代わりに、独自の C++ プログラムを使用してもかまいません。 または、別のヘルプ記事の C++ コード サンプルを使用することもできます。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを最後まで行うには、Visual Studio とオプションの **C++ によるデスクトップ開発**ワークロード、またはコマンド ラインの Build Tools for Visual Studio が、インストールされている必要があります。

Visual Studio は "*統合開発環境*" (IDE) です。 あらゆる機能を備えたエディター、リソース マネージャー、デバッガー、およびさまざまな言語とプラットフォームに対応したコンパイラがサポートされています。 利用可能なバージョンには無料の Visual Studio Community エディションが含まれており、すべてのバージョンで C と C++ の開発がサポートされています。 Visual Studio をダウンロードしてインストールする方法について詳しくは、「[Visual Studio での C++ サポートのインストール](vscpp-step-0-installation.md)」をご覧ください。

Build Tools for Visual Studio では、C と C++ のプログラムをビルドするために必要なコマンド ライン コンパイラ、ツール、ライブラリのみがインストールされます。 ビルド ラボやクラスルームの演習に最適であり、比較的短時間でインストールできます。 コマンド ライン ツールのみをインストールするには、[Visual Studio のダウンロード](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019) ページで Build Tools for Visual Studio を探してください。

C または C++ のプログラムをコマンド ラインでビルドするには、その前に、ツールがインストールされていて、コマンド ラインからアクセスできることを確認してください。 Visual C++ の場合、コマンド ライン環境で使用されるツール、ヘッダー、ライブラリを検出するには、複雑な要件があります。 何も準備を行わずに、**そのままのコマンド プロンプト ウィンドウで Visual C++ を使用することはできません**。 さいわい、Visual C++ では、コマンド ライン ビルド用の環境のセットアップが含まれる開発者コマンド プロンプトを起動するためのショートカットが、自動的にインストールされます。 残念ながら、開発者コマンド プロンプトのショートカットの名前とそれがある場所は、Visual C++ のほぼすべてのバージョンと Windows のバージョンで異なります。 チュートリアルでの最初のタスクは、使用する適切なものを見つけることです。

> [!NOTE]
> 開発者コマンド プロンプトのショートカットを使用すると、コンパイラとツールおよび必要なヘッダーとライブラリに対する正しいパスが、自動的に設定されます。 通常の**コマンド プロンプト** ウィンドウを使用する場合は、これらの環境の値を手作業で設定する必要があります。 詳細については、[コマンド ライン ビルドのパスと環境変数の設定](setting-the-path-and-environment-variables-for-command-line-builds.md)に関するページを参照してください。 自分で構築するのではなく、開発者コマンド プロンプトのショートカットを使用することをお勧めします。

### <a name="open-a-developer-command-prompt"></a>開発者コマンド プロンプトを開く

1. Windows 10 に Visual Studio 2017 以降をインストールしてある場合は、[スタート] メニューを開き、 **[すべてのアプリ]** を選択します。 下へスクロールして、([Visual Studio アプリケーション] ではなく) **[Visual Studio]** フォルダーを開きます。 **[開発者コマンド プロンプト for VS]** で始まる項目を選択して、コマンド プロンプト ウィンドウを開きます。

   Windows 10 に Microsoft Visual C++ Build Tools 2015 をインストールしてある場合は、 **[スタート]** メニューを開き、 **[すべてのアプリ]** を選択します。 下にスクロールし、 **[Visual C++ Build Tools]** フォルダー開きます。 **[Visual C++ 2015 x86 Native Tools Command Prompt]\(Visual C++ 2015 x86 Native Tools コマンドプロンプト\)** を選択して、コマンド プロンプト ウィンドウを開きます。

   また、Windows の検索機能を使用して "開発者コマンド プロンプト" を検索し、インストールされている Visual Studio のバージョンに一致するものを選択することもできます。 ショートカットを使用してコマンド プロンプト ウィンドウを開きます。

1. 次に、Visual C++ の開発者コマンド プロンプトが正しくセットアップされていることを確認します。 コマンド プロンプト ウィンドウで「`cl`」と入力し、出力が次のようになることを確認します。

   ```Output
   C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
   Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
   Copyright (C) Microsoft Corporation.  All rights reserved.

   usage: cl [ option... ] filename... [ /link linkoption... ]
   ```

   現在のディレクトリまたはバージョン番号は違っている可能性があります。 これらの値は、インストールされている Visual C++ と更新プログラムのバージョンによって異なります。 上記と似た出力が表示される場合は、コマンド ラインで C または C++ のプログラムをビルドする準備ができています。

   > [!NOTE]
   > **`cl`** コマンドを実行すると、"'cl' は、内部コマンドまたは外部コマンド、操作可能なプログラムまたはバッチ ファイルとして認識されていません"、エラー C1034、エラー LNK1104 などのエラーが発生する場合は、開発者コマンド プロンプトを使用していないか、または Visual C++ のインストールに何らかの問題があります。 続けるには、この問題を解決する必要があります。

   開発者コマンド プロンプトのショートカットが見つからない場合、または `cl` を入力するとエラー メッセージが表示される場合は、Visual C++ のインストールに問題がある可能性があります。 Visual Studio で Visual C++ コンポーネントを再インストールしてみるか、Microsoft Visual C++ Build Tools を再インストールしてください。 **`cl`** コマンドが機能するようになるまで、次のセクションに進まないでください。 Visual C++ のインストールとトラブルシューティングの詳細については、「[Visual Studio のインストール](/visualstudio/install/install-visual-studio)」を参照してください。

   > [!NOTE]
   > コンピューターの Windows のバージョンおよびシステムのセキュリティ構成によっては、このチュートリアルに従って作成するアプリケーションを正常にビルドして実行するために、開発者コマンド プロンプト ショートカットを右クリックしてショートカット メニューを開き、 **[管理者として実行]** を選択することが必要な場合があります。

### <a name="create-a-visual-c-source-file-and-compile-it-on-the-command-line"></a>Visual C++ のソース ファイルを作成してコマンド ラインでコンパイルする

1. 開発者コマンド プロンプト ウィンドウで、「`md c:\hello`」と入力してディレクトリを作成し、「`cd c:\hello`」と入力してそのディレクトリに変更します。 このディレクトリに、ソース ファイルとコンパイル済みプログラムが作成されます。

1. コマンド プロンプト ウィンドウで「`notepad hello.cpp`」と入力します。

   メモ帳でファイルの作成を確認するメッセージが表示されたら、 **[はい]** を選択します。 これにより、メモ帳で空のウィンドウが開き、hello.cpp という名前のファイルにコードを入力できるようになります。

1. メモ帳で、次のコード行を入力します。

   ```cpp
   #include <iostream>
   using namespace std;
   int main()
   {
       cout << "Hello, world, from Visual C++!" << endl;
   }
   ```

   このコードは、画面に 1 行のテキストを書き出して終了する、簡単なプログラムです。 エラーを最小限に抑えるには、このコードをコピーし、メモ帳に貼り付けます。

1. 作業内容を保存します。 メモ帳で、 **[ファイル]** メニューの **[保存]** を選びます。

   これで、コンパイルできる状態の C++ ソース ファイル hello.cpp が作成されました。

1. 開発者コマンド プロンプト ウィンドウに戻ります。 コマンド プロンプトで「`dir`」と入力して、c:\hello ディレクトリの内容の一覧を表示します。 次のように、ディレクトリの内容の一覧にソース ファイル hello.cpp が表示されるはずです。

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

   日付と他の詳細は使用しているコンピューターによって異なります。 ソース コード ファイル *hello.cpp* が表示されない場合は、作成した *c:\\hello* ディレクトリに移動していることを確認します。 メモ帳で、ソース ファイルをこのディレクトリに保存したことを確認します。 また、保存したソース コードのファイル名拡張子が、 *`.txt`* ではなく *`.cpp`* であることを確認します。

1. 開発者コマンド プロンプトで、「`cl /EHsc hello.cpp`」と入力してプログラムをコンパイルします。

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
   > "'cl' は、内部コマンドまたは外部コマンド、操作可能なプログラムまたはバッチ ファイルとして認識されていません"、エラー C1034、エラー LNK1104 などのエラーが発生する場合は、開発者コマンド プロンプトが正しくセットアップされていません。 この問題を解決する方法については、「**開発者コマンド プロンプトを開く**」セクションを再確認してください。

   > [!NOTE]
   > これとは異なるコンパイラ エラー、リンカー エラー、または警告が発生する場合は、ソース コードを確認してエラーを修正し、保存してからコンパイラを再度実行します。 特定のエラーの詳細については、検索ボックスを使用してエラー番号を検索してください。

1. hello.exe プログラムを実行するには、コマンド プロンプトで `hello`と入力します。

   プログラムは、次のテキストを表示して終了します。

   ```Output
   Hello, world, from Visual C++!
   ```

   これで、コマンド ライン ツールを使用した C++ プログラムのコンパイルと実行が完了しました。

## <a name="next-steps"></a>次の手順

この "Hello, World" の例は、C++ プログラムでできる最も簡単なことです。 実際のプログラムには、通常、ヘッダー ファイル、さらに多くのソース ファイル、ライブラリへのリンクが含まれます。

このチュートリアルの手順を使用すれば、示されているサンプル コードを入力する代わりに、独自の C++ コードを作成できます。 これらの手順では、他の場所で見つかる多くの C++ コード サンプル プログラムをビルドすることもできます。 任意の書き込み可能なディレクトリにソース コードを配置し、アプリをビルドすることができます。 既定では、Visual Studio IDE により、ユーザー フォルダー内の *source\\repos* サブフォルダーにプロジェクトが作成されます。 以前のバージョンでは、*Documents\\Visual Studio \<version>\\* Projects* フォルダーに、プロジェクトが配置される場合があります。

追加のソース コード ファイルがあるプログラムをコンパイルするには、次のようにコマンド ラインですべてを入力します。

`cl /EHsc file1.cpp file2.cpp file3.cpp`

`/EHsc` は、標準の C++ 例外処理動作を有効にするようコンパイラに指示するコマンド ライン オプションです。 これを行わないと、スローされた例外によって、破棄されないオブジェクトやリソースのリークが発生する可能性があります。 詳細については、「[/EH (例外処理モデル)](reference/eh-exception-handling-model.md)」を参照してください。

追加のソース ファイルを指定すると、コンパイラでは最初の入力ファイルを使用してプログラム名が作成されます。 この例では、file1.exe というプログラムが出力されます。 名前を program1.exe に変更するには、[/out](reference/out-output-file-name.md) リンカー オプションを追加します。

`cl /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

また、さらに多くのプログラミングの誤りが自動的にキャッチされるよう、[/W3](reference/compiler-option-warning-level.md) または [/W4](reference/compiler-option-warning-level.md) の警告レベル オプションを使用してコンパイルすることをお勧めします。

`cl /W4 /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

コンパイラ cl.exe には、さらに多くのオプションがあります。 これらを適用して、コードのビルド、最適化、デバッグ、分析を行うことができます。 簡単に一覧を見るには、開発者コマンド プロンプトで「`cl /?`」と入力します。 また、さらに複雑なビルド シナリオでは、コンパイルとリンクを別々に行い、リンカー オプションを適用することもできます。 コンパイラとリンカーのオプションと使用方法の詳細については、「[C/C++ ビルドのリファレンス](reference/c-cpp-building-reference.md)」を参照してください。

NMAKE とメイクファイル、MSBuild とプロジェクト ファイル、または CMake を使用すると、さらに複雑なプロジェクトをコマンド ラインで構成し、ビルドすることができます。 これらのツールの使用方法の詳細については、「[NMAKE リファレンス](reference/nmake-reference.md)」、「[MSBuild](msbuild-visual-cpp.md)」、および「[Visual Studio の CMake プロジェクト](cmake-projects-in-visual-studio.md)」を参照してください。

C 言語と C++ 言語は似ていますが、同じではありません。 MSVC コンパイラでは、簡単なルールを使用して、コードをコンパイルするときに使用する言語が決定されます。 既定の MSVC コンパイラでは、 *`.c`* で終わるファイルは C ソース コードとして扱われ、 *`.cpp`* で終わるファイルは C++ ソース コードとして扱われます。 ファイル名拡張子に関係なくコンパイラですべてのファイルが C++ として扱われるように強制するには、[/TP](reference/tc-tp-tc-tp-specify-source-file-type.md) コンパイラ オプションを使用します。

MSVC コンパイラには、小さな例外がいくつかありますが、ISO C99 標準に準拠する C ランタイム ライブラリ (CRT) が含まれています。 通常、移植可能なコードは予期したとおりにコンパイルおよび実行されます。 一部の古いライブラリ関数と、いくつかの POSIX 関数名は、MSVC コンパイラでは非推奨になっています。 関数はサポートされていますが、推奨される名前は変更されています。 詳細については、「[CRT のセキュリティ機能](../c-runtime-library/security-features-in-the-crt.md)」と「[コンパイラ警告 (レベル 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)」を参照してください。

## <a name="see-also"></a>関連項目

[C++ 言語リファレンス](../cpp/cpp-language-reference.md)<br/>
[プロジェクトおよびビルド システム](projects-and-build-systems-cpp.md)<br/>
[MSVC コンパイラ オプション](reference/compiler-options.md)
