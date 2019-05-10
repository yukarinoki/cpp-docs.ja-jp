---
title: Visual Studio で CMake のビルド設定をカスタマイズする
ms.date: 04/25/2019
helpviewer_keywords:
- CMake build settings
ms.openlocfilehash: 20ed066f71a5c8c3acb00ef5923fa5c9f16ac229
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877156"
---
# <a name="customize-cmake-build-settings"></a>CMake のビルド設定をカスタマイズする

::: moniker range="vs-2019"

Visual Studio 2019 以降では、構成を追加し、使用してその設定をカスタマイズ、、 **CMake の設定エディター**します。 エディターは、CMakeSettings.json ファイルを手動で編集する代わりに簡単にするものですが、ファイルを直接編集する場合は、クリックして、 **JSON の編集**エディターの右上のリンク。 

エディターを開くには、をクリックして、**構成**メイン ツールバーでは、ドロップダウンを選択**構成の管理**します。

![CMake 構成ドロップダウン](media/vs2019-cmake-manage-configurations.png)

表示、**設定エディター**左側でインストールされている構成を使っています。 

![CMake の設定エディター](media/cmake-settings-editor.png)

Visual Studio では、既定で 2 つの構成が用意されています:`x64-Debug`と`x86-Debug`します。 追加の構成を追加するには、緑色のプラス記号をクリックします。エディターで表示される設定は、構成の選択に応じて異なる場合があります。

エディターで選択したオプションは、CMakeSettings.json をという名前のファイルに書き込まれます。 このファイルは、コマンドライン引数と、プロジェクトをビルドするときに、CMake に渡される環境変数を提供します。 Visual Studio で CMakeLists.txt を自動的に変更は行わないCMakeSettings.json を使用して他のチームを使用している任意のツールで使用できるように、CMake プロジェクト ファイルの変更を加えずまま中に Visual Studio を使用してビルドをカスタマイズできます。

## <a name="cmake-general-settings"></a>CMake の 全般設定

次の設定は 使用可能な**全般**見出し。

### <a name="configuration-name"></a>構成名

対応する、**名前**設定します。 これに表示される名前、C++構成 ドロップダウン リスト。 使用することができます、`${name}`マクロをパスなどの他のプロパティ値を作成します。


### <a name="configuration-type"></a>構成の種類

対応する、 **configurationType**設定します。 選択したジェネレーターのビルド構成の種類を定義します。 現在サポートされている値は、"Debug"、"MinSizeRel"、"Release"、"RelWithDebInfo" です。

### <a name="toolset"></a>ツールセット

対応する、 **inheritedEnvironments**設定します。 選択した構成のビルドに使用されるコンパイラ環境を定義します。 サポートされている値は、構成の種類によって異なります。 カスタム環境を作成する をクリックして、**編集 JSON**設定エディターの右上隅にあるリンクし、CMakeSettings.json ファイルを直接編集します。

### <a name="cmake-toolchain-file"></a>CMake ツール チェーンのファイル

CMake ツール チェーンのファイルへのパス。 として CMake に渡される"-DCMAKE_TOOLCHAIN_FILE = \<filepath >"。

### <a name="build-root"></a>ルートを作成します。

対応する**buildRoot**します。 マップ **-DCMAKE_BINARY_DIR**切り替え、CMake キャッシュが作成される場所を指定します。 フォルダーが存在しない場合は、作成されます。

## <a name="command-arguments"></a>コマンド引数

次の設定は 使用可能な**コマンド引数**見出し。

### <a name="cmake-command-arguments"></a>CMake コマンド引数

対応する**cmakeCommandArgs**します。 CMake.exe を通過するすべてのスイッチを指定します。

### <a name="build-command-arguments"></a>ビルド コマンドの引数

対応する**buildCommandArgs**: ビルド システムを基になるに渡す追加のスイッチを指定します。 たとえば、Ninja ジェネレーターの使用時に -v を渡すと、コマンド ラインの出力が Ninja に強制されます。


### <a name="ctest-command-arguments"></a>CTest コマンド引数

対応する**ctestCommandArgs**: テストの実行時に CTest に渡す追加のスイッチを指定します。

## <a name="general-settings-for-remote-builds"></a>リモート ビルドの全般設定

リモート ビルドを使用する Linux などの構成を次の設定を使用できますも。

### <a name="rsync-command-arguments"></a>rsync コマンド引数

Rsync に渡されるコマンドライン引数を提供します。 

## <a name="cmake-variables-and-cache"></a>CMake 変数とキャッシュ

これらの設定を使用すると、CMake 変数を設定し、CMakeSettings.json で保存できます。 ビルド時に CMake に渡されるされ、どのような値があります CMakeLists.txt ファイルが上書きされます。 このセクションでは、編集する使用可能なすべての CMake 変数の一覧を表示する、CMakeGUI を使用するのと同じ方法で使用できます。 をクリックして、**を保存し、キャッシュの生成**(CMakeGUI) ごとの高度な変数を編集する使用可能なすべての CMake 変数の一覧を表示するボタンをクリックします。 変数名で一覧をフィルター処理できます。 

対応する**変数**: として返されます CMake 変数の名前と値のペアを含む **-d** *_名前_= _値_* に CMake にします。 CMake プロジェクトのビルド命令で CMake キャッシュ ファイルに直接変数を追加するように指定している場合は、代わりにここで追加することをお勧めします。

## <a name="advanced-settings"></a>詳細設定

### <a name="cmake-generator"></a>CMake ジェネレーター

