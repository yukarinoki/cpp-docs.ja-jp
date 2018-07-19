---
title: コマンドラインで C/C++ コードをビルド |Microsoft ドキュメント
ms.custom: conceptual
ms.date: 06/21/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command-line builds [C++]
- compiling source code [C++], command line
- builds [C++], command-line
- command line [C++], building from
- command line [C++], compilers
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 241a7ae0d7f6c1adf269370301b39a3267440995
ms.sourcegitcommit: e013acba70aa29fed60ae7945162adee23e19c3b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/22/2018
ms.locfileid: "36322317"
---
# <a name="build-cc-code-on-the-command-line"></a>コマンドラインで C/C++ コードをビルドします。

コマンドラインで C および C++ アプリケーションをビルドするには、Visual Studio に含まれているツールを使用します。

## <a name="how-to-get-the-command-line-tools"></a>コマンド ライン ツールを取得する方法

Visual Studio インストールを選択すると、C++ のワークロードのいずれかの Visual Studio インストーラーで、*プラットフォーム ツールセット*です。 プラットフォーム ツールセットには、C/C++ コンパイラ、リンカー、アセンブラー、およびその他のビルド ツールだけでなく、一致するライブラリを含む特定の Visual Studio バージョンのすべての C および C++ のツールがあります。 これらのツールを使用するには、コマンドラインでと、Visual Studio IDE によって内部的に使用されますもします。 X86 ホストおよび x64 がホストする個別のコンパイラおよび x86、x64、ARM コードを構築するためのツールと ARM64 ターゲットがあります。 特定のホストとターゲットのビルド アーキテクチャ用のツールの各セットは、独自のディレクトリに格納されます。

正常に機能するには、ツールにはいくつかの特定の環境変数を設定する必要があります。 これらのパスに追加および設定に使用されますファイル、ライブラリ ファイル、および SDK の場所が含まれます。 簡単にこれらの環境変数を設定、インストーラーによって作成カスタマイズされた*コマンド ファイル*インストール中にバッチ ファイル、または。 特定のホストとターゲットのビルドのアーキテクチャ、Windows SDK のバージョン、ターゲット プラットフォーム、およびプラットフォーム ツールセットを設定するコマンド プロンプト ウィンドウでは、これらのコマンド ファイルのいずれかを実行できます。 便宜上、インストーラーもショートカットを作成、[スタート] メニュー (または Windows のスタート ページ 8.x) すべての必要な環境変数が設定され、準備ができて、使用するようにこれらのコマンド ファイルを使用して開発者コマンド プロンプト ウィンドウを起動します。

必要な環境変数は、インストールして、ビルドのアーキテクチャを選択し、製品の更新プログラムやアップグレードによって変更される可能性に固有です。 そのため、インストールされているコマンド プロンプト ショートカットまたはコマンド ファイルのいずれかを自分で windows 環境変数を設定する代わりに使用することを強くお勧めします。 詳細については、次を参照してください。[コマンド ライン ビルドのパスと環境変数を設定](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)です。

コマンド ライン ツールセット、コマンド ファイルは、およびインストールされているコマンド プロンプト ショートカットは、コンピューターのプロセッサとのインストール時に選択したオプションによって異なります。 少なくとも 32 ビット x86 ネイティブ コードをビルドし、64 ビット x64 ネイティブ コードのビルド ツールに交差している 32 ビット x86 ホスト ツールがインストールされます。 64 ビットの Windows がある場合は、64 ビットのネイティブ コードをビルドし、32 ビットのネイティブ コードのビルド ツールに交差している 64 ビット x64 でホストされたツールもインストールされます。 省略可能な C++ ユニバーサル Windows プラットフォーム ツールをインストールする場合は、ARM コードをビルドする 32 ビットおよび 64 ビット ネイティブ ツールがインストールされます。 その他のワークロードでは、その他のツールをインストールできます。

## <a name="developer-command-prompt-shortcuts"></a>開発者コマンド プロンプト ショートカット

コマンド プロンプトのショートカットは、[スタート] メニューで、バージョン固有の Visual Studio フォルダーにインストールされます。 基本のコマンド プロンプトのショートカットとサポートするビルド アーキテクチャの一覧を次に示します。

