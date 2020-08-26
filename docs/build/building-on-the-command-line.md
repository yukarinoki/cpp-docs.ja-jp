---
title: コマンド ラインから Microsoft C++ ツールセットを使用する
description: Visual Studio IDE の外にあるコマンド ラインから Microsoft C++ (MSVC) コンパイラ ツールセットを使用します。
ms.custom: conceptual
ms.date: 04/21/2020
helpviewer_keywords:
- command-line builds [C++]
- compiling source code [C++], command line
- builds [C++], command-line
- command line [C++], building from
- command line [C++], compilers
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
ms.openlocfilehash: 1fe8e59c85e0c6b00bff4de639267a44c6ae369e
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838803"
---
# <a name="use-the-microsoft-c-toolset-from-the-command-line"></a>コマンド ラインから Microsoft C++ ツールセットを使用する

Visual Studio に含まれているツールを使用し、コマンド ラインで C と C++ のアプリケーションをビルドできます。 Microsoft C++ (MSVC) コンパイラ ツールセットは、スタンドアロン パッケージとしてダウンロードすることもできます。 Visual Studio IDE を使用する予定がない場合は、インストールする必要はありません。

> [!NOTE]
> この記事では、個々のコンパイラ、リンカー、ライブラリアン、その他の基本的なツールを使うように環境を設定する方法について説明します。 ネイティブのプロジェクト ビルド システム (MSBuild) では、この記事で説明されているような環境は使用されません。 コマンド ラインから MSBuild を使用する方法については、「[コマンド ラインでの MSBuild - C++](msbuild-visual-cpp.md)」をご覧ください。

## <a name="download-and-install-the-tools"></a>ツールのダウンロードとインストール

Visual Studio と C++ ワークロードがインストールされている場合は、すべてのコマンドライン ツールを使用できます。 C++ と Visual Studio をインストールする方法について詳しくは、「[Visual Studio での C++ サポートのインストール](vscpp-step-0-installation.md)」をご覧ください。 コマンドライン ツールセットのみが必要な場合、[Build Tools for Visual Studio](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019) をダウンロードしてください。 ダウンロードした実行可能ファイルを実行すると、Visual Studio インストーラーが更新され、実行されます。 C++ 開発に必要なツールのみをインストールするには、 **[C++ ビルド ツール]** ワークロードを選択します。 オプションのライブラリとツールセットを選択し、 **[インストールの詳細]** に含めることができます。 Visual Studio 2015 または 2017 ツールセットを使用してコードをビルドするには、オプションの MSVC v140 または MSVC v141 ビルド ツールを選択します。 選択が完了したら、 **[インストール]** を選択します。

## <a name="how-to-use-the-command-line-tools"></a>コマンド ライン ツールの使用方法

Visual Studio インストーラーでいずれかの C++ ワークロードを選択すると、Visual Studio *プラットフォーム ツールセット*がインストールされます。 プラットフォーム ツールセットには、特定の Visual Studio バージョンの C および C++ ツールがすべて含まれています。 これらのツールには、C/C++ コンパイラ、リンカー、アセンブラー、その他のビルド ツール、組みになるライブラリが含まれています。 これらのツールはすべて、コマンド ラインで使用できます。 また、Visual Studio IDE によって内部で使用されます。 x86 ホストと x64 ホストに分かれているコンパイラと、x86、x64、ARM、ARM64 ターゲット向けのコードをビルドするためのツールがあります。 特定のホストやターゲット ビルド アーキテクチャに対するそれぞれのツール セットは、その独自のディレクトリに保存されています。

ツールが正しく動作するには、特定の環境変数をいくつか設定する必要があります。 そのような環境変数は、ツールをパスに追加し、インクルード ファイル、ライブラリ ファイル、SDK の場所を設定する目的で使用されます。 このような環境変数をかん単に設定する目的で、インストーラーにより、インストール中、カスタマイズされた*コマンド ファイル*またはバッチ ファイルが作成されます。 いずれかのコマンド ファイルを実行し、特定のホストおよびターゲット ビルド アーキテクチャ、Windows SDK バージョン、プラットフォーム ツールセットを設定できます。 インストーラーによって、[スタート] メニューに便利なショートカットも作成されます。 ショートカットで開発者コマンド プロンプト ウィンドウが起動しますが、そのとき、ホストとターゲットの特定の組み合わせに対してこれらのコマンド ファイルが使用されます。 これらのショートカットによって、必要なすべての環境変数が設定され、使用できるようになります。

