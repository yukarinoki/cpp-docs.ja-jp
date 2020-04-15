---
title: Visual Studio で CMake のビルド設定をカスタマイズする
ms.date: 08/20/2019
helpviewer_keywords:
- CMake build settings
ms.openlocfilehash: c6bd1404799ccc9ad6b689646cd066849d48fca8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328678"
---
# <a name="customize-cmake-build-settings"></a>CMake のビルド設定をカスタマイズする

::: moniker range="vs-2019"

Visual Studio 2019 以降では、**CMake 設定エディター**を使うことにより、構成を追加して、その設定をカスタマイズすることができます。 エディターは *、CMakeSettings.json*ファイルを手動で編集する簡単な代替手段を意図していますが、ファイルを直接編集する場合は、エディターの右上にある **[JSON の編集]** リンクをクリックします。

エディターを開くには、メイン ツール バーの **[構成]** ドロップダウンをクリックして、**[構成の管理]** を選択します。

![CMake 構成ドロップダウン](media/vs2019-cmake-manage-configurations.png)

インストールされている構成が左側に示された**設定エディター**が表示されます。

![CMake 設定エディター](media/cmake-settings-editor.png)

既定では、1`x64-Debug`つの構成が用意されています。 緑のプラス記号をクリックすると、追加の構成を追加できます。 エディターに表示される設定は、選択した構成によって異なる場合があります。

エディターで選択したオプションは *、CMakeSettings.json*という名前のファイルに書き込まれます。 このファイルで指定されているコマンド ライン引数と環境変数は、プロジェクトをビルドするときに CMake に渡されます。 *CMakeLists.txt*が自動的に変更されることはありません。*CMakeSettings.json*を使用すると、Visual Studio を使用してビルドをカスタマイズし、CMake プロジェクト ファイルをそのままにして、チームの他のユーザーが使用しているツールを使用できるようにします。

## <a name="cmake-general-settings"></a>CMake の全般設定

**[全般]** では、次の設定を使用できます。

### <a name="configuration-name"></a>構成名

**name** の設定に対応します。 この名前は、C++ 構成ドロップダウンに表示されます。 `${name}` マクロを使って、パスなどの他のプロパティ値を作成できます。

### <a name="configuration-type"></a>Configuration type (構成の種類)

