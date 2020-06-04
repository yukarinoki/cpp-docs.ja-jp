---
title: Visual Studio の CMake プロジェクト
description: Visual Studio で CMake を使用して C++ プロジェクトを作成およびビルドする方法。
ms.date: 01/08/2020
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: 49ba53eaa8ac075ab6d3b2a66f33160c5c3ec410
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329158"
---
# <a name="cmake-projects-in-visual-studio"></a>Visual Studio の CMake プロジェクト

CMake は、複数のプラットフォームで動作するビルド プロセスを定義するためのクロスプラットフォームのオープン ソース ツールです。 この記事は、CMake についてよく理解されていることを前提としています。 詳細については、「[Build, Test and Package Your Software With CMake](https://cmake.org/)」 (CMake を使用してソフトウェアをビルド、テスト、パッケージ化する) を参照してください。

> [!NOTE]
> CMake は、過去数回のリリースで Visual Studio とより一層緊密に統合されてきました。 優先するバージョンの Visual Studio のドキュメントを表示するには、 **[バージョン]** セレクター コントロールを使用します。 このページの目次の一番上にあります。

::: moniker range="vs-2019"

**Windows 用 C++ CMake ツール** コンポーネントでは、[フォルダーを開く](open-folder-projects-cpp.md)機能を使用して、IntelliSense および参照の目的で、CMake プロジェクト ファイル (*CMakeLists.txt* など) を直接使用します。 Ninja と Visual Studio ジェネレーターはどちらもサポートされています。 Visual Studio ジェネレーターを使用すると、一時プロジェクト ファイルが生成され、msbuild.exe に渡されます。 ただし、プロジェクトが IntelliSense や参照の目的で読み込まれることはありません。 また、既存の CMake キャッシュをインポートすることもできます。

## <a name="installation"></a>インストール

**Windows 用 C++ CMake ツール**は、**C++ によるデスクトップ開発**および **C++ による Linux 開発**のワークロードの一部としてインストールされます。 詳細については、[クロスプラットフォーム CMake プロジェクト](../linux/cmake-linux-project.md)に関するページを参照してください。

![C++ デスクトップ ワークロードでの CMake コンポーネント](media/cmake-install-2019.png)

詳細については、「[Install the C++ Linux workload in Visual Studio](../linux/download-install-and-setup-the-linux-development-workload.md)」(Visual Studio で C++ の Linux ワークロードをインストールする) を参照してください。

## <a name="ide-integration"></a>IDE の統合

**[ファイル] > [開く] > [フォルダー]** を選択して、*CMakeLists.txt* ファイルを含むフォルダーを開くと、次の処理が行われます。

- Visual Studio は、CMake スクリプトを表示および編集するためのコマンドを含む **CMake** 項目を、 **[プロジェクト]** メニューに追加します。

- **ソリューション エクスプローラー**に、フォルダーの構造とファイルが表示されます。

- Visual Studio は cmake.exe を実行して、既定の (x64 デバッグ) 構成用の CMake キャッシュ ファイル (*CMakeCache.txt*) を生成します。 CMake コマンド ラインおよび CMake からの追加出力が、**出力ウィンドウ**に表示されます。

- Visual Studio は、IntelliSense、情報の参照、リファクタリングなどを有効にするためのソース ファイルのインデックス付けを、バックグラウンドで開始します。 ユーザーが作業を行っている間、Visual Studio は、エディターおよびディスク上での変更を監視し、インデックスとソースの同期を維持します。

開くフォルダーに含まれる CMake プロジェクトの数は制限されていません。 Visual Studio は、ワークスペース内にあるすべての "ルート" *CMakeLists.txt* ファイルを検出して構成します。 CMake の操作 (構成、ビルド、デバッグ)、C++ の IntelliSense、および参照は、ワークスペース内のすべての CMake プロジェクトで使用できます。

![複数のルートを持つ CMake プロジェクト](media/cmake-multiple-roots.png)

ターゲットごとに論理的にまとめられたプロジェクトを参照することも可能です。 **ソリューション エクスプローラー** ツールバーのドロップダウンから、 **[ターゲット ビュー]** を選択します。

![CMake ターゲット ビュー ボタン](media/cmake-targets-view.png)

**ソリューション エクスプローラー**の上部にある **[すべてのファイルの表示]** ボタンをクリックして、*out/build/\<config >* フォルダー内の CMake で生成されたすべての出力を表示します。

Visual Studio では **CMakeSettings.json** という構成ファイルを使用します。 このファイルを使用すると、複数のビルド構成を定義して格納し、IDE 内でそれらを簡単に切り替えることができます。 "*構成*" は、特定のビルドの種類に固有の設定をカプセル化する Visual Studio のコンストラクトです。 この設定は、Visual Studio が cmake.exe に渡す既定のコマンド ライン オプションを構成するために使用されます。 ここで追加の CMake オプションを指定し、必要に応じて追加の変数を定義することもできます。 すべてのオプションは、内部または外部変数として CMake キャッシュに書き込まれます。 Visual Studio 2019 では、設定を編集する便利な方法が **CMake 設定エディター**で提供されます。 詳細については、「[Customize CMake settings](customize-cmake-settings.md)」 (CMake 設定のカスタマイズ) を参照してください。

1 つの設定である `intelliSenseMode` は CMake に渡されず、Visual Studio でのみ使用されます。

**CMakeLists.txt** ファイルは、任意の CMake プロジェクトの場合と同様に、各プロジェクト フォルダーで使用します。 ソース ファイルの指定、ライブラリの検索、コンパイラおよびリンカーのオプションの設定、その他のビルド システムの関連情報の指定を行うことができます。

デバッグ時に実行可能ファイルに引数を渡す場合は、**launch.vs.json** という別のファイルを使用できます。 場合によっては、これらのファイルは Visual Studio によって自動的に生成されます。 それらを手動で編集することも、自分でファイルを作成することもできます。

> [!NOTE]
> 他の種類の "フォルダーを開く" プロジェクトには、さらに 2 つの JSON ファイルが使用されます。**CppProperties.json** と **tasks.vs.json** です。 これらはいずれも CMake プロジェクトには関連していません。

## <a name="open-an-existing-cache"></a>既存のキャッシュを開く

既存の CMake キャッシュ ファイル (*CMakeCache.txt*) を開くと、Visual Studio によるキャッシュとビルド ツリーの管理は行われません。 カスタムまたは好みのツールにより、CMake でのプロジェクトの構成方法を完全に制御できます。 Visual Studio で既存のキャッシュを開くには、 **[ファイル] > [開く] > [CMake]** を選択します。 次に、既存の *CMakeCache.txt* ファイルに移動します。

開いているプロジェクトに既存の CMake キャッシュを追加できます。 これは、新しい構成を追加する場合と同じ方法で行います。 詳細については、[Visual Studio で既存のキャッシュを開くこと](https://devblogs.microsoft.com/cppblog/open-existing-cmake-caches-in-visual-studio/)に関するブログ記事を参照してください。

## <a name="building-cmake-projects"></a>CMake プロジェクトのビルド

CMake プロジェクトをビルドするには、次の選択肢があります。

1. [全般] ツールバーで、 **[構成]** ドロップダウンを見つけます。 既定では、おそらく "x64-Debug" が表示されます。 対象の構成を選択して、**F5** キーを押すか、ツールバーの **[実行]** (緑色の三角形) ボタンをクリックします。 Visual Studio ソリューションと同じように、プロジェクトは最初に自動的にビルドされます。

1. *CMakeLists.txt* を右クリックして、コンテキスト メニューから **[ビルド]** を選択します。 フォルダー構造内に複数のターゲットがある場合は、すべてをビルドするか、特定の 1 つのターゲットだけをビルドするかを選べます。

1. メイン メニューから、 **[ビルド] > [すべてビルド]** (**F7** または **Ctrl + Shift + B** キー) を選択します。 **[全般]** ツール バーの **[スタートアップ アイテム]** ドロップダウンで CMake ターゲットが既に選択されていることを確認します。

![CMake のビルド メニュー コマンド](media/cmake-build-menu.png "CMake のビルド コマンド メニュー")

想像したとおり、ビルド結果が**出力ウィンドウ**と**エラー一覧**に表示されます。

![CMake ビルド エラー](media/cmake-build-errors.png "CMake ビルド エラー")

複数のビルド ターゲットがあるフォルダーでは、ビルドする CMake ターゲットを指定できます。 **[CMake]** メニューまたは *CMakeLists.txt* のコンテキスト メニューの **[ビルド]** 項目を選択して、ターゲットを指定します。 CMake プロジェクトで **Ctrl + Shift + B** を入力すると、現在アクティブなドキュメントがビルドされます。

## <a name="debugging-cmake-projects"></a>CMake プロジェクトのデバッグ

CMake プロジェクトをデバッグするには、対象の構成を選択して、**F5** キーを押すか、またはツール バーの **[実行]** ボタンを押します。 **[実行]** ボタンに [スタートアップ アイテムの選択] と表示されている場合は、ドロップダウンの矢印を選択します。 実行するターゲットを選択します。 (CMake プロジェクトでは、[現在のドキュメント] オプションは .cpp ファイルの場合にのみ有効です)。

![CMake の実行ボタン](media/cmake-run-button.png "CMake の実行ボタン")

**[実行]** または **F5** コマンドを選ぶと、前回のビルドの後で何かが変更されている場合は、最初にプロジェクトがビルドされます。 *CMakeSettings.json* を変更すると、CMake キャッシュが再生成されます。

**launch.vs.json** ファイルでプロパティを設定することで、CMake デバッグ セッションをカスタマイズすることができます。 詳細については、[CMake デバッグ セッションの構成](configure-cmake-debugging-sessions.md)に関するページを参照してください。

## <a name="just-my-code-for-cmake-projects"></a>CMake プロジェクトのマイ コードのみ

MSVC コンパイラを使用して Windows 用にビルドすると、CMake プロジェクトでマイ コードのみデバッグがサポートされます。 [マイ コードのみ] 設定を変更するには、 **[ツール]**  >  **[オプション]**  >  **[デバッグ]**  >  **[全般]** に移動します。

## <a name="vcpkg-integration"></a>Vcpkg の統合

[vcpkg](vcpkg.md) をインストールした場合、Visual Studio で開かれた CMake プロジェクトは、vcpkg ツールチェーン ファイルを自動的に統合します。 つまり、CMake プロジェクトで vcpkg を使用するために追加の構成は必要ありません。 このサポートは、ローカル vcpkg インストールと、対象としているリモート システム上の vcpkg インストールの両方に対して有効です。 CMake 設定の構成でその他のツールチェーンを指定すると、この動作は自動的に無効になります。

## <a name="customize-configuration-feedback"></a>構成に関するフィードバックをカスタマイズする

既定では、エラーが発生しない限り、ほとんどの構成メッセージが抑制されます。 **[ツール]**  >  **[オプション]**  >  **[CMake]** の次の機能を有効にすることで、すべてのメッセージを表示できます。

   ![CMake の診断オプションの構成](media/vs2019-cmake-configure-options.png "CMake の診断オプション")

## <a name="editing-cmakeliststxt-files"></a>CMakeLists.txt ファイルの編集

*CMakeLists.txt* ファイルを編集するには、**ソリューション エクスプローラー**でファイルを右クリックして、 **[開く]** を選択します。 ファイルを変更すると、黄色いステータス バーが表示され、IntelliSense が更新されることが示されます。 ここで更新操作を取り消すことができます。 *CMakeLists.txt* については、[CMake のドキュメント](https://cmake.org/documentation/)をご覧ください。

   ![CMakeLists.txt ファイルの編集](media/cmake-cmakelists.png "CMakeLists.txt ファイルの編集")

ファイルを保存するとすぐに構成手順が自動的に再び実行され、 **[出力]** ウィンドウに情報が表示されます。 エラーと警告は、 **[エラー一覧]** または **[出力]** ウィンドウに表示されます。 **[エラー一覧]** でエラーをダブルクリックすると、*CMakeLists.txt* 内の問題のある行に移動します。

   ![CMakeLists.txt ファイルのエラー](media/cmake-cmakelists-error.png "CMakeLists.txt ファイルのエラー")

## <a name="cmake-configure-step"></a>CMake の構成ステップ

*CMakeSettings.json* または *CMakeLists.txt* ファイルを大幅に変更すると、Visual Studio で CMake の構成ステップが自動的に再実行されます。 構成ステップがエラーなしで完了すると、収集された情報が、C++ IntelliSense および言語のサービスで使用できるようになります。 ビルドおよびデバッグの操作でも使用されます。

## <a name="troubleshooting-cmake-cache-errors"></a>CMake キャッシュ エラーのトラブルシューティング

問題を診断するために CMake キャッシュの状態に関する詳しい情報が必要な場合は、 **[プロジェクト]** メイン メニュー、または**ソリューション エクスプローラー**で *CMakeLists.txt* のコンテキスト メニューを開き、次のコマンドのいずれかを実行します。

- **[キャッシュの表示]** は、ビルド ルート フォルダーの *CMakeCache.txt* ファイルをエディターで開きます。 (ここで *CMakeCache.txt* に対して編集した内容はすべて、キャッシュを消去するとワイプされます。 キャッシュが消去された後も存続する変更を行うには、「[CMake 設定をカスタマイズする](customize-cmake-settings.md)」を参照してください。)

- **[キャッシュ フォルダーを開く]** は、エクスプローラー ウィンドウでビルド ルート フォルダーを開きます。

- **[キャッシュをクリーン]** は、次の CMake 構成ステップがクリーンなキャッシュから開始されるように、ビルド ルート フォルダーを削除します。

- **[キャッシュを生成]** は、Visual Studio が環境は最新の状態であると判断した場合でも、生成ステップを強制的に実行します。

キャッシュの自動生成は、 **[ツール] > [オプション] > [CMake] > [全般]** ダイアログで無効にできます。

## <a name="run-cmake-from-the-command-line"></a>コマンド ラインから CMake を実行する

Visual Studio インストーラーから CMake をインストールした場合は、次の手順に従ってコマンド ラインから実行できます。

1. 適切な vsdevcmd.bat (x86 または x64) を実行します。 詳細については、[コマンド ラインでのビルド](building-on-the-command-line.md)に関するページを参照してください。

1. 出力フォルダーに移動します。

1. CMake を実行してアプリをビルド/構成します。

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 2017 では、[クロスプラットフォーム CMake プロジェクト](../linux/cmake-linux-project.md)など、CMake のサポートが充実しています。 **CMake の Visual C++ ツール** コンポーネントでは、**フォルダーを開く**機能を使用して、IntelliSense および参照の目的で、IDE が CMake プロジェクト ファイル (*CMakeLists.txt* など) を直接使用できるようにします。 Ninja と Visual Studio ジェネレーターはどちらもサポートされています。 Visual Studio ジェネレーターを使用すると、一時プロジェクト ファイルが生成され、msbuild.exe に渡されます。 ただし、プロジェクトが IntelliSense や参照の目的で読み込まれることはありません。 また、既存の CMake キャッシュをインポートすることもできます。

## <a name="installation"></a>インストール

**CMake の Visual C++ ツール**は、**C++ によるデスクトップ開発**および **C++ による Linux 開発**のワークロードの一部としてインストールされます。

![C++ デスクトップ ワークロードでの CMake コンポーネント](media/cmake-install.png)

詳細については、「[Install the C++ Linux workload in Visual Studio](../linux/download-install-and-setup-the-linux-development-workload.md)」(Visual Studio で C++ の Linux ワークロードをインストールする) を参照してください。

## <a name="ide-integration"></a>IDE 統合

**[ファイル] > [開く] > [フォルダー]** を選択して、*CMakeLists.txt* ファイルを含むフォルダーを開くと、次の処理が行われます。

- Visual Studio は、CMake スクリプトを表示および編集するためのコマンドを含む **[CMake]** メニュー項目を、メイン メニューに追加します。

- **ソリューション エクスプローラー**に、フォルダーの構造とファイルが表示されます。

- Visual Studio は CMake.exe を実行して、既定の "*構成*" (x86 デバッグ) 用の CMake キャッシュをオプションで生成します。 CMake コマンド ラインおよび CMake からの追加出力が、**出力ウィンドウ**に表示されます。

- Visual Studio は、IntelliSense、情報の参照、リファクタリングなどを有効にするためのソース ファイルのインデックス付けを、バックグラウンドで開始します。 ユーザーが作業を行っている間、Visual Studio は、エディターおよびディスク上での変更を監視し、インデックスとソースの同期を維持します。

開くフォルダーに含まれる CMake プロジェクトの数は制限されていません。 Visual Studio は、ワークスペース内にあるすべての "ルート" *CMakeLists.txt* ファイルを検出して構成します。 CMake の操作 (構成、ビルド、デバッグ)、C++ の IntelliSense、および参照は、ワークスペース内のすべての CMake プロジェクトで使用できます。

![複数のルートを持つ CMake プロジェクト](media/cmake-multiple-roots.png)

ターゲットごとに論理的にまとめられたプロジェクトを参照することも可能です。 **ソリューション エクスプローラー** ツールバーのドロップダウンから、 **[ターゲット ビュー]** を選択します。

![CMake ターゲット ビュー ボタン](media/cmake-targets-view.png)

Visual Studio は *CMakeSettings.json* というファイルを使用して、環境変数や Cmake.exe のコマンド ライン オプションを格納します。 *CMakeSettings.json* では、複数の CMake ビルド構成を定義して格納することもできます。 それらは IDE 内で簡単に切り替えることができます。

そうでない場合は、任意の CMake プロジェクトと同じように *CMakeLists.txt* を使用してソース ファイルを指定し、ライブラリを見つけ、コンパイラとリンカーのオプションを設定し、その他のビルド システムの関連情報を指定します。

デバッグ時に実行可能ファイルに引数を渡す必要がある場合は、**launch.vs.json** という別のファイルを使用できます。 場合によっては、これらのファイルは Visual Studio によって自動的に生成されます。 それらを手動で編集することも、自分でファイルを作成することもできます。

> [!NOTE]
> 他の種類の "フォルダーを開く" プロジェクトには、さらに 2 つの JSON ファイルが使用されます。**CppProperties.json** と **tasks.vs.json** です。 これらはいずれも CMake プロジェクトには関連していません。

## <a name="import-an-existing-cache"></a>既存のキャッシュをインポートする

既存の *CMakeCache.txt* ファイルをインポートすると、Visual Studio ではカスタマイズされた変数が自動的に抽出され、それを基にして事前設定済みの *CMakeSettings.json* ファイルが作成されます。 元のキャッシュは、いかなる形でも変更されません。 これは、引き続きコマンド ラインから使用することも、その生成に使用したツールまたは IDE で使用することもできます。 新しい *CMakeSettings.json* ファイルは、プロジェクトのルート *CMakeLists.txt* と共に配置されます。 Visual Studio は、設定ファイルに基づいて新しいキャッシュを生成します。 キャッシュの自動生成は、 **[ツール] > [オプション] > [CMake] > [全般]** ダイアログでオーバーライドできます。

キャッシュ内のすべてのものがインポートされるわけではありません。  ジェネレーターや、コンパイラの場所などのプロパティは、IDE で問題なく機能することがわかっている既定値に置き換えられます。

### <a name="to-import-an-existing-cache"></a>既存のキャッシュをインポートするには

1. メイン メニューから **[ファイル] > [開く] > [CMake]** を選択します。

   ![CMake を開く](media/cmake-file-open.png "ファイル、開く、CMake")

   このコマンドにより、**キャッシュからの CMake のインポート** ウィザードが起動します。

2. インポートする *CMakeCache.txt* ファイルに移動して、 **[OK]** をクリックします。 **[キャッシュから CMake のプロジェクトをインポートします]** ウィザードが表示されます。

   ![CMake キャッシュのインポート](media/cmake-import-wizard.png "CMake キャッシュ インポート ウィザードを開く")

   ウィザードが完了すると、**ソリューション エクスプローラー**でプロジェクトのルート *CMakeLists.txt* ファイルの隣に新しい *CMakeCache.txt* ファイルが表示されます。

## <a name="building-cmake-projects"></a>CMake プロジェクトのビルド

CMake プロジェクトをビルドするには、次の選択肢があります。

1. [全般] ツールバーで、 **[構成]** ドロップダウンを見つけます。 既定では、おそらく "Linux-Debug" または "x64-Debug" が表示されます。 対象の構成を選択して、**F5** キーを押すか、ツールバーの **[実行]** (緑色の三角形) ボタンをクリックします。 Visual Studio ソリューションと同じように、プロジェクトは最初に自動的にビルドされます。

1. *CMakeLists.txt* を右クリックして、コンテキスト メニューから **[ビルド]** を選択します。 フォルダー構造内に複数のターゲットがある場合は、すべてをビルドするか、特定の 1 つのターゲットだけをビルドするかを選べます。

1. メイン メニューから、 **[ビルド] > [ソリューションのビルド]** (**F7** または **Ctrl + Shift + B** キー) を選択します。 **[全般]** ツール バーの **[スタートアップ アイテム]** ドロップダウンで CMake ターゲットが既に選択されていることを確認します。

![CMake のビルド メニュー コマンド](media/cmake-build-menu.png "CMake のビルド コマンド メニュー")

*CMakeSettings.json* ファイル内のビルド構成、環境変数、コマンド ライン引数、およびその他の設定をカスタマイズできます。 これにより、*CMakeLists.txt* ファイルを変更することなく、変更を行うことができます。 詳細については、「[Customize CMake settings](customize-cmake-settings.md)」 (CMake 設定のカスタマイズ) を参照してください。

想像したとおり、ビルド結果が**出力ウィンドウ**と**エラー一覧**に表示されます。

![CMake ビルド エラー](media/cmake-build-errors.png "CMake ビルド エラー")

複数のビルド ターゲットがあるフォルダーでは、ビルドする CMake ターゲットを指定できます。 **[CMake]** メニューまたは *CMakeLists.txt* のコンテキスト メニューの **[ビルド]** 項目を選択して、ターゲットを指定します。 CMake プロジェクトで **Ctrl + Shift + B** を入力すると、現在アクティブなドキュメントがビルドされます。

## <a name="debugging-cmake-projects"></a>CMake プロジェクトのデバッグ

CMake プロジェクトをデバッグするには、対象の構成を選択して、**F5** キーを押します。 または、ツール バーの **[実行]** ボタンを押します。 **[実行]** ボタンに [スタートアップ アイテムの選択] と表示されている場合は、ドロップダウン矢印を選んで、実行するターゲットを選びます (CMake プロジェクトでは、[現在のドキュメント] オプションは .cpp ファイルの場合にのみ有効です)。

![CMake の実行ボタン](media/cmake-run-button.png "CMake の実行ボタン")

**[実行]** または **F5** コマンドを選ぶと、前回のビルドの後で何かが変更されている場合は、最初にプロジェクトがビルドされます。

**launch.vs.json** ファイルでプロパティを設定することで、CMake デバッグ セッションをカスタマイズすることができます。 詳細については、[CMake デバッグ セッションの構成](configure-cmake-debugging-sessions.md)に関するページを参照してください。

## <a name="editing-cmakeliststxt-files"></a>CMakeLists.txt ファイルの編集

*CMakeLists.txt* ファイルを編集するには、**ソリューション エクスプローラー**でファイルを右クリックして、 **[開く]** を選択します。 ファイルを変更すると、黄色いステータス バーが表示され、IntelliSense が更新されることが示されます。 ここで更新操作を取り消すことができます。 *CMakeLists.txt* については、[CMake のドキュメント](https://cmake.org/documentation/)をご覧ください。

   ![CMakeLists.txt ファイルの編集](media/cmake-cmakelists.png "CMakeLists.txt ファイルの編集")

ファイルを保存するとすぐに構成手順が自動的に再び実行され、 **[出力]** ウィンドウに情報が表示されます。 エラーと警告は、 **[エラー一覧]** または **[出力]** ウィンドウに表示されます。 **[エラー一覧]** でエラーをダブルクリックすると、*CMakeLists.txt* 内の問題のある行に移動します。

   ![CMakeLists.txt ファイルのエラー](media/cmake-cmakelists-error.png "CMakeLists.txt ファイルのエラー")

## <a name="cmake-configure-step"></a>CMake の構成ステップ

*CMakeSettings.json* または *CMakeLists.txt* ファイルが大幅に変更されると、Visual Studio で CMake の構成ステップが自動的に再実行されます。 構成ステップがエラーなしで完了すると、収集された情報が、C++ IntelliSense および言語のサービスで使用できるようになります。 ビルドおよびデバッグの操作でも使用されます。

複数の CMake プロジェクトで、同じ CMake 構成名 (x86-Debug など) を使用できます。 その構成が選択されると、これらのすべてが構成され、(独自のビルド ルート フォルダー内で) ビルドされます。 その CMake 構成に参加しているすべての CMake プロジェクトから、ターゲットをデバッグすることができます。

   ![CMake の [ビルドのみ] メニュー項目](media/cmake-build-only.png "CMake の [ビルドのみ] メニュー項目")

ビルドとデバッグのセッションは、ワークスペース内のプロジェクトのサブセットに制限できます。 *CMakeSettings.json* ファイルに一意の名前を持つ新しい構成を作成します。 その後、これらのプロジェクトにのみ構成を適用します。 その構成が選択されると、IntelliSense およびビルドとデバッグの両コマンドは、指定されているプロジェクトにのみ適用されます。

## <a name="troubleshooting-cmake-cache-errors"></a>CMake キャッシュ エラーのトラブルシューティング

問題を診断するために CMake キャッシュの状態に関する詳しい情報が必要な場合は、**CMake** のメイン メニューまたは**ソリューション エクスプローラー**で *CMakeLists.txt* のコンテキスト メニューを開き、次のコマンドのいずれかを実行します。

- **[キャッシュの表示]** は、ビルド ルート フォルダーの *CMakeCache.txt* ファイルをエディターで開きます (ここで *CMakeCache.txt* に対して編集した内容はすべて、キャッシュを消去するとワイプされます。 キャッシュが消去された後も存続する変更を行うには、「[CMake 設定をカスタマイズする](customize-cmake-settings.md)」を参照してください。)

- **[キャッシュ フォルダーを開く]** は、エクスプローラー ウィンドウでビルド ルート フォルダーを開きます。

- **[キャッシュをクリーン]** は、次の CMake 構成ステップがクリーンなキャッシュから開始されるように、ビルド ルート フォルダーを削除します。

- **[キャッシュを生成]** は、Visual Studio が環境は最新の状態であると判断した場合でも、生成ステップを強制的に実行します。

キャッシュの自動生成は、 **[ツール] > [オプション] > [CMake] > [全般]** ダイアログで無効にできます。

## <a name="single-file-compilation"></a>単一ファイルのコンパイル

CMake プロジェクトで単一ファイルをビルドするには、**ソリューション エクスプローラー**でファイルを右クリックします。 ポップアップ メニューから **[コンパイル]** を選択します。 メインの **[CMake]** メニューを使用すると、エディターで現在開いているファイルをビルドすることも可能です。

![CMake の単一ファイルのコンパイル](media/cmake-single-file-compile.png)

## <a name="run-cmake-from-the-command-line"></a>コマンド ラインから CMake を実行する

Visual Studio インストーラーから CMake をインストールした場合は、次の手順に従ってコマンド ラインから実行できます。

1. 適切な vsdevcmd.bat (x86 または x64) を実行します。 詳細については、[コマンド ラインでのビルド](building-on-the-command-line.md)に関するページを参照してください。

1. 出力フォルダーに移動します。

1. CMake を実行してアプリをビルド/構成します。

::: moniker-end

::: moniker range="vs-2015"

Visual Studio 2015 では、Visual Studio のユーザーは [CMake ジェネレーター](https://cmake.org/cmake/help/latest/manual/cmake-generators.7.html)を使って MSBuild プロジェクト ファイルを生成し、IDE はそのファイルを IntelliSense、参照、およびコンパイルに使っていました。

::: moniker-end

## <a name="see-also"></a>関連項目

[チュートリアル: Visual Studio で C++ クロスプラットフォーム プロジェクトを作成する](get-started-linux-cmake.md)\
[Linux CMake プロジェクトを構成する](../linux/cmake-linux-project.md)\
[リモートの Linux コンピューターに接続する](../linux/connect-to-your-remote-linux-computer.md)\
[CMake のビルド設定をカスタマイズする](customize-cmake-settings.md)\
[CMakeSettings.json スキーマ リファレンス](cmakesettings-reference.md)\
[CMake デバッグ セッションを構成する](configure-cmake-debugging-sessions.md)\
[Linux プロジェクトの配置、実行、デバッグ](../linux/deploy-run-and-debug-your-linux-project.md)\
[CMake 定義済み構成リファレンス](cmake-predefined-configuration-reference.md)
