---
title: Visual Studio の CMake プロジェクト
ms.date: 03/05/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: b055a1e3ca1d43cc0a1633401c1a08a3d54c1a31
ms.sourcegitcommit: 90817d9d78fbaed8ffacde63f3add334842e596f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "58278451"
---
# <a name="cmake-projects-in-visual-studio"></a>Visual Studio の CMake プロジェクト

CMake は、複数のプラットフォームで動作するビルド プロセスを定義するためのクロスプラットフォームのオープン ソース ツールです。 この記事では、CMake についてよく理解されていることを前提としています。 詳細については、「[Build, Test and Package Your Software With CMake](https://cmake.org/)」 (CMake を使用してソフトウェアをビルド、テスト、パッケージ化する) を参照してください。

Visual Studio 2015 では、Visual Studio のユーザーは [CMake ジェネレーター](https://cmake.org/cmake/help/latest/manual/cmake-generators.7.html)を使って MSBuild プロジェクト ファイルを生成し、IDE はそのファイルを IntelliSense、参照、およびコンパイルに使っていました。

Visual Studio 2017 では、[クロスプラット フォーム CMake プロジェクト](../linux/cmake-linux-project.md)など、CMake の豊富なサポートが導入されています。 **CMake の Visual C++ ツール** コンポーネントでは、**フォルダーを開く**機能を使用して、IntelliSense および参照の目的で、IDE が CMake プロジェクト ファイル (CMakeLists.txt など) を直接使用できるようにします。 Ninja と Visual Studio ジェネレーターはどちらもサポートされています。 Visual Studio ジェネレーターを使用した場合は、一時プロジェクト ファイルが生成されて msbuild.exe に渡されますが、IntelliSense または参照のために読み込まれることはありません。 既存の CMake キャッシュをインポートできます。Visual Studio はカスタマイズされた変数を自動的に抽出し、事前設定済みの `CMakeSettings.json` ファイルを作成します。 

## <a name="installation"></a>インストール

**CMake の Visual C++ ツール**は、**C++ によるデスクトップ開発**ワークロードの一部として、および **C++ による Linux 開発**ワークロードの一部として既定でインストールされます。

![C++ デスクトップ ワークロードでの CMake コンポーネント](media/cmake-install.png)

詳細については、「[Install the C++ Linux workload in Visual Studio](../linux/download-install-and-setup-the-linux-development-workload.md)」(Visual Studio で C++ の Linux ワークロードをインストールする) を参照してください。

## <a name="ide-integration"></a>IDE の統合

**[ファイル] > [開く] > [フォルダー]** を選んで、CMakeLists.txt ファイルを含むフォルダーを開くと、次の処理が行われます。

- Visual Studio は、CMake スクリプトを表示および編集するためのコマンドを含む **[CMake]** メニュー項目を、メイン メニューに追加します。

- **ソリューション エクスプローラー**に、フォルダーの構造とファイルが表示されます。

- Visual Studio は CMake.exe を実行して、既定の "*構成*" (x86 デバッグ) 用の CMake キャッシュをオプションで生成します。 CMake コマンド ラインおよび CMake からの追加出力が、**出力ウィンドウ**に表示されます。

- Visual Studio は、IntelliSense、情報の参照、リファクタリングなどを有効にするためのソース ファイルのインデックス付けを、バックグラウンドで開始します。 ユーザーが作業を行っている間、Visual Studio は、エディターおよびディスク上での変更を監視し、インデックスとソースの同期を維持します。

開くフォルダーに含まれる CMake プロジェクトの数は制限されていません。 Visual Studio は、ワークスペース内にあるすべての "ルート" CMakeLists.txt ファイルを検出して構成します。 CMake の操作 (構成、ビルド、デバッグ) および C++ の IntelliSense と参照は、ワークスペース内のすべての CMake プロジェクトが使用できます。

![複数のルートを持つ CMake プロジェクト](media/cmake-multiple-roots.png)

ターゲットごとに論理的にまとめられたプロジェクトを参照することも可能です。 **ソリューション エクスプローラー** ツールバーのドロップダウンから、**[ターゲット ビュー]** を選択します。

![CMake ターゲット ビュー ボタン](media/cmake-targets-view.png)

Visual Studio は `CMakeSettings.json` という名前のファイルを使用して、環境変数または Cmake.exe のコマンド ライン オプションを格納します。 `CMakeSettings.json` を使用すると、複数の CMake ビルド構成を定義して格納し、IDE 内でそれらを簡単に切り替えることもできます。 

それ以外の場合は、CMake プロジェクトと同じように `CMakeLists.txt` を使用してソース ファイルを指定し、ライブラリを見つけ、コンパイラとリンカーのオプションを設定し、その他のビルド システムの関連情報を指定します。

デバッグ時に実行可能ファイルに引数を渡す必要がある場合は、`launch.vs.json` と呼ばれる別のファイルを使用することができます。 一部のシナリオでは、Visual Studio でこれらのファイルが自動的に生成され、それを手動で編集することができます。 自分でファイルを作成することもできます。

> [!NOTE]
> 他の種類の "フォルダーを開く" プロジェクトには、`CppProperties.json` と `tasks.vs.json` の 2 つの JSON ファイルが使用されます。 これらはいずれも CMake プロジェクトには関連していません。

## <a name="import-an-existing-cache"></a>既存のキャッシュをインポートする

ユーザーが既存の CMakeCache.txt ファイルをインポートすると、Visual Studio はカスタマイズされた変数を自動的に抽出し、それを基にして事前設定済みの [ `CMakeSettings.json`](#cmake_settings) ファイルを作成します。 元のキャッシュには、どのような変更も加えられておらず、コマンド ラインから、またはキャッシュの生成に使われた任意のツールや IDE で、使用することができます。 新しい `CMakeSettings.json` ファイルは、プロジェクトのルートの CMakeLists.txt と共に配置されます。 Visual Studio は、設定ファイルに基づいて新しいキャッシュを生成します。 キャッシュの自動生成は、**[ツール] > [オプション] > [CMake] > [全般]** ダイアログでオーバーライドできます。

キャッシュ内のすべてのものがインポートされるわけではありません。  ジェネレーターや、コンパイラの場所などのプロパティは、IDE で問題なく機能することがわかっている既定値に置き換えられます。

### <a name="to-import-an-existing-cache"></a>既存のキャッシュをインポートするには

1. メイン メニューから **[ファイル] > [開く] > [CMake]** を選びます。

   ![CMake を開く](media/cmake-file-open.png "[ファイル] > [開く] > [CMake]")

   これにより、**キャッシュからの CMake のインポート** ウィザードが起動します。

2. インポートする CMakeCache.txt ファイルに選んで、**[OK]** をクリックします。 **[キャッシュから CMake のプロジェクトをインポートします]** ウィザードが表示されます。

   ![CMake キャッシュのインポート](media/cmake-import-wizard.png "CMake キャッシュ インポート ウィザードを開く")

   ウィザードが完了すると、**ソリューション エクスプローラー**でプロジェクトのルート CMakeLists.txt ファイルの隣に新しい CMakeCache.txt ファイルが表示されます。

## <a name="building-cmake-projects"></a>CMake プロジェクトのビルド

CMake プロジェクトをビルドするには、次の選択肢があります。

1. [全般] のツールバーでは、検索、**構成**ドロップダウンです。 既定では、"Linux Debug"または"x64 Debug"を示すことが可能性があります。 必要な構成とキーを押して選択**F5**、 をクリックしてまたは、**実行**(緑の三角形)、ツールバーのボタンをクリックします。 Visual Studio ソリューションと同じように、プロジェクトは最初に自動的にビルドされます。

1. CMakeLists.txt を右クリックして、コンテキスト メニューから **[ビルド]** を選びます。 フォルダー構造内に複数のターゲットがある場合は、すべてをビルドするか、特定の 1 つのターゲットだけをビルドするかを選べます。

1. メイン メニューから、**[ビルド] > [ソリューションのビルド]** (**F7** キーまたは **Ctrl + Shift + B** キー) を選びます。 **[全般]** ツール バーの **[スタートアップ アイテム]** ドロップダウンで CMake ターゲットが既に選択されていることを確認します。

![CMake のビルド メニュー コマンド](media/cmake-build-menu.png "CMake のビルド コマンド メニュー")

`CMakeSettings.json` ファイルを使用すると、CMakeLists.txt ファイルを変更しなくても、ビルド構成、環境変数、コマンド ライン引数、およびその他の設定をカスタマイズすることができます。 詳細については、「[Customize CMake settings](customize-cmake-settings.md)」 (CMake 設定のカスタマイズ) を参照してください。

想像したとおり、ビルド結果が**出力ウィンドウ**と**エラー一覧**に表示されます。

![CMake ビルド エラー](media/cmake-build-errors.png "CMake ビルド エラー")

フォルダーに複数のビルド ターゲットがある場合は、**[CMake]** メニューまたは **CMakeLists.txt** のコンテキスト メニューで **[ビルド]** 項目を選び、ビルドする CMake ターゲットを指定できます。 CMake プロジェクトで **Ctrl + Shift + B** キーを押して、現在アクティブなドキュメントをビルドします。

## <a name="debugging-cmake-projects"></a>CMake プロジェクトのデバッグ

CMake プロジェクトをデバッグするには、対象の構成を選んで、**F5** キーを押すか、またはツール バーの **[実行]** ボタンをクリックします。 **[実行]** ボタンに [スタートアップ アイテムの選択] と表示されている場合は、ドロップダウン矢印を選んで、実行するターゲットを選びます (CMake プロジェクトでは、[現在のドキュメント] オプションは .cpp ファイルの場合にのみ有効です)。

![CMake の実行ボタン](media/cmake-run-button.png "CMake の実行ボタン")

**[実行]** または **F5** コマンドを選ぶと、前回のビルドの後で何かが変更されている場合は、最初にプロジェクトがビルドされます。

`launch.vs.json` ファイルでプロパティを設定することで、CMake デバッグ セッションをカスタマイズすることができます。 詳細については、[CMake デバッグ セッションの構成](configure-cmake-debugging-sessions.md)に関するページを参照してください。


## <a name="editing-cmakeliststxt-files"></a>CMakeLists.txt ファイルの編集

CMakeLists.txt ファイルを編集するには、**ソリューション エクスプローラー**でファイルを右クリックして、**[開く]** を選びます。 ファイルを変更すると表示される黄色いステータス バーでは、IntelliSense が更新されることが示され、更新操作をキャンセルできます。 CMakeLists.txt については、[CMake のドキュメント](https://cmake.org/documentation/)をご覧ください。

   ![CMakeLists.txt ファイルの編集](media/cmake-cmakelists.png "CMakeLists.txt ファイルの編集")

ファイルを保存するとすぐに構成手順が自動的に再び実行され、**[出力]** ウィンドウに情報が表示されます。 エラーと警告は、**[エラー一覧]** または **[出力]** ウィンドウに表示されます。 **[エラー一覧]** でエラーをダブルクリックすると、CMakeLists.txt で問題が発生した行に移動します。

   ![CMakeLists.txt ファイルのエラー](media/cmake-cmakelists-error.png "CMakeLists.txt ファイルのエラー")


## <a name="cmake-configure-step"></a>CMake の構成ステップ

`CMakeSettings.json` ファイルまたは CMakeLists.txt ファイルが大幅に変更されると、Visual Studio は CMake の構成ステップを自動的に再実行します。 構成ステップがエラーなしで完了すると、収集された情報が、C++ の IntelliSense サービスと言語サービス、およびビルドとデバッグの操作で使用できるようになります。

複数の CMake プロジェクトが同じ CMake 構成名 (x86-Debug など) を使っている場合、その構成を選ぶと、すべてのプロジェクトが構成されて (それぞれのビルド ルート フォルダーに) ビルドされます。 その CMake 構成に参加しているすべての CMake プロジェクトから、ターゲットをデバッグすることができます。

   ![CMake の [ビルドのみ] メニュー項目](media/cmake-build-only.png "CMake の [ビルドのみ] メニュー項目")

ビルドおよびデバッグ セッションをワークスペース内のプロジェクトのサブセットに制限するには、`CMakeSettings.json` ファイルに一意名を使って新しい構成を作成し、それらのプロジェクトのみに適用します。 その構成を選ぶと、IntelliSense およびビルドとデバッグのコマンドは、指定されているプロジェクトに対してのみ有効になります。

## <a name="troubleshooting-cmake-cache-errors"></a>CMake キャッシュ エラーのトラブルシューティング

問題を診断するために CMake キャッシュの状態に関する詳しい情報が必要な場合は、**CMake** のメイン メニューまたは**ソリューション エクスプローラー**で **CMakeLists.txt** のコンテキスト メニューを開き、次のコマンドのいずれかを実行します。

- **[キャッシュの表示]** は、ビルド ルート フォルダーの CMakeCache.txt ファイルをエディターで開きます (ここで CMakeCache.txt に対して編集した内容はすべて、キャッシュをクリーンアップするとワイプされます。 キャッシュがクリーンアップされた後も残るように変更する方法については、前の「[CMake の設定とカスタム構成](#cmake_settings)」をご覧ください)。

- **[キャッシュ フォルダーを開く]** は、エクスプローラー ウィンドウでビルド ルート フォルダーを開きます。

- **[キャッシュをクリーン]** は、次の CMake 構成ステップがクリーンなキャッシュから開始されるように、ビルド ルート フォルダーを削除します。

- **[キャッシュを生成]** は、Visual Studio が環境は最新の状態であると判断した場合でも、生成ステップを強制的に実行します。

キャッシュの自動生成は、**[ツール] > [オプション] > [CMake] > [全般]** ダイアログで無効化できます。

## <a name="single-file-compilation"></a>単一ファイルのコンパイル

CMake プロジェクトに単一ファイルをビルドするには、**ソリューション エクスプローラー**でファイルを右クリックし、**[コンパイル]** を選択します。 メインの CMake メニューを使用すると、エディターで現在開いているファイルをビルドすることも可能です。

![CMake の単一ファイルのコンパイル](media/cmake-single-file-compile.png)

## <a name="run-cmake-from-the-command-line"></a>コマンド ラインから CMake を実行する

Visual Studio インストーラーから CMake をインストールした場合は、次の手順に従ってコマンド ラインから実行できます。

1. 適切な vsdevcmd.bat (x86 または x64) を実行します。 詳細については、[コマンド ラインでのビルド](building-on-the-command-line.md)に関するページを参照してください。

1. 出力フォルダーに移動します。

1. CMake を実行してアプリをビルド/構成します。
  
## <a name="see-also"></a>関連項目

[チュートリアル: Visual Studio で C++ クロスプラットフォーム プロジェクトを作成する](get-started-linux-cmake.md)<br/>
[Linux CMake プロジェクトを構成する](../linux/cmake-linux-project.md)<br/>
[リモートの Linux コンピューターに接続する](../linux/connect-to-your-remote-linux-computer.md)<br/>
[CMake のビルド設定をカスタマイズする](customize-cmake-settings.md)<br/>
[CMakeSettings.json リファレンス](cmakesettings-reference.md)<br/>
[CMake デバッグ セッションを構成する](configure-cmake-debugging-sessions.md)<br/>
[Linux プロジェクトの配置、実行、デバッグ](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake 定義済み構成リファレンス](cmake-predefined-configuration-reference.md)<br/>
