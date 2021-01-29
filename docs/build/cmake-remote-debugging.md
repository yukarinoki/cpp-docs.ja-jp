---
title: 'チュートリアル: リモートの Windows コンピューターで CMake プロジェクトをデバッグする'
ms.date: 12/4/2020
ms.topic: tutorial
description: Windows で Visual Studio C++ を使用して、CMake プロジェクトを作成およびビルドする方法。 その後、リモートの Windows コンピューターでそれを展開してデバッグします。
ms.openlocfilehash: 742ee831fc30ffe291d68ff97ad4238e57c7e21d
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98668841"
---
# <a name="tutorial-debug-a-cmake-project-on-a-remote-windows-machine"></a>チュートリアル: リモートの Windows コンピューターで CMake プロジェクトをデバッグする

このチュートリアルでは、Windows 上で Visual Studio C++ を使用して、リモートの Windows コンピューターで展開してデバッグできる CMake プロジェクトを作成およびビルドします。 このチュートリアルは Windows ARM64 に固有ですが、手順は他のアーキテクチャ用に一般化することができます。

Visual Studio では、ARM64 の既定のデバッグ エクスペリエンスは ARM64 Windows コンピューターのリモート デバッグです。 このチュートリアルに示されているように、デバッグ設定を構成せずに ARM64 CMake プロジェクトをデバッグしようとすると、Visual Studio でリモート コンピューターを見つけられないというエラーが表示されます。

このチュートリアルでは、次の方法について説明します。

> [!div class="checklist"]
>
> * CMake プロジェクトを作成する
> * ARM64 用にビルドするように CMake プロジェクトを構成する
> * リモートの ARM64 Windows コンピューターで実行するように CMake プロジェクトを構成する
> * リモートの ARM64 Windows コンピューターで実行されている CMake プロジェクトをデバッグする

## <a name="prerequisites"></a>前提条件

### <a name="on-the-host-machine"></a>ホスト コンピューター上

クロスプラットフォームの C++ 開発用に Visual Studio を設定するには、ターゲット アーキテクチャ用のビルド ツールをインストールします。 このチュートリアルでは、次の手順を行って ARM64 ビルド ツールをインストールします。

