---
title: '[全般] プロパティ ページ (プロジェクト) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCConfiguration.IntermediateDirectory
- VC.Project.VCConfiguration.ConfigurationType
- VC.Project.VCConfiguration.ManagedExtensions
- VC.Project.VCConfiguration.BuildBrowserInformation
- VC.Project.VCConfiguration.BuildLogFile
- VC.Project.VCConfiguration.PlatformToolset
- VC.Project.VCConfiguration.TargetName
- VC.Project.VCConfiguration.
- VC.Project.VCConfiguration.TargetExt
- VC.Project.VCConfiguration.ATLMinimizesCRunTimeLibraryUsage
- VC.Project.VCConfiguration.ReferencesPath
- VC.Project.VCConfiguration.DeleteExtensionsOnClean
- VC.Project.VCConfiguration.useOfMfc
- VC.Project.VCConfiguration.CharacterSet
- VC.Project.VCGeneralMakefileSettings.ConfigurationType
- VC.Project.VCConfiguration.OutputDirectory
- VC.Project.VCConfiguration.AppSupport
- VC.Project.VCConfiguration.ToolFiles
- VC.Project.VCConfiguration.useOfATL
dev_langs:
- C++
helpviewer_keywords:
- Clean Build option
- output files, setting directory
- Unicode, creating C++ build configuration
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba98f7d9ed14df1e017f8b83e73cf5d318610f9f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="general-property-page-project"></a>[全般] プロパティ ページ (プロジェクト)

ソリューション エクスプ ローラーでプロジェクト ノードを右クリックし、選択する**プロパティ**、**全般**プロパティ ページ の下、**構成プロパティ**内のノード、左側のウィンドウには、プロパティの 2 つのセクションが表示されます。

- 全般

- プロジェクトの既定値

非 Windows プロジェクトでは、次を参照してください。 [Linux C++ プロパティのページ参照](../linux/prop-pages-linux.md)<!-- or [C++ Cross Platform Property Page Reference](../linux/prop-pages-linux.md)-->です。

## <a name="general"></a>全般

[全般] プロパティに影響を与えるファイルは、ビルド処理で作成されると、ときに削除するファイルの場所、**クリーン**オプション (**ビルド**メニュー) が選択されています。

**ターゲット プラットフォーム**  
プロジェクトが実行されるプラットフォームを指定します。 Windows、Android、または iOS などです。 値**Windows 10**ユニバーサル Windows プラットフォーム プロジェクトのターゲットを意味します。 以前のバージョンの Windows を対象とすると、バージョンが記載されていない、だけで、このフィールドの値が表示されます**Windows**です。 これは、プロジェクトを作成するときに設定される読み取り専用フィールドです。

**Windows SDK のバージョン**  
Windows ターゲット プラットフォームは、プロジェクトを必要とする Windows SDK のバージョンを指定します。 Visual Studio インストーラーを使用して C++ ワークロードをインストールすると、Windows SDK の必要な部分がインストールされます。 をコンピューターに他の Windows SDK バージョンがある場合、ドロップダウン リストにインストールされている SDK ツールの各バージョンが表示されます。

Windows 7 または Windows Vista を対象とする値を使用**8.1**Windows SDK 8.1 はこれらのプラットフォームとの下位互換性のあるのため、します。 さらに、適切な値を定義する必要があります **_WIN32_WINNT** targetver.h にします。 Windows 7 では、これは 0x0601 になります。 参照してください[WINVER および _WIN32_WINNT の変更](../porting/modifying-winver-and-win32-winnt.md)です。

Windows XP および Windows 2003 Server のプロジェクトをビルドし、ライブラリの現在のバージョンを使用する Visual Studio に含まれる Windows XP プラットフォーム ツールセットをインストールすることができます。 詳細を取得して、このプラットフォーム ツールセットを使用する方法については、次を参照してください。 [Windows XP 用プログラムを構成する](../build/configuring-programs-for-windows-xp.md)です。 プラットフォーム ツールセットの変更に関する詳細については、「[方法: ターゲット フレームワークおよびプラットフォームのツールセットを変更する](../build/how-to-modify-the-target-framework-and-platform-toolset.md)」を参照してください。

