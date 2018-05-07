---
title: ビルドのコマンドとプロパティの共通のマクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
dev_langs:
- C++
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
- SolutionPath macro $(SolutionPath)
ms.assetid: 239bd708-2ea9-4687-b264-043f1febf98b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b94347e48a7b8b134915456c92aea3397f97a1b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="common-macros-for-build-commands-and-properties"></a>ビルドのコマンドとプロパティの共通のマクロ
によっては、インストール オプションでは、Visual Studio できます何百ものマクロを使用できるようにします。 これらは、既定では、または .props または .targets ファイル、またはプロジェクトの設定に設定されている MSBuild プロパティに対応しています。 次のマクロは、プロジェクトの **[プロパティ ページ]** ダイアログ ボックス内の、文字列を入力できるどの場所にも使用できます。 これらのマクロの大文字と小文字は区別されません。  
  
 現在使用可能なマクロを表示するには、プロパティ名の右側の列で、ドロップダウン矢印をクリックします。 **[編集]** が使用可能な場合は、[編集] をクリックし、編集ダイアログ ボックスで **[マクロ]** をクリックします。 詳細については、「 **Property Pages (C++)** 」の「 [[プロパティ ページ]](../ide/property-pages-visual-cpp.md)をクリックします。  
  
 「非推奨」とマークされたマクロは使用されなくまたは同等な置き換え[項目メタデータ マクロ](/visualstudio/msbuild/itemmetadata-element-msbuild)(**%(***名前***)**). "非推奨。移行済みです" とマークされたマクロも使用できません。 さらに、そのマクロを含むプロジェクトが Visual Studio 2008 から移行された場合、Visual Studio はそのマクロを同等の現在のマクロに変換します。  
  
 次の表では、一般的に使用される使用可能なマクロのサブセットについて説明します。 この一覧は完全ではありません。 MSBuild プロパティの定義を作成および .props、.targets、および .vcxproj ファイルでマクロとして使用する方法の詳細については、「 [MSBuild プロパティ](/visualstudio/msbuild/msbuild-properties)です。  
  
