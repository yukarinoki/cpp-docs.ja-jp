---
title: Visual Studio で Linux CMake プロジェクトを構成する
description: Visual Studio で Linux CMake プロジェクトを構成、編集、コンパイルする方法
ms.date: 05/21/2019
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: e2cda5e9b942342cca035c48054aadb5425b69cf
ms.sourcegitcommit: bde3279f70432f819018df74923a8bb895636f81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "66182892"
---
# <a name="configure-a-linux-cmake-project"></a>Linux CMake プロジェクトを構成する

CMake プロジェクトを含むフォルダーを開くと、Visual Studio によって、CMake が生成するメタデータを使用して、IntelliSense が構成され、自動的にビルドされます。 ローカルの構成およびデバッグ設定は、必要に応じて Visual Studio を使用している他のユーザーと共有できる JSON ファイルに格納されます。 

Visual Studio では CMakeLists.txt ファイルまたは元の CMake キャッシュが変更されないため、同じプロジェクトで作業している他のユーザーが、既に使用している任意のツールを使用し続けることができます。

Visual Studio での CMake サポートに関する一般的な情報については、[CMake Tools for Visual Studio](../build/cmake-projects-in-visual-studio.md) に関するページを参照してください。 まずこちらを読んでから、ここでの作業を進めてください。

## <a name="before-you-begin"></a>始める前に

まず、CMake コンポーネントを含む **C++ による Linux 開発** ワークロードがインストールされていることを確認します。 [Visual Studio での C++ Linux ワークロードのインストール](download-install-and-setup-the-linux-development-workload.md)に関するページを参照してください。 

Linux マシンに次のものがインストールされていることを確認してください。 

- gcc
- gdb
- rsync
- zip 

::: moniker range="vs-2019"

Linux による CMake プロジェクトのサポートには、ターゲット マシンに CMake の最新バージョンがインストールされていることが必要となります。 多くの場合、ディストリビューションの既定のパッケージ マネージャーによって提供されるバージョンは、IDE のすべての機能をサポートできるほど最新ではありません。 Visual Studio 2019 では、CMake の最新バージョンがインストールされていないリモートの Linux マシンに、CMake のユーザー ローカル コピーを自動的にインストールできます。 プロジェクトを最初にビルドするときに CMake の互換性のあるバージョンが検出されなかった場合、CMake をインストールすることを勧める情報バーが表示されます。

バイナリは `~/.vs/cmake` にインストールされます。 バイナリを配布すると、プロジェクトが自動的に再生成されます。 `CMakeSettings.json` の `cmakeExecutable` フィールドで指定する CMake が無効 (存在しない、またはサポートされていないバージョン) で、かつビルド済みバイナリが存在している場合は、Visual Studio では `cmakeExecutable` が無視され、ビルド済みバイナリが使われます。

::: moniker-end

::: moniker range="vs-2017"

Visual Studio で CMake を利用するには、CMake 3.8 で導入されたサーバー モードに対応する必要があります。 Microsoft から提供されている CMake バリアントについては、[https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases) から最新のビルド済みバイナリをダウンロードします。

:::moniker-end

## <a name="open-a-folder"></a>フォルダーを開く

最初に、メイン メニューから **[ファイル]**  >  **[開く]**  >  **[フォルダー]** の順に選択するか、コマンド ラインに「`devenv.exe <foldername>`」と入力します。 開いたフォルダーには、ソース コードと共に CMakeLists.txt ファイルが入っているはずです。
次のサンプルでは、単純な CMakeLists.txt ファイルと .cpp ファイルを確認できます。

```cpp
// hello.cpp

#include <iostream>

int main(int argc, char* argv[])
{
    std::cout << "Hello from Linux CMake" << std::endl;
}
```

CMakeLists.txt:

```cmd
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="choose-a-linux-target"></a>Linux ターゲットを選ぶ

フォルダーを開くとすぐに、Visual Studio によって CMakeLists.txt ファイルが解析され、**x86-Debug** の Windows ターゲットが指定されます。 Linux を対象とするには、プロジェクト設定を **Linux-Debug** または **Linux-Release** に変更します。

既定では、 **[ツール]**  >  **[オプション]**  >  **[クロス プラットフォーム]**  >  **[接続マネージャー]** の下にある一覧の、最初のリモート システムが選ばれます。 リモート接続が見つからない場合、リモート接続を作成するように求められます。 詳細については、[リモートの Linux コンピューターへの接続](connect-to-your-remote-linux-computer.md)に関するページを参照してください。

Linux ターゲットを指定すると、ソースが Linux マシンにコピーされます。 次に、Linux マシンで CMake が実行され、プロジェクトの CMake キャッシュが生成されます。

![Linux で CMake キャッシュを生成する](media/cmake-linux-1.png "Linux で CMake キャッシュを生成する")

リモート ヘッダーの IntelliSense サポートを提供するため、Visual Studio によって、Linux コンピューターからローカルの Windows コンピューター上のディレクトリにそれらが自動的にコピーされます。 詳細については、[リモート ヘッダーの IntelliSense](configure-a-linux-project.md#remote_intellisense) のセクションを参照してください。

## <a name="debug-the-project"></a>プロジェクトをデバッグする

リモート システムでコードをデバッグするには、ブレークポイントを設定し、プロジェクト設定の隣にあるツール バー メニューのスタートアップ項目として CMake ターゲットを選び、ツール バーの **[&#x23f5; 実行]** を選択するか、F5 キーを押します。

プログラムのコマンド ライン引数をカスタマイズするには、**ソリューション エクスプローラー**で実行可能ファイルを右クリックし、 **[デバッグ設定と起動設定]** を選びます。 これにより、プログラムに関する情報を含んだ launch.vs.json 構成ファイルが開かれるか、作成されます。 追加の引数を指定するには、`args` JSON 配列に引数を追加します。 詳細については、「[Open Folder projects for C++](../build/open-folder-projects-cpp.md)」 (C++ の [フォルダーを開く] プロジェクト) と [CMake デバッグ セッションの構成](../build/configure-cmake-debugging-sessions.md)に関するページを参照してください。

## <a name="configure-cmake-settings-for-linux"></a>Linux の CMake 設定を構成する

CMake Linux プロジェクト内の CMakeSettings.json ファイルで、[CMake 設定のカスタマイズ](../build/customize-cmake-settings.md)に関するページで一覧表示されているすべてのプロパティに加え、リモートの Linux コンピューター上のビルド設定を制御する追加のプロパティを指定できます。 

::: moniker range="vs-2019"

Visual Studio 2019 の CMake の既定の設定を変更するには、メイン ツールバーから **[構成]** ドロップダウンを開き、 **[構成の管理]** を選択します。 

   ![CMake 構成の管理](../build/media/vs2019-cmake-manage-configurations.png "CMake 構成ドロップダウン")

これにより **CMake 設定エディター**が表示されます。これを使用してルート プロジェクト フォルダー内の `CMakeSettings.json` ファイルを編集できます。 エディターの **[JSON の編集]** ボタンをクリックしてファイルを直接開くこともできます。 詳細については、[CMake 設定のカスタマイズ](../build/customize-cmake-settings.md)に関するページを参照してください。

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 2017 の既定の CMake 設定を変更するには、メイン メニューから **[CMake]、[CMake の設定の変更]、[CMakeLists.txt]** の順に選択するか、 **[ソリューション エクスプローラー]** の CMakeSettings.txt を右クリックし、 **[Change CMake Settings]\(CMake の設定の変更\)** を選びます。 Visual Studio によって、ルート プロジェクト フォルダー内に新しい `CMakeSettings.json` ファイルが作成されます。 **CMake 設定**エディター使用してファイルを開いたり、ファイルを直接変更したりできます。 詳細については、「[Customize CMake settings](../build/customize-cmake-settings.md)」 (CMake 設定のカスタマイズ) を参照してください。

::: moniker-end

次のサンプルでは、前のコード サンプルに基づく、Linux デバッグの既定の構成を確認できます。

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
次の表に、設定をまとめています。

|設定|説明|
|-----------|-----------------|
|`name`|この値には、任意の値を指定できます。|
|`remoteMachineName`|リモート システムが複数存在する場合、ターゲットとするリモート システムを指定します。 このフィールドには IntelliSense が有効になっており、適切なシステムの選択を支援します。|
|`remoteCMakeListsRoot`|リモート システム上の、プロジェクト ソースのコピー先を指定します。|
|`remoteBuildRoot`|リモート システムでビルド出力が生成される場所を指定します。 その出力は、`buildRoot` によって指定される場所にもローカル コピーされます。|
|`remoteInstallRoot` および `installRoot`| CMake インストールを行うときに適用されることを除き、`remoteBuildRoot` フィールドと `buildRoot` フィールドに似ています。|
|`remoteCopySources`|ローカル ソースがリモート コンピューターにコピーされるかどうかを指定します。 ファイルが多数あり、自分で既にソースを同期している場合、これを false に設定することがあります。|
|`remoteCopyOutputVerbosity`| エラーを診断する必要がある場合のコピー ステップの詳細度を指定します。|
|`remoteCopySourcesConcurrentCopies`| コピーのために生成されるプロセスの数を指定します。|
|`remoteCopySourcesMethod`| `rsync` または `sftp` を指定できます。|
|`remoteCopySourcesExclusionList`| リモート コンピューターにコピーされないようにするファイルを指定します。|
|`rsyncCommandArgs`|コピーの rsync メソッドを制御します。|
|`remoteCopyBuildOutput`| リモート ビルド出力がローカル ビルド フォルダーにコピーされるかどうかを制御します。|

さらに制御するためにこれらのオプション設定を使用できます。

```json
{
      "remotePrebuildCommand": "",
      "remotePreGenerateCommand": "",
      "remotePostbuildCommand": "",
}
```

そうしたオプションでは、ビルドの前後や CMake 生成の前にリモート システムでコマンドを実行できます。 値は、リモート システムで有効な任意のコマンドを指定できます。 出力はパイプで Visual Studio に戻されます。

::: moniker range="vs-2019"

Visual Studio 2019 では、**CMake 設定エディター**でこれらの設定すべてを編集することができます。

::: moniker-end

## <a name="see-also"></a>関連項目

[プロジェクトのプロパティの操作](../build/working-with-project-properties.md)<br/>
[Visual Studio の CMake プロジェクト](../build/cmake-projects-in-visual-studio.md)<br/>
[リモートの Linux コンピューターに接続する](connect-to-your-remote-linux-computer.md)<br/>
[CMake 設定をカスタマイズする](../build/customize-cmake-settings.md)<br/>
[CMake デバッグ セッションを構成する](../build/configure-cmake-debugging-sessions.md)<br/>
[Linux プロジェクトの配置、実行、デバッグ](deploy-run-and-debug-your-linux-project.md)<br/>
[CMake 定義済み構成リファレンス](../build/cmake-predefined-configuration-reference.md)<br/>