必須の環境変数はインストールに固有であり、選択したビルド アーキテクチャに固有となります。 また、製品の更新やアップグレードによって変更される場合があります。 そのため、環境変数を自分で設定せず、インストールされているコマンド プロンプトのショートカットまたはコマンド ファイルを使用することをお勧めします。 詳細については、[コマンド ライン ビルドのパスと環境変数の設定](setting-the-path-and-environment-variables-for-command-line-builds.md)に関するページを参照してください。

インストールされるツールセット、コマンド ファイル、ショートカットは、コンピューター プロセッサとインストール中に選択されたオプションによって決まります。 x86 および x64 コードをビルドする x86 ホスト ツールとクロス ツールは、常にインストールされます。 64 ビットの Windows を使用している場合は、x86 および x64 コードをビルドする x64 ホスト ツールとクロス ツールもインストールされます。 任意の C++ ユニバーサル Windows プラットフォーム ツールを選択した場合、ARM および ARM64 コードをビルドする x86 および x64 ツールもインストールされます。 その他のワークロードによって追加のツールがインストールされることもあります。

## <a name="developer-command-prompt-shortcuts"></a><a name="developer_command_prompt_shortcuts"></a> 開発者コマンド プロンプト ショートカット

コマンド プロンプト ショートカットは、[スタート] メニューのバージョン固有の Visual Studio フォルダーにインストールされます。 次は、基本的なコマンド プロンプト ショートカットとそれによりサポートされるビルド アーキテクチャを一覧にまとめたものです。

- **開発者コマンド プロンプト** - 32 ビット x86 ネイティブ ツールを使用して 32 ビット x86 ネイティブ コードをビルドするように環境を設定します。
- **x86 Native Tools コマンド プロンプト** - 32 ビット x86 ネイティブ ツールを使用して 32 ビット x86 ネイティブ コードをビルドするように環境を設定します。
- **x64 Native Tools コマンド プロンプト** - 64 ビット x64 ネイティブ ツールを使用して 64 ビット x64 ネイティブ コードをビルドするように環境を設定します。
- **x86_x64 Cross Tools コマンド プロンプト** - 32 ビット x86 ネイティブ ツールを使用して 64 ビット x64 ネイティブ コードをビルドするように環境を設定します。
- **x64_x86 Cross Tools コマンド プロンプト** - 64 ビット x64 ネイティブ ツールを使用して 32 ビット x86 ネイティブ コードをビルドするように環境を設定します。

::: moniker range=">= vs-2019"

[スタート] メニューのフォルダーとショートカットの名前は、インストールされている Visual Studio のバージョンによって異なります。 設定した場合は、インストール **ニックネーム**にも依存します。 たとえば、Visual Studio 2019 をインストールし、*Latest* というニックネームを付けたとします。 開発者コマンド プロンプト ショートカットには、**Visual Studio 2019** という名前のフォルダーで **Developer Command Prompt for VS 2019 (Latest)** という名前が付けられます。

::: moniker-end
::: moniker range="= vs-2017"

[スタート] メニューのフォルダーとショートカットの名前は、インストールされている Visual Studio のバージョンによって異なります。 設定した場合は、インストール **ニックネーム**にも依存します。 たとえば、Visual Studio 2017 をインストールし、*Latest* というニックネームを付けたとします。 開発者コマンド プロンプト ショートカットには、**Visual Studio 2017** という名前のフォルダーで **Developer Command Prompt for VS 2017 (Latest)** という名前が付けられます。

::: moniker-end
::: moniker range="< vs-2017"

[スタート] メニューのフォルダーとショートカットの名前は、インストールされている Visual Studio のバージョンによって異なります。 たとえば、Visual Studio 2015 をインストールしたとします。 開発者コマンド プロンプト ショートカットには、**Developer Command Prompt for VS 2015** という名前が付けられます。

::: moniker-end

### <a name="to-open-a-developer-command-prompt-window"></a><a name="developer_command_prompt"></a> 開発者コマンド プロンプト ウィンドウを開くには

1. デスクトップで、Windows の **[スタート]** メニューを開き、スクロールしてお使いのバージョンの Visual Studio (たとえば、**Visual Studio 2019**) のフォルダーを見つけて開きます。

1. フォルダーで、お使いのバージョンの Visual Studio の **[開発者コマンド プロンプト]** を選択します。 このショートカットにより、32 ビット x86 ネイティブ ツールの既定のビルド アーキテクチャを使用して 32 ビット x86 ネイティブ コードをビルドする開発者コマンド プロンプト ウィンドウが起動します。 既定以外のビルド アーキテクチャを使用する場合、いずれかのネイティブまたはクロス ツール コマンド プロンプトを選択し、ホストおよびターゲット アーキテクチャを指定します。