1. Visual Studio インストーラーを実行します。 Visual Studio をまだインストールしていない場合は、「[Visual Studio のインストール](https://docs.microsoft.com/visualstudio/install/install-visual-studio#:~:text=Install%20Visual%20Studio%201%20Make%20sure%20your%20computer,...%204%20Choose%20workloads.%20...%20More%20items...%20)」を参照してください
1. Visual Studio インストーラーのホーム画面で、 **[変更]** を選択します。
1. 上部の選択肢から、 **[個々のコンポーネント]** を選びます。
1. **[コンパイラ、ビルド ツール、およびランタイム]** セクションまで下にスクロールします。
1. 確実に次のように選択されるようにします。
    - **Windows 用 C++ CMake ツール**
    - **MSVC v142 - VS 2019 C++ ARM64 ビルド ツール (最新)** `ARM` ビルド ツールではなく、`ARM64` ビルド ツールを選択する (64 のものを見つける) ことと、`VS 2019` に対応するバージョンを選ぶことが重要です。
1. **[変更]** を選択してツールをインストールします。

### <a name="on-the-remote-machine"></a>リモート コンピューター上

1. リモート コンピューター上にリモート ツールをインストールします。 このチュートリアルでは、「[リモート ツールのダウンロードおよびインストール](https://docs.microsoft.com/visualstudio/debugger/remote-debugging-cpp?%23download-and-install-the-remote-tools#download-and-install-the-remote-tools)」の手順に従って、ARM64 ツールをインストールします。
1. リモート コンピューター上でリモート デバッガーを起動して構成します。 このチュートリアルでは、リモートの Windows コンピューターで「[リモート デバッガーのセットアップ](https://docs.microsoft.com/visualstudio/debugger/remote-debugging-cpp?%23download-and-install-the-remote-tools#BKMK_setup)」の指示に従ってこれを行います。

## <a name="create-a-cmake-project"></a>CMake プロジェクトを作成する

Windows ホスト コンピューター上で次のようにします。
1. Visual Studio を実行します
1. メイン メニューから、 **[ファイル]**  >  **[新規作成]**  >  **[プロジェクト]** の順に選択します。
1. **[CMake プロジェクト]**  >  **[次へ]** の順に選択します
1. プロジェクトに名前を付け、場所を選びます。 **[作成]** を選択します。

しばらくの間、Visual Studio でプロジェクトが作成され、 **[ソリューション エクスプローラー]** が設定されるのを待ちます。

## <a name="configure-for-arm64"></a>ARM64 用に構成する

ARM64 Windows コンピューターをターゲットとするには、ARM64 ビルド ツールを使用してビルドする必要があります。

Visual Studio の **[構成]** ドロップダウンを選択し、 **[構成の管理]** を選びます。

![Visual Studio の構成ドロップダウンで [構成の管理] を選択する](media/vs2019-cmake-manage-configurations.png)

**[新規構成の追加]** (緑の **+** ボタン) を選択することで、新しい構成を追加します。
表示される **[CMakeSettings]** ダイアログで、 **[arm64-debug]** を選んでから、 **[選択]** を押します。

![arm64-debug 構成を追加する](media/cmake-add-config-icon-with-target-dialog.png)

これにより、**arm64-Debug** という名前のデバッグ構成が *`CmakeSettings.json`* ファイルに追加されます。 この構成名は、 **[構成]** ドロップダウンでこれらの設定をより簡単に特定できるようにする一意のフレンドリ名です。

**[ツールセット]** ドロップダウンは **[msvc_arm64_x64]** に設定されます。 これで、設定はこのようになるはずです。

![CMake の設定ダイアログ](media/cmake-settings-editor2.png)

> [!Note]
> **[ツールセット]** ドロップダウンでは、**msvc_arm64** の場合、32 ビットのホスト ツールを選択して ARM64 にクロスコンパイルします。一方、**msvc_arm64 x64** の場合は、64 ビットのホスト ツールを選択して ARM64 にクロスコンパイルします (このチュートリアルではこれを行います)。

`CMakeSettings.json` ファイルを保存します。 構成ドロップダウンで、 **[arm64-debug]** を選択します (`CMakeSettings.json` ファイルを保存してからそれが一覧に表示されるまでしばらく時間がかかることがあります)。

![Visual Studio の構成ドロップダウンで arm64-debug が確実に選択されるようにする](media/vs2019-cmake-manage-configurations-arm.png) 

## <a name="add-a-debug-configuration-file"></a>デバッグ構成ファイルを追加する

次に、他の構成の詳細と共に、リモート コンピューターを検索する場所を Visual Studio に指示する構成情報を追加します。

**[表示の切り替え]** ボタンを選択して、 **[ソリューション エクスプローラー]** のビューをターゲット ビューに変更します。

![ソリューション エクスプローラーの表示の切り替えボタン](media/solution-explorer-switch-view.png)

その後、 **[ソリューション エクスプローラー]** で、 **[CMake ターゲット ビュー]** をダブルクリックしてプロジェクトを表示します。

プロジェクト フォルダー (この例では **CMakeProject3 Project**) を開き、実行可能ファイルを右クリックして、 **[Add Debug Configuration]\(デバッグ構成の追加\)** を選択します。

![[Add Debug Configuration]\(デバッグ構成の追加\) を選択する](media/cmake-targets-add-debug-configuration.png)

これにより、プロジェクトに `launch.vs.json` ファイルが作成されます。 それを開き、以下のエントリを変更してリモート デバッグを有効にします。

- `projectTarget`: 上記の手順に従って **[ソリューション エクスプローラー]** のターゲット ビューからデバッグ構成ファイルを追加した場合は、これが自動的に設定されます。
- `remoteMachineName`: リモート ARM64 コンピューターの IP アドレス、またはそのコンピューター名を設定します。

`launch.vs.json` 設定の詳細については、[launch.vs.json スキーマ リファレンス](launch-vs-schema-reference-cpp.md)に関するページを参照してください。

> [!Note]
>  **[ソリューション エクスプローラー]** でターゲット ビューではなくフォルダー ビューを使用する場合は、`CMakeLists.txt` ファイルを右クリックし、 **[Add Debug Configuration]\(デバッグ構成の追加\)** を選択します。 このエクスペリエンスは、次の方法でターゲット ビューからデバッグ構成を追加することとは異なります。
> - デバッガーを選択するように求められます ( **[C または C++ リモート Windows デバッグ]** を選択する)。
> - Visual Studio によって提供される `launch.vs.json` ファイルの構成テンプレート情報は少ないため、自分で追加する必要があります。 `remoteMachineName` と `projectTarget` のエントリを指定する必要があります。 ターゲット ビューから構成を追加する場合、指定する必要があるのは `remoteMachineName`　のみです。
> - `projectTarget` 設定値については、スタートアップ項目ドロップダウンを確認し、ターゲットの一意の名前を取得します。たとえば、このチュートリアルでは "CMakeProject3.exe" です。

## <a name="start-the-remote-debugger-monitor-on-the-remote-windows-machine"></a>リモートの Windows コンピューターでリモート デバッガー モニターを起動する

CMake プロジェクトを実行する前に、リモートの Windows コンピューターで Visual Studio 2019 リモート デバッガーが確実に実行されるようにします。  場合によっては、認証状況に応じて、リモート デバッガーのオプションを変更する必要があります。

たとえば、リモート コンピューター上で、Visual Studio リモート デバッガーのメニュー バーから **[ツール]**  >  **[オプション]** の順に選択します。 お使いの環境の設定方法と一致するように **[認証モード]** を設定します。

![リモート デバッガーの認証オプション](media/remote-debugger-options.png)

その後、ホスト コンピューター上の Visual Studio で、`launch.vs.json` ファイルを更新して一致させます。 たとえば、リモート デバッガーで **[認証なし]** を選択した場合は、 **"authenticationType": "none"** を `configurations` セクション `launch.vs.json` に追加して、プロジェクトの `launch.vs.json` ファイルを更新します。 それ以外の場合、`"authenticationType"` は既定で `"windows"` に設定されており、明示的に指定する必要はありません。 この例は、認証なしで構成された `launch.vs.json` ファイルを示しています。

``` XAML
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
        "type": "remoteWindows",
        "authenticationType": "none"
        "name": "CMakeLists.txt",
        "project": "CMakeLists.txt",
        "projectTarget": "CMakeProject3.exe",
        "remoteMachineName": "<ip address goes here>",
        "cwd": "${debugInfo.defaultWorkingDirectory}",
        "program": "${debugInfo.fullTargetPath}",
        "deploy": [],
        "args": [],
        "env": {}
    },
    {
      "type": "default",
      "project": "CMakeLists.txt",
      "projectTarget": "CMakeProject3.exe",
      "name": "CMakeProject3.exe"
    }
  ]
}
```

## <a name="debug-the-app"></a>アプリをデバッグする

ホスト コンピューター上の Visual Studio の **[ソリューション エクスプローラー]** で、CMake プロジェクトの CPP ファイルを開きます。 **[CMake ターゲット ビュー]** を表示したままの場合は、 **(実行可能)** ノードを開いて確認する必要があります。

既定の CPP ファイルは、シンプルな hello world コンソール アプリです。 `return 0;` にブレークポイントを設定します。

Visual Studio のツール バーで、 **[スタートアップ項目]** ドロップダウンを使用して、`launch.vs.json` ファイルで `"name"` に指定した名前を選択します。

![CMakeProject3.exe が選択された状態のスタートアップ項目のドロップダウンの例](media/startup-item.png)

デバッグを開始するには、Visual Studio のツール バーで、 **[デバッグ]**  >  **[デバッグの開始]** の順に選択します (または **F5** キーを押す)。

開始されない場合は、`launch.vs.json` ファイルに次のものが正しく設定されていることを確実にします。
- `"remoteMachineName"` は、リモート ARM64 Windows コンピューターの IP アドレス、またはコンピューター名に設定する必要があります。
- `"name"` は、Visual Studio のスタートアップ項目ドロップダウンで選択した内容と一致する必要があります。
- `"projectTarget"` は、デバッグする CMake ターゲットの名前と一致する必要があります。
- `"type"` は、`"remoteWindows"` である必要があります。
- リモート デバッガーの認証の種類が **[認証なし]** に設定されている場合は、`launch.vs.json` ファイルで `"authenticationType": "none"` を設定する必要があります。
- Windows 認証を使用する場合は、メッセージが表示されたら、リモート コンピューターによって認識されるアカウントを使用してサインインします。

プロジェクトがビルドされた後、アプリがリモートの ARM64 Windows コンピューターに表示されるはずです。

![リモートの Windows ARM64 コンピューターで実行されている Hello CMake コンソール アプリ](media/remote-cmake-app.png)

ホスト コンピューター上の Visual Studio は、`return 0;` のブレークポイントで停止する必要があります。

## <a name="what-you-learned"></a>学習内容

このチュートリアルでは、CMake プロジェクトを作成し、それを ARM64 版 Windows 用にビルドするように構成し、リモートの ARM64 Windows コンピューターでデバッグしました。

## <a name="next-steps"></a>次の手順

Visual Studio での CMake プロジェクトの構成とデバッグについてさらに学習します。

> [!div class="nextstepaction"]
> [Visual Studio の CMake プロジェクト](cmake-projects-in-visual-studio.md)\
> [CMake のビルド設定をカスタマイズする](customize-cmake-settings.md)\
> [CMake デバッグ セッションを構成する](configure-cmake-debugging-sessions.md)\
> [CMake 定義済み構成リファレンス](cmake-predefined-configuration-reference.md)\
[launch.vs.json スキーマ リファレンス](launch-vs-schema-reference-cpp.md)
