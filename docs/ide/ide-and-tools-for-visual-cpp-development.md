---
title: IDE と Visual C 開発用ツール |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 02215cd585bf1644b5b01f779dd8ff46322c9181
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ide-and-tools-for-visual-c-development"></a>IDE と Visual C++ 開発用ツール

一部の Visual Studio 統合開発環境 (IDE)、としては、Microsoft Visual C++ (MSVC) は、さまざまなウィンドウやその他の言語と共通のツールを共有します。 などの多く**ソリューション エクスプ ローラー**、コード エディターと、デバッガーが下に記載されている[Visual Studio IDE](/visualstudio/ide/visual-studio-ide)です。 共有ツールやウィンドウの機能は C++ と、.NET 言語や Javascript とで若干異なることがよくあります。 一部のウィンドウやツールは、Visual Studio Pro または Visual Studio Enterprise でのみ使用できます。

共有ツールに加えて、Visual Studio IDE で、MSVC はネイティブ コードの開発を具体的にはいくつかのツールがします。 この記事には、これらのツールの一覧も掲載します。 そのうちツールは Visual Studio の各エディションで利用可能な一覧は、次を参照してください。 [Visual c ツールおよび Visual Studio のエディションで機能](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)します。

## <a name="creating-a-solution-and-projects"></a>ソリューションとプロジェクトの作成

A*プロジェクト*一連のソース コード ファイルと、実行可能ファイルに組み込まれているイメージやデータのファイルなどのリソースは、基本的にします。 Visual Studio 2017 には、すべてのビルド システムまたは使用し、Intellisense、閲覧とデバッグを完全にサポートするカスタム ビルド ツールをサポートできます。