開発者コマンド プロンプト ウィンドウをもっと速く起動するには、デスクトップの検索ボックスに「*developer command prompt*」と入力します。 それから、目的の結果を選択します。

## <a name="developer-command-file-locations"></a><a name="developer_command_file_locations"></a> 開発者コマンド ファイルの場所

既存のコマンド プロンプト ウィンドウにビルド環境を設定する場合、インストーラーによって作成されたいずれかのコマンド ファイルを使用できます。 新しいコマンド プロンプト ウィンドウで環境を設定することをお勧めします。 後で同じコマンド ウィンドウで環境を切り替えることはお勧めしません。

::: moniker range=">= vs-2019"

コマンド ファイルの場所は、インストールした Visual Studio のバージョンとインストール中に選択した場所によって変わります。 Visual Studio 2019 の場合、64 ビット システムの一般的なインストール場所は \\Program Files (x86)\\Microsoft Visual Studio\\2019\\*エディション*です。 *エディション*には、Community、Professional、Enterprise、BuildTools、または指定した別のニックネームが入ります。

::: moniker-end
::: moniker range="= vs-2017"

コマンド ファイルの場所は、インストールした Visual Studio のバージョンとインストール中に選択した場所によって変わります。 Visual Studio 2017 の場合、64 ビット システムの一般的なインストール場所は \\Program Files (x86)\\Microsoft Visual Studio\\2017\\*エディション*です。 *エディション*には、Community、Professional、Enterprise、BuildTools、または指定した別のニックネームが入ります。

::: moniker-end
::: moniker range="< vs-2017"

コマンド ファイルの場所は、Visual Studio のバージョンとインストール ディレクトリによって異なります。 Visual Studio 2015 の場合、一般的なインストール場所は \\Program Files (x86)\\Microsoft Visual Studio 14.0 です。

::: moniker-end

開発者コマンド プロンプトの主要なコマンド ファイルである VsDevCmd.bat は、Common7\\Tools サブディレクトリにあります。 パラメーターが指定されていない場合は、x86 ネイティブ ツールを使用して 32 ビット x86 コードをビルドするように環境が設定されます。

::: moniker range=">= vs-2017"

特定のビルド アーキテクチャを設定するためコマンド ファイルは他にもあります。 使用できるコマンド ファイルは、インストールした Visual Studio のワークロードとオプションによって異なります。 Visual Studio 2017 および Visual Studio 2019 では、サブディレクトリ VC\\Auxiliary\\Build にあります。

::: moniker-end
::: moniker range="< vs-2017"

特定のビルド アーキテクチャを設定するためコマンド ファイルは他にもあります。 使用できるコマンド ファイルは、インストールした Visual Studio のワークロードとオプションによって異なります。 Visual Studio 2015 の場合、サブディレクトリ VC、VC\\bin、または VC\\bin\\*architecture* にあります。*architectures* には、ネイティブまたはクロスコンパイラ オプションが入ります。

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
|**vcvarsall.bat**| パラメーターを使用し、ホストおよびターゲット アーキテクチャ、Windows SDK、プラットフォームを指定します。 サポートされているオプションの一覧が必要な場合、 **/help** パラメーターを使用して呼び出します。|

> [!CAUTION]
> vcvarsall.bat ファイルとその他の Visual Studio コマンド ファイルはコンピューターによって異なります。 vcvarsall.bat ファイルが見つからない場合や破損している場合でも、別のコンピューターのファイルを使用して置き換えないでください。 Visual Studio インストーラーを再実行し、不足しているファイルを置換します。
>
> vcvarsall.bat ファイルは、バージョンによっても異なります。 以前のバージョンの Visual Studio も入っているコンピューターに現行版の Visual Studio をインストールする場合、同じコマンド プロンプト ウィンドウで異なるバージョンの vcvarsall.bat または別の Visual Studio コマンド ファイルを実行しないでください。

## <a name="use-the-developer-tools-in-an-existing-command-window"></a>既存のコマンド ウィンドウで開発者ツールを使用する

既存のコマンド ウィンドウで特定のビルド アーキテクチャを指定する最も簡単な方法は、vcvarsall.bat ファイルを使用することです。 環境変数を設定し、ネイティブ 32 ビットまたは 64 ビット コンパイルのコマンド ラインを構成するには vcvarsall.bat を使用します。 引数を使用すると、x86、x64、ARM、または ARM64 プロセッサのクロスコンパイルを指定できます。 Microsoft Store、ユニバーサル Windows プラットフォーム、または Windows デスクトップ プラットフォームを対象にできます。 使用する Windows SDK を指定し、プラットフォーム ツールセットのバージョンを選択することもできます。

