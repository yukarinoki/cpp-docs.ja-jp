---
title: MSBuild コマンドとプロパティの共通マクロ
ms.date: 03/20/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
helpviewer_keywords:
- $(FrameworkSDKDir) macro
- ProjectName macro $(ProjectName)
- DevEnvDir macro $(DevEnvDir)
- $(DevEnvDir) macro
- TargetPath macro $(TargetPath)
- VSInstallDir macro $(VSInstallDir)
- $(InputFileName) macro
- $(SolutionFileName) macro
- macros [C++], build macros
- InputFileName macro $(InputFileName)
- $(VCInstallDir) macro
- $(IntDir) macro
- $(ConfigurationName) macro
- SolutionDir macro $(SolutionDir)
- $(TargetPath) macro
- $(Inherit) macro
- $(SolutionPath) macro
- WebDeployRoot macro $(WebDeployRoot)
- WebDeployPath macro $(WebDeployPath)
- StopEvaluating macro $(StopEvaluating)
- $(RootNamespace) macro
- $(WebDeployRoot) macro
- ProjectPath macro $(ProjectPath)
- $(ProjectPath) macro
- $(InputDir) macro
- SolutionName macro $(SolutionName)
- ProjectExt macro $(ProjectExt)
- $(TargetExt) macro
- $(ProjectFileName) macro
- TargetName macro $(TargetName)
- $(References) macro
- References macro $(References)
- TargetExt macro $(TargetExt)
- ProjectDir macro $(ProjectDir)
- $(TargetDir) macro
- SolutionExt macro $(SolutionExt)
- $(SolutionDir) macro
- ProjectFileName macro $(ProjectFileName)
- VCInstallDir macro $(VCInstallDir)
- $(InputExt) macro
- $(TargetFileName) macro
- $(SolutionExt) macro
- PlatformName macro $(PlatformName)
- IntDir macro $(IntDir)
- $(FrameworkVersion) macro
- $(ProjectDir) macro
- build macros [C++]
- InputPath macro $(InputPath)
- $(VSInstallDir) macro
- $(WebDeployPath) macro
- TargetFileName macro $(TargetFileName)
- NoInherit macro $(NoInherit)
- ConfigurationName macro $(ConfigurationName)
- $(ProjectExt) macro
- TargetDir macro $(TargetDir)
- InputName macro $(InputName)
- $(ProjectName) macro
- FrameworkSDKDir macro $(FrameworkSDKDir)
- $(ParentName) macro
- InputExt macro $(InputExt)
- $(SafeRootNamespace) macro
- InputDir macro $(InputDir)
- $(FxCopDir) macro
- $(RemoteMachine) macro
- Inherit macro $(Inherit)
- FrameworkVersion macro $(FrameworkVersion)
- $(StopEvaluating) macro
- $(OutDir) macro
- FrameworkDir macro $(FrameworkDir)
- SolutionFileName macro $(SolutionFileName)
- $(NoInherit) macro
- RemoteMachine macro $(RemoteMachine)
- properties [C++], build property macros
- $(TargetName) macro
- $(SolutionName) macro
- $(InputPath) macro
- ParentName macro $(ParentName)
- OutDir macro $(OutDir)
- SafeRootNamespace macro $(SafeRootNamespace)
- FxCopDir macro $(FxCopDir)
- $(InputName) macro
- RootNamespace macro $(RootNamespace)
- builds [C++], macros
- $(FrameworkDir) macro
- $(PlatformName) macro
- $(PlatformShortName) macro
- SolutionPath macro $(SolutionPath)
ms.assetid: 239bd708-2ea9-4687-b264-043f1febf98b
ms.openlocfilehash: 46fdd5e356ded96388a154ff459ef4cc3c02267f
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "58327679"
---
# <a name="common-macros-for-msbuild-commands-and-properties"></a>MSBuild コマンドとプロパティの共通マクロ

に応じて、インストール オプションでは、Visual Studio 利用できる何百ものマクロのする (MSBuild に基づく) Visual Studio プロジェクトにします。 これらは、既定で設定されている MSBuild プロパティ、.props または .targets ファイル内の MSBuild プロパティ、またはお使いのプロジェクトの設定内にある MSBuild プロパティに対応しています。 次のマクロは、プロジェクトの **[プロパティ ページ]** ダイアログ ボックス内の、文字列を入力できるどの場所にも使用できます。 これらのマクロの大文字と小文字は区別されません。

## <a name="view-the-current-properties-and-macros"></a>現在のプロパティとマクロを表示する

現在使用可能なマクロでは、すべてを表示する、**プロパティ ページ**ダイアログで、 **vc++ ディレクトリ**プロパティの行の末尾にあるドロップダウン矢印をクリックします。 をクリックして**編集**し、編集ダイアログ ボックスの 、**マクロ**ボタンをクリックします。 Visual Studio に表示されているプロパティとマクロの現在のセットが、それぞれの現在の値と共に表示されます。 詳細については、次を参照してください。、 **Specifying User-Defined 値**の[C++ プロジェクト プロパティ ページ リファレンス](property-pages-visual-cpp.md)します。