- MSBuild は Visual Studio のネイティブのビルド システムとユニバーサル Windows プラットフォーム (UWP) アプリまたは MFC または ATL を使用する従来の Windows デスクトップ アプリケーションに最適な選択肢では多くの場合 MSBuild ベースの C++ プロジェクトの詳細については、次を参照してください。[の作成とプロジェクトの MSBuild ベースの管理](creating-and-managing-visual-cpp-projects.md)です。
- CMake は、クロス プラットフォーム ビルドは、C++ のワークロードでデスクトップの開発をインストールするときに、Visual Studio IDE に統合されているシステムです。 詳細については、「[CMake projects in Visual C++ (Visual C++ の CMake プロジェクト)](cmake-tools-for-visual-cpp.md)」をご覧ください。
- フォルダーを開く機能を使用してその他の C++ ビルド システム、ファイルの厳密でないコレクションを含むがサポートされています。 ビルドのプログラムを起動し、デバッグ セッションを構成する単純な JSON ファイルを作成します。 詳細については、次を参照してください。 [、C++ コードを Visual Studio に取り込む](https://blogs.msdn.microsoft.com/vcblog/2017/04/14/bring-your-cpp-code-to-visual-studio/)です。

### <a name="project-templates-msbuild"></a>プロジェクト テンプレート (MSBuild)

Visual Studio のプロジェクトの MSBuild ベース; いくつかのテンプレートが付属します。このテンプレートには、スタート コードは、さまざまな種類の基本的なプログラムに必要な設定が含まれています。 通常は、まずを選択して**ファイル** > **新しいプロジェクト**プロジェクト テンプレートからプロジェクトを作成するにし、そのプロジェクトに新しいソース コード ファイルを追加または提供されているファイルでコーディングを開始します。 C++ プロジェクトやプロジェクト ウィザードに固有の情報を参照してください。 [Visual c プロジェクトの管理の作成と](../ide/creating-and-managing-visual-cpp-projects.md)です。

### <a name="application-wizards-msbuild"></a>アプリケーション ウィザード (MSBuild)

Visual Studio では、ウィザードによって MSBuild プロジェクトの種類を選択すると**ファイル** > **新しいプロジェクト**です。 このウィザードの手順に従って、新しいプロジェクトの作成プロセスを実行します。 これは、オプションや設定が多いプロジェクトの種類の場合に便利です。 詳細については、次を参照してください。[作成デスクトップ プロジェクトでアプリケーション ウィザードを使用した](../ide/creating-desktop-projects-by-using-application-wizards.md)です。

## <a name="creating-user-interfaces-with-designers-msbuild"></a>デザイナー (MSBuild) によるユーザー インターフェイスの作成

プログラムにユーザー インターフェイスがある場合、まずそのインターフェイスにボタン、リスト ボックスなどのコントロールを設定します。 Visual Studio には、C++ アプリケーションの種類ごとに、ビジュアル デザイン領域とツールボックスが含まれています。 どの種類のアプリを作成している場合であっても、[ツールボックス] ウィンドウからコントロールをドラッグして、目的の場所にあるデザイン領域にドロップするという基本的な概念は同じです。 Visual Studio は、バック グラウンドで、リソースとそれらすべてを正常に動作させるために必要なコードを生成します。 コントロールにデータを表示したり、外観と動作をカスタマイズするコードを記述します。

ユニバーサル Windows プラットフォーム アプリのユーザー インターフェイスの設計の詳細については、次を参照してください。[デザインと UI](https://developer.microsoft.com/en-us/windows/design)です。

MFC アプリケーションのユーザー インターフェイスの作成の詳細については、次を参照してください。 [MFC デスクトップ アプリケーション](../mfc/mfc-desktop-applications.md)です。 Win32 Windows プログラムについては、次を参照してください。 [Windows デスクトップ アプリケーション](../windows/windows-desktop-applications-cpp.md)です。

## <a name="writing-and-editing-code"></a>作成とコードの編集

### <a name="semantic-colorization"></a>セマンティクスの色づけ

プロジェクトを作成すると、すべてのプロジェクト ファイルが表示される、**ソリューション エクスプ ローラー**ウィンドウです。 .H または .cpp ファイルをクリックすると**ソリューション エクスプ ローラー**、コード エディターでファイルを開きます。 コード エディターは、C++ ソース コード専用のワード プロセッサです。 このエディターでは、コードを読みやすく理解しやすいものにするために、言語のキーワード、メソッド名と変数名、およびその他のコードの要素が色分けされます。

### <a name="intellisense"></a>Intellisense

コード エディターでは、Intellisense と呼ばれるいくつかの機能もサポートしています。 メソッドの上にポインターを合わせると、そのメソッドに関するいくつかの基本的な情報を参照できます。 クラスの変数名と . または -> を入力すると、 そのクラスのインスタンス メンバーの一覧が表示されます。 クラス名に続けて :: と入力すると、静的メンバーの一覧が表示されます。 クラスやメソッドの名前を入力し始めると、コード エディターが完全なステートメントの候補を表示します。 詳細については、「[IntelliSense の使用](/visualstudio/ide/using-intellisense)」を参照してください。

### <a name="code-snippets"></a>コード スニペット

Intellisense コード スニペットを使用すると、ショートカット キーを入力して、一般的に使用されるコード構造や複雑なコード構造を生成できます。 詳細については、「[Code Snippets](/visualstudio/ide/code-snippets)」を参照してください。

## <a name="navigating-code"></a>コード間の移動

**ビュー**メニューは、コード ファイル内をナビゲートするためのさまざまなウィンドウやツールへのアクセスを提供します。 これらのウィンドウの詳細については、次を参照してください。[コードの構造を表示する](/visualstudio/ide/viewing-the-structure-of-code)です。

### <a name="solution-explorer"></a>ソリューション エクスプローラー

Visual Studio のすべてのエディションで使用して、**ソリューション エクスプ ローラー**プロジェクト内のファイル間を移動するウィンドウです。 .H または .cpp ファイルのアイコンを展開するとファイル内のクラスが表示されます。 クラスを展開するとそのメンバーが表示されます。 メンバーをダブルクリックするとファイル内のそのメンバーの定義や実装に移動します。

### <a name="class-view-and-code-definition-window"></a>クラス ビューおよびコード定義ウィンドウ

使用して、**クラス ビュー**ペインを部分クラスを含むすべてのファイル名前空間とクラスを参照してください。 それぞれの名前空間またはクラスを展開するとそのメンバーが表示され、メンバーをダブルクリックするとソース ファイル内のそのメンバーの場所に移動します。 開く場合、**コード定義ウィンドウ**でそれを選択するときに、定義または型の実装を表示することができます**クラス ビュー**です。

### <a name="object-browser"></a>オブジェクト ブラウザー

使用して**オブジェクト ブラウザー**を Windows ランタイム コンポーネント (.winmd ファイル) の型情報を探索するには、.NET アセンブリおよび COM タイプ ライブラリ。 これは、Win32 の DLL では使用されません。

### <a name="go-to-definitiondeclaration"></a>定義 / 宣言へ移動

API 名またはメンバー変数の上で F12 キーを押して、その定義に移動します。 定義が (は UWP アプリまたは Windows 8.x ストア アプリ) の .winmd ファイルの場合は、オブジェクト ブラウザーの種類の情報が表示されます。 選択することもできます**定義へ移動**または**宣言へ移動**変数または型の名前を右クリックし、コンテキスト メニューからオプションを選択します。

### <a name="find-all-references"></a>[すべての参照の検索]

ソース コード ファイルでは、型メソッド、または変数の名前の上にマウス カーソルを右クリックし、選択**すべての参照の検索**に型が使用されているファイル、プロジェクトまたはソリューション内のすべての場所の一覧を返します。 **すべての参照の検索**はインテリジェントな機能と他の変数の別のスコープで同じ名前である場合でも、同じ変数のインスタンスをのみを返します。

## <a name="add-and-edit-resources--msbuild"></a>追加リソースと編集 (MSBuild)

用語*リソース*デスクトップ プロジェクトには Visual Studio のコンテキストでは、ダイアログ ボックス、アイコン、ローカライズ可能な文字列、スプラッシュ スクリーン、データベース接続文字列、または任意のデータに追加することなどが含まれています、実行可能ファイルです。

追加して、ネイティブ デスクトップ C++ プロジェクトにリソースの編集の詳細については、次を参照してください。[リソース ファイルの操作](../windows/working-with-resource-files.md)です。

## <a name="build-compile-and-link"></a>ビルド (コンパイルおよびリンク)

選択**ビルド** > **ソリューションのビルド**メニュー バー、または、ctrl キーと shift キーを押しながら B キーの組み合わせをコンパイルし、プロジェクトのリンクを入力します。 実行可能コードを作成するための Visual Studio の使用[MSBuild](/visualstudio/msbuild/msbuild1)経由でセットアップする CMake または任意のビルド環境または**フォルダーを開く**です。 MSBuild プロジェクトの下で [全般] ビルド オプションを設定する**ツール** > **オプション** > **プロジェクトおよびソリューション**プロパティを設定することができます特定のプロジェクトの**プロジェクト** > **プロパティ**です。 エラー一覧で、ビルド エラーと警告が報告される (Ctrl +\\E)。 非 MSBuild プロジェクトは、ソリューション エクスプ ローラーで作成する JSON ファイルで構成されます。 すべてのビルドを使用すると、システム、**出力**ウィンドウ (Alt + 2) は、ビルド プロセスの情報を表示します。 MSBuild の構成の詳細については、次を参照してください。[のプロジェクト プロパティの操作](../ide/working-with-project-properties.md)と[Visual Studio での C++ プロジェクトのビルド](../ide/building-cpp-projects-in-visual-studio.md)です。

コンパイラ (cl.exe) およびその他のビルド関連のスタンドアロン ツール NMAKE や LIB など、コマンドラインから直接使用することもできます。 詳細については、次を参照してください。[コマンドラインでビルドの c/c++ コード](../build/building-on-the-command-line.md)と[c/c++ ビルドのリファレンス](../build/reference/c-cpp-building-reference.md)です。

## <a name="test"></a>テスト

Visual Studio には、ネイティブ C++ の単体テスト フレームワークと C++/CLI の単体テスト フレームワークの両方が含まれています。 詳細については、次を参照してください[単体テストを使用したコードの検証](/visualstudio/test/unit-test-your-code)と[単体テストの記述した C++ 用の Microsoft 単体テスト フレームワーク c++。](/visualstudio/test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp)

## <a name="debug"></a>デバッグ

キーを押してプログラムをデバッグできます**f5 キーを押して**デバッグに、プロジェクトの構成を設定するとします。 キーを押してブレークポイントを設定するデバッグ中に**F9**、キーを押してコードをステップ**F10**、指定された変数やレジスタの値を表示およびも場合によってはコードでの変更を行うし、続行再コンパイルせずにデバッグします。 詳しくは、「[Visual Studio でのデバッグ](/visualstudio/debugger/debugging-in-visual-studio)」をご覧ください。

## <a name="deploy-completed-applications"></a>完成したアプリケーションを展開します。

Microsoft ストアを通じて顧客向けに、UWP アプリを展開する、**プロジェクト** > **ストア**メニュー オプション。 CRT の配置は、水面下で自動的に処理されます。 詳細については、「 [アプリの販売](http://go.microsoft.com/fwlink/p/?LinkId=262280)」を参照してください。

ネイティブ C++ デスクトップ アプリケーションを別のコンピューターに配置する場合、アプリケーション自体と、そのアプリケーションが依存するすべてのライブラリ ファイルをインストールする必要があります。 アプリケーションと共にユニバーサル C ランタイム (UCRT) を展開する次の 3 つの方法があります: 集中配置、ローカル配置、または静的にリンクします。 詳細については、次を参照してください。[デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)です。

C + の展開の詳細については +/CLI プログラムを参照してください[開発者向けの展開ガイド](/dotnet/framework/deployment/deployment-guide-for-developers)、

## <a name="related-articles"></a>関連トピック

|||
|-|-|
|[さまざまな Visual Studio エディションの Visual C++ ツールおよび機能](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)|Visual Studio の各種エディションで使用可能な機能が表示されます。|
|[作成して、プロジェクトの MSBuild ベースの管理](../ide/creating-and-managing-visual-cpp-projects.md)|C++ MSBuild ベース Visual Studio プロジェクトを作成し、それらを管理する方法を説明する他の記事へのリンクの概要を示します。|
|[Visual C で CMake プロジェクト](cmake-tools-for-visual-cpp.md)です。|CMake または Visual C では、他の非 MSBuild プロジェクトをビルドする方法について説明します。|
|[C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)|C++ プロジェクトの作成方法について説明します。|
|[デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)|C++ アプリケーションの配置の概要と、配置について詳しく説明する他の記事へのリンクが示されます。|
|[Visual C++ 移植とアップグレードのガイド](../porting/visual-cpp-porting-and-upgrading-guide.md)|Visual Studio 以外のツールを使用して作成されたアプリケーションを移行する方法と、Visual Studio の以前のバージョンで作成された C++ アプリケーションをアップグレードする方法の詳細についてはします。|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual Studio での Visual C++ の主な機能について説明し、他の Visual C++ ドキュメントへのリンクを示します。|