**configurationType** の設定に対応します。 選択したジェネレーターのビルド構成の種類を定義します。 現在サポートされている値は、"Debug"、"MinSizeRel"、"Release"、"RelWithDebInfo" です。 CMAKE_BUILD_TYPE[にマップ](https://cmake.org/cmake/help/latest/variable/CMAKE_BUILD_TYPE.html)されます。

### <a name="toolset"></a>ツールセット

**inheritedEnvironments** の設定に対応します。 選択した構成のビルドに使用するコンパイラ環境を定義します。 サポートされる値は、構成の種類によって異なります。 カスタム環境を作成するには、設定エディターの右上隅にある **[JSON**の編集] リンクを選択し *、CMakeSettings.json*ファイルを直接編集します。

### <a name="cmake-toolchain-file"></a>CMake ツールチェーン ファイル

[CMake ツールチェーン ファイル](https://cmake.org/cmake/help/latest/variable/CMAKE_TOOLCHAIN_FILE.html)へのパス。 このパスは、"-DCMAKE_TOOLCHAIN_FILE =\<ファイルパス>" として CMake に渡されます。 ツールチェーンファイルは、コンパイラやツールチェーンユーティリティの場所、およびその他のターゲットプラットフォームとコンパイラ関連の情報を指定します。 既定では、この設定が指定されていない場合は[、vcpkg ツールチェーン ファイル](https://github.com/microsoft/vcpkg/blob/master/docs/examples/installing-and-using-packages.md#cmake)が使用されます。

### <a name="build-root"></a>ビルド ルート

**buildRoot** に対応します。 [CMAKE_BINARY_DIR](https://cmake.org/cmake/help/v3.15/variable/CMAKE_BINARY_DIR.html)にマップし、CMake キャッシュを作成する場所を指定します。 指定したフォルダーが存在しない場合は作成されます。

## <a name="command-arguments"></a>コマンド引数

**[コマンド引数]** では、次の設定を使用できます。

### <a name="cmake-command-arguments"></a>CMake コマンド引数

**cmakeCommandArgs** に対応します。 CMake.exe に渡される追加[のコマンド ライン オプション](https://cmake.org/cmake/help/latest/manual/cmake.1.html)を指定します。

### <a name="build-command-arguments"></a>ビルド コマンド引数

**に対応しています**。 基になるビルド システムに渡す追加スイッチを指定します。 たとえば、Ninja`-v`ジェネレータを使用する場合に渡すと、Ninja はコマンドラインを出力するように強制されます。

### <a name="ctest-command-arguments"></a>CTest コマンド引数

**に対応しています**。 テストの実行時に CTest に渡す追加[のコマンド ライン オプション](https://cmake.org/cmake/help/v3.15/manual/ctest.1.html)を指定します。

## <a name="general-settings-for-remote-builds"></a>リモート ビルドの全般設定

リモート ビルドを使う Linux などの構成では、次の設定も使用できます。

### <a name="rsync-command-arguments"></a>rsync コマンド引数

[rsync](https://download.samba.org/pub/rsync/rsync.html)に渡される追加のコマンドライン オプションは、高速で多目的なファイル コピー ツールです。

## <a name="cmake-variables-and-cache"></a>CMake 変数とキャッシュ

これらの設定を使用すると、CMake 変数を設定し *、CMakeSettings.json*に保存できます。 ビルド時に CMake に渡され *、CMakeLists.txt*ファイル内の値をオーバーライドします。 CMakeGUI と同じ方法でこのセクションを使用し、編集できるすべての CMake 変数の一覧を表示できます。 **[Save and generate cache]\(キャッシュの保存と生成\)** ボタンをクリックして、高度な変数 (CMakeGUI ごと) を含む編集可能なすべての CMake 変数の一覧を表示します。 変数名でリストをフィルター処理できます。

**変数**に対応します。 **-D**名前値として CMake に渡される CMake 変数の*_名前_=と値*のペアが含まれています。 CMake プロジェクトのビルド命令で、CMake キャッシュ ファイルに直接変数を追加する方法を指定している場合は、ここで追加することをお勧めします。

## <a name="advanced-settings"></a>詳細設定

### <a name="cmake-generator"></a>CMake ジェネレーター

**ジェネレータ**に対応しています。 CMake **-G**スイッチにマップし、使用する[CMake ジェネレータ](https://cmake.org/cmake/help/latest/manual/cmake-generators.7.html)を指定します。 他のプロパティ値を作成するときに、このプロパティをマクロ `${generator}` として使うこともできます。 現在、Visual Studio では次の CMake ジェネレーターがサポートされています。

- "Ninja"
- "Unix Makefiles"
- "Visual Studio 16 2019"
- "Visual Studio 16 2019 Win64"
- "Visual Studio 16 2019 ARM"
- "Visual Studio 15 2017"
- "Visual Studio 15 2017 Win64"
- "Visual Studio 15 2017 ARM"
- "Visual Studio 14 2015"
- "Visual Studio 14 2015 Win64"
- "Visual Studio 14 2015 ARM"
  
Ninja は柔軟性と機能ではなく、高速なビルド速度を使用するように設計されているため、デフォルトとして設定されています。 ただし、CMake プロジェクトによっては、Ninja を使うと正しくビルドできないことがあります。 その場合は、代わりに Visual Studio プロジェクトを生成するように CMake に指示できます。

### <a name="intellisense-mode"></a>IntelliSense モード

IntelliSense エンジンで使用される IntelliSense モード。 モードが選択されていない場合、Visual Studio は指定されたツールセットから継承します。  

### <a name="install-directory"></a>インストール ディレクトリ

CMake がターゲットをインストールするディレクトリ。 CMAKE_INSTALL_PREFIX[にマップ](https://cmake.org/cmake/help/latest/variable/CMAKE_INSTALL_PREFIX.html)します。

### <a name="cmake-executable"></a>CMake 実行可能ファイル

CMake プログラムの実行可能ファイルへの完全パス(ファイル名と拡張子を含む)。 Visual Studio で CMake のカスタム バージョンを使用できます。 リモート ビルドの場合は、リモート マシン上の CMake の場所を指定します。

リモート ビルドを使う Linux などの構成では、次の設定も使用できます。

### <a name="remote-cmakeliststxt-root"></a>リモート CMakeLists.txt ルート

ルート*CMakeLists.txt*ファイルを含むリモート コンピューター上のディレクトリ。

### <a name="remote-install-root"></a>リモート インストール ルート

CMake によってターゲットがインストールされるリモート マシン上のディレクトリです。 CMAKE_INSTALL_PREFIX[にマップ](https://cmake.org/cmake/help/latest/variable/CMAKE_INSTALL_PREFIX.html)します。

### <a name="remote-copy-sources"></a>ソースのリモート コピー

リモート マシンにソース ファイルをコピーするかどうかを指定し、rsync と sftp のどちらを使用するかを指定できます。

## <a name="directly-edit-cmakesettingsjson"></a>CMakeSettings.json を直接編集する

また、カスタム構成を作成するために*CMakeSettings.json*を直接編集することもできます。 **設定エディター**の右上には **[JSON の編集]** ボタンがあり、編集用にファイルを開くことができます。

次の例では、作業を始めるときに使用できるサンプルの構成を示します。

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

ファイルを編集するのに役立ちます。 *CMakeSettings.json*

   ![CMake JSON インテリセンス](media/cmake-json-intellisense.png "CMake JSON インテリセンス")

互換性のない設定を選択すると、JSON エディタからも通知されます。

ファイルの各プロパティについて詳しくは、「[CMakeSettings.json スキーマ リファレンス](cmakesettings-reference.md)」をご覧ください。

::: moniker-end

::: moniker range="<=vs-2017"

Visual Studio 2017 では、特定のプロジェクトの CMake キャッシュを作成するために CMake.exe が呼び出される方法を定義する複数の CMake 構成が用意されています。 新しい構成を追加するには、ツール バーの [構成] ドロップダウンをクリックして **[構成の管理]** を選択します。

   ![CMake の構成の管理](media/cmake-manage-configurations.png)

定義済みの構成のリストから選択できます。

   ![CMake の定義済み構成](media/cmake-configurations.png)

構成を初めて選択すると、プロジェクトのルート フォルダーに*CMakeSettings.json*ファイルが作成されます。 このファイルは、たとえば**クリーン**操作の後などに、CMake キャッシュ ファイルを再作成するために使われます。

追加の構成を追加するには *、CMakeSettings.json*を右クリックし、[**構成の追加**] を選択します。

   ![CMake 追加構成](media/cmake-add-configuration.png "CMake 追加設定")

**CMake の設定エディター**を使用してファイルを編集することもできます。 **ソリューション エクスプローラー**で*CMakeSettings.json*を右クリックし **、[CMake 設定の編集]** を選択します。 または、エディター ウィンドウの上部にある構成ドロップダウンから **[構成の管理]** を選択します。

また、カスタム構成を作成するために*CMakeSettings.json*を直接編集することもできます。 次の例では、作業を始めるときに使用できるサンプルの構成を示します。

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

ファイルを編集するのに役立ちます。 *CMakeSettings.json*

   ![CMake JSON インテリセンス](media/cmake-json-intellisense.png "CMake JSON インテリセンス")

ファイルの各プロパティについて詳しくは、「[CMakeSettings.json スキーマ リファレンス](cmakesettings-reference.md)」をご覧ください。

::: moniker-end

## <a name="see-also"></a>関連項目

[C メイク プロジェクトのビジュアル スタジオ](cmake-projects-in-visual-studio.md)<br/>
[Linux CMake プロジェクトを構成する](../linux/cmake-linux-project.md)<br/>
[リモートの Linux コンピューターに接続する](../linux/connect-to-your-remote-linux-computer.md)<br/>
[CMake デバッグ セッションを構成する](configure-cmake-debugging-sessions.md)<br/>
[Linux プロジェクトの配置、実行、デバッグ](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake 定義済み構成リファレンス](cmake-predefined-configuration-reference.md)
