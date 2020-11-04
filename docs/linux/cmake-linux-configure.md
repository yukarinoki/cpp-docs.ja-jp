---
title: Visual Studio で Linux CMake プロジェクトを構成する
description: Visual Studio で Linux CMake の設定を構成する方法
ms.date: 08/08/2020
ms.openlocfilehash: c4c2d4682b6d18f9175a92a810b3f86d8132fc0c
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921920"
---
# <a name="configure-a-linux-cmake-project-in-visual-studio"></a>Visual Studio で Linux CMake プロジェクトを構成する

::: moniker range="msvc-140"
Linux サポートは Visual Studio 2017 以降で使用できます。 これらのバージョンのドキュメントを表示するには、目次の上にある **[バージョン]** ドロップダウンを **Visual Studio 2017** または **Visual Studio 2019** に設定します。
::: moniker-end

::: moniker range=">=msvc-150"
このトピックでは、リモート Linux システムまたは Linux 用 Windows サブシステム (WSL) のいずれかを対象とする CMake プロジェクトに Linux 構成を追加する方法について説明します。 これは、[Visual Studio での Linux CMake プロジェクトの作成](cmake-linux-project.md)に関する記事から始まるシリーズの続きです。 MSBuild を使用している場合は、代わりに [Visual Studio での Linux MSBuild プロジェクトの構成](configure-a-linux-project.md)に関する記事を参照してください

## <a name="add-a-linux-configuration"></a>Linux の構成を追加する

構成を使用すると、同じソース コードで異なるプラットフォーム (Windows、WSL、リモートシステム) を対象にすることができます。 構成は、コンパイラを設定し、環境変数を渡し、CMake の呼び出し方法をカスタマイズするためにも使用されます。 *CMakeSettings.json* ファイルでは、 [CMake 設定のカスタマイズ](../build/customize-cmake-settings.md)に関するページで一覧表示されているすべてのプロパティに加え、リモートの Linux コンピューター上のビルド設定を制御する追加のプロパティを指定します。
::: moniker-end

::: moniker range="msvc-150"
Visual Studio 2017 で既定の CMake 設定を変更するには、メイン メニューから **[CMake]**  >  **[CMake の設定を変更]**  >  **[CMakeLists.txt]** を選択します。 または、 **ソリューション エクスプローラー** で *CMakeLists.txt* を右クリックし、 **[CMake の設定を変更]** を選択します。 Visual Studio によって、ルート プロジェクト フォルダー内に新しい *CMakeSettings.json* ファイルが作成されます。 変更するには、ファイルを開き、直接変更します。 詳細については、「[Customize CMake settings](../build/customize-cmake-settings.md)」 (CMake 設定のカスタマイズ) を参照してください。

Visual Studio 2017 (および Visual Studio 2019 バージョン 16.0) での Linux-Debug の既定の構成は、次のようになります。

```json
{
      "name": "Linux-Debug",
      "generator": "Unix Makefiles",
      "remoteMachineName": "${defaultRemoteMachineName}",
      "configurationType": "Debug",
      "remoteCMakeListsRoot": "/var/tmp/src/${workspaceHash}/${name}",
      "cmakeExecutable": "/usr/local/bin/cmake",
      "buildRoot": "${env.LOCALAPPDATA}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.LOCALAPPDATA}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "remoteBuildRoot": "/var/tmp/build/${workspaceHash}/build/${name}",
      "remoteInstallRoot": "/var/tmp/build/${workspaceHash}/install/${name}",
      "remoteCopySources": true,
      "remoteCopySourcesOutputVerbosity": "Normal",
      "remoteCopySourcesConcurrentCopies": "10",
      "remoteCopySourcesMethod": "rsync",
      "remoteCopySourcesExclusionList": [".vs", ".git"],
      "rsyncCommandArgs" : "-t --delete --delete-excluded",
      "remoteCopyBuildOutput" : "false",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "",
      "ctestCommandArgs": "",
      "inheritEnvironments": [ "linux-x64" ]
}
```

::: moniker-end

::: moniker range="msvc-160"
Visual Studio 2019 の CMake の既定の設定を変更するには、メイン ツールバーから **[構成]** ドロップダウンを開き、 **[構成の管理]** を選択します。

![CMake の [構成の管理]](../build/media/vs2019-cmake-manage-configurations.png "CMake 構成ドロップダウン")

このコマンドにより **CMake 設定エディター** が開かれます。これを使用してルート プロジェクト フォルダー内の *CMakeSettings.json* ファイルを編集できます。 エディターの **[JSON の編集]** ボタンをクリックして、JSON エディターでファイルを開くこともできます。 詳細については、[CMake 設定のカスタマイズ](../build/customize-cmake-settings.md)に関するページを参照してください。

Visual Studio 2019 バージョン 16.1 以降での Linux-Debug の既定の構成は次のようになります。

```json
{
      "name": "Linux-Debug",
      "generator": "Unix Makefiles",
      "configurationType": "Debug",
      "cmakeExecutable": "/usr/bin/cmake",
      "remoteCopySourcesExclusionList": [ ".vs", ".git", "out" ],
      "cmakeCommandArgs": "",
      "buildCommandArgs": "",
      "ctestCommandArgs": "",
      "inheritEnvironments": [ "linux_x64" ],
      "remoteMachineName": "${defaultRemoteMachineName}",
      "remoteCMakeListsRoot": "$HOME/.vs/${projectDirName}/${workspaceHash}/src",
      "remoteBuildRoot": "$HOME/.vs/${projectDirName}/${workspaceHash}/out/build/${name}",
      "remoteInstallRoot": "$HOME/.vs/${projectDirName}/${workspaceHash}/out/install/${name}",
      "remoteCopySources": true,
      "rsyncCommandArgs": "-t --delete --delete-excluded",
      "remoteCopyBuildOutput": false,
      "remoteCopySourcesMethod": "rsync",
      "addressSanitizerRuntimeFlags": "detect_leaks=0",
      "variables": []
    }
  ]
}
```