**ターゲット プラットフォームの最小値。バージョン**  
プロジェクトを実行できるプラットフォームの最小バージョンを指定します。 このプロパティは、Windows ユニバーサル プロジェクトなどのプロジェクトの種類がサポートしている場合のみ表示されます。 アプリが最新の Windows SDK バージョンの機能を利用できるにもかかわらず、おそらく機能の一部が失われているためこれらの機能を使用せずに以前のバージョンで実行している場合、これら 2 つのプロパティの値は異なる可能性があります。 このような場合は、コードで実行時に実行しているプラットフォームのバージョンを確認する必要があります。古いバージョンのプラットフォームでは使用できない機能は使用しないでください。

Visual C++ ではこのオプションを適用しないことに注意してください。 これは、C# や JavaScript など、他の言語との一貫性のため、およびプロジェクトを使用する他のユーザーのガイドとして含められています。  最小バージョンで使用できない機能を使用する場合、Visual C++ ではエラーは生成されません。

**出力ディレクトリ**  
リンカーなどのツールが、ビルド処理で作成されるすべての最終出力ファイルを置くディレクトリを指定します。 通常は、リンカー、ライブラリアン、BSCMake などのツールの出力があります。 既定では、このプロパティは、マクロ $(SolutionDir) $(構成) で指定されたディレクトリ \ です。

プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.OutputDirectory%2A>」を参照してください。

**中間ディレクトリ**  
コンパイラなどのツールが、ビルド処理で作成されるすべての中間ファイルを置くディレクトリを指定します。 通常は、C/C++ コンパイラ、MIDL、リソース コンパイラなどのツールの出力があります。 既定では、このプロパティは、マクロ $(構成) で指定されたディレクトリ \ です。

プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.IntermediateDirectory%2A>」を参照してください。

**ターゲット名**  
このプロジェクトで生成されるファイル名を指定します。 既定では、このプロパティは、マクロ $(ProjectName) で指定されたファイル名です。

**ターゲットの拡張子**  
このプロジェクトで生成されるファイル名拡張子 (.exe、.dll など) を指定します。

**消去時に削除する拡張子**  
**クリーン**オプション (**ビルド**メニュー)、プロジェクトの構成が構成されている中間ディレクトリからファイルを削除します。 このプロパティで指定された拡張子を持つファイルになる時に削除**クリーン**が実行または再構築を実行するとします。 ビルド システムでは、中間ディレクトリでこれらの拡張子を持つファイルのほかに、置かれている場所に関係なく、(.obj ファイルなどの中間出力を含む) 既存のビルドの出力も削除します。 ワイルドカード文字を指定できます。

プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.DeleteExtensionsOnClean%2A>」を参照してください。

**ビルド ログ ファイル**  
プロジェクトをビルドしたときに作成されるログ ファイルの既定の場所を変更できます。 既定の場所は、マクロ $(IntDir) $(MSBuildProjectName) .log によって指定されます。

プロジェクト マクロを使用して、ディレクトリの場所を変更できます。 参照してください[ビルド コマンドとプロパティの一般的なマクロ](../ide/common-macros-for-build-commands-and-properties.md)です。

**プラットフォーム ツールセット**  
プロジェクトの対象を別のバージョンの Visual C++ のライブラリおよびコンパイラにすることができます。 Visual C プロジェクト対象にいずれか、既定のツールセット、Visual Studio または Windowx XP を実行できる実行可能ファイルを作成するツールセットをなど、Visual Studio の以前のバージョンをいくつかでインストールされているツールセットのいずれかでインストールできます。 プラットフォーム ツールセットを変更する方法については、次を参照してください。[する方法: ターゲット フレームワークおよびプラットフォームのツールセットを変更](../build/how-to-modify-the-target-framework-and-platform-toolset.md)です。

