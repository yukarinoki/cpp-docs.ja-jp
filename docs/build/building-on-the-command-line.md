---
title: コマンド ラインから MSVC ツールセットを使用する - Visual Studio
description: Visual Studio IDE の外にあるコマンド ラインから Microsoft C++ コンパイラ ツールチェーン (MSVC) を使用します。
ms.custom: conceptual
ms.date: 05/16/2019
helpviewer_keywords:
- command-line builds [C++]
- compiling source code [C++], command line
- builds [C++], command-line
- command line [C++], building from
- command line [C++], compilers
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
ms.openlocfilehash: 97626455ace0d3ad47b9011594e82c144d7ea27d
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837126"
---
# <a name="use-the-msvc-toolset-from-the-command-line"></a>コマンド ラインから MSVC ツールセットを使用する

Visual Studio に含まれているツールを使用し、コマンド ラインで C と C++ のアプリケーションをビルドできます。 [[Visual Studio ダウンロード]](https://visualstudio.microsoft.com/downloads/) ページからコンパイラ ツールセットをスタンドアロン パッケージとしてダウンロードすることもできます。 これは **Build Tools for Visual Studio** パッケージの一部です。C++ 開発に必要なツールのみをダウンロードするように選択できます。

## <a name="how-to-use-the-command-line-tools"></a>コマンド ライン ツールの使用方法

Visual Studio インストーラーでいずれかの C++ ワークロードを選択すると、Visual Studio *プラットフォーム ツールセット*がインストールされます。 プラットフォーム ツールセットには、C/C++ コンパイラ、リンカー、アセンブラ、その他のビルド ツール、対応するライブラリなど、特定の Visual Studio バージョンの C ツールと C++ ツールがすべて入っています。 このようなツールはすべて、コマンド ラインで使用できます。Visual Studio IDE により内部で使用されることもあります。 x86 ホストと x64 ホストに分かれているコンパイラと、x86、x64、ARM、ARM64 ターゲット向けのコードをビルドするためのツールがあります。 特定のホストやターゲット ビルド アーキテクチャに対するそれぞれのツール セットは、その独自のディレクトリに保存されています。

インストールされるコンパイラ ツールセットは、コンピューター プロセッサとインストール中に選択されたオプションに依存します。 少なくとも 32 ビット x86 ネイティブ コードをビルドする 32 ビット x86 ホストのツールと 64 ビット x64 ネイティブ コードをビルドするクロス ツールがインストールされます。 64 ビット Windows をお持ちの場合、64 ビット ネイティブ コードをビルドする 64 ビット x64 ホストのツールと 32 ネイティブ コードをビルドするクロス ツールもインストールされます。 任意の C++ ユニバーサル Windows プラットフォーム ツールをインストールするように選択した場合、ARM コードをビルドする 32 ビットと 64 ビットのネイティブ ツールもインストールされます。 その他のワークロードによって追加のツールがインストールされることもあります。

## <a name="environment-variables-and-developer-command-prompts"></a>環境変数と開発者コマンド プロンプト

ツールが正しく動作するには、特定の環境変数をいくつか設定する必要があります。 そのような環境変数は、それをパスに追加し、インクルード ファイル、ライブラリ ファイル、SDK の場所を設定する目的で使用されます。 このような環境変数をかん単に設定する目的で、インストーラーにより、インストール中、カスタマイズされた*コマンド ファイル*またはバッチ ファイルが作成されます。 コマンド プロンプト ウィンドウでいずれかのコマンド ファイルを実行し、特定のホストおよびターゲット ビルド アーキテクチャ、Windows SDK バージョン、ターゲット プラットフォーム、プラットフォーム ツールセットを設定できます。 また、利便性のために、インストーラーによって、これらのコマンド ファイルを使用して開発者コマンド プロンプト ウィンドウを起動するショートカットが [スタート] メニューに作成されます。

必須の環境変数はインストールに固有であり、選択したビルド アーキテクチャに固有となります。また、製品の更新やアップグレードによって変更される場合があります。 そのため、自分で Windows の環境変数を設定せず、インストールされたいずれかのコマンド プロンプト ショートカットまたはコマンド ファイルを使用することを強くお勧めします。 詳細については、[コマンド ライン ビルドのパスと環境変数の設定](setting-the-path-and-environment-variables-for-command-line-builds.md)に関するページを参照してください。

## <a name="developer_command_prompt_shortcuts"></a> 開発者コマンド プロンプト ショートカット

コマンド プロンプト ショートカットは、[スタート] メニューのバージョン固有の Visual Studio フォルダーにインストールされます。 次は、基本的なコマンド プロンプト ショートカットとそれによりサポートされるビルド アーキテクチャを一覧にまとめたものです。

- **開発者コマンド プロンプト** - 32 ビット x86 ネイティブ ツールを使用して 32 ビット x86 ネイティブ コードをビルドするように環境を設定します。
- **x86 Native Tools コマンド プロンプト** - 32 ビット x86 ネイティブ ツールを使用して 32 ビット x86 ネイティブ コードをビルドするように環境を設定します。
- **x64 Native Tools コマンド プロンプト** - 64 ビット x64 ネイティブ ツールを使用して 64 ビット x64 ネイティブ コードをビルドするように環境を設定します。
- **x86_x64 Cross Tools コマンド プロンプト** - 32 ビット x86 ネイティブ ツールを使用して 64 ビット x64 ネイティブ コードをビルドするように環境を設定します。
- **x64_x86 Cross Tools コマンド プロンプト** - 64 ビット x64 ネイティブ ツールを使用して 32 ビット x86 ネイティブ コードをビルドするように環境を設定します。

[スタート] メニュー フォルダーとショートカットの実際の名前は、インストールした Visual Studio のバージョンによって異なります。インストール ニックネームを設定した場合、それによっても異なります。 たとえば、Visual Studio 2019 をインストールし、それに *Preview* というインストール ニックネームを与えた場合、開発者コマンド プロンプト ショートカットの名前は **Developer Command Prompt for VS 2019** となり、**Visual Studio 2019** という名前のフォルダーに入ります。

## <a name="developer_command_prompt"></a> 開発者コマンド プロンプト ウィンドウを開くには

1. デスクトップで、Windows の **[スタート]** メニューを開き、スクロールしてお使いのバージョンの Visual Studio (たとえば、**Visual Studio 2019**) のフォルダーを見つけて開きます。 一部の古いバージョンの Visual Studio では、ショートカットが **Visual Studio Tools** という名前のサブフォルダーに入ります。

1. フォルダーで、お使いのバージョンの Visual Studio の **[開発者コマンド プロンプト]** を選択します。 このショートカットにより、32 ビット x86 ネイティブ ツールの既定のビルド アーキテクチャを使用して 32 ビット x86 ネイティブ コードをビルドする開発者コマンド プロンプト ウィンドウが起動します。 既定以外のビルド アーキテクチャを使用する場合、いずれかのネイティブまたはクロス ツール コマンド プロンプトを選択し、ホストおよびターゲット アーキテクチャを指定します。

開発者コマンド プロンプト ウィンドウをもっと速く起動する方法は、デスクトップの検索ボックスに「*developer command prompt*」と入力し、検索結果から目的のものを選択することです。

## <a name="developer_command_file_locations"></a> 開発者コマンド ファイルの場所

既存のコマンド プロンプト ウィンドウにビルド アーキテクチャ環境を設定する場合、インストーラーによって作成されたいずれかのコマンド ファイル (バッチ ファイル) を使用し、必要な環境を設定できます。 これは新しいコマンド プロンプト ウィンドウでのみ行うことをお勧めします。後で、同じコマンド ウィンドウで環境を切り替えることはお勧めしません。 これらのファイルの場所は、インストールした Visual Studio のバージョンとインストール中に選択した場所と命名規則によって変わります。 Visual Studio 2019 の場合、64 ビット コンピューター上の一般的なインストール場所は、\Program Files (x86)\Microsoft Visual Studio\2019\*edition* になります。*edition* には、Community、Professional、Enterprise、BuildTools、または指定した別の名前が入ります。 Visual Studio 2017 の場所も同様です。 Visual Studio 2015 の場合、一般的なインストール場所は \Program Files (x86)\Microsoft Visual Studio 14.0 です。

開発者コマンド プロンプトの主要なコマンド ファイルである VsDevCmd.bat は、インストール ディレクトリの Common7\Tools サブディレクトリにあります。 パラメーターが指定されていない場合、このコマンド ファイルにより、32 ビット x86 ネイティブ ツールを使用して 32 ビット x86 コードをビルドするように環境とホストおよびターゲット ビルド アーキテクチャが設定されます。

プロセッサ アーキテクチャと、インストールした Visual Studio のワークロードとオプションにもよりますが、特定のビルド アーキテクチャを設定する目的で、追加のコマンド ファイルを利用できます。 Visual Studio 2017 と Visual Studio 2019 の場合、追加のコマンド ファイルは Visual Studio インストール ディレクトリの VC\Auxiliary\Build サブディレクトリにあります。 Visual Studio 2015 の場合、追加のコマンド ファイルはインストール ディレクトリの VC、VC\bin、または VC\bin\\*architectures* にあります。*architectures* には、ネイティブまたはクロスコンパイラ オプションが入ります。 これらのコマンド ファイルにより既定のパラメーターが設定され、VsDevCmd.bat が呼び出されて指定のビルド アーキテクチャ環境が設定されます。 一般的なインストールに含まれるコマンド ファイル:

|コマンド ファイル|ホストおよびターゲット アーキテクチャ|
|---|---|
|**vcvars32.bat**| 32 ビット x86 ネイティブ ツールを使用し、32 ビット x86 コードをビルドします。|
|**vcvars64.bat**| 64 ビット x64 ネイティブ ツールを使用し、64 ビット x64 コードをビルドします。|
|**vcvarsx86_amd64.bat**| 32 ビット x86 ネイティブ クロス ツールを使用し、64 ビット x64 コードをビルドします。|
|**vcvarsamd64_x86.bat**| 64 ビット x64 ネイティブ クロス ツールを使用し、32 ビット x86 コードをビルドします。|
|**vcvarsx86_arm.bat**| 32 ビット x86 ネイティブ クロス ツールを使用し、ARM コードをビルドします。|
|**vcvarsamd64_arm.bat**| 64 ビット x64 ネイティブ クロス ツールを使用し、ARM コードをビルドします。|
|**vcvarsall.bat**| パラメーターを使用し、ホストおよびターゲット アーキテクチャ、SDK、プラットフォームを指定します。 サポートされているオプションの一覧が必要な場合、 **/help** パラメーターを使用して呼び出します。|

> [!CAUTION]
> vcvarsall.bat ファイルとその他の Visual Studio コマンド ファイルはコンピューターによって異なります。 vcvarsall.bat ファイルが見つからない場合や破損している場合でも、別のコンピューターのファイルを使用して置き換えないでください。 Visual Studio インストーラーを再実行し、不足しているファイルを置換します。
>
> vcvarsall.bat ファイルは、バージョンによっても異なります。 以前のバージョンの Visual Studio も入っているコンピューターに現行版の Visual Studio をインストールする場合、同じコマンド プロンプト ウィンドウで異なるバージョンの vcvarsall.bat または別の Visual Studio コマンド ファイルを実行しないでください。

## <a name="use-the-developer-tools-in-an-existing-command-window"></a>既存のコマンド ウィンドウで開発者ツールを使用する

既存のコマンド ウィンドウで特定のビルド アーキテクチャを指定する最も簡単な方法は、vcvarsall.bat ファイルを使用することです。 vcvarsall.bat を使用して環境変数を設定し、32 ビットまたは 64 ビットのネイティブ コンパイルまたは x86、x64、ARM プロセッサへのクロス コンパイルのためのコマンド ラインを構成したり、Microsoft Store、ユニバーサル Windows プラットフォーム、Windows Desktop プラットフォームをターゲットにしたり、使用する Windows SDK を指定したり、プラットフォーム ツールセットのバージョンを指定したりできます。 引数を指定せずに vcvarsall.bat を実行すると、x86 Windows Desktop を対象として現在の 32 ビット ネイティブ コンパイラを使用するための環境変数が構成されます。 ただし、このバッチ ファイルを使用して任意のネイティブまたはクロス コンパイラ ツールを構成できます。 ビルド コンピューターのアーキテクチャにインストールされていない、または使用できないコンパイラ構成を指定した場合は、エラー メッセージが表示されます。

### <a name="vcvarsall-syntax"></a>vcvarsall 構文

> **vcvarsall.bat** [*architecture*] [*platform_type*] [*winsdk_version*] [ **-vcvars_ver=**_vcversion_]

*アーキテクチャ*<br/>
この任意の引数では、使用するホストおよびターゲット アーキテクチャが指定されます。 *アーキテクチャ*が指定されていない、既定のビルド環境が使用されます。 以下の引数がサポートされています。

|*アーキテクチャ*|コンパイラ|ホスト コンピューターのアーキテクチャ|ビルド出力 (ターゲット) のアーキテクチャ|
|----------------------------|--------------|----------------------------------|-------------------------------|
|**x86**|x86 32 ビット ネイティブ|x86、x64|x86|
|**x86\_amd64** または **x86\_x64**|x64 on x86 クロス|x86、x64|X64|
|**x86_arm**|ARM on x86 クロス|x86、x64|ARM|
|**x86_arm64**|ARM64 on x86 クロス|x86、x64|ARM64|
|**amd64** または **x64**|x64 64 ビット ネイティブ|X64|X64|
|**amd64\_x86** または **x64\_x86**|x86 on x64 クロス|X64|x86|
|**amd64\_arm** または **x64\_arm**|ARM on x64 クロス|X64|ARM|
|**amd64\_arm64** または **x64\_arm64**|ARM64 on x64 クロス|X64|ARM64|

*platform_type*<br/>
この任意の引数では、プラットフォームの種類として **[ストア]** または **[uwp]** を指定できます。 既定では、デスクトップまたはコンソール アプリをビルドするように環境が設定されます。

*winsdk_version*<br/>
任意で、使用する Windows SDK のバージョンが指定されます。 既定では、インストールされた日付が最も新しい Windows SDK が使用されます。 Windows SDK のバージョンを指定するには、**10.0.10240.0** など、完全な Windows 10 SDK 番号を使用するか、**8.1** と指定して Windows 8.1 SDK を使用します。

*vcversion*<br/>
任意で、使用する Visual Studio コンパイラ ツールセットを指定します。 既定では、現在の Visual Studio コンパイラ ツールセットを使用するように環境が設定されます。 **-vcvars_ver=14.0** を使用すると Visual Studio 2015 コンパイラ ツールセットが指定され、 **-vcvars_ver=15.0** を使用すると Visual Studio 2017 コンパイラ ツールセットが指定されます。

<a name="vcvarsall"></a>
#### <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a>既存のコマンド プロンプト ウィンドウでビルド環境を設定するには

1. コマンド プロンプトで、CD コマンドを使用し、Visual Studio インストール ディレクトリに作業ディレクトリを変更します。 次に、CD をもう一度使用し、構成固有のコマンド ファイルが含まれるサブディレクトリに作業ディレクトリを変更します。 Visual Studio 2017 と Visual Studio 2019 の場合、これは VC\Auxiliary\Build サブディレクトリです。 Visual Studio 2015 の場合、VC サブディレクトリを使用します。

1. 優先開発者環境のコマンドを入力します。 たとえば、最新の Windows SDK と Visual Studio 2019 コンパイラ ツールセットを使用し、64 ビット プラットフォームで UWP 向け ARM コードをビルドするには、このコマンド ラインを使用します。

   `vcvarsall.bat amd64_arm uwp`

## <a name="create-your-own-command-prompt-shortcut"></a>独自のコマンド プロンプト ショートカットを作成する

既存のいずれかの開発者コマンド プロンプト ショートカットに対して [プロパティ] ダイアログを開くと、使用されているコマンド ターゲットが表示されます。 たとえば、**x64 Native Tools Command Prompt for VS 2019** ショートカットのターゲットは次のようになります。

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvars64.bat"`

このアーキテクチャ固有のバッチ ファイルにより *architecture* パラメーターが設定され、vcvarsall.bat が呼び出されます。 vcvarsall.bat に渡す場合と同様に、これらのバッチ ファイルに同じ追加オプションを渡すことができます。あるいは、vcvarsall.bat を直接呼び出すことができます。 独自のコマンド ショートカットのパラメーターを指定するには、それを二重引用符でコマンドの終わりに追加します。 たとえば、最新の Windows SDK と現行版より前のコンパイラ ツールセットを利用し、64 ビット プラットフォームで UWP 向けの ARM コードをビルドするには、バージョン番号を指定する必要があります。 ショートカットで次のようなコマンド ターゲットを使用します。

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvarsall.bat amd64_arm uwp -vcvars_ver=15.0"`

Visual Studio インストール ディレクトリが反映されるようにパスを調整する必要があります。 vcvarsall.bat ファイルには、特定のバージョン番号に関する追加情報があります。

## <a name="command-line-tools"></a>コマンド ライン ツール

コマンド ラインで C/C++ プロジェクトをビルドする目的で、Visual Studio からは以下のコマンドライン ツールが提供されます。

[CL](reference/compiling-a-c-cpp-program.md)<br/>
コンパイラ (cl.exe) は、ソース コード ファイルをアプリ、ライブラリ、および DLL にコンパイルおよびリンクするために使用します。

[リンク](reference/linking.md)<br/>
リンカー (link.exe) は、コンパイルされたオブジェクト ファイルおよびライブラリをアプリおよび DLL にリンクするために使用します。

[MSBuild](msbuild-visual-cpp.md)<br/>
MSBuild (msbuild.exe) とプロジェクト ファイル (.vcxproj) を使用し、ビルドを構成し、ツールセットを間接的に呼び出します。 これは、Visual Studio IDE で **[プロジェクトのビルド]** コマンドまたは **[ソリューションのビルド]** コマンドを実行することと同じです。 コマンド ラインから MSBuild を実行することは上級向けのシナリオであり、一般的には推奨されません。

[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)<br/>
DEVENV (devenv.exe) は、Visual Studio IDE を表示せずに特定のビルド コマンドを実行するために、 **/Build** や **/Clean** などのコマンド ライン スイッチと組み合わせて使用します。 一般的に、これは MSBuild を直接使用することよりも推奨されます。複雑な MSBuild を Visual Studio に処理させることができるためです。

[NMAKE](reference/nmake-reference.md)<br/>
Windows で NMAKE (nmake.exe) を使用し、従来のメイクファイルに基づいて C++ プロジェクトをビルドします。

コマンド ラインでビルドするとき、F1 コマンドでヘルプを瞬時に表示することはできません。 代わりに、検索エンジンを使用して警告、エラー、メッセージに関する情報を取得できます。あるいは、オフラインのヘルプ ファイルを使用できます。 [docs.microsoft.com](https://docs.microsoft.com/cpp/) で検索を使用するには、ページの一番上にある検索ボックスに検索文字列を入力します。

## <a name="in-this-section"></a>このセクションの内容

ドキュメントのこのセクションの記事では、コマンド ラインでアプリをビルドする方法を示し、64 ビット ツールセットを使用して x86、x64、および ARM プラットフォームを対象とするように、コマンド ライン ビルド環境をカスタマイズする方法について説明し、コマンド ライン ビルド ツール MSBuild および NMAKE を使用する方法を示します。

[チュートリアル: コマンド ラインでのネイティブ C++ プログラムのコンパイル](walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)<br/>
コマンド ラインで単純な C++ プログラムを作成およびコンパイルする方法を示す例があります。

[チュートリアル: コマンド ラインでの C プログラムのコンパイル](walkthrough-compile-a-c-program-on-the-command-line.md)<br/>
C プログラミング言語で書かれたプログラムをコンパイルする方法について説明します。

[チュートリアル: コマンド ラインでの C++/CLI プログラムのコンパイル](walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)<br/>
.NET Framework を使用する C++/CLI プログラムを作成およびコンパイルする方法について説明します。

[チュートリアル: コマンド ラインでの C++/CX プログラムのコンパイル](walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)<br/>
Windows ランタイムを使用する C++/CX プログラムを作成およびコンパイルする方法について説明します。

[コマンド ライン ビルドのパスと環境変数の設定](setting-the-path-and-environment-variables-for-command-line-builds.md)<br/>
32 ビットまたは 64 ビット ツールセットを使用することで x86、x64、ARM プラットフォームを対象とするコマンド ライン ビルドについて、必要な環境変数が設定されたコマンド プロンプト ウィンドウを起動する方法を説明します。

[NMAKE リファレンス](reference/nmake-reference.md)<br/>
NMAKE.EXE (Microsoft Program Maintenance Utility) について説明する記事へのリンクがあります。

[コマンド ラインでの MSBuild - C++](msbuild-visual-cpp.md)<br/>
コマンド ラインから msbuild.exe を使用する方法について説明する記事へのリンクがあります。

## <a name="related-sections"></a>関連項目

[/MD、/MT、/LD (ランタイム ライブラリの使用)](reference/md-mt-ld-use-run-time-library.md)<br/>
デバッグ バージョンまたはリリース バージョンのランタイム ライブラリを使用するための、コンパイラ オプションの使用方法について説明します。

[C/C++ コンパイラ オプション](reference/compiler-options.md)<br/>
C と C++ のコンパイラ オプションおよび CL.exe に関する記事へのリンクがあります。

[MSVC リンカー オプション](reference/linker-options.md)<br/>
リンカー オプションおよび LINK.exe に関する記事へのリンクがあります。

[追加の MSVC ビルド ツール](reference/c-cpp-build-tools.md)<br/>
Visual Studio に含まれている C/C++ ビルド ツールへのリンクがあります。

## <a name="see-also"></a>関連項目

[プロジェクトおよびビルド システム](projects-and-build-systems-cpp.md)