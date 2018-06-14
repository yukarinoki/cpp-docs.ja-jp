---
title: ビルドのコマンドとプロパティの共通マクロ | Microsoft Docs
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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339632"
---
# <a name="common-macros-for-build-commands-and-properties"></a>ビルドのコマンドとプロパティの共通マクロ
インストール オプションによっては、Visual Studio で何百ものマクロが使用できるようになります。 これらは、既定で設定されている MSBuild プロパティ、.props または .targets ファイル内の MSBuild プロパティ、またはお使いのプロジェクトの設定内にある MSBuild プロパティに対応しています。 次のマクロは、プロジェクトの **[プロパティ ページ]** ダイアログ ボックス内の、文字列を入力できるどの場所にも使用できます。 これらのマクロの大文字と小文字は区別されません。  
  
 現在使用可能なマクロを表示するには、プロパティ名の右側の列で、ドロップダウン矢印をクリックします。 **[編集]** が使用可能な場合は、[編集] をクリックし、編集ダイアログ ボックスで **[マクロ]** をクリックします。 詳細については、「 **Property Pages (C++)** 」の「 [[プロパティ ページ]](../ide/property-pages-visual-cpp.md)をクリックします。  
  
 "非推奨" とマークされたマクロは使用できないか、同等の [項目メタデータ マクロ](/visualstudio/msbuild/itemmetadata-element-msbuild) (**%(***name***)**) と置き換えられています。 "非推奨。移行済みです" とマークされたマクロも使用できません。 さらに、そのマクロを含むプロジェクトが Visual Studio 2008 から移行された場合、Visual Studio はそのマクロを同等の現在のマクロに変換します。  
  
 次の表では、使用可能なマクロの一般的に使用されるサブセットについて説明します。 このリストは完全ではありません。 MSBuild プロパティ定義がどのように作成され、.props、.targets、および .vcxproj ファイル内でマクロとして使用されるかについて詳しくは、「[MSBuild プロパティ](/visualstudio/msbuild/msbuild-properties)」を参照してください。  
  
