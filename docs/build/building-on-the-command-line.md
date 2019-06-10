---
title: 使用して、MicrosoftC++からコマンド ライン ツールセット
description: Visual Studio IDE の外にあるコマンド ラインから Microsoft C++ コンパイラ ツールチェーン (MSVC) を使用します。
ms.custom: conceptual
ms.date: 06/06/2019
helpviewer_keywords:
- command-line builds [C++]
- compiling source code [C++], command line
- builds [C++], command-line
- command line [C++], building from
- command line [C++], compilers
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
ms.openlocfilehash: b5e9bf266d79ee86cae84535641a52c7c52be391
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821138"
---
# <a name="use-the-microsoft-c-toolset-from-the-command-line"></a>使用して、MicrosoftC++からコマンド ライン ツールセット

Visual Studio に含まれているツールを使用し、コマンド ラインで C と C++ のアプリケーションをビルドできます。 Microsoft C++ (MSVC) コンパイラ ツールセットからのスタンドアロン パッケージとしてダウンロードできますも、 [Visual Studio のダウンロード](https://visualstudio.microsoft.com/downloads/)ページ。 一部に、 **for Visual Studio Build Tools**パッケージ。 必要なツールだけをダウンロードすることもできますC++開発します。

## <a name="how-to-use-the-command-line-tools"></a>コマンド ライン ツールの使用方法

Visual Studio インストーラーでいずれかの C++ ワークロードを選択すると、Visual Studio *プラットフォーム ツールセット*がインストールされます。 プラットフォームのツールセットが、すべての C とC++Visual Studio のバージョンを特定するためのツール。 このツールは、C/C++コンパイラ、リンカー、アセンブラー、およびその他のビルド ツール、および一致するライブラリ。 コマンドラインでは、これらのツールを使用できます。 Visual Studio IDE では、それらが内部的に使用もいます。 個別の x86 でホストされているし、x64 でホストされているコンパイラがあり、x86、x64、ARM および ARM64 のターゲット コード、ビルドするためのツール。 特定のホストやターゲット ビルド アーキテクチャに対するそれぞれのツール セットは、その独自のディレクトリに保存されています。

ツールが正しく動作するには、特定の環境変数をいくつか設定する必要があります。 これらの変数を使用して、ツールと設定するには、パスに含めるファイル、ライブラリ ファイル、および SDK の場所を追加できます。 このような環境変数をかん単に設定する目的で、インストーラーにより、インストール中、カスタマイズされた*コマンド ファイル*またはバッチ ファイルが作成されます。 特定のホストとターゲットのビルドのアーキテクチャ、Windows SDK のバージョンとプラットフォーム ツールセットを設定するには、これらのコマンド ファイルのいずれかの操作を行うことができます。 便宜上、インストーラーはまた、スタート メニューにショートカットを作成します。 ショートカットは、これらのコマンド ファイルをホストおよびターゲットの特定の組み合わせを使用して開発者コマンド プロンプト ウィンドウを起動します。 これらのショートカットでは、すべての必要な環境変数が設定および使用する準備を確認します。

必要な環境変数は、ビルドのアーキテクチャを選択して、インストールに固有です。 製品の更新プログラムやアップグレードによって変更される可能性があります。 理由は自分で環境変数を設定する代わりに、インストールされているコマンド プロンプト ショートカットまたはコマンド ファイルを使用することをお勧めします。 詳細については、次を参照してください。[コマンド ライン ビルドのパスと環境変数を設定](setting-the-path-and-environment-variables-for-command-line-builds.md)します。

ツールセット、コマンド ファイルは、インストールされているショートカットは、コンピューターのプロセッサとのインストール時に選択したオプションによって異なります。 X86 でホストされたツールおよび x86 と x64 のコードをビルドするクロス ツールは常にインストールします。 64 ビット Windows の場合は、x64 でホストされたツールおよび x86 と x64 のコードをビルドするクロス ツールもインストールします。 省略可能な場合C++、ユニバーサル Windows プラットフォーム ツール ARM および ARM64 のコードをビルドする x86 および x64 のツールもインストールされます。 その他のワークロードによって追加のツールがインストールされることもあります。

## <a name="developer_command_prompt_shortcuts"></a> 開発者コマンド プロンプト ショートカット

コマンド プロンプト ショートカットは、[スタート] メニューのバージョン固有の Visual Studio フォルダーにインストールされます。 次は、基本的なコマンド プロンプト ショートカットとそれによりサポートされるビルド アーキテクチャを一覧にまとめたものです。

- **開発者コマンド プロンプト** - 32 ビット x86 ネイティブ ツールを使用して 32 ビット x86 ネイティブ コードをビルドするように環境を設定します。
- **x86 Native Tools コマンド プロンプト** - 32 ビット x86 ネイティブ ツールを使用して 32 ビット x86 ネイティブ コードをビルドするように環境を設定します。
- **x64 Native Tools コマンド プロンプト** - 64 ビット x64 ネイティブ ツールを使用して 64 ビット x64 ネイティブ コードをビルドするように環境を設定します。
- **x86_x64 Cross Tools コマンド プロンプト** - 32 ビット x86 ネイティブ ツールを使用して 64 ビット x64 ネイティブ コードをビルドするように環境を設定します。
- **x64_x86 Cross Tools コマンド プロンプト** - 64 ビット x64 ネイティブ ツールを使用して 32 ビット x86 ネイティブ コードをビルドするように環境を設定します。

::: moniker range=">= vs-2019"

スタート メニュー フォルダーとショートカット名は、Visual Studio のインストールされているバージョンによって異なります。 1 つを設定した場合も、インストールで依存**ニックネーム**します。 たとえば、Visual Studio 2019 をインストールしてのニックネームを指定した*最新*します。 開発者コマンド プロンプトのショートカットの名前は**開発者コマンド プロンプト for VS 2019 (最新)** 、という名前のフォルダーで**Visual Studio 2019**します。

::: moniker-end
::: moniker range="= vs-2017"

スタート メニュー フォルダーとショートカット名は、Visual Studio のインストールされているバージョンによって異なります。 1 つを設定した場合も、インストールで依存**ニックネーム**します。 たとえば、Visual Studio 2017 をインストールしてのニックネームを指定した*最新*します。 開発者コマンド プロンプトのショートカットの名前は**開発者コマンド プロンプト for VS 2017 (最新)** 、という名前のフォルダーで**Visual Studio 2017**します。

::: moniker-end
::: moniker range="< vs-2017"

スタート メニュー フォルダーとショートカット名は、Visual Studio のインストールされているバージョンによって異なります。 たとえば、Visual Studio 2015 をインストールしたとします。 開発者コマンド プロンプトのショートカットの名前は**開発者コマンド プロンプト for VS 2015**します。

::: moniker-end

## <a name="developer_command_prompt"></a> 開発者コマンド プロンプト ウィンドウを開くには

1. デスクトップで、Windows の **[スタート]** メニューを開き、スクロールしてお使いのバージョンの Visual Studio (たとえば、**Visual Studio 2019**) のフォルダーを見つけて開きます。

1. フォルダーで、お使いのバージョンの Visual Studio の **[開発者コマンド プロンプト]** を選択します。 このショートカットにより、32 ビット x86 ネイティブ ツールの既定のビルド アーキテクチャを使用して 32 ビット x86 ネイティブ コードをビルドする開発者コマンド プロンプト ウィンドウが起動します。 既定以外のビルド アーキテクチャを使用する場合、いずれかのネイティブまたはクロス ツール コマンド プロンプトを選択し、ホストおよびターゲット アーキテクチャを指定します。

さらに高速の開発者コマンド プロンプトを開き、方法を次のように入力します。*開発者コマンド プロンプト*デスクトップ検索ボックスにします。 目的の結果を選択します。

## <a name="developer_command_file_locations"></a> 開発者コマンド ファイルの場所

既存のコマンド プロンプト ウィンドウで、ビルド環境を設定する場合は、インストーラーによって作成されたコマンド ファイルのいずれかを使用できます。 新しいコマンド プロンプト ウィンドウで、環境を設定することをお勧めします。 後で同じコマンド ウィンドウで環境を切り替えますお勧めしません。

::: moniker range=">= vs-2019"

コマンド ファイルの場所は、インストールした Visual Studio のバージョンおよびインストール中に行った選択によって異なります。 Visual Studio 2019、64 ビット システム上の一般的なインストール場所は\\Program Files (x86)\\Microsoft Visual Studio\\2019\\*edition*します。 *Edition* Community、Professional、Enterprise、build Tools、または別のニックネームを指定する場合があります。

::: moniker-end
::: moniker range="= vs-2017"

コマンド ファイルの場所は、インストールした Visual Studio のバージョンおよびインストール中に行った選択によって異なります。 Visual Studio 2017 では、64 ビット システム上の一般的なインストール場所は\\Program Files (x86)\\Microsoft Visual Studio\\2017\\*edition*します。 *Edition* Community、Professional、Enterprise、build Tools、または別のニックネームを指定する場合があります。

::: moniker-end
::: moniker range="< vs-2017"

コマンド ファイルの場所は、Visual Studio のバージョンと、インストール ディレクトリによって異なります。 一般的なインストール場所は、Visual Studio 2015 で\\Program Files (x86)\\Microsoft Visual Studio 14.0 です。

::: moniker-end

主な開発者コマンド プロンプトのコマンド ファイルを VsDevCmd.bat の場合は、Common7 \appdata\local\microsoft\microsoft\\Tools サブディレクトリ。 X86 ネイティブ ツールを使用して、32 ビット x86 を構築する環境を設定するパラメーターが指定されていない場合のコード。

::: moniker range=">= vs-2017"

複数のコマンド ファイルは特定のビルドのアーキテクチャを設定します。 利用可能なコマンド ファイルは、Visual Studio のワークロードとインストールされているオプションによって異なります。 Visual Studio 2017 と Visual Studio 2019 で見つかりますに vc\\補助\\サブディレクトリを作成します。

::: moniker-end
::: moniker range="< vs-2017"

複数のコマンド ファイルは特定のビルドのアーキテクチャを設定します。 利用可能なコマンド ファイルは、Visual Studio のワークロードとインストールされているオプションによって異なります。 VC、VC で Visual Studio 2015 で配置している\\bin、または VC\\bin\\*アーキテクチャ*、サブディレクトリ、*アーキテクチャ*はネイティブのいずれかまたはクロス コンパイラ オプション。

::: moniker-end

これらのコマンド ファイルにより既定のパラメーターが設定され、VsDevCmd.bat が呼び出されて指定のビルド アーキテクチャ環境が設定されます。 一般的なインストールに含まれるコマンド ファイル:

|コマンド ファイル|ホストおよびターゲット アーキテクチャ|
|---|---|
|**vcvars32.bat**| 32 ビット x86 ネイティブ ツールを使用し、32 ビット x86 コードをビルドします。|
|**vcvars64.bat**| 64 ビット x64 ネイティブ ツールを使用し、64 ビット x64 コードをビルドします。|
|**vcvarsx86_amd64.bat**| 32 ビット x86 ネイティブ クロス ツールを使用し、64 ビット x64 コードをビルドします。|
|**vcvarsamd64_x86.bat**| 64 ビット x64 ネイティブ クロス ツールを使用し、32 ビット x86 コードをビルドします。|
|**vcvarsx86_arm.bat**| 32 ビット x86 ネイティブ クロス ツールを使用し、ARM コードをビルドします。|
|**vcvarsamd64_arm.bat**| 64 ビット x64 ネイティブ クロス ツールを使用し、ARM コードをビルドします。|
|**vcvarsall.bat**| パラメーターを使用すると、ホストとターゲット アーキテクチャ、Windows SDK、およびプラットフォームのオプションを指定します。 サポートされているオプションの一覧が必要な場合、 **/help** パラメーターを使用して呼び出します。|

> [!CAUTION]
> vcvarsall.bat ファイルとその他の Visual Studio コマンド ファイルはコンピューターによって異なります。 vcvarsall.bat ファイルが見つからない場合や破損している場合でも、別のコンピューターのファイルを使用して置き換えないでください。 Visual Studio インストーラーを再実行し、不足しているファイルを置換します。
>
> vcvarsall.bat ファイルは、バージョンによっても異なります。 以前のバージョンの Visual Studio も入っているコンピューターに現行版の Visual Studio をインストールする場合、同じコマンド プロンプト ウィンドウで異なるバージョンの vcvarsall.bat または別の Visual Studio コマンド ファイルを実行しないでください。

## <a name="use-the-developer-tools-in-an-existing-command-window"></a>既存のコマンド ウィンドウで開発者ツールを使用する

既存のコマンド ウィンドウで特定のビルド アーキテクチャを指定する最も簡単な方法は、vcvarsall.bat ファイルを使用することです。 Vcvarsall.bat を使用して、32 ビットまたは 64 ビットのネイティブ コンパイルのコマンドラインを構成する環境変数を設定します。 引数では、x86、x64、ARM にクロス コンパイルを指定できます。 または ARM64 プロセッサ。 Microsoft Store、ユニバーサル Windows プラットフォーム、または Windows デスクトップ プラットフォームを対象にすることができます。 でもを使用するには、どの Windows SDK を指定し、プラットフォーム ツールセットのバージョンを選択できます。

引数なしで使用される、vcvarsall.bat は 32 ビットの Windows デスクトップのターゲットの現在の x86 ネイティブ コンパイラを使用する環境変数を構成します。 ネイティブやクロス コンパイラ ツールを使用する環境を構成する引数を追加することができます。 vcvarsall.bat がインストールされていない構成を指定する場合、エラー メッセージを表示またはコンピューターで使用します。

### <a name="vcvarsall-syntax"></a>vcvarsall 構文

> **vcvarsall.bat** [*architecture*] [*platform_type*] [*winsdk_version*] [ **-vcvars_ver=** _vcversion_]

*architecture*<br/>
この任意の引数では、使用するホストおよびターゲット アーキテクチャが指定されます。 場合*アーキテクチャ*が指定されていない、既定のビルド環境を使用します。 以下の引数がサポートされています。

|*architecture*|コンパイラ|ホスト コンピューターのアーキテクチャ|ビルド出力 (ターゲット) のアーキテクチャ|
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
任意で、使用する Visual Studio コンパイラ ツールセットを指定します。 既定では、現在の Visual Studio コンパイラ ツールセットを使用するように環境が設定されます。

::: moniker range=">= vs-2019"

使用 **-'-vcvars_ver=14.0' = 14.2 .yyyyy x**特定バージョンの Visual Studio 2019 コンパイラ ツールセットを指定します。

使用 **-'-vcvars_ver=14.0' = 14.16** Visual Studio 2017 のコンパイラ ツールセットの最新バージョンを指定します。

::: moniker-end
::: moniker range="= vs-2017"

使用 **-'-vcvars_ver=14.0' = 14.16** Visual Studio 2017 のコンパイラ ツールセットの最新バージョンを指定します。

使用 **-'-vcvars_ver=14.0' = 14.1 x .yyyyy**特定のバージョンの Visual Studio 2017 のコンパイラ ツールセットを指定します。

::: moniker-end

使用 **-'-vcvars_ver=14.0' = 14.0** Visual Studio 2015 コンパイラ ツールセットを指定します。

<a name="vcvarsall"></a>
#### <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a>既存のコマンド プロンプト ウィンドウでビルド環境を設定するには

1. コマンド プロンプトで、CD コマンドを使用し、Visual Studio インストール ディレクトリに作業ディレクトリを変更します。 次に、CD をもう一度使用し、構成固有のコマンド ファイルが含まれるサブディレクトリに作業ディレクトリを変更します。 Visual Studio 2019 と Visual Studio 2017 では、使用して、 *VC\\補助\\ビルド*サブディレクトリ。 Visual Studio 2015 を使用して、 *VC*サブディレクトリ。

1. 優先開発者環境のコマンドを入力します。 たとえば、最新 Windows SDK と Visual Studio コンパイラ ツールセットを使用して、64 ビット プラットフォームで、UWP の ARM コードをビルドするには、このコマンドラインを使用します。

   `vcvarsall.bat amd64_arm uwp`

## <a name="create-your-own-command-prompt-shortcut"></a>独自のコマンド プロンプト ショートカットを作成する

::: moniker range=">= vs-2019"

コマンド ターゲットを使用して開発者コマンド プロンプト ショートカットのプロパティ ダイアログを開きます。 たとえば、**x64 Native Tools Command Prompt for VS 2019** ショートカットのターゲットは次のようになります。

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvars64.bat"`

::: moniker-end
::: moniker range="= vs-2017"

コマンド ターゲットを使用して開発者コマンド プロンプト ショートカットのプロパティ ダイアログを開きます。 ターゲットなど、 **x64 Native Tools コマンド プロンプト for VS 2017**ショートカットは、以下のようにします。

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvars64.bat"`

::: moniker-end
::: moniker range="< vs-2017"

コマンド ターゲットを使用して開発者コマンド プロンプト ショートカットのプロパティ ダイアログを開きます。 ターゲットなど、 **VS2015 x64 Native Tools コマンド プロンプト**ショートカットは、以下のようにします。

`%comspec% /k ""C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\vcvarsall.bat"" amd64`

::: moniker-end

このアーキテクチャ固有のバッチ ファイルにより *architecture* パラメーターが設定され、vcvarsall.bat が呼び出されます。 Vcvarsall.bat にも直接 vcvarsall.bat だけ呼び出すことができます、これらのバッチ ファイルを同じオプションを渡すことができます。 独自のコマンド ショートカットのパラメーターを指定するには、それを二重引用符でコマンドの終わりに追加します。 たとえば、最新の Windows SDK を使用して、64 ビット プラットフォームで、UWP の ARM コードをビルドへのショートカットを次に示します。 以前のコンパイラ ツールセットを使用するには、バージョン番号を指定します。 ショートカットで次のようなコマンド ターゲットを使用します。

::: moniker range=">= vs-2019"

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvarsall.bat amd64_arm uwp -vcvars_ver=14.16"`

::: moniker-end
::: moniker range="= vs-2017"

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvarsall.bat amd64_arm uwp -vcvars_ver=14.0"`

::: moniker-end
::: moniker range="< vs-2017"

`%comspec% /k ""C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\vcvarsall.bat"" amd64 -vcvars_ver=12.0`

::: moniker-end

Visual Studio インストール ディレクトリを反映するようにパスを調整します。 vcvarsall.bat ファイルには、特定のバージョン番号に関する追加情報があります。

## <a name="command-line-tools"></a>コマンド ライン ツール

C を構築する/C++コマンド プロンプト、Visual Studio でプロジェクトには、これらのコマンド ライン ツールが用意されています。

[CL](reference/compiling-a-c-cpp-program.md)<br/>
コンパイラ (cl.exe) は、ソース コード ファイルをアプリ、ライブラリ、および DLL にコンパイルおよびリンクするために使用します。

[リンク](reference/linking.md)<br/>
リンカー (link.exe) は、コンパイルされたオブジェクト ファイルおよびライブラリをアプリおよび DLL にリンクするために使用します。

[MSBuild](msbuild-visual-cpp.md)<br/>
MSBuild (msbuild.exe) とプロジェクト ファイル (.vcxproj) を使用し、ビルドを構成し、ツールセットを間接的に呼び出します。 これは実行に相当、**ビルド**プロジェクトまたは**ソリューションのビルド**Visual Studio IDE にコマンド。 コマンドラインから MSBuild を実行している、高度なシナリオし、よくないことをお勧めします。

[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)<br/>
コマンド ライン スイッチとなど DEVENV (devenv.exe) を使用してが組み合わせて **/build**または **/clean**を実行する特定のビルド コマンド、Visual Studio IDE を表示せずします。 一般に、DEVENV をお勧め MSBuild を直接を使用するため、Visual Studio の MSBuild の複雑さを処理させることができます。

[NMAKE](reference/nmake-reference.md)<br/>
Windows で NMAKE (nmake.exe) を使用し、従来のメイクファイルに基づいて C++ プロジェクトをビルドします。

コマンドラインでビルドするときに F1 コマンドはインスタント ヘルプ使用できません。 代わりに、検索エンジンを使用して警告、エラー、メッセージに関する情報を取得できます。あるいは、オフラインのヘルプ ファイルを使用できます。 検索を使用する[docs.microsoft.com](https://docs.microsoft.com/cpp/)ページの上部にある検索ボックスを使用します。

## <a name="in-this-section"></a>このセクションの内容

これらの記事は、コマンドラインでアプリをビルドする方法について説明し、コマンド ライン ビルド環境をカスタマイズする方法について説明します。 64 ビットのツールセットを使用して、x64、ARM、x86 を対象とする方法を表示するいくつか、ARM64 プラットフォーム。 MSBuild および NMAKE コマンド ライン ビルド ツールの使用についても説明します。

[チュートリアル: コマンド ラインでのネイティブ C++ プログラムのコンパイル](walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)<br/>
作成およびコンパイルする方法を示す例を示しています、C++コマンドライン上のプログラム。

[チュートリアル: コマンド ラインでの C プログラムのコンパイル](walkthrough-compile-a-c-program-on-the-command-line.md)<br/>
C プログラミング言語で書かれたプログラムをコンパイルする方法について説明します。

[チュートリアル: コマンド ラインでの C++/CLI プログラムのコンパイル](walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)<br/>
.NET Framework を使用する C++/CLI プログラムを作成およびコンパイルする方法について説明します。

[チュートリアル: コマンド ラインでの C++/CX プログラムのコンパイル](walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)<br/>
Windows ランタイムを使用する C++/CX プログラムを作成およびコンパイルする方法について説明します。

[コマンド ライン ビルドのパスと環境変数の設定](setting-the-path-and-environment-variables-for-command-line-builds.md)<br/>
ターゲット x86、x64、ARM、32 ビットまたは 64 ビット ツールセットを使用する環境変数を設定する方法および ARM64 プラットフォーム。

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
