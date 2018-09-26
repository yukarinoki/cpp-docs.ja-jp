---
title: IDE と Visual C++ 開発用ツール | Microsoft Docs
ms.custom: ''
ms.date: 06/02/2018
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
ms.openlocfilehash: d4e7742afd3fecc4dd115624da0c1650dc662004
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412523"
---
# <a name="ide-and-tools-for-visual-c-development"></a>IDE と Visual C++ 開発用ツール

Visual Studio 統合開発環境 (IDE) に属する Microsoft Visual C++ (MSVC) は、他の言語と共通の多くのウィンドウやツールを共有します。 **ソリューション エクスプローラー**、コード エディター、デバッガーなどの多くは、「[Visual Studio IDE](/visualstudio/ide/visual-studio-ide)」に記載されています。 共有ツールやウィンドウの機能は C++ と、.NET 言語や Javascript とで若干異なることがよくあります。 一部のウィンドウやツールは、Visual Studio Pro または Visual Studio Enterprise でのみ使用できます。

Visual Studio IDE の共有ツールに加えて、MSVC には、ネイティブ コード開発に特化したいくつかのツールがあります。 この記事には、これらのツールの一覧も掲載します。 Visual Studio の各エディションで使用可能なツールの一覧については、「[さまざまな Visual Studio エディションの Visual C++ ツールおよび機能](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)」を参照してください。

## <a name="creating-a-solution-and-projects"></a>ソリューションとプロジェクトの作成

*プロジェクト* は基本的には、実行可能ファイルに組み込まれている、イメージやデータ ファイルなどの一連のソース コード ファイルとリソースです。

Visual Studio 2015 では、MSBuild プロジェクトのサポートを提供します。 Qt や CMake などの他のビルド システム向けの Visual Studio 拡張機能をダウンロードすることができます。

Visual Studio 2017 では、使用するすべてのビルド システムやカスタム ビルド ツールがサポートされ、IntelliSense、参照、デバッグなどの機能が完全にサポートされます。