引数なしで使用すると、32 ビット Windows Desktop を対象として現在の x86 ネイティブ コンパイラを使用するための環境変数が構成されます。 引数を追加し、ネイティブまたはクロス コンパイラ ツールを使用するように環境を構成できます。 コンピューターにインストールされていない構成、または使用できない構成を指定すると、vcvarsall.bat によってエラー メッセージが表示されます。

### <a name="vcvarsall-syntax"></a>vcvarsall 構文

> **vcvarsall.bat** [*architecture*] [*platform_type*] [*winsdk_version*] [ **-vcvars_ver=** _vcversion_]

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
任意で、使用する Visual Studio コンパイラ ツールセットを指定します。 既定では、現在の Visual Studio コンパイラ ツールセットを使用するように環境が設定されます。

::: moniker range=">= vs-2019"

Visual Studio 2019 コンパイラ ツールセットの特定のバージョンを指定するには、 **-vcvars_ver=14.2x.yyyyy** を使用します。

Visual Studio 2017 コンパイラ ツールセットの最新のバージョンを指定するには、 **-vcvars_ver=14.16** を使用します。

::: moniker-end
::: moniker range="= vs-2017"

Visual Studio 2017 コンパイラ ツールセットの最新のバージョンを指定するには、 **-vcvars_ver=14.16** を使用します。

Visual Studio 2017 コンパイラ ツールセットの特定のバージョンを指定するには、 **-vcvars_ver=14.1x.yyyyy** を使用します。

::: moniker-end

Visual Studio 2015 コンパイラ ツールセットを指定するには、 **-vcvars_ver=14.0** を使用します。

#### <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a><a name="vcvarsall"></a> 既存のコマンド プロンプト ウィンドウでビルド環境を設定するには

1. コマンド プロンプトで、CD コマンドを使用し、Visual Studio インストール ディレクトリに作業ディレクトリを変更します。 次に、CD をもう一度使用し、構成固有のコマンド ファイルが含まれるサブディレクトリに作業ディレクトリを変更します。 Visual Studio 2019 および Visual Studio 2017 では、サブディレクトリ *VC\\Auxiliary\\Build* を使用します。 Visual Studio 2015 の場合、*VC* サブディレクトリを使用します。

1. 優先開発者環境のコマンドを入力します。 たとえば、最新の Windows SDK と Visual Studio コンパイラ ツールセットを使用し、64 ビット プラットフォームで UWP 向け ARM コードをビルドするには、このコマンド ラインを使用します。

   `vcvarsall.bat amd64_arm uwp`

## <a name="create-your-own-command-prompt-shortcut"></a>独自のコマンド プロンプト ショートカットを作成する

::: moniker range=">= vs-2019"

開発者コマンド プロンプト ショートカットに対して [プロパティ] ダイアログを開くと、使用されているコマンド ターゲットが表示されます。 たとえば、**x64 Native Tools Command Prompt for VS 2019** ショートカットのターゲットは次のようになります。

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvars64.bat"`

::: moniker-end
::: moniker range="= vs-2017"

開発者コマンド プロンプト ショートカットに対して [プロパティ] ダイアログを開くと、使用されているコマンド ターゲットが表示されます。 たとえば、**x64 Native Tools Command Prompt for VS 2017** ショートカットのターゲットは次のようになります。

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvars64.bat"`

::: moniker-end
::: moniker range="< vs-2017"

開発者コマンド プロンプト ショートカットに対して [プロパティ] ダイアログを開くと、使用されているコマンド ターゲットが表示されます。 たとえば、**VS2015 x64 Native Tools Command Prompt** ショートカットのターゲットは次のようになります。

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\vcvarsall.bat" amd64`

::: moniker-end

このアーキテクチャ固有のバッチ ファイルにより *architecture* パラメーターが設定され、vcvarsall.bat が呼び出されます。 vcvarsall.bat に渡す場合と同様に、これらのバッチ ファイルに同じオプションを渡すことができます。あるいは、vcvarsall.bat を直接呼び出すことができます。 独自のコマンド ショートカットのパラメーターを指定するには、それを二重引用符でコマンドの終わりに追加します。 たとえば、最新の Windows SDK を使用し、64 ビット プラットフォームで UWP の ARM コードをビルドするショートカットを次に示します。 以前のコンパイラ ツールセットを使用するには、バージョン番号を指定します。 ショートカットで次のようなコマンド ターゲットを使用します。

::: moniker range=">= vs-2019"

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvarsall.bat" amd64_arm uwp -vcvars_ver=14.16`

::: moniker-end
::: moniker range="= vs-2017"

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvarsall.bat" amd64_arm uwp -vcvars_ver=14.0`