**マネージ インクリメンタル ビルドを有効にします。**  
外部の可視性の検出これにより、マネージ プロジェクトにアセンブリを生成します。 マネージ プロジェクトに変更が他のプロジェクトに表示されていない場合は、依存プロジェクトが再構築されますされません。 これにより、マネージ プロジェクトに格納されているソリューションのビルド時間が大幅に向上します。

## <a name="project-defaults"></a>プロジェクトの既定値

[プロジェクトの既定値] セクションのプロパティは、変更できる既定のプロパティを表します。 .Props ファイル内でこれらのプロパティの定義が見つかりません*インストール ディレクトリ*\VC\VCProjectDefaults です。

**構成の種類**  
選択できる構成ファイルの種類は以下のとおりです。

- **アプリケーション (.exe)** リンカーのツールセット (C/C++ コンパイラ、MIDL、リソース コンパイラ、リンカー、BSCMake、XML Web サービス プロキシ ジェネレーター、カスタム ビルド、ビルド、リンク、ビルド後イベント) が表示されます。

- **ダイナミック ライブラリ (.dll)** リンカーのツールセットを表示、/DLL リンカー オプションを指定し、_WINDLL 定義を CL に追加します。

- **メイクファイル**メイクファイルのツールセット (NMake) を表示します。

- **スタティック ライブラリ (.lib)** ライブラリアンのツールセット (リンカーのライブラリアンを置き換えるし、XML Web サービス プロキシ ジェネレーター以外はリンカーのツールセットと同じ) を表示します。

- **ユーティリティ**ユーティリティのツールセット (MIDL、カスタム ビルド、ビルド、ビルド後イベント) を表示します。

プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.ConfigurationType%2A>」を参照してください。

**MFC の使用**  
MFC プロジェクトが MFC DLL に静的にリンクするか動的にリンクするかを指定します。 非 MFC プロジェクトを選択できます**標準 Windows ライブラリを使用して**MFC を使用する場合に含まれているさまざまな Win32 ライブラリにリンクします。

プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfMfc%2A>」を参照してください。

**ATL の使用**  
ATL プロジェクトが ATL .DLL に静的にリンクするか動的にリンクするかを指定します。 指定するもの以外の場合**ATL を使用しない**、定義はコンパイラに追加されます**コマンドライン**プロパティ ページ。

プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfATL%2A>」を参照してください。

**文字セット**  
_UNICODE または _MBCS を設定する必要があるかどうかを定義します。 該当する場合は、リンカーのエントリ ポイントにも影響します。

プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.CharacterSet%2A>」を参照してください。

**共通言語ランタイム サポート**  
により、 [/clr](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションが使用されます。

プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.ManagedExtensions%2A>」を参照してください。

**.NET ターゲット フレームワークのバージョン**  
マネージ プロジェクトでは、対象とする .NET framework バージョンを指定します。

**プログラム全体の最適化**  
指定します、 [/GL](../build/reference/gl-whole-program-optimization.md)コンパイラ オプションと[/LTCG](../build/reference/ltcg-link-time-code-generation.md)リンカー オプション。 既定では、これはデバッグ構成で無効になっているあり、製品の構成を有効になっています。

**Windows ストア アプリのサポート**  
このプロジェクトが Windows ランタイム (ユニバーサル Windows プラットフォーム) アプリをサポートしているかどうかを指定します。 詳細については、次を参照してください。 [/ZW (Windows ランタイムのコンパイル)](../build/reference/zw-windows-runtime-compilation.md)、および Windows デベロッパー センターです。

## <a name="see-also"></a>関連項目

[プロパティ ページ](../ide/property-pages-visual-cpp.md)  