---
title: コマンドラインで C/C++ コードをビルドします。
ms.custom: conceptual
ms.date: 06/21/2018
helpviewer_keywords:
- command-line builds [C++]
- compiling source code [C++], command line
- builds [C++], command-line
- command line [C++], building from
- command line [C++], compilers
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
ms.openlocfilehash: bc5080ff14cf8629c98077bf1e3e39e4b824b48b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452040"
---
# <a name="build-cc-code-on-the-command-line"></a>コマンドラインで C/C++ コードをビルドします。

Visual Studio に含まれているツールを使用して、コマンドラインでの C および C++ のアプリケーションを構築できます。

## <a name="how-to-get-the-command-line-tools"></a>コマンド ライン ツールを取得する方法

Visual Studio インストーラーで C++ のワークロードのいずれかを選択すると、Visual Studio がインストールされます*プラットフォーム ツールセット*します。 プラットフォーム ツールセットには、C と C++ コンパイラ、リンカー、アセンブラー、およびその他のビルド ツールだけでなく、一致するライブラリを含む特定の Visual Studio バージョンをすべての C および C++ ツールがあります。 これらすべてのツールを使用するには、コマンドラインでと、Visual Studio IDE で内部的に使用されることもできます。 個別の x86 でホストされているし、x64 でホストされているコンパイラおよび x86、x64、ARM 用にコードを構築するためのツールと ARM64 ターゲットがあります。 特定のホストとターゲットのビルド アーキテクチャ用のツールの各セットは、独自のディレクトリに格納されます。

正常に機能するには、ツールはいくつかの特定の環境変数を設定する必要があります。 これらは、パスに追加して、設定に使用されますファイル、ライブラリ ファイル、および SDK の場所が含まれます。 インストーラーによりカスタマイズされた、簡単にこれらの環境変数を設定する*コマンド ファイル*インストール時にバッチ ファイル、または。 特定のホストとターゲットのビルドのアーキテクチャ、Windows SDK のバージョン、ターゲット プラットフォーム、およびプラットフォーム ツールセットを設定するコマンド プロンプト ウィンドウで、これらのコマンド ファイルのいずれかを行うことができます。 便宜上、インストーラーも作成します。 ショートカットで、[スタート] メニュー (または Windows のスタート ページ 8.x) すべての必要な環境変数が設定され、すぐに使用するために、これらのコマンド ファイルを使用して、開発者コマンド プロンプト ウィンドウを起動します。

必要な環境変数に、ビルドのアーキテクチャを選択し、製品の更新プログラムやアップグレードによって変更される可能性が、インストールに固有です。 そのため、インストールされているコマンド プロンプト ショートカットまたはコマンド ファイルのいずれかを自分で Windows の環境変数を設定する代わりに使用することを強くお勧めします。 詳細については、次を参照してください。[コマンド ライン ビルドのパスと環境変数を設定する](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)します。

コマンド ライン ツールセットやコマンド ファイルは、インストールされているコマンド プロンプトのショートカットは、コンピューターのプロセッサとのインストール時に選択したオプションによって異なります。 少なくとも 32 ビット x86 ネイティブ コードのビルドし、64 ビット x64 ネイティブ コードのビルド ツールを通過する 32 ビット x86 でホストされたツールがインストールされます。 64 ビット Windows の場合は、64 ビット ネイティブ コードをビルドして、32 ビット ネイティブ コードのビルド ツールをクロス 64 ビット x64 でホストされたツールもインストールされます。 省略可能な C++ ユニバーサル Windows プラットフォーム ツールをインストールするように選択すると、ARM コードをビルドする 32 ビットおよび 64 ビットのネイティブ ツールはインストールされます。 その他のワークロードには、その他のツールをインストールできます。

## <a name="developer-command-prompt-shortcuts"></a>開発者コマンド プロンプト ショートカット

コマンド プロンプトのショートカットは、[スタート] メニューで、バージョン固有の Visual Studio フォルダーにインストールされます。 基本のコマンド プロンプトのショートカットとサポートされるビルドのアーキテクチャの一覧を次に示します。

- **開発者コマンド プロンプト**-32 ビットの x86 ネイティブ ツールを使用して、32 ビットの x86 ネイティブ コードを構築する環境を設定します。
- **x86 native Tools コマンド プロンプト**-32 ビットの x86 ネイティブ ツールを使用して、32 ビットの x86 ネイティブ コードを構築する環境を設定します。
- **x64 native Tools コマンド プロンプト**-64 ビットの x64 ネイティブ ツールを使用して、64 ビットの x64 ネイティブ コードを構築する環境を設定します。
- **x86_x64 Cross Tools コマンド プロンプト**-32 ビットの x86 ネイティブ ツールを使用して、64 ビットの x64 ネイティブ コードを構築する環境を設定します。
- **x64_x86 Cross Tools コマンド プロンプト**-64 ビットの x64 ネイティブ ツールを使用して、32 ビットの x86 ネイティブ コードを構築する環境を設定します。