![VC + + マクロ ボタン](../media/vcppdir_libdir_macros.png "マクロ メニュー")

## <a name="list-of-common-macros"></a>一般的なマクロの一覧

このテーブルには、一般的に使用される使用可能なマクロ; のサブセットがについて説明しますこの一覧にないより多くがあります。 移動して、**マクロ**プロパティとその現在の値、プロジェクト内のすべてを表示するダイアログ。 MSBuild プロパティ定義がどのように作成され、.props、.targets、および .vcxproj ファイル内でマクロとして使用されるかについて詳しくは、「[MSBuild プロパティ](/visualstudio/msbuild/msbuild-properties)」を参照してください。

|マクロ|説明|
|-----------|-----------------|
|**$(Configuration)**|現在のプロジェクト構成の名前 ("Debug" など)。|
|**$(DevEnvDir)**|Visual Studio のインストール ディレクトリ (ドライブ + パスで定義) です。最後に円記号 (\\) が含まれます。|
|**$(FrameworkDir)**|.NET Framework をインストールしたディレクトリです。|
|**$(FrameworkSDKDir)**|.NET Framework をインストールしたディレクトリです。 .NET Framework は、Visual Studio 一部としてインストールされている場合も、個別にインストールされている場合もあります。|
|**$(FrameworkVersion)**|Visual Studio が使用する .NET Framework のバージョンです。 **$(FrameworkDir)** と組み合わせると、Visual Studio が使用する .NET Framework のバージョンへの完全なパスになります。|
|**$(FxCopDir)**|fxcop.cmd ファイルへのパスです。 fxcop.cmd ファイルは、Visual C++ のすべてのエディションでインストールされるとは限りません。|
|**$(IntDir)**|中間ファイルに指定されたディレクトリへのパスです。 これが相対パスの場合、中間ファイルはこのパスを通じてプロジェクト ディレクトリに追加されます。 このパスの末尾にはスラッシュが必要です。 これは **Intermediate Directory** プロパティの値に解決されます。 **$(OutDir)** を使用して、このプロパティを定義しないでください。|
|**$(OutDir)**|出力ファイルのディレクトリへのパスです。 これが相対パスの場合、出力ファイルはこのパスを通じてプロジェクト ディレクトリに追加されます。 このパスの末尾にはスラッシュが必要です。 これは **Output Directory** プロパティの値に解決されます。 **$(IntDir)** を使用して、このプロパティを定義しないでください。|
|**$(Platform)**|現在のプロジェクト プラットフォームの名前 (例: "Win32") です。|
|**$(PlatformShortName)**|たとえば、"x86"または"x64"、現在のアーキテクチャの短い名前。|
|**$(ProjectDir)**|プロジェクトのディレクトリ (ドライブ + パスで定義) です。最後に円記号 (\\) が含まれます。|
|**$(ProjectExt)**|プロジェクトのファイル拡張子。 ファイル拡張子の前にピリオド '.' が付きます。|
|**$(ProjectFileName)**|プロジェクトのファイル名 (基本名 + ファイル拡張子で定義) です。|
|**$(ProjectName)**|プロジェクトの基本名です。|
|**$(ProjectPath)**|プロジェクトの絶対パス名 (ドライブ + パス + 基本名 + ファイル拡張子で定義) です。|
|**$(RemoteMachine)**|[デバッグ] プロパティ ページで **Remote Machine** プロパティの値を設定します。 詳細については、「 [C または C++ デバッグ構成のプロジェクト設定](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration) 」を参照してください。|
|**$(RootNameSpace)**|アプリケーションを含む名前空間 (定義されている場合) です。|
|**$(SolutionDir)**|ソリューションのディレクトリ (ドライブ + パスで定義) です。最後に円記号 (\\) が含まれます。 IDE でソリューションをビルドする場合にのみ定義されます。|
|**$(SolutionExt)**|ソリューションのファイル拡張子です。 ファイル拡張子の前にピリオド '.' が付きます。 IDE でソリューションをビルドする場合にのみ定義されます。|
|**$(SolutionFileName)**|ソリューションのファイル名 (基本名 + ファイル拡張子で定義) です。 IDE でソリューションをビルドする場合にのみ定義されます。|
|**$(SolutionName)**|ソリューションの基本名です。 IDE でソリューションをビルドする場合にのみ定義されます。|
|**$(SolutionPath)**|ソリューションの絶対パス名 (ドライブ + パス + 基本名 + ファイル拡張子で定義) です。 IDE でソリューションをビルドする場合にのみ定義されます。|
|**$(TargetDir)**|ビルドのプライマリ出力ファイルのディレクトリ (ドライブ + パスで定義) です。最後に円記号 (\\) が含まれます。|
|**$(TargetExt)**|ビルドのプライマリ出力ファイルのファイル拡張子。 ファイル拡張子の前にピリオド '.' が付きます。|
|**$(TargetFileName)**|ビルドのプライマリ出力ファイルの名前 (基本名 + ファイル拡張子で定義) です。|
|**$(TargetName)**|ビルドのプライマリ出力ファイルの基本名です。|
|**$(TargetPath)**|ビルドのプライマリ出力ファイルの絶対パス名 (ドライブ + パス + 基本名 + ファイル拡張子で定義) です。|
|**$(VCInstallDir)**|Visual Studio インストールの C++ コンテンツを格納するディレクトリ。 このプロパティにはターゲットの Visual C++ ツールセットのバージョンが含まれますが、ホストの Visual C++ とは異なることがあります。 たとえば、`$(PlatformToolset) = v140` を設定してビルドした場合、**$(VCInstallDir)** には Visual C++ 2015 インストールへのパスが含まれます。|
|**$(VSInstallDir)**|Visual Studio をインストールしたディレクトリです。 このプロパティにはターゲットの Visual Studio ツールセットのバージョンが含まれますが、ホストの Visual C++ とは異なることがあります。 たとえば、 `$(PlatformToolset) = v110`を設定してビルドした場合、 **$(VSInstallDir)** には Visual Studio 2012 インストールへのパスが含まれます。|
|**$(WebDeployPath)**|Web 配置のルートから、プロジェクト出力が存在するディレクトリへの相対パスです。 <xref:Microsoft.VisualStudio.VCProjectEngine.VCWebDeploymentTool.RelativePath%2A>と同じ値を返します。|
|**$(WebDeployRoot)**|**\<localhost>** への絶対パスです。 たとえば、c:\inetpub\wwwroot などです。|