|マクロ|説明|  
|-----------|-----------------|  
|**$ (Remotemachine)**|[デバッグ] プロパティ ページで **Remote Machine** プロパティの値を設定します。 詳細については、「 [C または C++ デバッグ構成のプロジェクト設定](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration) 」を参照してください。|  
|**$(Configuration)**|現在のプロジェクト構成の名前 ("Debug" など)。|  
|**$(Platform)**|たとえば、"Win32"現在のプロジェクト プラットフォームの名前。|  
|**$ (Parentname)**|(非推奨)このプロジェクト項目を含む項目の名前です。 これは、親フォルダー名またはプロジェクト名になります。|  
|**$ (Rootnamespace)**|アプリケーションを含む名前空間 (定義されている場合) です。|  
|**$(IntDir)**|中間ファイルに指定されたディレクトリへのパスです。 これが相対パスである場合は、中間ファイルがプロジェクト ディレクトリに追加されます。 このパスに移動します。 このパスの末尾にはスラッシュが必要です。 これは **Intermediate Directory** プロパティの値に解決されます。 **$(OutDir)** を使用して、このプロパティを定義しないでください。|  
|**$(OutDir)**|出力ファイルのディレクトリへのパスです。 これが相対パスの場合、出力ファイルはこのパスを通じてプロジェクト ディレクトリに追加されます。 このパスの末尾にはスラッシュが必要です。 これは **Output Directory** プロパティの値に解決されます。 **$(IntDir)** を使用して、このプロパティを定義しないでください。|  
|**$ (Devenvdir)**|(ドライブ + パスとして定義) です。 Visual Studio のインストール ディレクトリ末尾に円記号を含む '\\' です。|  
|**$ (Inputdir)**|(非推奨。移行済みです。)(ドライブ + パスとして定義) です。 入力ファイルのディレクトリ末尾に円記号を含む '\\' です。 プロジェクトが入力の場合、このマクロは **$(ProjectDir)** と同等です。|  
|**$ (Inputpath)**|(非推奨。移行済みです。)入力ファイルの絶対パス名 (ドライブ + パス + 基本名 + ファイル拡張子で定義) です。 プロジェクトが入力の場合、このマクロは **$(ProjectPath)** と同等です。|  
|**$ (Inputname)**|(非推奨。移行済みです。)入力ファイルの基本名です。 プロジェクトが入力の場合、このマクロは **$(ProjectName)** と同等です。|  
|**$ (Inputfilename)**|(非推奨。移行済みです。)入力ファイルの名前 (基本名 + ファイル拡張子で定義) です。 プロジェクトが入力の場合、このマクロは **$(ProjectFileName)** と同等です。|  
|**$ (Inputext)**|(非推奨。移行済みです。)入力ファイルのファイル拡張子。 ファイル拡張子の前にピリオド '.' が付きます。 プロジェクトが入力の場合、このマクロは **$(ProjectExt)** と同等です。|  
|**$(ProjectDir)**|(ドライブ + パスとして定義) です。 プロジェクトのディレクトリ末尾に円記号を含む '\\' です。|  
|**$(ProjectPath)**|プロジェクトの絶対パス名 (ドライブ + パス + 基本名 + ファイル拡張子で定義) です。|  
|**$(ProjectName)**|プロジェクトの基本名です。|  
|**$(ProjectFileName)**|プロジェクトのファイル名 (基本名 + ファイル拡張子で定義) です。|  
|**$(ProjectExt)**|プロジェクトのファイル拡張子。 ファイル拡張子の前にピリオド '.' が付きます。|  
|**$ (Solutiondir)**|(ドライブ + パスとして定義) です。 ソリューションのディレクトリ末尾に円記号を含む '\\' です。 IDE でソリューションを構築する場合にのみ定義されています。|  
|**$ (Solutionpath)**|ソリューションの絶対パス名 (ドライブ + パス + 基本名 + ファイル拡張子で定義) です。 IDE でソリューションを構築する場合にのみ定義されています。|  
|**$ (Solutionname)**|ソリューションの基本名です。 IDE でソリューションを構築する場合にのみ定義されています。|  
|**$ (Solutionfilename)**|ソリューションのファイル名 (基本名 + ファイル拡張子で定義) です。 IDE でソリューションを構築する場合にのみ定義されています。|  
|**$ (Solutionext)**|ソリューションのファイル拡張子です。 ファイル拡張子の前にピリオド '.' が付きます。 IDE でソリューションを構築する場合にのみ定義されています。|  
|**$ (Targetdir)**|(ドライブ + パスとして定義) です。 ビルドのプライマリ出力ファイルのディレクトリ末尾に円記号を含む '\\' です。|  
|**$ (Targetpath)**|ビルドのプライマリ出力ファイルの絶対パス名 (ドライブ + パス + 基本名 + ファイル拡張子で定義) です。|  
|**$ (Targetname)**|ビルドのプライマリ出力ファイルの基本名です。|  
|**$ (Targetfilename)**|ビルドのプライマリ出力ファイルの名前 (基本名 + ファイル拡張子で定義) です。|  
|**$ (Targetext)**|ビルドのプライマリ出力ファイルのファイル拡張子。 ファイル拡張子の前にピリオド '.' が付きます。|  
|**$(VSInstallDir)**|Visual Studio をインストールしたディレクトリです。<br /><br /> このプロパティにはターゲットの Visual Studio のバージョンが含まれますが、ホストの Visual Studio とは異なることがあります。 たとえば、 `$(PlatformToolset) = v110`を設定してビルドした場合、 **$(VSInstallDir)** には Visual Studio 2012 インストールへのパスが含まれます。|  
|**$(VCInstallDir)**|Visual C++ をインストールしたディレクトリです。<br /><br /> このプロパティにはターゲットの Visual C++ のバージョンが含まれますが、ホストの Visual C++ とは異なることがあります。 たとえば、してビルドした場合`$(PlatformToolset) = v140`、 **$ (vcinstalldir)** Visual C 2015 のインストールへのパスが含まれています。|  
|**$(FrameworkDir)**|.NET Framework をインストールしたディレクトリです。|  
|**$ (Frameworkversion)**|Visual Studio が使用する .NET Framework のバージョンです。 **$(FrameworkDir)** と組み合わせると、Visual Studio が使用する .NET Framework のバージョンへの完全なパスになります。|  
|**$ (Frameworksdkdir)**|.NET Framework をインストールしたディレクトリです。 .NET Framework は、Visual Studio 一部としてインストールされている場合も、個別にインストールされている場合もあります。|  
|**$ (Webdeploypath)**|Web 配置のルートから、プロジェクト出力が存在するディレクトリへの相対パスです。 <xref:Microsoft.VisualStudio.VCProjectEngine.VCWebDeploymentTool.RelativePath%2A>と同じ値を返します。|  
|**$ (Webdeployroot)**|場所への絶対パス **\<localhost >** です。 たとえば、c:\inetpub\wwwroot などです。|  
|**$(SafeParentName)**|(非推奨)有効な名前形式で指定された、直接の親の名前です。 たとえば、フォームは .resx ファイルの親です。|  
|**$(SafeInputName)**|(非推奨)有効なクラス名としてのファイル名です。ファイル拡張子は除きます。|  
|**$ (Saferootnamespace)**|(非推奨)プロジェクト ウィザードでコードが追加される名前空間の名前です。 この名前空間名には、有効な C++ 識別子で許可される文字列だけが含まれます。|  
|**$ (Fxcopdir)**|fxcop.cmd ファイルへのパスです。 fxcop.cmd ファイルは、Visual C++ のすべてのエディションでインストールされるとは限りません。|  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio での C++ プロジェクトのビルド](../ide/building-cpp-projects-in-visual-studio.md)