- **開発者コマンド プロンプト**-32 ビット、x86 ネイティブ コードをビルドする 32 ビット x86 ネイティブ ツールを使用する環境を設定します。
- **x86 native Tools コマンド プロンプト**-32 ビット、x86 ネイティブ コードをビルドする 32 ビット x86 ネイティブ ツールを使用する環境を設定します。
- **x64 native Tools コマンド プロンプト**-64 ビット、x64 ネイティブ コードをビルドする 64 ビット、x64 ネイティブ ツールを使用する環境を設定します。
- **x86_x64 Cross Tools コマンド プロンプト**-64 ビット、x64 ネイティブ コードをビルドする 32 ビット x86 ネイティブ ツールを使用する環境を設定します。
- **x64_x86 Cross Tools コマンド プロンプト**-64 ビット、x64 ネイティブ ツールを使用して、32 ビット、x86 ネイティブ コードをビルドするための環境を設定します。

実際のスタート メニュー フォルダーとショートカット名は、1 つを設定した場合をインストールしたら、Visual Studio のバージョンおよびインストール ニックネームによって異なります。 たとえば、Visual Studio 2017 年 1 をインストールした場合とするした、指定したインストール ニックネームの*プレビュー*、開発者コマンド プロンプトのショートカットの名前は**VS 2017 (プレビュー)用開発者コマンドプロンプト**、という名前のフォルダーで**Visual Studio 2017**です。

