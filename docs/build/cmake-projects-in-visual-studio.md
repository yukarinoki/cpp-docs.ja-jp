---
title: Visual Studio の CMake プロジェクト
description: Visual Studio で CMake を使用して C++ プロジェクトを作成およびビルドする方法について説明します。
ms.date: 01/08/2020
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: 49ba53eaa8ac075ab6d3b2a66f33160c5c3ec410
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329158"
---
# <a name="cmake-projects-in-visual-studio"></a>Visual Studio の CMake プロジェクト

CMake は、複数のプラットフォームで動作するビルド プロセスを定義するためのクロスプラットフォームのオープン ソース ツールです。 この記事は、CMake についてよく理解していることを前提としています。 詳細については、「[Build, Test and Package Your Software With CMake](https://cmake.org/)」 (CMake を使用してソフトウェアをビルド、テスト、パッケージ化する) を参照してください。

> [!NOTE]
> CMake は、ここ数リリースで Visual Studio との統合がますます増えました。 Visual Studio の優先バージョンのドキュメントを表示するには、**バージョン**セレクター コントロールを使用します。 このページの目次の上部に表示されます。

::: moniker range="vs-2019"

Windows コンポーネント**用の C++ CMake ツール**は[、フォルダーを開く](open-folder-projects-cpp.md)機能を使用して、IntelliSense と参照の目的で CMake プロジェクト ファイル *(CMakeLists.txt*など) を直接使用します。 Ninja と Visual Studio ジェネレーターはどちらもサポートされています。 Visual Studio ジェネレーターを使用すると、一時プロジェクト ファイルが生成され、msbuild.exe に渡されます。 ただし、プロジェクトは、IntelliSense または参照の目的で読み込まれることはありません。 既存の CMake キャッシュをインポートすることもできます。

## <a name="installation"></a>インストール

**Windows 用の C++ CMake ツール**は **、C++ ワークロードを使用したデスクトップ開発**と**Linux 開発**の一環としてインストールされます。 詳細については、「[クロスプラットフォーム CMake プロジェクト](../linux/cmake-linux-project.md)」を参照してください。

![C++ デスクトップ ワークロードでの CMake コンポーネント](media/cmake-install-2019.png)

詳細については、「[Install the C++ Linux workload in Visual Studio](../linux/download-install-and-setup-the-linux-development-workload.md)」(Visual Studio で C++ の Linux ワークロードをインストールする) を参照してください。

## <a name="ide-integration"></a>IDE の統合

**[ファイル >開く> フォルダー**を選択して*CMakeLists.txt*ファイルを含むフォルダーを開くと、次の処理が行われます。

- **CMake**スクリプトを表示および編集するためのコマンドを使用して **、CMake**項目を [プロジェクト] メニューに追加します。

- **ソリューション エクスプローラー**に、フォルダーの構造とファイルが表示されます。

- Cmake.exe を実行し、既定の (x64 デバッグ) 構成の CMake キャッシュ ファイル (*CMakeCache.txt*) を生成します。 CMake コマンド ラインおよび CMake からの追加出力が、**出力ウィンドウ**に表示されます。

- Visual Studio は、IntelliSense、情報の参照、リファクタリングなどを有効にするためのソース ファイルのインデックス付けを、バックグラウンドで開始します。 ユーザーが作業を行っている間、Visual Studio は、エディターおよびディスク上での変更を監視し、インデックスとソースの同期を維持します。

開くフォルダーに含まれる CMake プロジェクトの数は制限されていません。 ワークスペース内のすべての "ルート" *CMakeLists.txt*ファイルが検出され、構成されます。 CMake 操作 (構成、ビルド、デバッグ)、C++ IntelliSense、および参照は、ワークスペース内のすべての CMake プロジェクトで使用できます。

![複数のルートを持つ CMake プロジェクト](media/cmake-multiple-roots.png)

ターゲットごとに論理的にまとめられたプロジェクトを参照することも可能です。 **ソリューション エクスプローラー** ツールバーのドロップダウンから、**[ターゲット ビュー]** を選択します。

![CMake ターゲット ビュー ボタン](media/cmake-targets-view.png)

**ソリューション エクスプローラー**の上部にある **[すべてのファイルを表示]** ボタンをクリックすると、CMake によって生成されたすべての出力が *、出力/ビルド/\<構成>* フォルダーに表示されます。

構成ファイルを**使用しています。** このファイルを使用すると、複数のビルド構成を定義および格納でき、IDE で簡単に切り替えることができます。 *構成*は、特定のビルドの種類に固有の設定をカプセル化する Visual Studio の構成です。 この設定は、Visual Studio が cmake.exe に渡す既定のコマンド ライン オプションを構成するために使用されます。 また、ここで追加の CMake オプションを指定し、必要に応じて任意の追加変数を定義することもできます。 すべてのオプションは、CMake キャッシュに内部変数または外部変数として書き込まれます。 Visual Studio 2019 では **、CMake 設定エディター**を使用して設定を編集できます。 詳細については、「 [CMake の設定をカスタマイズ](customize-cmake-settings.md)する 」を参照してください。

1 つの`intelliSenseMode`設定は CMake に渡されませんが、Visual Studio でのみ使用されます。

CMake プロジェクトの場合と同様に、各プロジェクト フォルダーで**CMakeLists.txt**ファイルを使用します。 ソース ファイルの指定、ライブラリの検索、コンパイラオプションとリンカ オプションの設定、その他のビルド システム関連情報の指定を行うことができます。

デバッグ時に実行可能ファイルに引数を渡す場合は、 **launch.vs.json**という別のファイルを使用できます。 一部のシナリオでは、Visual Studio は、これらのファイルを自動的に生成します。 手動で編集することも、自分でファイルを作成することもできます。

> [!NOTE]
> 他の種類のオープン フォルダー プロジェクトでは、2 つの追加 JSON ファイルが使用されます: **CppProperties.json**と**タスク.vs.json**。 これらはいずれも CMake プロジェクトには関連していません。

## <a name="open-an-existing-cache"></a>既存のキャッシュを開く

既存の CMake キャッシュ ファイル (*CMakeCache.txt*) を開くと、キャッシュとビルド ツリーの管理は行われず、キャッシュとビルド ツリーは管理されません。 カスタム ツールまたは優先ツールは、CMake でのプロジェクトの構成方法を完全に制御できます。 Visual Studio で既存のキャッシュを開くには、[**ファイル] > [CMake >開く**] を選択します。 次に、既存の*CMakeCache.txt*ファイルに移動します。

開いているプロジェクトに既存の CMake キャッシュを追加できます。 新しい構成を追加するのと同じ方法で行われます。 詳細については[、Visual Studio で既存のキャッシュを開く](https://devblogs.microsoft.com/cppblog/open-existing-cmake-caches-in-visual-studio/)ブログ記事を参照してください。

## <a name="building-cmake-projects"></a>CMake プロジェクトのビルド

CMake プロジェクトをビルドするには、次の選択肢があります。

1. [General]\(全般\) ツールバーで、**[Configurations]\(構成\)** ドロップダウンを見つけます。 既定では 、おそらく "x64-Debug" が表示されます。 優先する構成を選択して**F5**キーを押すか、ツールバーの [**実行**] (緑の三角形) ボタンをクリックします。 Visual Studio ソリューションと同じように、プロジェクトは最初に自動的にビルドされます。

1. *CMakeLists.txt*を右クリックし、コンテキスト メニューから **[ビルド**] を選択します。 フォルダー構造内に複数のターゲットがある場合は、すべてをビルドするか、特定の 1 つのターゲットだけをビルドするかを選べます。

1. メイン メニューから、[**ビルド >すべてビルド**]**(F7**キーまたは**Ctrl+ Shift + B)** を選択します。 **[全般]** ツール バーの **[スタートアップ アイテム]** ドロップダウンで CMake ターゲットが既に選択されていることを確認します。

![C ビルド メニュー コマンドを作成する](media/cmake-build-menu.png "CMake ビルド コマンド メニュー")

想像したとおり、ビルド結果が**出力ウィンドウ**と**エラー一覧**に表示されます。

![CMake ビルド エラー](media/cmake-build-errors.png "CMake ビルド エラー")

複数のビルド ターゲットを持つフォルダーでは、ビルドする CMake ターゲットを指定**Build**できます。 **CMake** *CMakeLists.txt* CMake プロジェクトで**Ctrl+ Shift + B と**入力すると、現在アクティブなドキュメントが作成されます。

## <a name="debugging-cmake-projects"></a>CMake プロジェクトのデバッグ

CMake プロジェクトをデバッグするには、優先する構成を選択して**F5**キーを押すか、ツール バーの [**実行**] ボタンを押します。 [**実行**] ボタンに [スタートアップ項目の選択] と表示されている場合は、ドロップダウン矢印を選択します。 実行するターゲットを選択します。 (CMake プロジェクトでは、[現在のドキュメント] オプションは .cpp ファイルの場合にのみ有効です)。

![C[実行] ボタンの作成](media/cmake-run-button.png "C[実行] ボタンの作成")

**[実行]** または **F5** コマンドを選ぶと、前回のビルドの後で何かが変更されている場合は、最初にプロジェクトがビルドされます。 *CMakeSettings.json*に変更を加えた場合、CMake キャッシュが再生成されます。

cMake デバッグ セッションをカスタマイズするには **、launch.vs.json**ファイルでプロパティを設定します。 詳細については、[CMake デバッグ セッションの構成](configure-cmake-debugging-sessions.md)に関するページを参照してください。

## <a name="just-my-code-for-cmake-projects"></a>CMake プロジェクトのマイ コードだけ

MSVC コンパイラを使用して Windows 用にビルドする場合、CMake プロジェクトはマイ コードのデバッグのみをサポートします。 [マイ コードのみを使用する] 設定を変更するには、[**ツール** > **オプション** > **のデバッグ** > **全般**] に移動します。

## <a name="vcpkg-integration"></a>Vcpkg 統合

[vcpkg](vcpkg.md)をインストールしている場合、Visual Studio で開かれた CMake プロジェクトは、vcpkg ツールチェーン ファイルを自動的に統合します。 つまり、CMake プロジェクトで vcpkg を使用するために追加の構成は必要ありません。 このサポートは、対象とするリモート システム上のローカル vcpkg インストールと vcpkg インストールの両方で機能します。 この動作は、CMake 設定の構成で他のツールチェーンを指定すると自動的に無効になります。

## <a name="customize-configuration-feedback"></a>構成フィードバックのカスタマイズ

既定では、エラーがない限り、ほとんどの構成メッセージは表示されません。 この機能を有効にすると、すべての**メッセージを** > **Options** > 表示**できます。**

   ![CMake 診断オプションの構成](media/vs2019-cmake-configure-options.png "CMake 診断オプション")

## <a name="editing-cmakeliststxt-files"></a>CMakeLists.txt ファイルの編集

*CMakeLists.txt*ファイルを編集するには、**ソリューション エクスプローラー**でファイルを右クリックし、[**開く**] を選択します。 ファイルに変更を加えた場合、黄色のステータス バーが表示され、IntelliSense が更新されることを通知します。 更新操作をキャンセルする機会を与えます。 *CMakeLists.txt*の詳細については[、CMake のドキュメントを参照してください](https://cmake.org/documentation/)。

   ![ファイル編集](media/cmake-cmakelists.png "ファイル編集")

ファイルを保存するとすぐに構成手順が自動的に再び実行され、**[出力]** ウィンドウに情報が表示されます。 エラーと警告は、**[エラー一覧]** または **[出力]** ウィンドウに表示されます。 **[エラー一覧**] でエラーをダブルクリックして *、CMakeLists.txt*の問題のある行に移動します。

   ![ファイルエラー](media/cmake-cmakelists-error.png "ファイルエラー")

## <a name="cmake-configure-step"></a>CMake の構成ステップ

*CMakeSettings.json*ファイルまたは*CMakeLists.txt*ファイルに大幅な変更を加えた場合、CMake 構成手順が自動的に再実行されます。 構成手順がエラーなしで完了した場合、収集された情報は C++ IntelliSense および言語サービスで利用できます。 ビルド操作やデバッグ操作でも使用されます。

## <a name="troubleshooting-cmake-cache-errors"></a>CMake キャッシュ エラーのトラブルシューティング

CMake キャッシュの状態に関する詳細な情報が必要な場合は、次のいずれかのコマンドを実行するには、**ソリューション エクスプローラー**で**プロジェクト**のメイン メニューまたは*CMakeLists.txt*コンテキスト メニューを開きます。

- **ビュー キャッシュ**は、エディターでビルド ルート フォルダーから*CMakeCache.txt*ファイルを開きます。 (*ここで CMakeCache.txt*に対して行った編集は、キャッシュをクリーンアップすると消去されます。 キャッシュのクリーンアップ後も変更を行う場合は[、「CMake 設定のカスタマイズ](customize-cmake-settings.md)」を参照してください)。

- **[キャッシュ フォルダーを開く]** は、エクスプローラー ウィンドウでビルド ルート フォルダーを開きます。

- **[キャッシュをクリーン]** は、次の CMake 構成ステップがクリーンなキャッシュから開始されるように、ビルド ルート フォルダーを削除します。

- **[キャッシュの生成]** は、Visual Studio が環境を最新の状態と見なしている場合でも、生成ステップを強制的に実行します。

自動キャッシュ生成は **、[CMake] ダイアログ ボックスの [ツール > オプション] > [一般>]** ダイアログで無効にすることができます。

## <a name="run-cmake-from-the-command-line"></a>コマンド ラインから CMake を実行する

Visual Studio インストーラーから CMake をインストールした場合は、次の手順に従ってコマンド ラインから実行できます。

1. 適切な vsdevcmd.bat (x86 または x64) を実行します。 詳細については、「コマンド[ラインでのビルド」](building-on-the-command-line.md)を参照してください。

1. 出力フォルダーに移動します。

1. CMake を実行してアプリをビルド/構成します。

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 2017 には、クロスプラットフォーム CMake プロジェクトを含む[CMake の](../linux/cmake-linux-project.md)豊富なサポートがあります。 CMake 用**Visual C++ ツール**コンポーネントは **、フォルダーを開く**機能を使用して、IDE が IntelliSense と参照の目的で CMake プロジェクト ファイル *(CMakeLists.txt*など) を直接使用できるようにします。 Ninja と Visual Studio ジェネレーターはどちらもサポートされています。 Visual Studio ジェネレーターを使用すると、一時プロジェクト ファイルが生成され、msbuild.exe に渡されます。 ただし、プロジェクトは、IntelliSense または参照の目的で読み込まれることはありません。 既存の CMake キャッシュをインポートすることもできます。

## <a name="installation"></a>インストール

**CMake 用 Visual C++ ツール**は **、C++ ワークロードを使用したデスクトップ開発**と**Linux 開発**の一環としてインストールされます。

![C++ デスクトップ ワークロードでの CMake コンポーネント](media/cmake-install.png)

詳細については、「[Install the C++ Linux workload in Visual Studio](../linux/download-install-and-setup-the-linux-development-workload.md)」(Visual Studio で C++ の Linux ワークロードをインストールする) を参照してください。

## <a name="ide-integration"></a>IDE 統合

**[ファイル >開く> フォルダー**を選択して*CMakeLists.txt*ファイルを含むフォルダーを開くと、次の処理が行われます。

- Visual Studio は、CMake スクリプトを表示および編集するためのコマンドを含む **[CMake]** メニュー項目を、メイン メニューに追加します。

- **ソリューション エクスプローラー**に、フォルダーの構造とファイルが表示されます。

- Visual Studio は CMake.exe を実行して、既定の "*構成*" (x86 デバッグ) 用の CMake キャッシュをオプションで生成します。 CMake コマンド ラインおよび CMake からの追加出力が、**出力ウィンドウ**に表示されます。

- Visual Studio は、IntelliSense、情報の参照、リファクタリングなどを有効にするためのソース ファイルのインデックス付けを、バックグラウンドで開始します。 ユーザーが作業を行っている間、Visual Studio は、エディターおよびディスク上での変更を監視し、インデックスとソースの同期を維持します。

開くフォルダーに含まれる CMake プロジェクトの数は制限されていません。 ワークスペース内のすべての "ルート" *CMakeLists.txt*ファイルが検出され、構成されます。 CMake 操作 (構成、ビルド、デバッグ)、C++ IntelliSense、および参照は、ワークスペース内のすべての CMake プロジェクトで使用できます。

![複数のルートを持つ CMake プロジェクト](media/cmake-multiple-roots.png)

ターゲットごとに論理的にまとめられたプロジェクトを参照することも可能です。 **ソリューション エクスプローラー** ツールバーのドロップダウンから、**[ターゲット ビュー]** を選択します。

![CMake ターゲット ビュー ボタン](media/cmake-targets-view.png)

Cmake.exe の環境変数またはコマンド ライン オプションを格納するために*CMakeSettings.json*という名前のファイルを使用します。 *また、CMakeSettings.json*を使用して、複数の CMake ビルド構成を定義および格納することもできます。 IDE でこれらを切り替えることができます。

それ以外の場合は *、CMakeLists.txt*を使用して、ソース ファイルの指定、ライブラリの検索、コンパイラおよびリンカー オプションの設定、その他のビルド システム関連情報の指定を行います。

デバッグ時に実行可能ファイルに引数を渡す必要がある場合は、 **launch.vs.json**という別のファイルを使用できます。 一部のシナリオでは、Visual Studio は、これらのファイルを自動的に生成します。 手動で編集することも、自分でファイルを作成することもできます。

> [!NOTE]
> 他の種類のオープン フォルダー プロジェクトでは、2 つの追加 JSON ファイルが使用されます: **CppProperties.json**と**タスク.vs.json**。 これらはいずれも CMake プロジェクトには関連していません。

## <a name="import-an-existing-cache"></a>既存のキャッシュをインポートする

既存の*CMakeCache.txt*ファイルをインポートすると、カスタマイズされた変数が自動的に抽出され、それらに基づいて事前に設定された*CMakeSettings.json*ファイルが作成されます。 元のキャッシュは変更されません。 コマンド ラインから、または生成に使用するツールや IDE で使用できます。 新しい*CMakeSettings.json*ファイルは、プロジェクトのルート*CMakeLists.txt*と並んで配置されます。 Visual Studio は、設定ファイルに基づいて新しいキャッシュを生成します。 自動キャッシュ生成は **、[CMake] ダイアログ ボックスの [ツール > オプション] >>設定**を変更できます。

キャッシュ内のすべてのものがインポートされるわけではありません。  ジェネレーターや、コンパイラの場所などのプロパティは、IDE で問題なく機能することがわかっている既定値に置き換えられます。

### <a name="to-import-an-existing-cache"></a>既存のキャッシュをインポートするには

1. メイン メニューから[**ファイル]>[CMake] >開く] を**選択します。

   ![CMake を開く](media/cmake-file-open.png "ファイル、開く、CMake")

   このコマンドを実行すると **、CMake をキャッシュからインポート**ウィザードが起動します。

2. インポートする*CMakeCache.txt*ファイルに移動し **、[OK]** をクリックします。 **[キャッシュから CMake のプロジェクトをインポートします]** ウィザードが表示されます。

   ![CMake キャッシュをインポートする](media/cmake-import-wizard.png "CMake インポート キャッシュ ウィザードを開く")

   ウィザードが完了すると、プロジェクトのルート*CMakeLists.txt*ファイルの横にある**ソリューション エクスプローラー**に新しい*CMakeCache.txt*ファイルが表示されます。

## <a name="building-cmake-projects"></a>CMake プロジェクトのビルド

CMake プロジェクトをビルドするには、次の選択肢があります。

1. [General]\(全般\) ツールバーで、**[Configurations]\(構成\)** ドロップダウンを見つけます。 デフォルトでは、おそらく"Linux-Debug"または"x64-Debug"が表示されています。 優先する構成を選択して**F5**キーを押すか、ツールバーの [**実行**] (緑の三角形) ボタンをクリックします。 Visual Studio ソリューションと同じように、プロジェクトは最初に自動的にビルドされます。

1. *CMakeLists.txt*を右クリックし、コンテキスト メニューから **[ビルド**] を選択します。 フォルダー構造内に複数のターゲットがある場合は、すべてをビルドするか、特定の 1 つのターゲットだけをビルドするかを選べます。

1. メイン メニューから、[**ビルド > ソリューションのビルド**]**(F7**キーまたは**Ctrl + Shift + B)** を選択します。 **[全般]** ツール バーの **[スタートアップ アイテム]** ドロップダウンで CMake ターゲットが既に選択されていることを確認します。

![C ビルド メニュー コマンドを作成する](media/cmake-build-menu.png "CMake ビルド コマンド メニュー")

*CMakeSettings.json*ファイルでビルド構成、環境変数、コマンド ライン引数、およびその他の設定をカスタマイズできます。 *CMakeLists.txt*ファイルを変更せずに変更を加えることができます。 詳細については、「 [CMake の設定をカスタマイズ](customize-cmake-settings.md)する 」を参照してください。

想像したとおり、ビルド結果が**出力ウィンドウ**と**エラー一覧**に表示されます。

![CMake ビルド エラー](media/cmake-build-errors.png "CMake ビルド エラー")

複数のビルド ターゲットを持つフォルダーでは、ビルドする CMake ターゲットを指定**Build**できます。 **CMake** *CMakeLists.txt* CMake プロジェクトで**Ctrl+ Shift + B と**入力すると、現在アクティブなドキュメントが作成されます。

## <a name="debugging-cmake-projects"></a>CMake プロジェクトのデバッグ

CMake プロジェクトをデバッグするには、優先する構成を選択し **、F5**キーを押します。 または、ツールバーの「**実行**」ボタンを押します。 **[実行]** ボタンに [スタートアップ アイテムの選択] と表示されている場合は、ドロップダウン矢印を選んで、実行するターゲットを選びます (CMake プロジェクトでは、[現在のドキュメント] オプションは .cpp ファイルの場合にのみ有効です)。

![C[実行] ボタンの作成](media/cmake-run-button.png "C[実行] ボタンの作成")

**[実行]** または **F5** コマンドを選ぶと、前回のビルドの後で何かが変更されている場合は、最初にプロジェクトがビルドされます。

cMake デバッグ セッションをカスタマイズするには **、launch.vs.json**ファイルでプロパティを設定します。 詳細については、[CMake デバッグ セッションの構成](configure-cmake-debugging-sessions.md)に関するページを参照してください。

## <a name="editing-cmakeliststxt-files"></a>CMakeLists.txt ファイルの編集

*CMakeLists.txt*ファイルを編集するには、**ソリューション エクスプローラー**でファイルを右クリックし、[**開く**] を選択します。 ファイルに変更を加えた場合、黄色のステータス バーが表示され、IntelliSense が更新されることを通知します。 更新操作をキャンセルする機会を与えます。 *CMakeLists.txt*の詳細については[、CMake のドキュメントを参照してください](https://cmake.org/documentation/)。

   ![ファイル編集](media/cmake-cmakelists.png "ファイル編集")

ファイルを保存するとすぐに構成手順が自動的に再び実行され、**[出力]** ウィンドウに情報が表示されます。 エラーと警告は、**[エラー一覧]** または **[出力]** ウィンドウに表示されます。 **[エラー一覧**] でエラーをダブルクリックして *、CMakeLists.txt*の問題のある行に移動します。

   ![ファイルエラー](media/cmake-cmakelists-error.png "ファイルエラー")

## <a name="cmake-configure-step"></a>CMake の構成ステップ

*CMakeSettings.json*ファイルまたは*CMakeLists.txt*ファイルに大幅な変更が加えられた場合、CMake 構成手順が自動的に再実行されます。 構成手順がエラーなしで完了した場合、収集された情報は C++ IntelliSense および言語サービスで利用できます。 ビルド操作やデバッグ操作でも使用されます。

複数の CMake プロジェクトで同じ CMake 構成名を使用する場合があります (たとえば、x86-Debug)。 その構成が選択されると、すべて (独自のビルド ルート フォルダーに) 構成およびビルドされます。 その CMake 構成に参加しているすべての CMake プロジェクトから、ターゲットをデバッグすることができます。

   ![CMake ビルドのみメニュー項目](media/cmake-build-only.png "CMake ビルドのみメニュー項目")

ワークスペース内のプロジェクトのサブセットにビルドセッションとデバッグセッションを制限できます。 一意の名前を持つ新しい構成を*作成*します。 次に、これらのプロジェクトにのみ構成を適用します。 その構成を選択すると、IntelliSense とビルド コマンドとデバッグ コマンドは、指定されたプロジェクトにのみ適用されます。

## <a name="troubleshooting-cmake-cache-errors"></a>CMake キャッシュ エラーのトラブルシューティング

問題を診断するために CMake キャッシュの状態に関する詳しい情報が必要な場合は、**CMake** のメイン メニューまたは**ソリューション エクスプローラー**で *CMakeLists.txt* のコンテキスト メニューを開き、次のコマンドのいずれかを実行します。

- **ビュー キャッシュ**は、エディターでビルド ルート フォルダーから*CMakeCache.txt*ファイルを開きます。 (*ここで CMakeCache.txt*に対して行った編集は、キャッシュをクリーンアップすると消去されます。 キャッシュのクリーンアップ後も変更を行う場合は[、「CMake 設定のカスタマイズ](customize-cmake-settings.md)」を参照してください)。

- **[キャッシュ フォルダーを開く]** は、エクスプローラー ウィンドウでビルド ルート フォルダーを開きます。

- **[キャッシュをクリーン]** は、次の CMake 構成ステップがクリーンなキャッシュから開始されるように、ビルド ルート フォルダーを削除します。

- **[キャッシュの生成]** は、Visual Studio が環境を最新の状態と見なしている場合でも、生成ステップを強制的に実行します。

自動キャッシュ生成は **、[CMake] ダイアログ ボックスの [ツール > オプション] > [一般>]** ダイアログで無効にすることができます。

## <a name="single-file-compilation"></a>単一ファイルのコンパイル

CMake プロジェクトで 1 つのファイルをビルドするには、**ソリューション エクスプローラー**でファイルを右クリックします。 ポップアップメニューから「**コンパイル」** を選択します。 CMake のメイン メニューを使用して、現在開いているファイル**CMake**をエディタでビルドすることもできます。

![CMake の単一ファイルのコンパイル](media/cmake-single-file-compile.png)

## <a name="run-cmake-from-the-command-line"></a>コマンド ラインから CMake を実行する

Visual Studio インストーラーから CMake をインストールした場合は、次の手順に従ってコマンド ラインから実行できます。

1. 適切な vsdevcmd.bat (x86 または x64) を実行します。 詳細については、コマンド[ラインでのビルドを](building-on-the-command-line.md)参照してください。

1. 出力フォルダーに移動します。

1. CMake を実行してアプリをビルド/構成します。

::: moniker-end

::: moniker range="vs-2015"

Visual Studio 2015 では、Visual Studio のユーザーは [CMake ジェネレーター](https://cmake.org/cmake/help/latest/manual/cmake-generators.7.html)を使って MSBuild プロジェクト ファイルを生成し、IDE はそのファイルを IntelliSense、参照、およびコンパイルに使っていました。

::: moniker-end

## <a name="see-also"></a>関連項目

[チュートリアル: Visual Studio で C++ クロスプラットフォーム プロジェクトを作成する](get-started-linux-cmake.md)\
[Linux CMake プロジェクトを構成する](../linux/cmake-linux-project.md)\
[リモート Linux コンピュータに接続する](../linux/connect-to-your-remote-linux-computer.md)\
[CMake ビルド設定のカスタマイズ](customize-cmake-settings.md)\
[スキーマリファレンス](cmakesettings-reference.md)\
[CMake デバッグ セッションの構成](configure-cmake-debugging-sessions.md)\
[Linux プロジェクトのデプロイ、実行、デバッグ](../linux/deploy-run-and-debug-your-linux-project.md)\
[CMake 定義済み構成リファレンス](cmake-predefined-configuration-reference.md)
