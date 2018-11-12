---
title: C++ メイクファイル プロジェクトの作成
ms.date: 10/19/2018
f1_keywords:
- vc.appwiz.makefile.project
helpviewer_keywords:
- Makefile projects, creating
- project files [C++], Makefile projects
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
ms.openlocfilehash: 0c64f6df342e82e3ea5409e2b07af1e591747d7c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494849"
---
# <a name="creating-a-c-makefile-project"></a>C++ メイクファイル プロジェクトの作成

*makefile* は、一連の C++ ソース コード ファイルをコンパイルし、リンクする (あるいは*ビルド*する) 方法を含むテキスト ファイルです。 *make* プログラムによってメイクファイルが読み取られ、コンパイラ、リンカー、そしておそらくは他のプログラムが呼び出され、実行可能ファイルが作成されます。 Microsoft の *make* プログラム実装は **NMAKE** と呼ばれています。 (Visual Studio では既定で、.vcxproj ファイルに基づいて MSBuild システムが使用されます。これは **[ファイル]、[新規]、[プロジェクト]** で作成されます。)

既存のメイクファイル プロジェクトがある場合、Visual Studio IDE でそれをコード化またはデバッグするとき、次の選択肢が表示されます。

- Visual Studio で、既存のメイクファイルを使用して IDE でコードをビルドするメイクファイル プロジェクトを作成します。 (ネイティブの MSBuild プロジェクトで与えられる IDE 機能は一部のみ与えられます。)下の「[メイクファイル プロジェクトを作成するには](#create_a_makefile_project)」を参照してください。
- **[既存コード ファイルからの新しいプロジェクトの作成]** ウィザードを使用し、ソース コードからネイティブ MSBuild プロジェクトを作成します。 詳細については、「[方法 : 既存のコードから C++ プロジェクトを作成する](how-to-create-a-cpp-project-from-existing-code.md)」を参照してください。
- **Visual Studio 2017 以降**: **[フォルダーを開く]** 機能を使用して MSBuild に変換せずにメイクファイル プロジェクトを開きます。 詳細については、「[Open Folder projects in Visual C++ (Visual C++ の [フォルダーを開く] プロジェクト)](non-msbuild-projects.md)」をご覧ください。

## <a name="a-namecreateamakefileproject-to-create-a-makefile-project-with-the-makefile-project-template"></a><a name="create_a_makefile_project"> メイクファイル プロジェクト テンプレートでメイクファイル プロジェクトを作成するには

Visual Studio 2017 以降では、メイクファイル プロジェクト テンプレートは、C++ デスクトップ開発ワークロードがインストールされているときに利用できます。

ウィザードに従い、メイクファイルによって使用されるコマンドと環境を指定します。 次に、このプロジェクトを使用して、Visual Studio 開発環境でコードをビルドできます。

既定では、ソリューション エクスプローラーにメイクファイル プロジェクトのファイルは表示されません。 メイクファイル プロジェクトで指定したビルド構成は、プロジェクトのプロパティ ページに反映されます。

プロジェクトで指定した出力ファイルは、ビルド スクリプトの生成するファイルの名前には直接は影響しません。 メイクファイルでは、引き続きビルド プロセスの制御とビルド ターゲットの指定を行います。

1. Visual Studio のスタート ページで、**[新しいプロジェクト]** 検索ボックスに「makefile」と入力します。 あるいは、**[新しいプロジェクト]** ダイアログ ボックスで **[Visual C++]**、**[全般]** (Visual Studio 2015) または **[その他]** (Visual Studio 2017) の順に展開し、[テンプレート] ウィンドウの **[メイクファイル プロジェクト]** を選択してプロジェクト ウィザードを開きます。

1. [[アプリケーションの設定]](../ide/application-settings-makefile-project-wizard.md) ページで、デバッグと製品ビルドに対してコマンド、出力、クリーンアップ、およびリビルドに関する情報を指定します。

1. **[完了]** をクリックしてウィザードを閉じ、**ソリューション エクスプローラー**で新しく作成したプロジェクトを開きます。

プロジェクトのプロパティは、プロパティ ページで表示および編集できます。 プロパティ ページの表示方法については、[Visual C++ プロジェクトのプロパティの設定](../ide/working-with-project-properties.md)に関するページを参照してください。

## <a name="see-also"></a>参照

[メイクファイル アプリケーション ウィザード](../ide/makefile-project-wizard.md)<br/>
[メイクファイルの特殊文字](../build/special-characters-in-a-makefile.md)<br/>
[メイクファイルの内容](../build/contents-of-a-makefile.md)<br/>
