---
title: Visual Studio で CMake のビルド設定をカスタマイズする
ms.date: 03/05/2019
helpviewer_keywords:
- CMake build settings
ms.openlocfilehash: 1bdf4ef3e20b055b6fa3d5449a880ddb7aab44a0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037524"
---
# <a name="customize-cmake-build-settings"></a>CMake のビルド設定をカスタマイズする

Visual Studio では、特定のプロジェクトの CMake キャッシュを作成するために CMake.exe が呼び出される方法を定義する複数の CMake 構成が用意されています。 新しい構成を追加するには、ツール バーの [構成] ドロップダウンをクリックして **[構成の管理]** を選択します。

   ![CMake の構成の管理](media/cmake-manage-configurations.png)

定義済みの構成のリストから選択できます。

   ![CMake の定義済み構成](media/cmake-configurations.png)

初めて構成を選択すると、Visual Studio によって `CMakeSettings.json` ファイルがプロジェクトのルート フォルダー内に作成されます。 このファイルは、たとえば**クリーン**操作の後などに、CMake キャッシュ ファイルを再作成するために使われます。 

追加の構成を追加するには、`CMakeSettings.json` を右クリックして、**[構成の追加]** を選択します。 

   ![CMake の構成の追加](media/cmake-add-configuration.png "CMake の構成の追加")

JSON の IntelliSense は、`CMakeSettings.json` ファイルの編集を支援します。

   ![CMake の JSON IntelliSense](media/cmake-json-intellisense.png "CMake の JSON IntelliSense")

**CMake の設定エディター**を使用してファイルを編集することもできます。 **ソリューション エクスプローラー**で `CMakeSettings.json` を右クリックして、**[CMake 設定の編集]** を選択します。 または、エディター ウィンドウの上部にある構成ドロップダウンから **[構成の管理]** を選択します。 

また、`CMakeSettings.json` を直接編集してカスタム構成を作成することもできます。次の例は、開始点として使用できるサンプルの構成を示しています。

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

- **name**: C++ の構成ドロップダウンに表示される名前です。 `${name}` マクロを使用すると、パスなどの他のプロパティ値を作成するときに、この値を使用することができます。 例については、`CMakeSettings.json` の **buildRoot** の定義をご覧ください。

- **generator**: CMake **-G** スイッチに対応し、使用するジェネレーターを指定します。 他のプロパティ値を作成するときに、このプロパティをマクロ `${generator}` として使うこともできます。 現在、Visual Studio では次の CMake ジェネレーターがサポートされています。

  - "Ninja"
  - "Visual Studio 14 2015"
  - "Visual Studio 14 2015 ARM"
  - "Visual Studio 14 2015 Win64"
  - "Visual Studio 15 2017"
  - "Visual Studio 15 2017 ARM"
  - "Visual Studio 15 2017 Win64"

  Ninja は柔軟性や機能ではなく、ビルド速度が速いことを目的に設計されているため、既定値としてこれが設定されます。 ただし、CMake プロジェクトによっては、Ninja を使うと正しくビルドできないことがあります。 そのような場合は、代わりに Visual Studio プロジェクトを生成するように CMake に指示できます。

  Visual Studio ジェネレーターを指定するには、メイン メニューから **[CMake] > [CMake の設定を変更]** を選んで、`CMakeSettings.json` を開きます。 "Ninja" を削除して「V」と入力します。 これにより IntelliSense がアクティブになり、必要なジェネレーターを選択できます。

  アクティブな構成で Visual Studio ジェネレーターを指定すると、`-m -v:minimal` 引数を指定して MSBuild.exe が既定で呼び出されます。 ビルドをカスタマイズするには、`CMakeSettings.json` ファイル内で、`buildCommandArgs` プロパティによりビルド システムに渡される追加の [MSBuild コマンド ライン引数](../build/reference/msbuild-visual-cpp-overview.md)を指定できます。
    
    ```json
    "buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
    ```

- **buildRoot**: **-DCMAKE_BINARY_DIR** スイッチに対応し、CMake キャッシュが作成される場所を指定します。 フォルダーが存在しない場合は、作成されます。

- **variables**: **-D** *_name_=_value_* として CMake に渡される、CMake 変数の名前と値のペアを含みます。 CMake プロジェクトのビルド命令で CMake キャッシュ ファイルに直接変数を追加するように指定している場合は、代わりにここで追加することをお勧めします。 次の例は、14.14.26428 MSVC ツールセットに名前と値のペアを指定する方法を示しています。

```json
"variables": [
    {
      "name": "CMAKE_CXX_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe"
    },
    {
      "name": "CMAKE_C_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe"
    }
  ]
```

- **cmakeCommandArgs**: CMake.exe に渡す追加のスイッチを指定します。

- **configurationType**: 選択したジェネレーターのビルド構成の種類を定義します。 現在サポートされている値は、"Debug"、"MinSizeRel"、"Release"、"RelWithDebInfo" です。

- **ctestCommandArgs**: テストの実行時に CTest に渡される追加スイッチを指定します。

- **buildCommandArgs**: 基礎となるビルド システムに渡される追加スイッチを指定します。 たとえば、Ninja ジェネレーターの使用時に -v を渡すと、コマンド ラインの出力が Ninja に強制されます。

CMake Linux プロジェクトでは、追加の設定が使用できます。 「[Configure a CMake Linux project](../linux/cmake-linux-project.md)」 (CMake Linux プロジェクトの構成) を参照してください。