インストールしている場合、[構築ツールを Visual Studio 2017 の](https://go.microsoft.com/fwlink/p/?linkid=875721)(をも含む Visual Studio 2015 Update 3 のコンパイラ ツールセット) をアーキテクチャ固有のネイティブまたはクロス ツールのオプションがインストールされた開発者コマンド プロンプト、および一般的ないない**開発者コマンド プロンプト**ショートカットです。

<a name="developer_command_prompt"></a>
### <a name="to-open-a-developer-command-prompt-window"></a>開発者コマンド プロンプト ウィンドウを開く

1. デスクトップで、ウィンドウを開く**開始**メニューのおよびを見つけてなど、Visual Studio のバージョンのフォルダーを開き、スクロール**Visual Studio 2017**です。 以前のバージョンの Visual Studio でのショートカットは、というサブフォルダーに**Visual Studio Tools**です。

1. フォルダーで、選択、**開発者コマンド プロンプト**Visual Studio のバージョンにします。 このショートカットは、アーキテクチャを使用する、既定ビルド ツールの 32 ビット、x86 ネイティブの 32 ビット、x86 ネイティブ コードをビルドする開発者コマンド プロンプト ウィンドウを起動します。 既定ではないビルド アーキテクチャを使用する場合は、ネイティブのいずれかを選択またはクロス ツール コマンド プロンプトをホストとターゲット アーキテクチャを指定します。

開発者コマンド プロンプト ウィンドウを開くに高速の方法は、入力する*開発者コマンド プロンプト*デスクトップ検索 ボックスで、目的の結果を選択し、します。

## <a name="developer-command-files-and-locations"></a>開発者コマンド ファイルと場所

既存のコマンド プロンプト ウィンドウで、アーキテクチャのビルド環境を設定する場合は、必要な環境を設定するコマンド ファイル (バッチ ファイル) のいずれかがインストーラーによって作成されたを使用できます。 のみをお勧めする、新しいコマンド プロンプト ウィンドウでこれを行うし、しないようにお勧めする同じコマンド ウィンドウでそれ以降のスイッチ環境。 これらのファイルの場所をインストールしたら、Visual Studio のバージョンおよび場所と名前付けの選択肢のインストール時に行われたによって異なります。 Visual Studio 2017、64 ビット コンピューター上の標準的なインストール場所は \Program Files (x86) \Microsoft Visual Studio\2017 で\\*エディション*ここで、*エディション*コミュニティがあります。Professional、Enterprise、BuildTools、または別の名前を入力します。 Visual Studio 2015 では、標準的なインストール場所は \Program Files (x86) \Microsoft Visual Studio 14.0 です。

プライマリの開発者コマンド プロンプト コマンドのファイル、VsDevCmd.bat、は、common7 \tools のインストール ディレクトリのサブディレクトリにあります。 パラメーターが指定されていない、環境を設定し、ホストとターゲットのビルド ツールを使用して、32 ビット x86 ネイティブ 32 ビット x86 をビルドするアーキテクチャとコード。

追加のコマンド ファイルは、プロセッサ アーキテクチャと Visual Studio のワークロードとインストールしたオプションに応じて、特定のビルド アーキテクチャを設定します。 Visual Studio 2017 でこれらは、VC\Auxiliary\Build、Visual Studio インストール ディレクトリのサブディレクトリにあります。 Visual Studio 2015 では、これらに VC、vc \bin、または vc \bin\\*アーキテクチャ*インストール ディレクトリのサブディレクトリを*アーキテクチャ*はネイティブの 1 つまたはクロス コンパイラ オプションです。 これらのコマンド ファイルは、既定のパラメーターを設定し、指定したビルド アーキテクチャ環境をセットアップする VsDevCmd.bat を呼び出します。 標準的なインストールには、これらのコマンド ファイルが含まれます。

|コマンド ファイル|ホストとターゲットのアーキテクチャ|
|---|---|
|**vcvars32.bat**| ツールを使用して、32 ビット x86 ネイティブ 32 ビット x86 をビルドするコードです。|
|**vcvars64.bat**| ツールを使用して、64 ビット x64 ネイティブ 64 ビット x64 をビルドするコードです。|
|**vcvarsx86_amd64.bat**| 32 ビット x86 ネイティブ クロス ツールを使用して、64 ビット x64 をビルドするコードです。|
|**vcvarsamd64_x86.bat**| 64 ビット x64 ネイティブ クロス ツールを使用して、32 ビット x86 をビルドするコードです。|
|**vcvarsx86_arm.bat**| ARM コードをビルドするのにには、32 ビット x86 ネイティブ クロス ツールを使用します。|
|**vcvarsamd64_arm.bat**| ARM コードをビルドするのにには、64 ビット x64 ネイティブ クロス ツールを使用します。|
|**vcvarsall.bat**| パラメーターを使用すると、ホストとターゲット アーキテクチャに加え、SDK とプラットフォームのオプションを指定します。 サポートされているオプションの一覧を使用して呼び出して、 **/help**パラメーター。|

> [!CAUTION]
> Vcvarsall.bat ファイルとその他の Visual Studio のコマンド ファイルには、コンピューターが異なります。 vcvarsall.bat ファイルが見つからない場合や破損している場合でも、別のコンピューターのファイルを使用して置き換えないでください。 見つからないファイルを置換する Visual Studio インストーラーを再実行します。
>
> vcvarsall.bat ファイルは、バージョンによっても異なります。 現在のバージョンの Visual Studio が Visual Studio の以前のバージョンは、コンピューターにインストールされている場合は実行されません vcvarsall.bat または別の Visual Studio のコマンド ファイルから別のバージョンの同じコマンド プロンプト ウィンドウ。

## <a name="use-the-developer-tools-in-an-existing-command-window"></a>開発者ツールを使用して、既存のコマンド ウィンドウ

既存のコマンド ウィンドウで、特定のビルドのアーキテクチャを指定する最も簡単な方法では、vcvarsall.bat ファイルを使用します。 Vcvarsall.bat を使用してネイティブの 32 ビットまたは 64 ビット コンパイル用または x86、x64、または ARM プロセッサ; にクロス コンパイルのコマンドラインを構成する環境変数を設定することができます。Microsoft Store、ユニバーサル Windows プラットフォーム、または Windows デスクトップ プラットフォームを対象とする使用するには、どの Windows SDK の指定プラットフォーム ツールセットのバージョンを指定します。 Vcvarsall.bat が x86 の現在の 32 ビット ネイティブ コンパイラを使用するための環境変数を構成する引数が指定されていない場合 Windows デスクトップのターゲットです。 ただし、ネイティブのまたはクロス コンパイラ ツールを構成するのには使用できます。 コンパイラ構成がインストールされていないまたはビルド コンピューターのアーキテクチャ上で利用できることを指定すると、エラー メッセージが表示されます。

### <a name="vcvarsall-syntax"></a>vcvarsall 構文

> **vcvarsall.bat** [*architecture*] [*platform_type*] [*winsdk_version*] [**-vcvars_ver=**_vcversion_]

*architecture*<br/>
この省略可能な引数は、使用するホストとターゲット アーキテクチャを指定します。 場合*アーキテクチャ*が指定されていない、既定のビルド環境を使用します。 これらの引数がサポートされています。

|*architecture*|コンパイラ|ホスト コンピューターのアーキテクチャ|ビルド出力 (ターゲット) のアーキテクチャ|
|----------------------------|--------------|----------------------------------|-------------------------------|
|**x86**|x86 32 ビット ネイティブ|x86、x64|x86|
|**x86\_amd64**または**x86\_x64**|on x86 クロス x64|x86、x64|X64|
|**x86_arm**|ARM on x86 クロス|x86、x64|ARM|
|**x86_arm64**|ARM64 on x86 クロス|x86、x64|ARM64|
|**amd64**または**x64**|x64 64 ビット ネイティブ|X64|X64|
|**amd64\_x86**または**x64\_x86**|x64 で x86 クロスします。|X64|x86|
|**amd64\_arm**または**x64\_arm**|ARM on x64 クロス|X64|ARM|
|**amd64\_arm64**または**x64\_arm64**|X64 クロス ARM64|X64|ARM64|

*platform_type*<br/>
この省略可能な引数を指定できます。**格納**または**uwp** 、プラットフォームの種類として。 既定では、デスクトップまたはコンソール アプリをビルドする環境が設定されます。

*winsdk_version*<br/>
使用する Windows SDK のバージョンを指定します。 既定では、最新インストールされている Windows SDK を使用します。 Windows SDK のバージョンを指定することができますなど使用する完全 Windows 10 SDK 番号**10.0.10240.0**、または指定**8.1** Windows 8.1 SDK を使用します。

*vcversion*<br/>
必要に応じて、Visual Studio コンパイラ ツールセットを使用するを指定します。 既定では、環境は、現在の Visual Studio 2017 コンパイラ ツールセットを使用する設定します。 使用して **-vcvars_ver = 14.0**を Visual Studio 2015 コンパイラ ツールセットを指定します。

<a name="vcvarsall"></a>
#### <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a>既存のコマンド プロンプト ウィンドウで、ビルド環境をセットアップするには

1. コマンド プロンプトで、Visual Studio インストール ディレクトリに変更する CD コマンドを使用します。 次に、構成に固有のコマンド ファイルを含むサブディレクトリに変更する CD をもう一度使用します。 Visual Studio 2017、これは VC\Auxiliary\Build サブディレクトリです。 Visual Studio 2015 では、VC サブディレクトリを使用します。

1. 優先の開発環境内のコマンドを入力します。 たとえば、最新の Windows SDK と Visual Studio 2017 RTM コンパイラ ツールセットを使用して、64 ビット プラットフォームでの UWP の ARM コードをビルドするには、このコマンドラインを使用します。

   `vcvarsall.bat amd64_arm uwp -vcvars_ver=14.10`

## <a name="create-your-own-command-prompt-shortcut"></a>コマンド プロンプト ショートカットを作成します。

既存の開発者コマンド プロンプト ショートカットのいずれかのプロパティ ダイアログ ボックスを開くと場合、は、使用されるコマンドのターゲットを表示できます。 たとえば、ターゲットを**x64 VS 2017 用の Native Tools コマンド プロンプト**ショートカットは、以下のように。

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvars64.bat"`

アーキテクチャに固有のバッチ ファイルのセット、*アーキテクチャ*パラメーターと呼び出し vcvarsall.bat を実行します。 Vcvarsall.bat に渡す場合や、vcvarsall.bat を直接呼び出すことができますのみ、これらのバッチ ファイルを同じ追加のオプションを渡すことができます。 コマンドのショートカットのパラメーターを指定するには、二重引用符で囲まれたコマンドの末尾に追加します。 たとえば、最新の Windows SDK と Visual Studio 2017 RTM コンパイラ ツールセットを使用して、64 ビット プラットフォームでの UWP ARM コードをビルドするショートカットを設定するを使用してこのコマンドの対象のようなものショートカットに。

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvarsall.bat amd64_arm uwp -vcvars_ver=14.10"`

Visual Studio インストール ディレクトリを反映するようにパスを調整する必要があります。

## <a name="command-line-tools"></a>コマンド ライン ツール

コマンドラインで C/C++ プロジェクトを作成するには、Visual Studio には、これらのコマンド ライン ツールが用意されています。

[CL](../build/reference/compiling-a-c-cpp-program.md)<br/>
コンパイラ (cl.exe) は、ソース コード ファイルをアプリ、ライブラリ、および DLL にコンパイルおよびリンクするために使用します。

[リンク](../build/reference/linking.md)<br/>
リンカー (link.exe) は、コンパイルされたオブジェクト ファイルおよびライブラリをアプリおよび DLL にリンクするために使用します。

[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)<br/>
MSBuild (msbuild.exe) を使用すると、Visual C プロジェクトおよび Visual Studio ソリューションを構築できます。 これは、実行中に、**ビルド**プロジェクトまたは**ソリューションのビルド**Visual Studio IDE でコマンド。

[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)<br/>
DEVENV (devenv.exe) を使用するコマンド ライン スイッチと組み合わせて使用 — たとえば、 **/build**または **/clean**: Visual Studio IDE を表示せずにコマンドをビルドを実行する特定します。

[(NMAKE の)](../build/nmake-reference.md)<br/>
NMAKE (nmake.exe) を使用すると、従来のメイクファイルを使用して Visual C プロジェクトをビルドするタスクを自動化できます。

コマンドラインでビルドするときに F1 コマンドはインスタント ヘルプを使用できません。 代わりに、警告、エラー、およびメッセージに関する情報を取得する検索エンジンを使用することができますか、オフラインのヘルプ ファイルを使用することができます。 検索を使用する[docs.microsoft.com](https://docs.microsoft.com/cpp/)ページの上部にある検索ボックスに検索文字列を入力します。

## <a name="in-this-section"></a>このセクションの内容

ドキュメントのこのセクションの記事では、コマンド ラインでアプリをビルドする方法を示し、64 ビット ツールセットを使用して x86、x64、および ARM プラットフォームを対象とするように、コマンド ライン ビルド環境をカスタマイズする方法について説明し、コマンド ライン ビルド ツール MSBuild および NMAKE を使用する方法を示します。

[チュートリアル: コマンド ラインでのネイティブ C++ プログラムのコンパイル](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)<br/>
コマンド ラインで単純な C++ プログラムを作成およびコンパイルする方法を示す例があります。

[チュートリアル: コマンドラインでの C プログラムをコンパイルします。](../build/walkthrough-compile-a-c-program-on-the-command-line.md)<br/>
C プログラミング言語で書かれたプログラムをコンパイルする方法について説明します。

[チュートリアル: コマンド ラインでの C++/CLI プログラムのコンパイル](../build/walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)<br/>
.NET Framework を使用する C++/CLI プログラムを作成およびコンパイルする方法について説明します。

[チュートリアル: コマンド ラインでの C++/CX プログラムのコンパイル](../build/walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)<br/>
Windows ランタイムを使用する C++/CX プログラムを作成およびコンパイルする方法について説明します。

[コマンド ライン ビルドのパスと環境変数の設定](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)<br/>
ターゲットとする x86、x64、コマンド ライン ビルドの設定および ARM プラットフォームを 32 ビットまたは 64 ビット ツールセットを使用して必要な環境変数を持つコマンド プロンプト ウィンドウを起動する方法について説明します。

[NMAKE リファレンス](../build/nmake-reference.md)<br/>
NMAKE.EXE (Microsoft Program Maintenance Utility) について説明する記事へのリンクがあります。

[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)<br/>
MSBuild.EXE の使用方法について説明する記事へのリンクがあります。

## <a name="related-sections"></a>関連項目

[/MD、/MT、/LD (ランタイム ライブラリの使用)](../build/reference/md-mt-ld-use-run-time-library.md)<br/>
デバッグ バージョンまたはリリース バージョンのランタイム ライブラリを使用するための、コンパイラ オプションの使用方法について説明します。

[C/C++ コンパイラ オプション](../build/reference/compiler-options.md)<br/>
C と C++ のコンパイラ オプションおよび CL.exe に関する記事へのリンクがあります。

[リンカー オプション](../build/reference/linker-options.md)<br/>
リンカー オプションおよび LINK.exe に関する記事へのリンクがあります。

[C/C++ のビルド ツール](../build/reference/c-cpp-build-tools.md)<br/>
C と C++ へのリンクは、Visual Studio に含まれているツールをビルドを提供します。

## <a name="see-also"></a>関連項目

[C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)