::: moniker-end
::: moniker range="< vs-2017"

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\vcvarsall.bat" amd64 -vcvars_ver=12.0`

::: moniker-end

Visual Studio インストール ディレクトリが反映されるようにパスを調整します。 vcvarsall.bat ファイルには、特定のバージョン番号に関する追加情報があります。

## <a name="command-line-tools"></a>コマンド ライン ツール

コマンド プロンプトで C/C++ プロジェクトをビルドする目的で、Visual Studio からは以下のコマンドライン ツールが提供されます。

[CL](reference/compiling-a-c-cpp-program.md)<br/>
コンパイラ (cl.exe) は、ソース コード ファイルをアプリ、ライブラリ、および DLL にコンパイルおよびリンクするために使用します。

[リンク](reference/linking.md)<br/>
リンカー (link.exe) は、コンパイルされたオブジェクト ファイルおよびライブラリをアプリおよび DLL にリンクするために使用します。

[NMAKE](reference/nmake-reference.md)<br/>
Windows で NMAKE (nmake.exe) を使用し、従来のメイクファイルに基づいて C++ プロジェクトをビルドします。

コマンド ラインでビルドするとき、F1 コマンドでヘルプを瞬時に表示することはできません。 代わりに、検索エンジンを使用して警告、エラー、メッセージに関する情報を取得できます。 また、オフラインのヘルプ ファイルをダウンロードして使用することもできます。 docs.microsoft.com で検索を使用するには、記事の上部にある検索ボックスにクエリを入力します。

## <a name="command-line-project-management-tools"></a>コマンド ライン プロジェクト管理ツール

Visual Studio IDE では、MSBuild に基づくネイティブ プロジェクト ビルド システムが使用されます。 MSBuild を直接呼び出すことも、IDE を使わずにネイティブ プロジェクト システムを使用することもできます。

[MSBuild](msbuild-visual-cpp.md)<br/>
MSBuild (msbuild.exe) とプロジェクト ファイル (.vcxproj) を使用し、ビルドを構成し、ツールセットを間接的に呼び出します。 これは、Visual Studio IDE で **[プロジェクトのビルド]** コマンドまたは **[ソリューションのビルド]** コマンドを実行することと同じです。 コマンド ラインから MSBuild を実行することは上級向けのシナリオであり、一般的には推奨されません。 Visual Studio バージョン 16.5 以降では、使用するツールセットとライブラリを制御するために MSBuild でコマンド ライン環境が使用されることはありません。

[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)<br/>
DEVENV (devenv.exe) は、Visual Studio IDE を表示せずに特定のビルド コマンドを実行するために、 **/Build** や **/Clean** などのコマンド ライン スイッチと組み合わせて使用します。 一般的に、DEVENV は MSBuild を直接使用することよりも推奨されます。複雑な MSBuild を Visual Studio に処理させることができるためです。 Visual Studio バージョン 16.5 以降では、使用するツールセットとライブラリを制御するために DEVENV でコマンド ライン環境が使用されることはありません。

## <a name="in-this-section"></a>このセクションの内容

これらの記事では、コマンド ラインでアプリを作成する方法と、コマンドライン ビルド環境をカスタマイズする方法を説明します。 一部の記事では、64 ビット ツールセットを使用する方法と、x86、x64、ARM、ARM64 の各プラットフォームを対象とする方法を紹介しています。 また、コマンドライン ビルド ツール MSBuild と NMAKE の使用方法について説明します。

[チュートリアル: コマンド ラインでのネイティブ C++ プログラムのコンパイル](walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)<br/>
コマンド ラインで C++ プログラムを作成およびコンパイルする方法を示す例があります。

[チュートリアル: コマンド ラインでの C プログラムのコンパイル](walkthrough-compile-a-c-program-on-the-command-line.md)<br/>
C プログラミング言語で書かれたプログラムをコンパイルする方法について説明します。

[チュートリアル: コマンド ラインでの C++/CLI プログラムのコンパイル](walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)<br/>
.NET Framework を使用する C++/CLI プログラムを作成およびコンパイルする方法について説明します。

[チュートリアル: コマンド ラインでの C++/CX プログラムのコンパイル](walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)<br/>
Windows ランタイムを使用する C++/CX プログラムを作成およびコンパイルする方法について説明します。

[コマンド ライン ビルドのパスと環境変数の設定](setting-the-path-and-environment-variables-for-command-line-builds.md)<br/>
32 ビットまたは 64 ビットのツールセットを使用し、x86、x64、ARM、ARM64 の各プラットフォームを対象とするように環境変数を設定する方法について説明します。

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
