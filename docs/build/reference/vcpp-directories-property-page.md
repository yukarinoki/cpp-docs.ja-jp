---
title: '[VC++ ディレクトリ] プロパティ ページ'
ms.date: 10/09/2018
f1_keywords:
- VC.Project.VCDirectories.IncludePath
- VC.Project.VCDirectories.ReferencePath
- VC.Project.VCDirectories.SourcePath
- VC.Project.VCDirectories.LibraryWPath
- VC.Project.VCDirectories.ExecutablePath
- VC.Project.VCDirectories.LibraryPath
- VS.ToolsOptionsPages.Projects.VCDirectories
- VC.Project.VCDirectories.ExcludePath
helpviewer_keywords:
- VC++ Directories Property Page
ms.assetid: 428eeef6-f127-4271-b3ea-0ae6f2c3d624
ms.openlocfilehash: e739ea99df424f44dc43a28e3dc01c3529bb0c1a
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450719"
---
# <a name="vc-directories-property-page-windows"></a>[VC++ ディレクトリ] プロパティ ページ (Windows)

このプロパティ ページを使用して、現在選択されているプロジェクトをビルドするときに使用するディレクトリを Visual Studio に指示します。 ソリューションに複数のプロジェクトのディレクトリを設定するにはカスタム プロパティ シートを」の説明に従って使用[Visual Studio の C++ プロジェクトの設定を共有または resuse](../create-reusable-property-configurations.md)します。

このページの Linux バージョンについては、「[VC++ ディレクトリ (Linux C++)](../../linux/prop-pages/directories-linux.md)」を参照してください。

**[VC++ ディレクトリ]** プロパティ ページにアクセスするには:

1. **ソリューション エクスプローラー** ウィンドウが表示されない場合は、メイン メニューで **[表示]**  >  **[ソリューション エクスプローラー]** を選択します。
1. (最上位レベルのソリューションではなく) プロジェクト ノードを右クリックして、 **[プロパティ]** を選択します。
1. **[プロパティ ページ]** ダイアログ ボックスの左側のウィンドウで **[構成プロパティ]**  >  **[VC++ ディレクトリ]** の順に選択します。

[VC++ ディレクトリ] プロパティは、最上位のソリューション ノードではなく、プロジェクトに適用されます。 **[構成プロパティ]** の下に **[VC++ ディレクトリ]** が表示されない場合は、 **[ソリューション エクスプローラー]** ウィンドウで C++ プロジェクト ノードを選択します。

![プロジェクト ノードを選択](../media/vcppdir.png "プロジェクト ノードを選択して、VC++ ディレクトリのプロパティを表示する")

クロスプラット フォーム プロジェクトの **[VC++ ディレクトリ]** プロパティ ページは外観が異なることに注意してください。 Linux C++ プロジェクトに固有の情報については、「[VC++ ディレクトリ (Linux C++)](../../linux/prop-pages/directories-linux.md)」を参照してください。

