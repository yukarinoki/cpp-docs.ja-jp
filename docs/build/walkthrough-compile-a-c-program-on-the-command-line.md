---
title: 'チュートリアル: コマンドラインでの C プログラムのコンパイル |Microsoft ドキュメント'
ms.custom: conceptual
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
helpviewer_keywords:
- command-line applications [C++], C programs
- Visual C, compiling
- compiling programs [C++]
- C program compiling [C++]
ms.assetid: 7e74cc2d-54b1-49de-b7ad-d3ae6b39ab8d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 033c29ff9871a427222b59fbf5c8350794a9bbe2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="walkthrough-compile-a-c-program-on-the-command-line"></a>チュートリアル: コマンドラインでの C プログラムをコンパイルします。
Visual C には、完全な Windows デスクトップ アプリケーション、モバイル アプリは、基本的なコンソール プログラムから作成するすべてのものを使用できる C コンパイラが含まれています。  
  
 このチュートリアルでは、基本的な「こんにちは, World」を作成する方法のエディター、テキストを使用して、C プログラムをスタイルし、コマンドラインでコンパイルします。 作業する場合とではなく C++ では、コマンドラインを参照してください。[チュートリアル: コマンドラインでネイティブ C++ プログラムのコンパイル](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)です。 コマンドラインを使用する代わりに、Visual Studio IDE の再試行を確認したい場合[チュートリアル: プロジェクトとソリューション (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md)または[C++ デスクトップ開発用 Visual Studio IDE を使用して](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)です。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルを完了するには、必要がありますがインストールした Visual Studio と省略可能な Visual C コンポーネント、または Microsoft Visual C ビルド ツール。  
  
 Visual Studio は、多くの言語とプラットフォームの全機能を備えたエディター、リソース マネージャー、デバッガー、およびコンパイラをサポートする強力な統合開発環境です。 これらの機能とをダウンロードして無料の Visual Studio Community エディションをなど、Visual Studio をインストールする方法についてを参照してください。 [VisualStudio.com](https://www.visualstudio.com/)です。  
  
 Visual Studio ビルド ツールは、コマンド ライン コンパイラ、ツール、および C および C++ プログラムのビルドに必要なライブラリのみをインストールします。 ビルド ラボに最適ですや教室行使比較的迅速にインストールします。 コマンド ライン ツールのみをインストールするには、ダウンロード[Visual Studio ビルド ツール](https://go.microsoft.com/fwlink/p/?linkid=840931)installer を実行します。 詳細については、次を参照してください。 [Visual c ビルド ツール](http://landinghub.visualstudio.com/visual-cpp-build-tools)です。  
  
 C または C++ プログラムをビルドするには、コマンドラインで、前に、ツールがインストールされていると、コマンドラインからアクセスできることを確認する必要があります。 Visual C では、ツール、ヘッダー、および使用するライブラリを検索するためにコマンドライン環境の複雑な要件がします。 **標準のコマンド プロンプト ウィンドウで、Visual C を使用することはできません**です。 必要があります、*開発者コマンド プロンプト*は通常のコマンド プロンプト ウィンドウを設定されているすべての必要な環境変数を持つウィンドウです。 幸いにも、Visual C は、コマンド ライン ビルド用に設定する環境がある開発者コマンド プロンプトを起動するためのショートカットをインストールします。 残念ながら、開発者コマンド プロンプトのショートカットと配置されている場所の名前は、異なるバージョンの Windows で Visual C のほぼすべてのバージョンで異なります。 最初のチュートリアル タスクを使用する右側のショートカットの検索を開始します。  
  
> [!NOTE]
>  開発者コマンド プロンプト ショートカットでは、コンパイラおよびツール、および、必要なヘッダーとライブラリによって正しいパスが自動的に設定します。 これらの値の一部は、ビルド構成ごとに異なります。 必要がありますこれらの環境値自分で設定する場合は、ショートカットのいずれかを使用しません。 詳細については、次を参照してください。[コマンド ライン ビルドのパスと環境変数を設定](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)です。 ビルド環境は複雑であるため、開発者コマンド プロンプト ショートカットを使用して、独自のビルドではなくを強くお勧めします。  
  
## <a name="open-a-developer-command-prompt"></a>開発者コマンド プロンプトを開きます  
  
1.  Windows 10 に Visual Studio 2017 をインストールした場合、[スタート] メニューのおよび下にスクロールし、開き、 **Visual Studio 2017**フォルダー (Visual Studio 2017 アプリケーションではなく)。 選択**VS 2017 用開発者コマンド プロンプト**をコマンド プロンプト ウィンドウを開きます。  
  
     Windows 10 に Microsoft Visual C ビルド ツール 2015 をインストールした場合は開きます、**開始** メニューとし、一覧をスクロールして開く、 **Visual C ビルド ツール**フォルダーです。 選択**Native Tools コマンド プロンプトを Visual C 2015 x86**をコマンド プロンプト ウィンドウを開きます。  
  
     異なるバージョンの Visual Studio を使用しているか、別のバージョンの Windows を実行している場合は、[スタート] メニューでは、ファイルの場所か、開発者コマンド プロンプト ショートカットが含まれる Visual Studio ツール フォルダーのページを起動します。 また、「開発者コマンド プロンプト」を検索し、インストールされているバージョンの Visual Studio に一致する 1 つを選択する Windows の検索機能を使用することができます。 ショートカットを使用して、コマンド プロンプト ウィンドウを開きます。  
  
2.  次に、Visual C 開発者コマンド プロンプトが正しく設定されていることを確認します。 コマンド プロンプト ウィンドウで次のように入力します。`cl`し、出力が次のようなことを確認します。  
  
    ```Output  
    C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl  
    Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86  
    Copyright (C) Microsoft Corporation.  All rights reserved.  
    
    usage: cl [ option... ] filename... [ /link linkoption... ]  
    
    C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>  
    ```  
  
     現在のディレクトリまたは Visual C と更新プログラムがインストールされている任意のバージョンによっては、バージョン番号の相違がある可能性があります。 表示される内容のような場合は、コマンドラインでの C または C++ のプログラムをビルドする準備がされます。  
  
    > [!NOTE]
    >  「'Cl' は、内部または外部コマンド、操作可能なプログラムまたはバッチ ファイルとしては認識されません"など、エラーが発生した場合エラー C1034 またはエラー LNK1104 を実行すると、 **cl**コマンドを使用するか、開発者コマンド プロンプトでは、使用しない、またはVisual C のインストールの問題がします。 続行するには、この問題を解決する必要があります。  
  
     見つからない場合、開発者コマンド プロンプト ショートカット、または入力すると、エラー メッセージが表示された場合`cl`、Visual C インストールの問題があるし、します。 Visual Studio で、Visual C コンポーネントを再インストールを実行するか、Visual Studio ビルド ツールを再インストールします。 入りません次のセクションにこれが機能するまでです。 インストールして、Visual C のトラブルシューティングに関する詳細については、次を参照してください。 [Visual Studio インストール](/visualstudio/install/install-visual-studio)です。  
  
    > [!NOTE]
    >  Windows のバージョンに応じて、コンピューターと、システム セキュリティ構成で、右クリックすると、開発者コマンド プロンプト ショートカットのショートカット メニューを開き、選択する必要があります**管理者として実行**に正常にビルドして、このチュートリアルで作成するプログラムを実行します。  
  
## <a name="create-a-c-source-file-and-compile-it-on-the-command-line"></a>C ソース ファイルを作成し、コマンドラインでコンパイルします。  
  
1.  開発者コマンド プロンプト ウィンドウで次のように入力します。 **cd c:\\**  、c: ドライブのルートに現在の作業ディレクトリを変更します。 次に、入力**md c:\simple**ディレクトリを作成し、入力**cd c:\simple**そのディレクトリに変更します。 これは、ソース ファイルとコンパイル済みプログラムを格納するディレクトリです。  
  
2.  入力**メモ帳 simple.c**開発者コマンド プロンプトでします。 メモ帳警告ダイアログ ボックスでポップアップ表示される、次のように選択します。**はい**自分の作業ディレクトリに新しい simple.c ファイルを作成します。  
  
3.  メモ帳で、次のコード行を入力します。  
  
    ```C  
    #include <stdio.h>  
  
    int main()  
    {  
        printf("Hello, World! This is a native C program compiled on the command line.\n");  
        return 0;  
    }   
    ```  
  
4.  メモ帳のメニュー バー、**ファイル**、**保存**simple.c を自分の作業ディレクトリに保存します。  
  
5.  開発者コマンド プロンプト ウィンドウに切り替えます。 入力**dir**コマンド プロンプトを c:\simple のディレクトリの内容を一覧表示します。 ディレクトリの一覧については、次のようにソース ファイル simple.c が表示されます。  
  
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
  
     日付とその他の詳細については、コンピューターに異なります。 ソース コード ファイルが見つからない場合、simple.c は、作成した c:\simple のディレクトリに加えた変更かどうかを確認し、メモ帳で、このディレクトリに、ソース ファイルを保存することを確認します。 また、.c ファイル名拡張子、.txt 拡張子ではなくソース コードを保存することを確認します。  
  
6.  プログラムをコンパイルするには、次のように入力します。 **cl simple.c**開発者コマンド プロンプトでします。  
  
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
    >  「'Cl' は、内部または外部コマンド、操作可能なプログラムまたはバッチ ファイルとしては認識されません"など、エラーが発生した場合エラー C1034 またはエラー LNK1104、開発者コマンド プロンプトが正しく設定されていません。 この問題を解決する方法についてに戻って、**開発者コマンド プロンプトを開き**セクションです。  
  
    > [!NOTE]
    >  別のコンパイラやリンカー エラーまたは警告が発生した場合は、エラーを修正してから保存し、コンパイラを再実行するソース コードを確認します。 特定のエラーについてには、エラー番号を検索するこの MSDN ページの検索ボックスを使用します。  
  
7.  プログラムを実行するには、次のように入力します。**単純**コマンド プロンプトでします。  
  
     プログラムは、次のテキストを表示して終了します。  
  
    ```Output  
    Hello, World! This is a native C program compiled on the command line.  
    ```  
  
     これで先ほどコンパイルし、コマンドラインを使用して C プログラムを実行します。  
  
## <a name="next-steps"></a>次の手順  
 この「こんにちは, World」の例は、簡単に C プログラムを取得できます。 ヘッダー ファイルと複数のソース ファイルではライブラリにリンクし、有益な処理を行う現実世界のプログラムがあります。  
  
 このチュートリアルで手順を使用すると、示したサンプル コードを入力する代わりに、独自の C コードをビルドします。 また、別の場所に表示されている多くの C コード サンプル プログラムをビルドすることができます。 複数のソース コード ファイルのあるプログラムをコンパイルするには、すべてのコマンド ラインで、次のようにそれらを入力します。  
  
 `cl file1.c file2.c file3.c`  
  
 コンパイラは、file1.exe と呼ばれるプログラムを出力します。 Program1.exe に名前を変更するには、追加、 [/out](../build/reference/out-output-file-name.md)リンカー オプション。  
  
 `cl file1.c file2.c file3.c /link /out:program1.exe`  
  
 複数のプログラミングの間違いを自動的にキャッチすることをお勧めするかを使用してコンパイルして、 [/W3](../build/reference/compiler-option-warning-level.md)または[/W4](../build/reference/compiler-option-warning-level.md)警告レベルのオプション。  
  
 `cl /W4 file1.c file2.c file3.c /link /out:program1.exe`  
  
 コンパイラ、cl.exe、ビルド、最適化、デバッグに適用して、コードを分析の多くの豊富なオプションです。 クイック一覧は、入力**cl/しますか?** 開発者コマンド プロンプトではします。 コンパイル、リンクを別々 にし、およびビルドのより複雑なシナリオでリンカー オプションを適用もできます。 コンパイラとリンカー オプション、および使用状況の詳細については、次を参照してください。 [c/c++ ビルドのリファレンス](../build/reference/c-cpp-building-reference.md)です。  
  
 NMAKE とメイクファイル、または MSBuild とプロジェクト ファイルを使用するを構成して、コマンドラインでより複雑なプロジェクトをビルドします。 これらのツールを使用する方法については、次を参照してください。 [NMAKE リファレンス](../build/nmake-reference.md)と[MSBuild](../build/msbuild-visual-cpp.md)です。  
  
 C および C++ 言語は同様ですが、同じではありません。 Visual C コンパイラでは、単純なルールを使用して、コードをコンパイルするときに使用する言語を決定します。 既定では、Visual C++ コンパイラは .c で終わるファイルをすべて C ソース コードとして扱い、.cpp で終わるファイルをすべて C++ ソース コードとして扱います。 コンパイラにファイル名拡張子に関係なく、すべてのファイルを C として扱うを使用して、 [/Tc](../build/reference/tc-tp-tc-tp-specify-source-file-type.md)コンパイラ オプション。  
  
 C++ の Visual C コンパイラは、ISO C99 標準と互換性のある一般的に厳密に準拠していません。 ほとんどの場合、C コードの移植性がコンパイルされ、期待どおりを実行します。 Visual C は、ISO C11 のほとんどの変更をサポートしていません。 Visual C コンパイラでは、特定のライブラリ関数と POSIX 関数名が使用されなくなりました。 関数がサポートされますが、優先名が変更されました。 詳細については、次を参照してください。 [CRT のセキュリティ機能](../c-runtime-library/security-features-in-the-crt.md)と[コンパイラの警告 (レベル 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)です。  
  
## <a name="see-also"></a>関連項目  
 [チュートリアル: 標準の C++ プログラム (C++) の作成](../windows/walkthrough-creating-a-standard-cpp-program-cpp.md)   
 [C 言語リファレンス](../c-language/c-language-reference.md)   
 [C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)   
 [互換性](../c-runtime-library/compatibility.md)