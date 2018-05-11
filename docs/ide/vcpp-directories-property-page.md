---
title: Vc++ ディレクトリ プロパティ ページ |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/26/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCDirectories.IncludePath
- VC.Project.VCDirectories.ReferencePath
- VC.Project.VCDirectories.SourcePath
- VC.Project.VCDirectories.LibraryWPath
- VC.Project.VCDirectories.ExecutablePath
- VC.Project.VCDirectories.LibraryPath
- VS.ToolsOptionsPages.Projects.VCDirectories
- VC.Project.VCDirectories.ExcludePath
dev_langs:
- C++
helpviewer_keywords:
- VC++ Directories Property Page
ms.assetid: 428eeef6-f127-4271-b3ea-0ae6f2c3d624
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3acaccff2e2764f4fd7f6f4815f5721f0ba845a3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="vc-directories-property-page-windows"></a>Vc++ ディレクトリ プロパティ ページ (Windows)

このプロパティ ページを使用して、現在選択されているプロジェクトをビルドするときに使用するディレクトリを Visual Studio に指示します。 ソリューションに複数のプロジェクトのディレクトリを設定するにシートを使用して、カスタム プロパティ」の説明に従って[再利用可能なプロパティ構成の作成](working-with-project-properties.md#bkmkPropertySheets)です。

このページの Linux バージョンを参照してください。 [vc++ ディレクトリ (Linux C++)](../linux/prop-pages/directories-linux.md)です。   

アクセスする、 **vc++ ディレクトリ**プロパティ ページ。

1. 場合、**ソリューション エクスプ ローラー**ウィンドウが表示されていない、し、メイン メニューで次のように選択します。**ビュー** > **ソリューション エクスプ ローラー**です。
1. (最上位レベルのソリューションではなく) プロジェクト ノードを右クリックして選択**プロパティ**です。
1. 左側のウィンドウで、**プロパティ ページ**ダイアログ ボックスで、**構成プロパティ** > **vc++ ディレクトリ**です。  

Vc++ ディレクトリのプロパティは、最上位のソリューション ノードではなく、プロジェクトに適用されます。 表示されない場合**vc++ ディレクトリ****構成プロパティ**での C++ プロジェクト ノードを選択、**ソリューション エクスプ ローラー**ウィンドウ。 

![プロジェクト ノードを選択](media/vcppdir.png "vc++ ディレクトリのプロパティを表示するプロジェクト ノードを選択")

なお、 **vc++ ディレクトリ**クロスプラット フォーム プロジェクトのプロパティ ページが異なるように見えます。 Linux の C++ プロジェクトに固有の情報を参照してください。 [vc++ ディレクトリ (Linux C++)](../linux/prop-pages/directories-linux.md)です。 
 
慣れていない場合*プロジェクト プロパティ*Visual Studio で、役に立つその最初の読み取りに[のプロジェクト プロパティの操作](working-with-project-properties.md)です。 
 
既定の設定**vc++ ディレクトリ**プロパティは、プロジェクトの種類によって異なります。 デスクトップ プロジェクトの場合、特定のプラットフォーム ツールセットの C++ のツールの場所と、Windows SDK の場所が含まれます。 変更することができます、**プラットフォーム ツールセット**と**Windows SDK バージョン**上、**構成プロパティ** > **全般**ページです。 

ディレクトリのいずれかの値を表示するには。

1. プロパティのいずれかを選択、 **vc++ ディレクトリ**ページ。 たとえば、選択**ライブラリ ディレクトリ**です。
1. プロパティの値フィールドの末尾にある下向きの矢印ボタンを選択します。
1. ドロップダウン メニューで選択して**編集**です。

![ライブラリ ディレクトリを編集](media/vcppdir_libdir_edit.png "ライブラリ パスを編集するためのダイアログ")

次のように、ダイアログ ボックスが表示されます。 

![ライブラリ ディレクトリを表示する](media/vcppdir_libdir.png "ライブラリ パスを追加または削除 ダイアログ")

現在のディレクトリを表示するのにには、このダイアログ ボックスを使用します。 ただし、変更またはディレクトリを追加する場合は、あるを使用する方がよい**プロパティ マネージャー**プロパティ シートを作成または既定のユーザー プロパティ シートを変更します。 詳細については、次を参照してください。[再利用可能なプロパティ構成の作成](working-with-project-properties.md#bkmkPropertySheets)です。

上記のように、継承されたパスの多くがマクロとして与えられます。  マクロの現在の値を検証するには、選択、**マクロ** ダイアログ ボックスの右下隅のボタンをクリックします。 多くのマクロは、構成の種類によって異なりますに注意してください。 デバッグ ビルドでのマクロは、リリース ビルドで同じマクロとは異なるパスに評価される場合があります。 

編集ボックスに部分的または完全な一致を検索することができます。 次の図は、文字列"WindowsSDK"が含まれるすべてのマクロとマクロに評価される現在のパスも示しています。

![マクロの値を参照してください](media/vcppdir_libdir_macros.png "マクロを編集するためのダイアログ")

注: 入力すると、一覧が表示されます。 キーを押さない**Enter**です。

マクロとそれらの可能な限りハードコードされたパスの代わりに使用する理由の詳細については、次を参照してください。[のプロジェクト プロパティの操作](../ide/working-with-project-properties.md#bkmkPropertiesVersusMacros)です。 

一般的に使用されるマクロの一覧は、次を参照してください。[のビルドのコマンドとプロパティの一般的なマクロ](https://docs.microsoft.com/en-us/cpp/ide/common-macros-for-build-commands-and-properties)です。

2 つの方法では、独自のマクロを定義できます。
-   開発者コマンド プロンプトで環境変数を設定します。 すべての環境変数は、MSBuild プロパティ/マクロとして扱われます。
-   .Props ファイル内のユーザー マクロを定義します。 詳細については、次を参照してください。[プロパティ ページ マクロ](working-with-project-properties.md#bkmkPropertiesVersusMacros)です。 

詳細については、次のブログ投稿を参照してください: [vc++ ディレクトリ](http://blogs.msdn.com/b/vsproject/archive/2009/07/07/vc-directories.aspx)、[継承プロパティとプロパティ シート](http://blogs.msdn.com/b/vsproject/archive/2009/06/23/inherited-properties-and-property-sheets.aspx)、および[Visual Studio 2010 C プロジェクトのアップグレード ガイド](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx)です。  
  
## <a name="directory-types"></a>ディレクトリの種類

また、次のように、その他のディレクトリも指定できます。  
  
**実行可能ファイルのディレクトリ**<br/>
実行可能ファイルを検索するディレクトリ。 対応する、**パス**環境変数。

**インクルード ディレクトリ**<br/>
ソース コードで参照されるインクルード ファイルを検索するディレクトリ。 対応する、 **INCLUDE**環境変数。

**参照ディレクトリ**<br/>
 アセンブリと、ソース コードの中で参照されるモジュール (メタデータ) ファイルを検索するディレクトリ、 [#using](../preprocessor/hash-using-directive-cpp.md)ディレクティブです。 対応する、 **LIBPATH**環境変数。

**ライブラリ ディレクトリ**<br/>
ライブラリ (.lib) ファイル (ランタイム ライブラリを含む) を検索するディレクトリ。 対応する、 **LIB**環境変数。 この設定が .obj ファイルには適用されません.obj ファイルにリンクする、**構成プロパティ** > **リンカー** > **全般**プロパティ ページで、 **追加のライブラリ依存関係**し、ファイルの相対パスを指定します。 詳細については、次を参照してください。[リンカー プロパティ ページ](../ide/linker-property-pages.md)です。

**WinRT のライブラリ ディレクトリ**<br/>
ユニバーサル Windows プラットフォーム (UWP) アプリでの WinRT ライブラリ ファイルを検索するディレクトリを使用します。 

**ソース ディレクトリ**<br/>
IntelliSense で使用されるソース ファイルを検索するディレクトリ。

**ディレクトリを除外します。**<br/>
各コンパイル前に、Visual Studio は、いずれかが前回のコンパイル以降変更されているかどうかを判断するすべてのファイルのタイムスタンプを照会します。 プロジェクトに多数の安定したライブラリがある場合は、する可能性のある時間を短縮できますビルド時間タイムスタンプ チェックからこれらのディレクトリを除外することによりします。

## <a name="sharing-the-settings"></a>設定の共有

プロジェクトのプロパティを、他のユーザーと共有したり、複数のコンピューター間で共有したりできます。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../ide/working-with-project-properties.md)です。