慣れていない場合*プロジェクト プロパティ*Visual Studio で、役に立つその最初の読み取り専用に[Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

**VC++ ディレクトリ** プロパティの既定の設定は、プロジェクトの種類によって異なります。 デスクトップ プロジェクトの場合、特定のプラットフォーム ツールセットの C++ ツールの場所と、Windows SDK の場所が含まれます。 **プラットフォーム ツールセット**と **Windows SDK バージョン**は、 **[構成プロパティ]**  >  **[全般]** ページで変更できます。

いずれかのディレクトリの値を表示するには:

1. **[VC++ ディレクトリ]** ページで、プロパティのいずれか 1 つを選択します。 たとえば、 **[ライブラリ ディレクトリ]** を選択します。
1. プロパティの値フィールドの末尾にある下向きの矢印ボタンを選択します。
1. ドロップダウン メニューで **[編集]** を選択します。

![ライブラリ ディレクトリの編集](../media/vcppdir_libdir_edit.png "ライブラリ パスを編集するためのダイアログ")

次のようなダイアログ ボックスが表示されます。

![ライブラリ ディレクトリの表示](../media/vcppdir_libdir.png "ライブラリ パスを削除するためのダイアログ")

現在のディレクトリを表示するには、このダイアログ ボックスを使用します。 ただし、ディレクトリを変更または追加する場合は、**プロパティ マネージャー**を使用してプロパティ シートを作成するか、既定のユーザー プロパティ シートを変更することをお勧めします。 詳細については、次を参照してください。 [Visual Studio の C++ プロジェクトの設定を共有または resuse](../create-reusable-property-configurations.md)します。

上記のように、継承されたパスの多くがマクロとして提供されます。  マクロの現在の値を調べるには、ダイアログ ボックスの右下隅の **[マクロ]** ボタンを選択します。 多くのマクロは、構成の種類に依存していることに注意してください。 デバッグ ビルドでのマクロは、リリース ビルドの同じマクロとは異なるパスに評価される場合があります。

編集ボックスで部分一致または完全一致を検索することができます。 次の図は、文字列 "WindowsSDK" が含まれるすべてのマクロと、マクロが評価される現在のパスも示しています。

![マクロ値の参照](../media/vcppdir_libdir_macros.png "マクロを編集するためのダイアログ")

メモ:入力すると、一覧が表示されます。 **Enter** キーを押さないでください。

マクロとそれらを可能であればハード コードされたパスの代わりに使用する理由の詳細については、次を参照してください。 [Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

一般的に使用されるマクロの一覧は、次を参照してください。[用マクロの一般的なコマンドとプロパティのビルド](common-macros-for-build-commands-and-properties.md)します。

独自のマクロは次の 2 通りの方法で定義できます。

- 開発者コマンド プロンプトで環境変数を設定します。 すべての環境変数は、MSBuild プロパティ/マクロとして扱われます。

- .props ファイルでユーザー マクロを定義します。 詳細については、「[Property page macros](../working-with-project-properties.md)」 (プロパティ ページ マクロ) を参照してください。

詳細については、次のブログ投稿を参照してください。[Vc++ ディレクトリ](https://blogs.msdn.com/b/vsproject/archive/2009/07/07/vc-directories.aspx)、[継承されたプロパティとプロパティ シート](https://blogs.msdn.com/b/vsproject/archive/2009/06/23/inherited-properties-and-property-sheets.aspx)、および[Visual Studio 2010 C プロジェクト アップグレード ガイド](https://devblogs.microsoft.com/cppblog/visual-studio-2010-c-project-upgrade-guide/)します。

## <a name="directory-types"></a>ディレクトリの種類

また、次のように、その他のディレクトリも指定できます。

**実行ファイル ディレクトリ**<br/>
実行可能ファイルを検索するディレクトリ。 **PATH** 環境変数に対応します。

**インクルード ディレクトリ**<br/>
ソース コードで参照されるインクルード ファイルを検索するディレクトリ。 **INCLUDE** 環境変数に対応します。

**参照ディレクトリ**<br/>
[#using](../../preprocessor/hash-using-directive-cpp.md) ディレクティブによってソース コード内で参照されるアセンブリおよびモジュール (メタデータ) ファイルを検索するディレクトリ。 **LIBPATH** 環境変数に対応します。

**ライブラリ ディレクトリ**<br/>
ライブラリ (.lib) ファイル (ランタイム ライブラリを含む) を検索するディレクトリ。 **LIB** 環境変数に対応します。 この設定は、.obj ファイルには適用されません。 .obj ファイルにリンクするには、 **[構成プロパティ]**  >  **[リンカー]**  >  **[全般]** プロパティ ページで **[Additional Library Dependencies]\(追加のライブラリ依存関係\)** を選択してファイルの相対パスを指定します。 詳細については、「[[リンカー] プロパティ ページ](linker-property-pages.md)」を参照してください。

**ライブラリ WinRT ディレクトリ**<br/>
ユニバーサル Windows プラットフォーム (UWP) アプリで WinRT ライブラリ ファイルを検索するためのディレクトリ。

**ソース ディレクトリ**<br/>
IntelliSense で使用されるソース ファイルを検索するディレクトリ。

**ディレクトリの除外**<br/>
各コンパイルの前に、Visual Studio によってすべてのファイルのタイムスタンプが照会され、前回のコンパイルから変更されているものがあるかどうかが判断されます。 プロジェクトに多数の安定したライブラリがある場合は、タイムスタンプ チェックからこれらのディレクトリを除外することで、ビルド時間を短縮できる場合があります。

## <a name="sharing-the-settings"></a>設定の共有

プロジェクトのプロパティを、他のユーザーと共有したり、複数のコンピューター間で共有したりできます。 詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。
