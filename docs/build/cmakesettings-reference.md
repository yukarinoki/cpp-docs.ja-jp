---
title: CMakeSettings.json スキーマ リファレンス
ms.date: 04/25/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: 80392eedd5ef50ddd9c9bcb81c1605a534088133
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877102"
---
# <a name="cmakesettingsjson-schema-reference"></a>CMakeSettings.json スキーマ リファレンス

**Cmakesettings.json**' ファイルには、指定したプラットフォームのプロジェクトをビルドするために CMake と Visual Studio の対話方法を指定する情報が含まれています。 ファイルは、環境変数または引数 cmake.exe 環境などの情報を格納します。 直接編集したり、使用して、**の CMake 設定エディター**します。 参照してください[CMake のカスタマイズは、Visual Studio での設定をビルド](customize-cmake-settings.md)エディターの詳細についてはします。

## <a name="environments"></a>環境

`environments`配列の一覧に含まれる`items`型の`object`コンパイラ ツールセット「環境」を定義する。 環境は変数のセットを `configuration` に適用するのに使用できます。 `environments` 配列内の各項目は以下で構成されています。

- `namespace`: フォーム `namespace.variable` 内の構成から環境変数を参照できるように環境に名前を付けます。 既定の環境オブジェクトは `env` と呼ばれ、`%USERPROFILE%` などの特定のシステム環境変数で設定されます。
- `environment`: この変数グループを一意に識別します。 後で `inheritEnvironments` エントリでグループが継承できるようにします。
- `groupPriority`:これらの変数を評価するときの優先順位を指定する整数。 数字が大きい大きい項目が最初に評価されます。
- `inheritEnvironments`:このグループによって継承される環境セットを指定する値の配列。 この機能を使用すると、既定の環境を継承し、実行時に CMake.exe に渡されるカスタム環境変数を作成できます。

   ```json
   "inheritEnvironments": [ "msvc_x64_x64" ]
   ```

   上の例は、**-arch=amd64 -host_arch=amd64** 引数を指定して **VS 2017 の開発者コマンド プロンプト**を実行するのと同じです。 任意のカスタム環境を使用することも、次の定義済みの環境を使用することもできます。
 
  - linux_arm:ARM Linux をリモートでターゲットにします。
  - linux_x64:x64 Linux をリモートでターゲットにします。
  - linux_x86:x86 Linux をリモートでターゲットにします。
  - msvc_arm:MSVC コンパイラを使用して ARM Windows をターゲットとします。
  - msvc_arm_x64:64 ビットの MSVC コンパイラを使用して ARM Windows をターゲットとします。
  - msvc_arm64:MSVC コンパイラを使用して ARM64 Windows をターゲットとします。
  - msvc_arm64_x64:64 ビットの MSVC コンパイラを使用して ARM64 Windows をターゲットとします。
  - msvc_x64:MSVC コンパイラを使用して x64 Windows をターゲットとします。
  - msvc_x64_x64:64 ビットの MSVC コンパイラを使用して x64 Windows をターゲットとします。
  - msvc_x86:MSVC コンパイラを使用して x86 Windows をターゲットとします。
  - msvc_x86_x64:64 ビットの MSVC コンパイラを使用して x86 Windows をターゲットとします。

## <a name="configurations"></a>構成

`configurations` 配列は、同じフォルダー内の CMakeLists.txt ファイルに適用される CMake 構成を表すオブジェクトで構成されます。 これらのオブジェクトを使用して、複数のビルド構成を定義して、IDE 内でそれらを簡単に切り替えることもできます。 

`configuration` には次のプロパティがあります。
- `name`: 構成に名前を付けます。
- `description`: メニューに表示されるこの構成の説明。
- `generator`: この構成に使用する CMake ジェネレーターを指定します。 次のいずれかを指定できます。

  - Visual Studio 15 2017
  - Visual Studio 15 2017 Win64
  - Visual Studio 15 2017 ARM
  - Visual Studio 14 2015
  - Visual Studio 14 2015 Win64
  - Visual Studio 14 2015 ARM
  - UNIX メイクファイル
  - Ninja

Ninja は柔軟性や機能ではなく、ビルド速度が速いことを目的に設計されているため、既定値としてこれが設定されます。 ただし、CMake プロジェクトによっては、Ninja を使うと正しくビルドできないことがあります。 そのような場合は、代わりに Visual Studio プロジェクトを生成するように CMake に指示できます。

Visual Studio ジェネレーターを指定するには、メイン メニューから **[CMake] > [CMake の設定を変更]** を選んで、`CMakeSettings.json` を開きます。 "Ninja" を削除して「V」と入力します。 これにより IntelliSense がアクティブになり、必要なジェネレーターを選択できます。