|マクロ|説明|  
|-----------|-----------------|  
|**$(RemoteMachine)**|[デバッグ] プロパティ ページで **Remote Machine** プロパティの値を設定します。 詳細については、「 [C または C++ デバッグ構成のプロジェクト設定](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration) 」を参照してください。|  
|**$(Configuration)**|現在のプロジェクト構成の名前 ("Debug" など)。|  
|**$(Platform)**|現在のプロジェクト プラットフォームの名前 (例: "Win32") です。|  
|**$(ParentName)**|(非推奨)このプロジェクト項目を含む項目の名前です。 これは、親フォルダー名またはプロジェクト名になります。|  
|**$(RootNameSpace)**|アプリケーションを含む名前空間 (定義されている場合) です。|  
|**$(IntDir)**|中間ファイルに指定されたディレクトリへのパスです。 これが相対パスの場合、中間ファイルはこのパスを通じてプロジェクト ディレクトリに追加されます。 このパスの末尾にはスラッシュが必要です。 これは **Intermediate Directory** プロパティの値に解決されます。 **$(OutDir)** を使用して、このプロパティを定義しないでください。|  
|**$(OutDir)**|出力ファイルのディレクトリへのパスです。 これが相対パスの場合、出力ファイルはこのパスを通じてプロジェクト ディレクトリに追加されます。 このパスの末尾にはスラッシュが必要です。 これは **Output Directory** プロパティの値に解決されます。 **$(IntDir)** を使用して、このプロパティを定義しないでください。|  
|**$(DevEnvDir)**|Visual Studio のインストール ディレクトリ (ドライブ + パスで定義) です。最後に円記号 (\\) が含まれます。|  
|**$(InputDir)**|(非推奨。移行済みです。)入力ファイルのディレクトリ (ドライブ + パスで定義) です。最後に円記号 (\\) が含まれます。 プロジェクトが入力の場合、このマクロは **$(ProjectDir)** と同等です。|  
|**$(InputPath)**|(非推奨。移行済みです。)入力ファイルの絶対パス名 (ドライブ + パス + 基本名 + ファイル拡張子で定義) です。 プロジェクトが入力の場合、このマクロは **$(ProjectPath)** と同等です。|  
|**$(InputName)**|(非推奨。移行済みです。)入力ファイルの基本名です。 プロジェクトが入力の場合、このマクロは **$(ProjectName)** と同等です。|  
|**$(InputFileName)**|(非推奨。移行済みです。)入力ファイルの名前 (基本名 + ファイル拡張子で定義) です。 プロジェクトが入力の場合、このマクロは **$(ProjectFileName)** と同等です。|  
|**$(InputExt)**|(非推奨。移行済みです。)入力ファイルのファイル拡張子。 ファイル拡張子の前にピリオド '.' が付きます。 プロジェクトが入力の場合、このマクロは **$(ProjectExt)** と同等です。|  
|**$(ProjectDir)**|プロジェクトのディレクトリ (ドライブ + パスで定義) です。最後に円記号 (\\) が含まれます。|  
|**$(ProjectPath)**|プロジェクトの絶対パス名 (ドライブ + パス + 基本名 + ファイル拡張子で定義) です。|  
|**$(ProjectName)**|プロジェクトの基本名です。|  
|**$(ProjectFileName)**|プロジェクトのファイル名 (基本名 + ファイル拡張子で定義) です。|  
|**$(ProjectExt)**|プロジェクトのファイル拡張子。 ファイル拡張子の前にピリオド '.' が付きます。|  
|**$(SolutionDir)**|ソリューションのディレクトリ (ドライブ + パスで定義) です。最後に円記号 (\\) が含まれます。 IDE でソリューションをビルドする場合にのみ定義されます。|  
|**$(SolutionPath)**|ソリューションの絶対パス名 (ドライブ + パス + 基本名 + ファイル拡張子で定義) です。 IDE でソリューションをビルドする場合にのみ定義されます。|  
|**$(SolutionName)**|ソリューションの基本名です。 IDE でソリューションをビルドする場合にのみ定義されます。|  
|**$(SolutionFileName)**|ソリューションのファイル名 (基本名 + ファイル拡張子で定義) です。 IDE でソリューションをビルドする場合にのみ定義されます。|  
|**$(SolutionExt)**|ソリューションのファイル拡張子です。 ファイル拡張子の前にピリオド '.' が付きます。 IDE でソリューションをビルドする場合にのみ定義されます。|  
|**$(TargetDir)**|ビルドのプライマリ出力ファイルのディレクトリ (ドライブ + パスで定義) です。最後に円記号 (\\) が含まれます。|  
|**$(TargetPath)**|ビルドのプライマリ出力ファイルの絶対パス名 (ドライブ + パス + 基本名 + ファイル拡張子で定義) です。|  
|**$(TargetName)**|ビルドのプライマリ出力ファイルの基本名です。|  
|**$(TargetFileName)**|ビルドのプライマリ出力ファイルの名前 (基本名 + ファイル拡張子で定義) です。|  
|**$(TargetExt)**|ビルドのプライマリ出力ファイルのファイル拡張子。 ファイル拡張子の前にピリオド '.' が付きます。|  
|**$(VSInstallDir)**|Visual Studio をインストールしたディレクトリです。<br /><br /> このプロパティにはターゲットの Visual Studio のバージョンが含まれますが、ホストの Visual Studio とは異なることがあります。 たとえば、 `$(PlatformToolset) = v110`を設定してビルドした場合、 **$(VSInstallDir)** には Visual Studio 2012 インストールへのパスが含まれます。|  
|**$(VCInstallDir)**|Visual C++ をインストールしたディレクトリです。<br /><br /> このプロパティにはターゲットの Visual C++ のバージョンが含まれますが、ホストの Visual C++ とは異なることがあります。 たとえば、`$(PlatformToolset) = v140` を設定してビルドした場合、**$(VCInstallDir)** には Visual C++ 2015 インストールへのパスが含まれます。|  
|**$(FrameworkDir)**|.NET Framework をインストールしたディレクトリです。|  
|**$(FrameworkVersion)**|Visual Studio が使用する .NET Framework のバージョンです。 **$(FrameworkDir)** と組み合わせると、Visual Studio が使用する .NET Framework のバージョンへの完全なパスになります。|  
|**$(FrameworkSDKDir)**|.NET Framework をインストールしたディレクトリです。 .NET Framework は、Visual Studio 一部としてインストールされている場合も、個別にインストールされている場合もあります。|  
|**$(WebDeployPath)**|Web 配置のルートから、プロジェクト出力が存在するディレクトリへの相対パスです。 <xref:Microsoft.VisualStudio.VCProjectEngine.VCWebDeploymentTool.RelativePath%2A>と同じ値を返します。|  
|**$(WebDeployRoot)**|**\<localhost>** への絶対パスです。 たとえば、c:\inetpub\wwwroot などです。|  
|**$(SafeParentName)**|(非推奨)有効な名前形式で指定された、直接の親の名前です。 たとえば、フォームは .resx ファイルの親です。|  
|**$(SafeInputName)**|(非推奨)有効なクラス名としてのファイル名です。ファイル拡張子は除きます。|  
|**$(SafeRootNamespace)**|(非推奨)プロジェクト ウィザードでコードが追加される名前空間の名前です。 この名前空間名には、有効な C++ 識別子で許可される文字列だけが含まれます。|  
|**$(FxCopDir)**|fxcop.cmd ファイルへのパスです。 fxcop.cmd ファイルは、Visual C++ のすべてのエディションでインストールされるとは限りません。|  
  
## <a name="see-also"></a>参照  
 [Visual Studio での C++ プロジェクトのビルド](../ide/building-cpp-projects-in-visual-studio.md)