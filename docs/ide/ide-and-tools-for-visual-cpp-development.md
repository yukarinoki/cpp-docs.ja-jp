---
title: IDE と Visual C++ 開発用ツール | Microsoft Docs
description: Visual Studio IDE は、コード エディター、デバッガー、テスト フレームワーク、静的アナライザー、その他のプログラミング ツールを利用した Windows、Linux、Android、iOS 上での C++ 開発をサポートしています。
ms.custom: ''
ms.date: 09/27/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, development tools
ms.assetid: 56eabafb-1956-4f0f-bec5-29b887763559
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 310dc9b8e31f72fbd04c620987d9857932f7a0a1
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2018
ms.locfileid: "48821147"
---
# <a name="ide-and-compiler-tools-for-visual-c-development"></a>IDE と Visual C++ 開発用コンパイラ ツール

Visual Studio 統合開発環境 (IDE) に属する Microsoft Visual C++ (MSVC) は、他の言語と共通の多くのウィンドウやツールを共有します。 **ソリューション エクスプローラー**、コード エディター、デバッガーなどの多くは、「[Visual Studio IDE](/visualstudio/ide/visual-studio-ide)」に記載されています。 共有ツールやウィンドウの機能は C++ と、.NET 言語や JavaScript とで若干異なることがよくあります。 一部のウィンドウやツールは、Visual Studio Professional 版または Visual Studio Enterprise 版でのみ使用できます。

Visual Studio IDE の共有ツールに加えて、MSVC には、ネイティブ コード開発に特化したいくつかのツールがあります。 この記事には、これらのツールの一覧も掲載します。 Visual Studio の各エディションで使用可能なツールの一覧については、「[さまざまな Visual Studio エディションの Visual C++ ツールおよび機能](visual-cpp-tools-and-features-in-visual-studio-editions.md)」を参照してください。

## <a name="create-projects"></a>プロジェクトを作成する

*プロジェクト* は基本的には、実行可能ファイルに組み込まれている、イメージやデータ ファイルなどの一連のソース コード ファイルとリソースです。 

Visual Studio 2015 では、MSBuild プロジェクトのサポートを提供します。 Qt や CMake などの他のビルド システム向けの Visual Studio 拡張機能をダウンロードすることができます。

Visual Studio 2017 では、使用するすべてのビルド システムやカスタム ビルド ツールがサポートされ、IntelliSense、参照、デバッグなどの機能が完全にサポートされます。

- **MSBuild** は、Visual Studio 用のネイティブ ビルド システムです。 メイン メニューから **[ファイル]**、**[新規]**、**[プロジェクト]** の順に選択すると、さまざまな種類の MSBuild *プロジェクト テンプレート*が表示されます。これを利用すると、さまざまな種類の C++ アプリケーションの開発を簡単に始められます。

   ![プロジェクト テンプレート](media/vs2017-new-project.png "Visual Studio 2017 の [新しいプロジェクト] ダイアログ")

   一般的に、CMake や別のプロジェクト システムを利用する特別な理由がない限り、新しいプロジェクトにはこれらのテンプレートを使用してください。 一部のプロジェクトには*ウィザード*が含まれています。そのウィザードの手順に従って、新しいプロジェクトの作成プロセスを実行します。 詳細については、[MSBuild ベースのプロジェクトを作成し、管理する](creating-and-managing-visual-cpp-projects.md)方法に関するページを参照してください。

- **CMake** はクロスプラットフォームのビルド システムであり、C++ によるデスクトップ開発のワークロードをインストールする際に Visual Studio IDE に統合されます。 詳細については、「[CMake projects in Visual C++ (Visual C++ の CMake プロジェクト)](cmake-tools-for-visual-cpp.md)」をご覧ください。
- ファイルの緩やかな集合を含む、その他の C++ ビルド システムは、**[フォルダーを開く]** 機能を通じてサポートされます。 単純な JSON ファイルを作成して、ビルド プログラムを呼び出し、デバッグ セッションを構成します。 詳細については、「[Open Folder projects in Visual C++ (Visual C++ の [フォルダーを開く] プロジェクト)](non-msbuild-projects.md)」をご覧ください。

## <a name="add-to-source-control"></a>ソース管理に追加