アクティブな構成で Visual Studio ジェネレーターを指定すると、`-m -v:minimal` 引数を指定して MSBuild.exe が既定で呼び出されます。 ビルドをカスタマイズするには、`CMakeSettings.json` ファイル内で、`buildCommandArgs` プロパティによりビルド システムに渡される追加の [MSBuild コマンド ライン引数](../build/reference/msbuild-visual-cpp-overview.md)を指定できます。

   ```json
   "buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
   ```

- `configurationType`: 選択したジェネレーターにビルドの種類の構成を指定します。 次のいずれかを指定できます。
 
  - デバッグ
  - 解放
  - MinSizeRel
  - RelWithDebInfo
 
- `inheritEnvironments`: この構成が依存している 1 つまたは複数のコンパイラの環境を指定します。 任意のカスタム環境または定義済みの環境の 1 つがあります。
- `buildRoot`: CMake が選択したジェネレーター用のビルド スクリプトを生成するディレクトリを指定します。  マップ **-DCMAKE_BINARY_DIR**切り替え、CMake キャッシュが作成される場所を指定します。 フォルダーが存在しない場合は作成されます。サポートされているマクロを含める`${workspaceRoot}`、 `${workspaceHash}`、 `${projectFile}`、 `${projectDir}`、 `${thisFile}`、 `${thisFileDir}`、 `${name}`、 `${generator}`、`${env.VARIABLE}`します。
- `installRoot`: 選択したジェネレーターに CMake がインストール ターゲットを生成するディレクトリを指定します。 サポートされているマクロには、`${workspaceRoot}`、`${workspaceHash}`、`${projectFile}`、`${projectDir}`、`${thisFile}`、`${thisFileDir}`、`${name}`、`${generator}`、`${env.VARIABLE}` などがあります。
- `cmakeCommandArgs`: キャッシュを生成するために、CMake が呼び出されたときに渡される追加のコマンド ライン オプションを指定します。
- `cmakeToolchain`: toolchain ファイルを指定します。 これは、-DCMAKE_TOOLCHAIN_FILE を使用して CMake に渡されます。
- `buildCommandArgs`: - ビルド - の後に、CMake に渡されるネイティブ ビルド スイッチを指定します。 たとえば、Ninja ジェネレーターの使用時に -v を渡すと、コマンド ラインの出力が Ninja に強制されます。 参照してください[Ninja のコマンドライン引数](#ninja)Ninja コマンドの詳細についてはします。
- `ctestCommandArgs`: テストの実行中に CTest に渡す追加のコマンド ライン オプションを指定します。
- `codeAnalysisRuleset`: コード分析を実行しているときに使用するルールセットを指定します。 完全なパスまたは Visual Studio によってインストールされたルールセット ファイルのファイル名を指定できます。
- `intelliSenseMode`: IntelliSense の情報を計算するために使用するモードを指定します。 次のいずれかを指定できます。
 
  - windows-msvc-x86
  - windows-msvc-x64
  - windows-msvc-arm
  - windows-msvc-arm64
  - android-clang-x86
  - android-clang-x64
  - android-clang-arm
  - android-clang-arm64
  - ios-clang-x86
  - ios-clang-x64
  - ios-clang-arm
  - ios-clang-arm64
  - windows-clang-x86
  - windows-clang-x64
  - windows-clang-arm
  - windows-clang-arm64
  - linux-gcc-x86
  - linux-gcc-x64
  - linux-gcc-arm

- `cacheRoot`: CMake キャッシュへのパスを指定します。 このディレクトリには、既存の CMakeCache.txt ファイルを含める必要があります。

### <a name="additional-settings-for-cmake-linux-projects"></a>CMake Linux プロジェクトの設定を追加します。 

- `remoteMachineName`: CMake、ビルド、およびデバッガーをホストするリモートの Linux マシンの名前を指定します。 新しい Linux マシンを追加するには、接続マネージャーを使用します。 サポートされているマクロには、`${defaultRemoteMachineName}` が含まれます。
- `remoteCopySourcesOutputVerbosity`: リモート マシンへのソース コピー操作の詳細レベルを指定します。 "ノーマル"、"詳細"、"診断" のいずれかを指定できます。
- `remoteCopySourcesConcurrentCopies`: ソースからリモート マシンへの同期中に使用される同時コピー数を指定します。
- `remoteCopySourcesMethod`: リモート マシンにファイルをコピーするメソッドを指定します。 "rsync" または "sftp" のいずれかを指定できます。
- `remoteCMakeListsRoot`: CMake プロジェクトを含むリモート マシン上のディレクトリを指定します。 サポートされているマクロには、`${workspaceRoot}`、`${workspaceHash}`、`${projectFile}`、`${projectDir}`、`${thisFile}`、`${thisFileDir}`、`${name}`、`${generator}`、`${env.VARIABLE}` などがあります。
- `remoteBuildRoot`: 選択したジェネレーターに CMake がビルド スクリプトを生成するリモート マシン上のディレクトリを指定します。 サポートされているマクロには、`${workspaceRoot}`、`${workspaceHash}`、`${projectFile}`、`${projectDir}`、`${thisFile}`、`${thisFileDir}`、`${name}`、`${generator}`、`${env.VARIABLE}` などがあります。
- `remoteInstallRoot`: 選択したジェネレーターに CMake がインストール ターゲットを生成するリモート マシン上のディレクトリを指定します。 サポートされているマクロには、`${workspaceRoot}`、`${workspaceHash}`、`${projectFile}`、`${projectDir}`、`${thisFile}`、`${thisFileDir}`、`${name}`、`${generator}`、`${env.VARIABLE}` などがあります。`VARIABLE` は、システム、ユーザー、またはセッション レベルで定義されている変数です。
- `remoteCopySources`:Visual Studio がリモート マシンにソース ファイルをコピーするかどうかを指定する `boolean`。 既定値は true です。 自分でファイルの同期を管理する場合は、false に設定します。
- `remoteCopyBuildOutput`:リモート システムからビルド出力をコピーするかどうかを指定する `boolean`。
- `rsyncCommandArgs`: rsync に渡される追加のコマンド ライン オプションのセットを指定します。
- `remoteCopySourcesExclusionList`:ソース ファイルのコピー中に除外するパスの一覧を指定する `array`: パスには、ファイルまたはディレクトリの名前か、コピーのルートに対する相対パスを指定できます。 glob パターン マッチング用のワイルドカード \\\"*\\\" および \\\"?\\\" を使用できます。
- `cmakeExecutable`: CMake プログラムの実行可能ファイルへの完全なパスを指定します。ファイル名と拡張子を含めます。
- `remotePreGenerateCommand`: CMakeLists.txt ファイルを解析するために CMake の実行前に実行するコマンドを指定します。
- `remotePrebuildCommand`: ビルド前にリモート マシン上で実行するコマンドを指定します。
- `remotePostbuildCommand`: ビルド後にリモート マシン上で実行するコマンドを指定します。
- `variables`: として返されます CMake 変数の名前と値のペアを含む **-d** *_名前_=_値_* に CMake にします。 CMake プロジェクトのビルド命令で CMake キャッシュ ファイルに直接変数を追加するように指定している場合は、代わりにここで追加することをお勧めします。 次の例は、14.14.26428 MSVC ツールセットに名前と値のペアを指定する方法を示しています。

```json
"variables": [
    {
      "name": "CMAKE_CXX_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe",
      "type": "FILEPATH"
    },
    {
      "name": "CMAKE_C_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe",
      "type": "FILEPATH"
    }
  ]
```

定義していない場合、 `"type"`、既定では"STRING"型と見なされます。

## <a name="environment-variables"></a>環境変数

`CMakeSettings.json` 上記のようにそのプロパティのいずれかで使用の環境変数もサポートしています。 `${env.FOO}` という構文を使うと、環境変数 %FOO% が展開されます。

このファイルの内部で組み込みマクロにアクセスすることもできます。

- `${workspaceRoot}` – ワークスペース フォルダーの完全なパスを提供します
- `${workspaceHash}` – ワークスペースの場所のハッシュです。現在のワークスペースの一意識別子を作成するのに便利です (たとえば、フォルダーのパスで使用する場合)
- `${projectFile}` – ルート CMakeLists.txt ファイルの完全なパスです
- `${projectDir}` – ルート CMakeLists.txt ファイルのフォルダーの完全なパスです
- `${thisFile}` – `CMakeSettings.json` ファイルの完全なパスです
- `${name}` – 構成の名前です
- `${generator}` – この構成で使用される CMake ジェネレーターの名前です


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
          "BuildDir": "D:\\custom-builddir"
          // This environment does not specify a namespace, hence by default "env" will be assumed.
          // "namespace" : "name" would require that this variable be referenced with "${name.BuildDir}".
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

## <a name="ninja"></a> Ninja のコマンドライン引数

ターゲットが指定されていない場合は、'既定' のターゲットをビルドします。

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