- MSBuild は Visual Studio のネイティブ ビルド システムであり、多くの場合、MFC または ATL を使用するユニバーサル Windows プラットフォーム (UWP) アプリや従来の Windows デスクトップ アプリケーションに最適です。 MSBuild ベースの C++ プロジェクトの詳細については、「[MSBuild ベース プロジェクトの作成と管理](creating-and-managing-visual-cpp-projects.md)」を参照してください。
- CMake はクロスプラットフォームのビルド システムであり、C++ によるデスクトップ開発のワークロードをインストールする際に Visual Studio IDE に統合されます。 詳細については、「[CMake projects in Visual C++ (Visual C++ の CMake プロジェクト)](cmake-tools-for-visual-cpp.md)」をご覧ください。
- ファイルの緩やかな集合を含む、その他の C++ ビルド システムは、[フォルダーを開く] 機能を通じてサポートされます。 単純な JSON ファイルを作成して、ビルド プログラムを呼び出し、デバッグ セッションを構成します。 詳細については、「[Bring your C++ code to Visual Studio](https://blogs.msdn.microsoft.com/vcblog/2017/04/14/bring-your-cpp-code-to-visual-studio/)」 (C++ コードを Visual Studio に取り込む) を参照してください。

### <a name="project-templates-msbuild"></a>プロジェクト テンプレート (MSBuild)

Visual Studio には MSBuild ベース プロジェクト用のいくつかのテンプレートが付属しています。これらのテンプレートには、スタート コードや、さまざまな種類の基本的なプログラムで必要とされる設定が含まれています。 通常は、まず **[ファイル]** > **[新しいプロジェクト]** の順に選択してプロジェクト テンプレートからプロジェクトを作成し、次にそのプロジェクトに新しいソース コード ファイルを追加するか、付属のファイルでコーディングを開始します。 C++ プロジェクトやプロジェクト ウィザードに固有の情報については、「[Visual C++ プロジェクトの作成と管理](../ide/creating-and-managing-visual-cpp-projects.md)」を参照してください。

### <a name="application-wizards-msbuild"></a>アプリケーション ウィザード (MSBuild)

Visual Studio では、**[ファイル]** > **[新しいプロジェクト]** を選択したときにいくつかの MSBuild プロジェクトの種類のウィザードが提供されます。 このウィザードの手順に従って、新しいプロジェクトの作成プロセスを実行します。 これは、オプションや設定が多いプロジェクトの種類の場合に便利です。 詳細については、「[アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../ide/creating-desktop-projects-by-using-application-wizards.md)」を参照してください。

## <a name="creating-user-interfaces-with-designers-msbuild"></a>デザイナーによるユーザー インターフェイスの作成 (MSBuild)

プログラムにユーザー インターフェイスがある場合、まずそのインターフェイスにボタン、リスト ボックスなどのコントロールを設定します。 Visual Studio には、C++ アプリケーションの種類ごとに、ビジュアル デザイン領域とツールボックスが含まれています。 どの種類のアプリを作成している場合であっても、[ツールボックス] ウィンドウからコントロールをドラッグして、目的の場所にあるデザイン領域にドロップするという基本的な概念は同じです。 Visual Studio は、バック グラウンドで、リソースとそれらすべてを正常に動作させるために必要なコードを生成します。 次に、コードを記述してコントロールにデータを読み込むか、その外観と動作をカスタマイズします。

ユニバーサル Windows プラットフォーム アプリのユーザー インターフェイスの設計方法については、[デザインと UI](https://developer.microsoft.com/en-us/windows/design) に関するページを参照してください。

MFC アプリケーションのユーザー インターフェイスの作成方法については、「[MFC デスクトップ アプリケーション](../mfc/mfc-desktop-applications.md)」を参照してください。 Win32 Windows プログラムについては、「[Windows デスクトップ アプリケーション](../windows/windows-desktop-applications-cpp.md)」を参照してください。

## <a name="writing-and-editing-code"></a>作成とコードの編集

### <a name="semantic-colorization"></a>セマンティクスの色づけ

プロジェクトを作成すると、すべてのプロジェクト ファイルが**ソリューション エクスプローラー** ウィンドウに表示されます。 **ソリューション エクスプローラー**で .h または .cpp ファイルをクリックすると、ファイルがコード エディターで開きます。 コード エディターは、C++ ソース コード専用のワード プロセッサです。 このエディターでは、コードを読みやすく理解しやすいものにするために、言語のキーワード、メソッド名と変数名、およびその他のコードの要素が色分けされます。

### <a name="intellisense"></a>IntelliSense

コード エディターでは、IntelliSense と呼ばれるいくつかの機能もサポートしています。 メソッドの上にポインターを合わせると、そのメソッドに関するいくつかの基本的な情報を参照できます。 クラスの変数名と . または -> を入力すると、 そのクラスのインスタンス メンバーの一覧が表示されます。 クラス名に続けて :: と入力すると、静的メンバーの一覧が表示されます。 クラスやメソッドの名前を入力し始めると、コード エディターが完全なステートメントの候補を表示します。 詳細については、「[IntelliSense の使用](/visualstudio/ide/using-intellisense)」を参照してください。

### <a name="code-snippets"></a>コード スニペット

IntelliSense コード スニペットを使用すると、ショートカット キーを入力して、一般的に使用されるコード構造や複雑なコード構造を生成できます。 詳細については、「[Code Snippets](/visualstudio/ide/code-snippets)」を参照してください。

## <a name="navigating-code"></a>コード間の移動

**[表示]** メニューから、コード ファイル間を移動するためのさまざまなウィンドウやツールにアクセスできます。 これらのウィンドウの詳細については、「[コードの構造の表示](/visualstudio/ide/viewing-the-structure-of-code)」を参照してください。

### <a name="solution-explorer"></a>ソリューション エクスプローラー

Visual Studio のすべてのエディションでは、**ソリューション エクスプローラー** ウィンドウを使用して、プロジェクト内のファイル間を移動します。 .H または .cpp ファイルのアイコンを展開するとファイル内のクラスが表示されます。 クラスを展開するとそのメンバーが表示されます。 メンバーをダブルクリックするとファイル内のそのメンバーの定義や実装に移動します。

### <a name="class-view-and-code-definition-window"></a>クラス ビューおよびコード定義ウィンドウ

すべてのファイルの名前空間とクラス (部分クラスを含む) は、**[クラス ビュー]** ウィンドウを使用して参照します。 それぞれの名前空間またはクラスを展開するとそのメンバーが表示され、メンバーをダブルクリックするとソース ファイル内のそのメンバーの場所に移動します。 **コード定義ウィンドウ**を開いている場合、**[クラス ビュー]** で種類を選択すると、その種類の定義や実装を表示できます。

### <a name="object-browser"></a>オブジェクト ブラウザー

Windows ランタイム コンポーネント (.winmd ファイル)、.NET アセンブリ、および COM タイプ ライブラリ内の種類の情報を表示するには、**オブジェクト ブラウザー**を使用します。 これは、Win32 の DLL では使用されません。

### <a name="go-to-definitiondeclaration"></a>定義 / 宣言へ移動

API 名またはメンバー変数の上で F12 キーを押して、その定義に移動します。 定義が (UWP アプリまたは Windows 8.x ストア アプリの) .winmd ファイル内にある場合、オブジェクト ブラウザーに種類の情報が表示されます。 変数または種類の名前を右クリックし、コンテキスト メニューからオプションを選択して、**[定義へ移動]** または **[宣言へ移動]** を選ぶこともできます。

### <a name="find-all-references"></a>[すべての参照の検索]

ソース コード ファイルで、種類、メソッド、または変数の名前の上にマウス カーソルを置いて右クリックし、**[すべての参照の検索]** を選択すると、その種類が使用されているファイル、プロジェクト、またはソリューション内のすべての場所の一覧が返されます。 **[すべての参照の検索]** はインテリジェントな機能であり、別のスコープの同じ名前の他の変数があっても、完全に一致する変数のインスタンスのみを返します。

## <a name="add-and-edit-resources--msbuild"></a>リソースの追加および編集 (MSBuild)

Visual Studio デスクトップ プロジェクトのコンテキストにおける*リソース* という用語には、ダイアログ ボックス、アイコン、ローカライズ可能な文字列、スプラッシュ画面、データベースの接続文字列、または実行可能ファイルに含める任意のデータなどが含まれます。

ネイティブ デスクトップ C++ プロジェクトでのリソースの追加および編集の詳細については、「[リソース ファイルの操作](../windows/working-with-resource-files.md)」を参照してください。

## <a name="build-compile-and-link"></a>ビルド (コンパイルおよびリンク)

メニュー バーの **[ビルド]** > **[ソリューションのビルド]** を選択するか、Ctrl + Shift + B キーを押してプロジェクトをコンパイルおよびリンクします。 実行可能コードを作成する場合、Visual Studio では [MSBuild](/visualstudio/msbuild/msbuild1) または CMake を使用します。あるいは、**[フォルダーを開く]** を通じてセットアップした任意のビルド環境を使用します。 MSBuild プロジェクトでは、**[ツール]** > **[オプション]** > **[プロジェクトおよびソリューション]** で一般的なビルド オプションを設定し、**[プロジェクト]** > **[プロパティ]** で特定のプロジェクトのプロパティを設定できます。 ビルド エラーと警告は、エラー一覧 (Ctrl + \\、E) に報告されます。 非 MSBuild プロジェクトは、ソリューション エクスプローラーで作成する JSON ファイルで構成されます。 使用する任意のビルド システムのビルド プロセスに関する情報は、**[出力]** ウィンドウ (Alt + 2) に表示されます。 MSBuild 構成の詳細については、「[プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)」と「[Visual Studio での C++ プロジェクトのビルド](../ide/building-cpp-projects-in-visual-studio.md)」を参照してください。

コンパイラ (cl.exe) や、その他多くのビルド関連のスタンドアロン ツール (コマンド ラインから直接入力する NMAKE や LIB など) も使用できます。 詳細については、「[コマンドラインでの C/C++ コードのビルド](../build/building-on-the-command-line.md)」と「[C/C++ ビルドのリファレンス](../build/reference/c-cpp-building-reference.md)」を参照してください。

## <a name="test"></a>テスト

Visual Studio には、ネイティブ C++ の単体テスト フレームワークと C++/CLI の単体テスト フレームワークの両方が含まれています。 詳細については、「[単体テストを使用したコードの検証](/visualstudio/test/unit-test-your-code)」と「[C++ 用の Microsoft 単体テスト フレームワークを使用した C++ 用単体テストの記述](/visualstudio/test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp)」を参照してください。

## <a name="analyze"></a>解析

Visual Studio には、[C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md) ルール チェッカーの実装など、C++ の静的コード分析ツールが含まれます。 詳細については、「[C/C++ のコード分析の概要](/visualstudio/code-quality/code-analysis-for-c-cpp-overview)」を参照してください。

## <a name="debug"></a>デバッグ

プロジェクト構成が [デバッグ] に設定されている場合、**F5** キーを押してプログラムをデバッグできます。 デバッグ中には、**F9** キーを押してブレークポイントを設定したり、**F10** キーを押してコードをステップ実行したり、指定された変数やレジスタの値を表示したり、場合によってはコードに変更を加え、再コンパイルせずにデバッグを続行したりすることができます。 詳しくは、「[Visual Studio でのデバッグ](/visualstudio/debugger/debugging-in-visual-studio)」をご覧ください。

## <a name="deploy-completed-applications"></a>完成したアプリケーションの配置

UWP アプリは、Microsoft Store の **[プロジェクト]** > **[ストア]** メニュー オプションを通じて顧客向けに配置できます。 CRT の配置は、水面下で自動的に処理されます。 詳細については、「[Publish Windows apps and games](/windows/uwp/publish/)」(Windows のアプリとゲームを公開する) を参照してください。

ネイティブ C++ デスクトップ アプリケーションを別のコンピューターに配置する場合、アプリケーション自体と、そのアプリケーションが依存するすべてのライブラリ ファイルをインストールする必要があります。 アプリケーションと共にユニバーサル C++ ランタイム (UCRT) を配置する方法として、集中配置、ローカル配置、静的リンクの 3 とおりの方法があります。 詳細については、「[デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)」を参照してください。

C++/CLI プログラムの配置について詳しくは、「[配置ガイド (開発者向け)](/dotnet/framework/deployment/deployment-guide-for-developers)」を参照してください。

## <a name="related-articles"></a>関連トピック

|||
|-|-|
|[さまざまな Visual Studio エディションの Visual C++ ツールおよび機能](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)|Visual Studio の各種エディションで使用可能な機能が表示されます。|
|[MSBuild ベースのプロジェクトの作成と管理](../ide/creating-and-managing-visual-cpp-projects.md)|Visual Studio の C++ MSBuild ベースのプロジェクトの概要と、それらを作成し、管理する方法を説明する他の記事へのリンクが示されます。|
|[Visual C++ の CMake プロジェクト](cmake-tools-for-visual-cpp.md)。|Visual C++ で CMake や他の非 MSBuild プロジェクトをビルドする方法について説明します。|
|[C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)|C++ プロジェクトの作成方法について説明します。|
|[デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)|C++ アプリケーションの配置の概要と、配置について詳しく説明する他の記事へのリンクが示されます。|
|[Visual C++ 移植とアップグレードのガイド](../porting/visual-cpp-porting-and-upgrading-guide.md)|Visual Studio の旧バージョンで作成された C++ アプリケーションをアップグレードする方法と、Visual Studio 以外のツールを使用して作成されたアプリケーションを移行する方法について詳しく説明します。|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual Studio での Visual C++ の主な機能について説明し、他の Visual C++ ドキュメントへのリンクを示します。|