ソース管理では、複数の開発者間で作業を調整したり、開発中の作業を運用コードから分離したり、ソース コードをバックアップしたりすることができます。 Visual Studio は、Git と [Team Foundation バージョン管理 \(TFVC\)](/azure/devops/repos/tfvc/) をその**チーム エクスプローラー** ウィンドウをサポートしています。

![チーム エクスプローラー](media/vs2017-team-explorer.png "Visual Studio 2017 チーム エクスプローラー")

Git と Azure のリポジトリの統合については、「[Share your code with Visual Studio 2017 and Azure Repos Git](/azure/devops/repos/git/share-your-code-in-git-vs-2017)」 (Visual Studio 2017 と Azure Repos Git でコードを共有する) を参照してください。 Git と GitHub の統合については、「[GitHub Extension for Visual Studio](https://visualstudio.github.com/)」 (Visual Studio 向けの GitHub 拡張) を参照してください。

## <a name="create-user-interfaces-with-designers"></a>デザイナーでユーザー インターフェイスを作成する

プログラムにユーザー インターフェイスがある場合、デザイナーを使用し、ボタンやリスト ボックスなどのコントロールをユーザー インターフェイスに簡単に入力できます。 ツールボックス ウィンドウからコントロールをドラッグし、デザイン サーフェイスにドロップすると、Visual Studio によって、それを動かすために必要なリソースとコードが生成されます。 その後、外観と動作をカスタマイズするコードを記述します。

![デザイナーとツールボックス](media/vs2017-toolbox-designer.png "Visual Studio 2017 のデザイナーとツールボックス")

ユニバーサル Windows プラットフォーム アプリのユーザー インターフェイスの設計方法については、[デザインと UI](https://developer.microsoft.com/en-us/windows/design) に関するページを参照してください。

MFC アプリケーションのユーザー インターフェイスの作成方法については、「[MFC デスクトップ アプリケーション](../mfc/mfc-desktop-applications.md)」を参照してください。 Win32 Windows プログラムについては、「[Windows デスクトップ アプリケーション](../windows/windows-desktop-applications-cpp.md)」を参照してください。

## <a name="write-code"></a>コードの記述

プロジェクトを作成すると、すべてのプロジェクト ファイルが**ソリューション エクスプローラー** ウィンドウに表示されます。 (*ソリューション*は、1 つまたは複数の関連プロジェクトのための論理コンテナーです。)**ソリューション エクスプローラー**で .h または .cpp ファイルをクリックすると、ファイルがコード エディターで開きます。 

![ソリューション エクスプローラーとコード エディター](media/vs2017-solution-explorer-code-editor.png "Visual Studio 2017 のソリューション エクスプローラーとコード エディター")

コード エディターは、C++ ソース コード専用のワード プロセッサです。 このエディターでは、コードを読みやすく理解しやすいものにするために、言語のキーワード、メソッド名と変数名、およびその他のコードの要素が色分けされます。

詳細については、[コードの作成とリファクタリング](writing-and-refactoring-code-cpp.md)に関するページを参照してください。

## <a name="add-and-edit-resources"></a>リソースの追加と編集

*リソース* という用語には、ダイアログ、アイコン、画像、ローカライズ可能な文字列、スプラッシュ画面、データベースの接続文字列、または実行可能ファイルに含める任意のデータなどが含まれます。

ネイティブ デスクトップ C++ プロジェクトでのリソースの追加および編集の詳細については、「[リソース ファイルの操作](../windows/working-with-resource-files.md)」を参照してください。

## <a name="build-compile-and-link"></a>ビルド (コンパイルおよびリンク)

メニュー バーの **[ビルド]** > **[ソリューションのビルド]** を選択するか、Ctrl + Shift + B キーを押してプロジェクトをコンパイルおよびリンクします。 ビルド エラーと警告は、エラー一覧 (Ctrl + \\、E) に報告されます。 **[出力]** ウィンドウ (Alt + 2) にビルド プロセスに関する情報が表示されます。

![出力ウィンドウとエラー一覧](media/vs2017-output-error-list.png "Visual Studio 2017 の出力ウィンドウとエラー一覧") MSBuild 構成の詳細については、「[プロジェクトのプロパティの操作](working-with-project-properties.md)」と「[Visual Studio での C++ プロジェクトのビルド](building-cpp-projects-in-visual-studio.md)」を参照してください。

コンパイラ (cl.exe) や、その他多くのビルド関連のスタンドアロン ツール (コマンド ラインから直接入力する NMAKE や LIB など) も使用できます。 詳細については、「[コマンドラインでの C/C++ コードのビルド](../build/building-on-the-command-line.md)」と「[C/C++ ビルドのリファレンス](../build/reference/c-cpp-building-reference.md)」を参照してください。

## <a name="debug"></a>デバッグ

**[F5]** を押すことでデバッグを開始できます。 実行は、設定したブレークポイントで一時停止します。 また、コードを一度に 1 行ずつステップ実行したり、変数やレジスタの値を表示したり、場合によってはコードに変更を加え、再コンパイルせずにデバッグを続行したりできます。 次の図は、ブレークポイントで実行が停止したデバッグ セッションを示しています。 データ構造体メンバーの値は**ウォッチ ウィンドウ**に表示されます。

![デバッグ セッション](media/vs2017-debug-watch.png "Visual Studio 2017 のデバッグ セッション")

詳しくは、「[Visual Studio でのデバッグ](/visualstudio/debugger/debugging-in-visual-studio)」をご覧ください。

## <a name="test"></a>テスト

Visual Studio には、ネイティブ C++ の単体テスト フレームワークと C++/CLI の単体テスト フレームワークの両方が含まれています。 Boost.Test、Google Test、CTest もサポートされています。 **テスト エクスプローラー** ウィンドウからテストを実行します。

![テスト エクスプローラー](media/cpp-test-explorer-passed.png "Visual Studio 2017 テスト エクスプローラー")

詳細については、[単体テストを使用してコードを検証する](/visualstudio/test/unit-test-your-code)方法に関するページと「[Visual Studio で C/C++ 用の単体テストを作成する](/visualstudio/test/writing-unit-tests-for-c-cpp)」を参照してください。

## <a name="analyze"></a>解析

Visual Studio には、ソース コードの潜在的な問題を検出できる静的コード分析ツールが含まれています。 それらのツールには、[C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md) ルール チェッカーの実装が含まれています。 詳細については、「[C/C++ のコード分析の概要](/visualstudio/code-quality/code-analysis-for-c-cpp-overview)」を参照してください。

## <a name="deploy-completed-applications"></a>完成したアプリケーションの配置

Microsoft Store から従来のデスクトップ アプリケーションと UWP アプリの両方を展開できます。 CRT の配置は、水面下で自動的に処理されます。 詳細については、「[Publish Windows apps and games](/windows/uwp/publish/)」(Windows のアプリとゲームを公開する) を参照してください。

ネイティブ C++ デスクトップを別のコンピューターに配置することもできます。詳細については、[デスクトップ アプリケーションの配置](deploying-native-desktop-applications-visual-cpp.md)に関するページを参照してください。

C++/CLI プログラムの配置について詳しくは、「[配置ガイド (開発者向け)](/dotnet/framework/deployment/deployment-guide-for-developers)」を参照してください。

## <a name="related-articles"></a>関連トピック

|||
|-|-|
|[さまざまな Visual Studio エディションの Visual C++ ツールおよび機能](visual-cpp-tools-and-features-in-visual-studio-editions.md)|Visual Studio の各種エディションで使用可能な機能が表示されます。|
|[MSBuild ベースのプロジェクトの作成と管理](creating-and-managing-visual-cpp-projects.md)|Visual Studio の C++ MSBuild ベースのプロジェクトの概要と、それらを作成し、管理する方法を説明する他の記事へのリンクが示されます。|
|[Visual C++ の CMake プロジェクト](cmake-tools-for-visual-cpp.md)。|Visual C++ で CMake や他の非 MSBuild プロジェクトをビルドする方法について説明します。|
|[C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)|C++ プロジェクトの作成方法について説明します。|
|[デスクトップ アプリケーションの配置](deploying-native-desktop-applications-visual-cpp.md)|C++ アプリケーションの配置の概要と、配置について詳しく説明する他の記事へのリンクが示されます。|
|[Visual C++ 移植とアップグレードのガイド](../porting/visual-cpp-porting-and-upgrading-guide.md)|Visual Studio の旧バージョンで作成された C++ アプリケーションをアップグレードする方法と、Visual Studio 以外のツールを使用して作成されたアプリケーションを移行する方法について詳しく説明します。|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual Studio での Visual C++ の主な機能について説明し、他の Visual C++ ドキュメントへのリンクを示します。|