## <a name="environment-variables"></a>環境変数

 `CMakeSettings.json` 上記で説明したプロパティのいずれかの使用の環境変数もサポートしています。 `${env.FOO}` という構文を使うと、環境変数 %FOO% が展開されます。
このファイルの内部で組み込みマクロにアクセスすることもできます。

- `${workspaceRoot}` – ワークスペース フォルダーの完全なパスを提供します。
- `${workspaceHash}` – ワークスペースの場所のハッシュ(たとえば、フォルダー パスで使用する場合)、現在のワークスペースの一意の識別子を作成するのに役立ちます
- `${projectFile}` – ルート CMakeLists.txt ファイルの完全なパス
- `${projectDir}` – ルート CMakeLists.txt ファイルのフォルダーの完全なパス
- `${thisFile}` – の完全なパス、`CMakeSettings.json`ファイル
- `${name}` – 構成の名前
- `${generator}` – この構成で使用されている CMake ジェネレーターの名前

## <a name="ninja-command-line-arguments"></a>Ninja のコマンド ライン引数

ターゲットを指定しないと、"default" ターゲットがビルドされます (マニュアルを参照)。

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|オプション|説明|
|--------------|------------|
| --version  | Ninja のバージョンを書き出します ("1.7.1")|
|   -C DIR   | 何かを実行する前に、DIR (ディレクトリ) に変更します|
|   -f FILE  | 入力ビルド ファイルを指定します (既定値は build.ninja)|
|   -j N     | N 個のジョブを並列実行します (既定値は 14、使用可能な CPU の数から派生)|
|   -k N     | N 個のジョブが失敗するまで続けます (既定値は 1)|
|   -l N     | 負荷の平均が N より大きい場合は、新しいジョブを開始しません|
|   -n       | ドライ実行 (コマンドを実行しませんが、成功したように動作します)|
|   -v       | ビルド中にすべてのコマンド ラインを表示します|
|   -d MODE  | デバッグを有効にします (モードを一覧表示するには -d list を使用)|
|   -t TOOL  | サブツールを実行します (サブツールを一覧表示するには -t list を使用)。 最上位レベルのオプションを終了します。さらに、ツールに渡される、フラグ|
|   -w FLAG  | 警告を調整します (警告を一覧表示するには -w list を使用)|

## <a name="inherited-environments"></a>継承された環境

 `CMakeSettings.json` サポートは、環境を継承します。 この機能を使うと、(1) 既定の環境を継承することができ、(2) 実行時に CMake.exe に渡されるカスタム環境変数を作成できます。

```json
  "inheritEnvironments": [ "msvc_x64_x64" ]
```

上の例は、**-arch=amd64 -host_arch=amd64** 引数を指定して **VS 2017 の開発者コマンド プロンプト**を実行するのと同じです。

次の表は、既定の値を示します。

|コンテキスト名|説明|
|-----------|-----------------|
|vsdev|既定の Visual Studio 環境|
|msvc_x86|x86 ツールを使って、x86 用にコンパイルします|
|msvc_arm| x86 ツールを使って、ARM 用にコンパイルします|
|msvc_arm64|x86 ツールを使って、ARM64 用にコンパイルします|
|msvc_x86_x64|x86 ツールを使って、AMD64 用にコンパイルします|
|msvc_x64_x64|64 ビット ツールを使って、AMD64 用にコンパイルします|
|msvc_arm_x64|64 ビット ツールを使って、ARM 用にコンパイルします|
|msvc_arm64_x64|64 ビット ツールを使って、ARM64 用にコンパイルします|

### <a name="custom-environment-variables"></a>カスタム環境変数

`CMakeSettings.json` では、グローバルに、または **environments** プロパティを使用して構成ごとに、カスタム環境変数を定義できます。 次の例では、1 つのグローバル変数 **BuildDir** を定義します。これは、x86-Debug と x64-Debug の両方の構成で継承されます。 各構成は、この変数を使って、その構成の **buildRoot** プロパティの値を指定します。 各構成が **inheritEnvironments** プロパティを使ってその構成のみに適用される変数を指定する方法にも注意してください。

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x86 compiler.
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.BuildDir}\\${name}"    },
    {
      "name": "x64-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x64 compiler.
      "inheritEnvironments": [ "msvc_x64" ],
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

次の例では、x86 デバッグ構成が **BuildDir** プロパティに対して独自の値を定義します。 この値は、**BuildRoot** が `D:\custom-builddir\x86-Debug` に評価されるように、グローバル **BuildDir** プロパティによって設定される値をオーバーライドします。

```json
{
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",

      // The syntax for this property is the same as the global one above.
      "environments": [
        {
          // Replace the global property entirely.
          "BuildDir": "D:\\custom-builddir",
        }
      ],

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      // Evaluates to "D:\custom-builddir\x86-Debug"
      "buildRoot": "${env.BuildDir}\\${name}"
    },
    {
      "name": "x64-Debug",

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x64" ],
      // Since this configuration doesn’t modify BuildDir, it inherits
      // from the one defined globally.
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

## <a name="see-also"></a>関連項目

[Visual Studio で CMake プロジェクト](cmake-projects-in-visual-studio.md)<br/>
[Linux CMake プロジェクトを構成する](../linux/cmake-linux-project.md)<br/>
[リモートの Linux コンピューターに接続する](../linux/connect-to-your-remote-linux-computer.md)<br/>
[CMake デバッグ セッションを構成する](configure-cmake-debugging-sessions.md)<br/>
[Linux プロジェクトのデプロイ、実行、デバッグ](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake 定義済み構成リファレンス](cmake-predefined-configuration-reference.md)<br/>