実際のスタート メニュー フォルダーとショートカット名は、1 つを設定した場合、インストールすると、Visual Studio のバージョンとインストールのニックネームによって異なります。 例では、Visual Studio 2017 がインストールされている必要がある場合のしただインストール ニックネームの*プレビュー*、開発者コマンド プロンプトのショートカットの名前は**開発者コマンド プロンプト for VS 2017 (プレビュー)**、という名前のフォルダーで**Visual Studio 2017**します。

インストールした場合、 [Build Tools for Visual Studio 2017](https://go.microsoft.com/fwlink/p/?linkid=875721) (これも含む、Visual Studio 2015 Update 3 のコンパイラ ツールセット) で、アーキテクチャ固有のネイティブまたはクロス ツールの開発者コマンド プロンプトのインストール オプション、および一般的ないない**開発者コマンド プロンプト**ショートカット。

<a name="developer_command_prompt"></a>
### <a name="to-open-a-developer-command-prompt-window"></a>開発者コマンド プロンプト ウィンドウを開く

1. デスクトップで開き、Windows**開始**メニューのおよび下へスクロールを検索してなど、Visual Studio のバージョンのフォルダーを開く**Visual Studio 2017**します。 いくつか以前のバージョンの Visual Studio で、ショートカットはというサブフォルダーに、 **Visual Studio Tools**します。

1. フォルダーで、選択、**開発者コマンド プロンプト**Visual Studio のバージョンにします。 このショートカットは、32 ビットの x86 ネイティブ コードをビルドする 32 ビットの x86 ネイティブ ツールの既定のビルドのアーキテクチャを使用する開発者コマンド プロンプト ウィンドウを起動します。 既定以外のビルド アーキテクチャ場合は、ネイティブのいずれかを選択またはクロス ツール コマンド プロンプトをホストおよびターゲット アーキテクチャを指定します。

開発者コマンド プロンプト ウィンドウを開き、さらに高速の方法は、入力する*開発者コマンド プロンプト*デスクトップ検索ボックスで、目的の結果を選択します。

## <a name="developer-command-files-and-locations"></a>開発者コマンド ファイルと場所

既存のコマンド プロンプト ウィンドウで、アーキテクチャのビルド環境を設定する場合は、必要な環境を設定するインストーラーによって作成されたコマンド ファイル (バッチ ファイル) のいずれかを使用できます。 推奨するだけで新しいコマンド プロンプト ウィンドウでは、これを行うし、お勧めしませんが、同じコマンド ウィンドウで後に環境を切り替えます。 これらのファイルの場所は、インストールすると、Visual Studio のバージョンおよび場所と名前付けの選択肢のインストール中に行われたによって異なります。 Visual Studio 2017 では、64 ビット コンピューター上の一般的なインストール場所は \Program Files (x86) \Microsoft Visual Studio\2017 で\\*edition*ここで、 *edition*コミュニティがあります。Professional、Enterprise、build Tools、または別の名前を指定します。 For Visual Studio 2015 では、一般的なインストール場所は、\Program Files (x86) \Microsoft Visual Studio 14.0 にします。

主な開発者コマンド プロンプトのコマンド ファイルを VsDevCmd.bat は次のインストール ディレクトリの Common7\Tools サブディレクトリにあります。 パラメーターを指定しないと、環境を設定して、ホストとターゲットは、32 ビット x86 ネイティブ ツールを使用して、32 ビット x86 を構築するアーキテクチャを構築コード。

追加のコマンド ファイルは、プロセッサ アーキテクチャと、Visual Studio のワークロードとインストールしたオプションに応じて、特定のビルドのアーキテクチャを設定します。 Visual Studio 2017 では、Visual Studio のインストール ディレクトリの VC\Auxiliary\Build サブディレクトリにあるこれらは。 Visual Studio 2015 では、これらが VC、vc \bin、または vc \bin にあります\\*アーキテクチャ*インストール ディレクトリのサブディレクトリで*アーキテクチャ*はネイティブのいずれかまたは。クロス コンパイラ オプション。 これらのコマンド ファイルは、既定のパラメーターを設定し、指定したビルドのアーキテクチャの環境をセットアップする VsDevCmd.bat を呼び出します。 一般的なインストールでは、これらのコマンド ファイルを含めることができます。

|コマンド ファイル|ホストとターゲット アーキテクチャ|
|---|---|
|**vcvars32.bat**| 32 ビット x86 ネイティブ ツールを使用して、32 ビット x86 ビルド コード。|
|**vcvars64.bat**| 64 ビット x64 ネイティブ ツールを使用して、64 ビット x64 を構築するコードです。|
|**vcvarsx86_amd64.bat**| 32 ビット x86 ネイティブ クロス ツールを使用して、64 ビット x64 を構築するコードです。|
|**vcvarsamd64_x86.bat**| 64 ビット x64 ネイティブ クロス ツールを使用して、32 ビット x86 を構築するコードです。|
|**vcvarsx86_arm.bat**| ARM コードをビルドするのにには、32 ビット x86 ネイティブ クロス ツールを使用します。|
|**vcvarsamd64_arm.bat**| ARM コードをビルドするのにには、64 ビット x64 ネイティブ クロス ツールを使用します。|
|**vcvarsall.bat**| パラメーターを使用すると、ホストとターゲットのアーキテクチャと、SDK とプラットフォームの選択を指定します。 サポートされているオプションの一覧は、呼び出しを使用して、 **/help**パラメーター。|

> [!CAUTION]
> Vcvarsall.bat ファイルとその他の Visual Studio のコマンド ファイルは、コンピューターを変更できます。 vcvarsall.bat ファイルが見つからない場合や破損している場合でも、別のコンピューターのファイルを使用して置き換えないでください。 不足しているファイルを置換する Visual Studio インストーラーを再実行します。
>
> vcvarsall.bat ファイルは、バージョンによっても異なります。 Visual Studio の現在のバージョンは、Visual Studio の以前のバージョンがコンピューターにインストールされて場合から実行しないで vcvarsall.bat または Visual Studio コマンドのもう 1 つのファイルと同じコマンド プロンプト ウィンドウで、さまざまなバージョン。

## <a name="use-the-developer-tools-in-an-existing-command-window"></a>開発者ツールを使用して既存のコマンド ウィンドウ

既存のコマンド ウィンドウで、特定のビルドのアーキテクチャを指定する最も簡単な方法は、vcvarsall.bat ファイルを使用することです。 Vcvarsall.bat を使用してネイティブの 32 ビットまたは 64 ビットのコンパイルまたは x86、x64、または ARM プロセッサにクロス コンパイル コマンドラインを構成する環境変数を設定することができます。Microsoft Store、ユニバーサル Windows プラットフォーム、または Windows デスクトップ プラットフォームを対象を使用するには、どの Windows SDK を指定するにはプラットフォーム ツールセットのバージョンを指定します。 Vcvarsall.bat が x86 の現在の 32 ビット ネイティブ コンパイラを使用するための環境変数を構成する引数が指定されていない場合は、Windows デスクトップのターゲット。 ただし、ネイティブのまたはクロス コンパイラ ツールのいずれかを構成するのには使用できます。 インストールされていないか、ビルド コンピューターのアーキテクチャでは入手できないコンパイラ構成を指定する場合は、エラー メッセージが表示されます。

### <a name="vcvarsall-syntax"></a>vcvarsall 構文

> **vcvarsall.bat** [*architecture*] [*platform_type*] [*winsdk_version*] [**-vcvars_ver=**_vcversion_]

*architecture*<br/>
この省略可能な引数には、使用するホストとターゲット アーキテクチャを指定します。 場合*アーキテクチャ*が指定されていない、既定のビルド環境を使用します。 これらの引数がサポートされています。

|*architecture*|コンパイラ|ホスト コンピューターのアーキテクチャ|ビルド出力 (ターゲット) のアーキテクチャ|
|----------------------------|--------------|----------------------------------|-------------------------------|
|**x86**|x86 32 ビット ネイティブ|x86、x64|x86|
|**x86\_amd64**または**x86\_x64**|on x86 クロス x64|x86、x64|X64|
|**x86_arm**|ARM on x86 クロス|x86、x64|ARM|
|**x86_arm64**|On x86 クロス ARM64|x86、x64|ARM64|
|**amd64**または**x64**|x64 64 ビット ネイティブ|X64|X64|
|**amd64\_x86**または**x64\_x86**|x64 で x86 クロスします。|X64|x86|
|**amd64\_arm**または**x64\_arm**|ARM on x64 クロス|X64|ARM|
|**amd64\_arm64**または**x64\_arm64**|X64 クロス ARM64|X64|ARM64|

*platform_type*<br/>
この省略可能な引数を指定できます。**格納**または**uwp**プラットフォームの種類として。 既定では、環境は、デスクトップまたはコンソール アプリをビルドに設定されます。

*winsdk_version*<br/>
必要に応じて使用する Windows SDK のバージョンを指定します。 既定では、最新インストールされている Windows SDK が使用されます。 Windows SDK のバージョンを指定するには番号を使用する完全な Windows 10 SDK など**10.0.10240.0**、または指定**8.1** Windows 8.1 の SDK を使用しています。

*vcversion*<br/>
必要に応じて使用する Visual Studio コンパイラ ツールセットを指定します。 既定では、Visual Studio 2017 の現在のコンパイラ ツールセットを使用する環境が設定されます。 使用 **-'-vcvars_ver=14.0' = 14.0** Visual Studio 2015 コンパイラ ツールセットを指定します。

<a name="vcvarsall"></a>
#### <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a>既存のコマンド プロンプト ウィンドウで、ビルド環境を設定するには

1. コマンド プロンプトでは、Visual Studio のインストール ディレクトリに変更する CD コマンドを使用します。 次に、構成に固有のコマンド ファイルを含むサブディレクトリに変更する CD をもう一度使用します。 Visual Studio 2017 では、これは VC\Auxiliary\Build サブディレクトリです。 Visual Studio 2015 では、VC サブディレクトリを使用します。

1. 優先の開発環境のコマンドを入力します。 たとえば、最新の Windows SDK と Visual Studio 2017 RTM のコンパイラ ツールセットを使用して、64 ビット プラットフォームでの UWP の ARM コードを構築するには、このコマンドラインを使用します。

   `vcvarsall.bat amd64_arm uwp -vcvars_ver=14.10`

## <a name="create-your-own-command-prompt-shortcut"></a>コマンド プロンプト ショートカットを作成します。

既存の開発者コマンド プロンプト ショートカットのいずれかのプロパティ ダイアログを開く場合に使用されるコマンドのターゲットを確認できます。 ターゲットなど、 **x64 Native Tools コマンド プロンプト for VS 2017**ショートカットは、以下のようにします。

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvars64.bat"`

アーキテクチャに固有のバッチ ファイルのセット、*アーキテクチャ*vcvarsall.bat のパラメーターを呼び出します。 Vcvarsall.bat にも直接 vcvarsall.bat だけ呼び出すことができます、これらのバッチ ファイルを同じ追加のオプションを渡すことができます。 コマンドのショートカットのパラメーターを指定するには、二重引用符で囲まれたコマンドの末尾に追加します。 たとえば、最新の Windows SDK と Visual Studio 2017 RTM のコンパイラ ツールセットを使用して、64 ビット プラットフォームで UWP の ARM コードをビルドするショートカットを設定するを使用して、コマンド ターゲットはこのようなもののショートカットで。

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvarsall.bat amd64_arm uwp -vcvars_ver=14.10"`

Visual Studio インストール ディレクトリを反映するようにパスを調整する必要があります。

## <a name="command-line-tools"></a>コマンド ライン ツール

コマンドラインで C/C++ プロジェクトを作成するには、Visual Studio は、これらのコマンド ライン ツールを提供します。

[CL](../build/reference/compiling-a-c-cpp-program.md)<br/>
コンパイラ (cl.exe) は、ソース コード ファイルをアプリ、ライブラリ、および DLL にコンパイルおよびリンクするために使用します。

[リンク](../build/reference/linking.md)<br/>
リンカー (link.exe) は、コンパイルされたオブジェクト ファイルおよびライブラリをアプリおよび DLL にリンクするために使用します。

[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)<br/>
MSBuild (msbuild.exe) を使用すると、Visual C プロジェクトと Visual Studio ソリューションを構築できます。 これは、実行中に、**ビルド**プロジェクトまたは**ソリューションのビルド**Visual Studio IDE にコマンド。

[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)<br/>
コマンド ライン スイッチを組み合わせて使用 DEVENV (devenv.exe) — など **/build**または **/clean**: を実行する特定のビルド コマンド、Visual Studio IDE を表示せずします。

[(NMAKE の)](../build/nmake-reference.md)<br/>
NMAKE (nmake.exe) を使用すると、従来のメイクファイルを使用して Visual C プロジェクトをビルドするタスクを自動化できます。

コマンドラインでビルドするときに F1 コマンドはインスタント ヘルプの使用可能なされません。 代わりに、警告、エラー、およびメッセージに関する情報を取得する検索エンジンを使用するか、オフライン ヘルプ ファイルを使用することができます。 検索を使用する[docs.microsoft.com](https://docs.microsoft.com/cpp/)ページの上部にある検索ボックスに検索文字列を入力します。

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
必要な環境変数ターゲット x86、x64、コマンド ライン ビルドの設定し、プラットフォームを 32 ビットまたは 64 ビット ツールセットを使用して ARM を持つコマンド プロンプト ウィンドウを起動する方法について説明します。

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
Visual Studio に含まれているツールをビルドする C と C++ へのリンクを提供します。

## <a name="see-also"></a>関連項目

[C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)