対応する**ジェネレーター**: CMake にマップ **-g**スイッチを使用するコード ジェネレーターを指定します。 他のプロパティ値を作成するときに、このプロパティをマクロ `${generator}` として使うこともできます。 現在、Visual Studio では次の CMake ジェネレーターがサポートされています。

  - "Ninja"
  - 「Unix メイクファイル」
  - "Visual Studio 16 2019"
  - "Visual Studio 16 2019 Win64"
  - - "Visual Studio 16 2019 ARM"
  - "Visual Studio 15 2017"
  - "Visual Studio 15 2017 Win64"
  - "Visual Studio 15 2017 ARM"
  - "Visual Studio 14 2015"
  - "Visual Studio 14 2015 Win64"
  - "Visual Studio 14 2015 ARM"
  
  Ninja は柔軟性や機能ではなく、ビルド速度が速いことを目的に設計されているため、既定値としてこれが設定されます。 ただし、CMake プロジェクトによっては、Ninja を使うと正しくビルドできないことがあります。 そのような場合は、代わりに Visual Studio プロジェクトを生成するように CMake に指示できます。

### <a name="intellisense-mode"></a>IntelliSense モード

正確な intellisense は、プロジェクトの適切な値に設定します。

### <a name="install-directory"></a>インストール ディレクトリ

CMake が構築されているターゲットをインストールするディレクトリ。

### <a name="cmake-executable"></a>CMake の実行可能ファイル

ファイル名と拡張子を含む、CMake 実行ファイルの完全パスです。 リモート ビルドを行うには、リモート コンピューターで CMake の場所を指定します。

リモート ビルドを使用する Linux などの構成を次の設定を使用できますも。

### <a name="remote-cmakeliststxt-root"></a>リモートの CMakeLists.txt ルート

ルートの CMakeLists.txt ファイルが含まれているリモート コンピューター上のディレクトリ。

### <a name="remote-install-root"></a>リモート インストール ルート

CMake がターゲットをインストールするリモート コンピューター上のディレクトリ。

### <a name="remote-copy-sources"></a>リモート コピーのソース

ソース ファイルをリモート コンピューターにコピーするかどうかを指定し、指定することができますか sftp、rsync を使用するかどうか。 

## <a name="directly-edit-cmakesettingsjson"></a>CMakeSettings.json を直接編集します。

直接編集することができます`CMakeSettings.json`カスタム構成を作成します。 **設定エディター**が、 **JSON の編集**ファイルを編集用に表示される右上のボタンをクリックします。 

次の例は、サンプル構成には、開始点として使用することを示しています。

```json
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "-v",
      "ctestCommandArgs": ""
    },

```

編集が JSON の IntelliSense によって、`CMakeSettings.json`ファイル。

   ![CMake の JSON IntelliSense](media/cmake-json-intellisense.png "CMake の JSON IntelliSense")

JSON エディターも通知する互換性のない設定を選択するとします。

各ファイルのプロパティの詳細については、次を参照してください。 [CMakeSettings.json スキーマ リファレンス](cmakesettings-reference.md)します。

::: moniker-end

::: moniker range="<=vs-2017"

Visual Studio 2017 には、指定したプロジェクトの CMake キャッシュを作成する CMake.exe を呼び出す方法を定義するいくつかの CMake 構成が用意されています。 新しい構成を追加するには、ツール バーの [構成] ドロップダウンをクリックして **[構成の管理]** を選択します。

   ![CMake の構成の管理](media/cmake-manage-configurations.png)

定義済みの構成のリストから選択できます。

   ![CMake の定義済み構成](media/cmake-configurations.png)

初めて構成を選択すると、Visual Studio によって `CMakeSettings.json` ファイルがプロジェクトのルート フォルダー内に作成されます。 このファイルは、たとえば**クリーン**操作の後などに、CMake キャッシュ ファイルを再作成するために使われます。 

追加の構成を追加するには、`CMakeSettings.json` を右クリックして、**[構成の追加]** を選択します。 

   ![CMake の構成の追加](media/cmake-add-configuration.png "CMake の構成の追加")

**CMake の設定エディター**を使用してファイルを編集することもできます。 **ソリューション エクスプローラー**で `CMakeSettings.json` を右クリックして、**[CMake 設定の編集]** を選択します。 または、エディター ウィンドウの上部にある構成ドロップダウンから **[構成の管理]** を選択します。 

直接編集することができます`CMakeSettings.json`カスタム構成を作成するには、次の例を示しますサンプル構成には、開始点として使用することができます。

```json
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "-v",
      "ctestCommandArgs": ""
    },

```

JSON の IntelliSense は、`CMakeSettings.json` ファイルの編集を支援します。

   ![CMake の JSON IntelliSense](media/cmake-json-intellisense.png "CMake の JSON IntelliSense")

各ファイルのプロパティの詳細については、次を参照してください。 [CMakeSettings.json スキーマ リファレンス](cmakesettings-reference.md)します。

::: moniker-end

## <a name="see-also"></a>関連項目

[Visual Studio の CMake プロジェクト](cmake-projects-in-visual-studio.md)<br/>
[Linux CMake プロジェクトを構成する](../linux/cmake-linux-project.md)<br/>
[リモートの Linux コンピューターに接続する](../linux/connect-to-your-remote-linux-computer.md)<br/>
[CMake デバッグ セッションを構成する](configure-cmake-debugging-sessions.md)<br/>
[Linux プロジェクトの配置、実行、デバッグ](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake 定義済み構成リファレンス](cmake-predefined-configuration-reference.md)<br/>