## <a name="obsolete-macros"></a>古いマクロ

C++ のビルド システムは、Visual Studio 2008 と Visual Studio 2010 の間で大幅に変更されました。 以前のプロジェクトの種類で使用されていた多くのマクロは、新しいものに変更されています。 これらのマクロは使用されなくなったか、あるいは 1 つまたは複数の同等のプロパティまたは[項目メタデータ マクロ ](/visualstudio/msbuild/itemmetadata-element-msbuild)(**%(**_名前_**)**) 値に置き換えられました。 "移行済み" とマークされたマクロは、プロジェクトの移行ツールによって更新できます。 そのマクロを含むプロジェクトが Visual Studio 2008 以前から Visual Studio 2010 に移行された場合、Visual Studio はそのマクロを同等の現在のマクロに変換します。 新しいバージョンの Visual Studio は、プロジェクトを Visual Studio 2008 以前から新しいプロジェクトの種類に変換できません。 2 つの手順でこれらのプロジェクトを変換する必要があります。まず Visual Studio 2010 に変換し、Visual Studio の新しいバージョンにその結果を変換します。 詳細については、「[Overview of potential upgrade issues](../../porting/overview-of-potential-upgrade-issues-visual-cpp.md)」 (アップグレードの潜在的な問題の概要) を参照してください。

|マクロ|説明|
|-----------|-----------------|
|**$(InputDir)**|(移行済み)入力ファイルのディレクトリ (ドライブ + パスで定義) です。最後に円記号 (\\) が含まれます。 プロジェクトが入力の場合、このマクロは **$(ProjectDir)** と同等です。|
|**$(InputExt)**|(移行済み)入力ファイルのファイル拡張子。 ファイル拡張子の前にピリオド '.' が付きます。 プロジェクトが入力の場合、このマクロは **$(ProjectExt)** と同等です。 ソース ファイルの場合、これは **%(Extension)** です。|
|**$(InputFileName)**|(移行済み)入力ファイルの名前 (基本名 + ファイル拡張子で定義) です。 プロジェクトが入力の場合、このマクロは **$(ProjectFileName)** と同等です。 ソース ファイルの場合、これは **%(Identity)** です。|
|**$(InputName)**|(移行済み)入力ファイルの基本名です。 プロジェクトが入力の場合、このマクロは **$(ProjectName)** と同等です。 ソース ファイルの場合、これは **%(Filename)** です。|
|**$(InputPath)**|(移行済み)入力ファイルの絶対パス名 (ドライブ + パス + 基本名 + ファイル拡張子で定義) です。 プロジェクトが入力の場合、このマクロは **$(ProjectPath)** と同等です。 ソース ファイルの場合、これは **%(FullPath)** です。|
|**$(ParentName)**|このプロジェクト項目を含む項目の名前です。 これは、親フォルダー名またはプロジェクト名になります。|
|**$(SafeInputName)**|有効なクラス名としてのファイル名です。ファイル拡張子は除きます。 このプロパティには、正確に等しいものはありません。|
|**$(SafeParentName)**|有効な名前形式で指定された、直接の親の名前です。 たとえば、フォームは .resx ファイルの親です。 このプロパティには、正確に等しいものはありません。|
|**$(SafeRootNamespace)**|プロジェクト ウィザードでコードが追加される名前空間の名前です。 この名前空間名には、有効な C++ 識別子で許可される文字列だけが含まれます。 このプロパティには、正確に等しいものはありません。|

## <a name="see-also"></a>関連項目

- [Visual Studio プロジェクト - C++](../creating-and-managing-visual-cpp-projects.md)
- [Visual C++ 移植とアップグレードのガイド](../../porting/visual-cpp-porting-and-upgrading-guide.md)
- [アップグレード時の潜在的な問題の概要](../../porting/overview-of-potential-upgrade-issues-visual-cpp.md)