Visual Studio 2019 バージョン 16.6 以降では、Ninja が、リモート システムまたは WSL をターゲットとする構成の既定のジェネレーターです。 詳細については、[C++ チームのこちらのブログ記事](https://devblogs.microsoft.com/cppblog/linux-development-with-visual-studio-first-class-support-for-gdbserver-improved-build-times-with-ninja-and-updates-to-the-connection-manager/)を参照してください。

::: moniker-end
::: moniker range=">=msvc-150"
これらの設定の詳細については、[CMakeSettings.json リファレンス](../build/cmakesettings-reference.md)に関するページを参照してください。

ビルドを実行する場合:

- リモート システムを対象にしている場合、Visual Studio では、リモート ターゲットに対する既定として、 **[ツール]** > **[オプション]** > **[クロス プラットフォーム]** > **[接続マネージャー]** の下にある最初のリモート システムが選択されます。
- リモート接続が見つからない場合、リモート接続を作成するように求められます。 詳細については、[リモートの Linux コンピューターへの接続](connect-to-your-remote-linux-computer.md)に関するページを参照してください。

## <a name="choose-a-linux-target"></a>Linux ターゲットを選ぶ

CMake プロジェクト フォルダーを開くと、Visual Studio によって *CMakeLists.txt* ファイルが解析され、 **x86-Debug** の Windows ターゲットが指定されます。 リモート Linux システムをターゲットにするには、Linux コンパイラに基づいてプロジェクト設定を変更します。 たとえば、Linux で GCC を使用し、デバッグ情報を使用してコンパイルする場合は、次を選択します: **Linux-GCC-Debug** または **Linux-GCC-Release** 。

リモートの Linux を対象に指定した場合、ソースはリモート システムにコピーされます。

対象を選択したら、CMake は Linux システム上で自動実行され、プロジェクト用の CMake キャッシュを生成します。

![Linux での CMake キャッシュの生成](media/cmake-linux-1.png "Linux で CMake キャッシュを生成する")

::: moniker-end
::: moniker range="msvc-160"

### <a name="target-windows-subsystem-for-linux"></a>Linux 用 Windows サブシステムを対象にする

Linux 用 Windows サブシステム (WSL) が対象の場合は、リモート接続を追加する必要はありません。

WSL を対象にするには、メイン ツールバーの構成ドロップダウンの **[構成の管理]** を選択します。

![CMake の [構成の管理]](../build/media/vs2019-cmake-manage-configurations.png "CMake 構成ドロップダウン")

**[CMakeSettings.json]** ウィンドウが表示されます。

![構成の追加](media/cmake-linux-configurations.png "CMake の設定に構成を追加する")

**[構成の追加]** (緑の '+' ボタン) を押した後、GCC を使用する場合は **Linux-GCC-Debug** または **Linux-GCC-Release** を選択します。 Clang/LLVM ツールセットを使用する場合は [Clang バリアント] を使用します。  **[選択]** を押した後、 **Ctrl + S** キーを押して構成を保存します。

**Visual Studio 2019 バージョン 16.1** WSL が対象の場合、Visual Studio では、ソース ファイルをコピーし、ビルド ツリーの 2 つの同期コピーを保持する必要はありません。これは、Linux 上のコンパイラが、マウントされた Windows ファイル システムのソース ファイルに直接アクセスできるためです。
::: moniker-end
::: moniker range=">=msvc-150"

### <a name="intellisense"></a>IntelliSense

正確な C++ IntelliSense では、C++ ソース ファイルによって参照される C++ ヘッダーへのアクセスが必要です。 Visual Studio により、Linux から Windows の CMake プロジェクトによって参照されるヘッダーが自動的に使用されて、完全に忠実な IntelliSense エクスペリエンスが提供されます。 詳細については、[リモート ヘッダーの IntelliSense](configure-a-linux-project.md#remote_intellisense) のセクションを参照してください。

### <a name="locale-setting"></a>ロケールの設定

Visual studio はインストールされているパッケージを管理または構成しないため、Visual Studio の言語設定は Linux ターゲットに反映されません。 ビルド エラーなどの [出力] ウィンドウに表示されるメッセージは、Linux ターゲットの言語とロケールを使用して表示されます。 目的のロケールに合わせて Linux ターゲットを構成する必要があります。

## <a name="additional-settings"></a>追加設定

ビルドの前後や CMake 生成の前に Linux システムでコマンドを実行するには、次の設定を使用します。 値は、リモート システムで有効な任意のコマンドを指定できます。 出力はパイプで Visual Studio に戻されます。

```json
{
      "remotePrebuildCommand": "",
      "remotePreGenerateCommand": "",
      "remotePostbuildCommand": "",
}
```

## <a name="next-steps"></a>次の手順

[CMake デバッグ セッションを構成する](../build/configure-cmake-debugging-sessions.md?toc=/cpp/linux/toc.json&bc=/cpp/_breadcrumb/toc.json)

## <a name="see-also"></a>関連項目

[プロジェクトのプロパティの操作](../build/working-with-project-properties.md)<br/>
[CMake 設定をカスタマイズする](../build/customize-cmake-settings.md)<br/>
[CMake 定義済み構成リファレンス](../build/cmake-predefined-configuration-reference.md)

::: moniker-end
