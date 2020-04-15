---
title: CMakeSettings.json スキーマ リファレンス
ms.date: 11/22/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: f9c864b66df86165090b7d6d6fc9c4fc51d65a5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328891"
---
# <a name="cmakesettingsjson-schema-reference"></a>CMakeSettings.json スキーマ リファレンス

::: moniker range="vs-2015"

CMake プロジェクトは、Visual Studio 2017 以降でサポートされています。

::: moniker-end

::: moniker range=">=vs-2017"

**CMakeSettings.json**ファイルには、指定された*構成*およびコンパイラ*環境*の cmake.exe に渡されるコマンド ライン引数を作成するために、Visual Studio が IntelliSense に使用する情報が含まれています。 構成では、特定のプラットフォームやビルドの種類に適用されるプロパティ`x86-Debug`を指定します。 `Linux-Release` 各構成では、コンパイラ ツールセットに関する情報 (MSVC、GCC、Clang など) をカプセル化する環境を指定します。 CMake は、コマンド ライン引数を使用して、プロジェクトのルート*CMakeCache.txt*ファイルおよびその他のプロジェクト ファイルを再生成します。 値は*CMakeLists.txt*ファイルでオーバーライドできます。

IDE で構成を追加または削除し、JSON ファイルで直接編集するか **、CMake 設定エディター** (Visual Studio 2019 以降) を使用できます。 IDE で構成を簡単に切り替えて、さまざまなプロジェクトファイルを生成できます。 詳細については[、「Visual Studio で CMake ビルド設定をカスタマイズ](customize-cmake-settings.md)する」を参照してください。

## <a name="configurations"></a>構成

配列`configurations`には、CMake プロジェクトのすべての構成が含まれています。 事前[定義された構成の詳細については、「CMake の定義済み構成リファレンス](cmake-predefined-configuration-reference.md)」を参照してください。 事前定義された構成またはカスタム構成をいくつでもファイルに追加できます。

`configuration` には次のプロパティがあります。

- `addressSanitizerEnabled`:`true`アドレスサニタイザー (Windowsの実験) でプログラムをコンパイルする場合。 Linux では、-fno-omit-frame-pointer およびコンパイラ最適化レベル -Os または -Oo を使用してコンパイルすると、最良の結果が得られます。
- `addressSanitizerRuntimeFlags`: ASAN_OPTIONS環境変数を介して AddressSanitizer に渡されるランタイム フラグ。 形式: フラグ1=値:フラグ2=値2。
- `buildCommandArgs`: --ビルド-- の後に CMake に渡されるネイティブ ビルド スイッチを指定します。 たとえば、Ninja ジェネレーターの使用時に -v を渡すと、コマンド ラインの出力が Ninja に強制されます。 Ninja コマンドの詳細については、「[Ninja のコマンド ライン引数](#ninja)」参照してください。
- `buildRoot`: 選択したジェネレーターに CMake がビルド スクリプトを生成するディレクトリを指定します。  **DCMAKE_BINARY_DIR**スイッチにマップし *、CMakeCache.txt*を作成する場所を指定します。 フォルダーが存在しない場合は、作成されます。 サポートされているマクロには、`${workspaceRoot}`、`${workspaceHash}`、`${projectFile}`、`${projectDir}`、`${thisFile}`、`${thisFileDir}`、`${name}`、`${generator}`、`${env.VARIABLE}` などがあります。
- `cacheGenerationCommand`: コマンドラインツールと引数を指定します。 *gencache.bat debug* コマンドは、ユーザーが明示的に再生成を要求するか、CMakeLists.txt または CMakeSettings.json ファイルが変更されたときに、指定された環境でシェルから実行されます。
- `cacheRoot`: CMake キャッシュへのパスを指定します。 このディレクトリには、既存の*CMakeCache.txt*ファイルが含まれている必要があります。
- `clangTidyChecks`: clang-tidy に渡される警告のコンマ区切りリスト。ワイルドカードが使用でき、'-' プレフィックスはチェックを削除します。
- `cmakeCommandArgs`: プロジェクト ファイルを生成するために CMake を呼び出したときに、追加のコマンド ライン オプションを指定します。
- `cmakeToolchain`: toolchain ファイルを指定します。 これは、-DCMAKE_TOOLCHAIN_FILE を使用して CMake に渡されます。
- `codeAnalysisRuleset`: コード分析を実行しているときに使用するルールセットを指定します。 Visual Studio によってインストールされたルールセット ファイルの完全なパスまたはファイル名を指定できます。
- `configurationType`: 選択したジェネレーターにビルドの種類の構成を指定します。 次のいずれかを指定できます。

  - デバッグ
  - Release
  - MinSizeRel
  - RelWithDebInfo
  
- `ctestCommandArgs`: テストの実行中に CTest に渡す追加のコマンド ライン オプションを指定します。
- `description`: メニューに表示されるこの構成の説明。
- `enableClangTidyCodeAnalysis`: コード分析には Clang-Tidy を使用します。
- `enableMicrosoftCodeAnalysis`: コード分析用に Microsoft コード分析ツールを使用します。
- `generator`: この構成に使用する CMake ジェネレーターを指定します。 次のいずれかを指定できます。
  
  **Visual Studio 2019 のみ:**
  - Visual Studio 16 2019
  - Visual Studio 16 2019 Win64
  - Visual Studio 16 2019 ARM

  **Visual Studio 2017 以降:**
  - Visual Studio 15 2017
  - Visual Studio 15 2017 Win64
  - Visual Studio 15 2017 ARM
  - Visual Studio 14 2015
  - Visual Studio 14 2015 Win64
  - Visual Studio 14 2015 ARM
  - UNIX メイクファイル
  - Ninja

Ninja は柔軟性や機能ではなく、ビルド速度が速いことを目的に設計されているため、既定値としてこれが設定されます。 ただし、CMake プロジェクトによっては、Ninja を使うと正しくビルドできないことがあります。 この場合は、代わりに Visual Studio プロジェクトを生成するように CMake に指示できます。

Visual Studio 2017 で Visual Studio ジェネレーターを指定するには **、CMake |CMake の設定を変更する** 「忍者」を削除し、「V」と入力します。 これにより IntelliSense がアクティブになり、必要なジェネレーターを選択できます。

Visual Studio 2019 で Visual Studio ジェネレーターを指定するには、**ソリューション エクスプローラー**で*CMakeLists.txt*ファイルを右クリックし、[**高度な設定を表示**>するプロジェクトの> **CMake 設定]** を**選択します。**

アクティブな構成で Visual Studio ジェネレーターを指定すると、`-m -v:minimal` 引数を指定して MSBuild.exe が既定で呼び出されます。 ビルドをカスタマイズするには *、CMakeSettings.json*ファイル内で、プロパティを使用してビルド システムに渡す追加[の MSBuild コマンド ライン引数](../build/reference/msbuild-visual-cpp-overview.md)を`buildCommandArgs`指定できます。

   ```json
   "buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
   ```

- `installRoot`: 選択したジェネレーターに CMake がインストール ターゲットを生成するディレクトリを指定します。 サポートされているマクロには、`${workspaceRoot}`、`${workspaceHash}`、`${projectFile}`、`${projectDir}`、`${thisFile}`、`${thisFileDir}`、`${name}`、`${generator}`、`${env.VARIABLE}` などがあります。
- `inheritEnvironments`: この構成が依存している 1 つまたは複数のコンパイラ環境を指定します。 任意のカスタム環境を使用することも、定義済みの環境を使用することもできます。 詳細については、[環境](#environments)に関するページを参照してください。
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

- `name`: 構成に名前を付けます。  事前[定義された構成の詳細については、「CMake の定義済み構成リファレンス](cmake-predefined-configuration-reference.md)」を参照してください。
- `wslPath`: Linux 用 Windows サブシステムのインスタンスの起動ツールへのパス。

### <a name="additional-settings-for-cmake-linux-projects"></a>CMake Linux プロジェクトの追加設定

- `remoteMachineName`: CMake、ビルド、およびデバッガーをホストするリモートの Linux マシンの名前を指定します。 新しい Linux マシンを追加するには、接続マネージャーを使用します。 サポートされているマクロには、`${defaultRemoteMachineName}` が含まれます。
- `remoteCopySourcesOutputVerbosity`: リモート マシンへのソース コピー操作の詳細レベルを指定します。 "ノーマル"、"詳細"、"診断" のいずれかを指定できます。
- `remoteCopySourcesConcurrentCopies`: リモート マシンへのソースの同期中に使用される同時コピーの数を指定します (sftp のみ)。
- `remoteCopySourcesMethod`: リモート マシンにファイルをコピーするメソッドを指定します。 "rsync" または "sftp" のいずれかを指定できます。
- `remoteCMakeListsRoot`: CMake プロジェクトを含むリモート マシン上のディレクトリを指定します。 サポートされているマクロには、`${workspaceRoot}`、`${workspaceHash}`、`${projectFile}`、`${projectDir}`、`${thisFile}`、`${thisFileDir}`、`${name}`、`${generator}`、`${env.VARIABLE}` などがあります。
- `remoteBuildRoot`: 選択したジェネレーターに CMake がビルド スクリプトを生成するリモート マシン上のディレクトリを指定します。 サポートされているマクロには、`${workspaceRoot}`、`${workspaceHash}`、`${projectFile}`、`${projectDir}`、`${thisFile}`、`${thisFileDir}`、`${name}`、`${generator}`、`${env.VARIABLE}` などがあります。
- `remoteInstallRoot`: 選択したジェネレーターに CMake がインストール ターゲットを生成するリモート マシン上のディレクトリを指定します。 サポートされているマクロには、`${workspaceRoot}`、`${workspaceHash}`、`${projectFile}`、`${projectDir}`、`${thisFile}`、`${thisFileDir}`、`${name}`、`${generator}`、`${env.VARIABLE}` などがあります。`VARIABLE` は、システム、ユーザー、またはセッション レベルで定義されている変数です。
- `remoteCopySources`: `boolean` Visual Studio でソース ファイルをリモート コンピューターにコピーするかどうかを指定する A。 既定値は true です。 自分でファイルの同期を管理する場合は、false に設定します。
- `remoteCopyBuildOutput`:`boolean`リモート システムからビルド出力をコピーするかどうかを指定する A。
- `remoteCopyAdditionalIncludeDirectories`: IntelliSense をサポートするためにリモート コンピューターからコピーする追加インクルード ディレクトリ。 "/パス1;/パス2...." として書式設定します。
- `remoteCopyExcludeDirectories`: リモートコンピュータからコピーするディレクトリを含まない。 "/パス1;/パス2...." として書式設定します。
- `remoteCopyUseCompilerDefaults`: IntelliSense の既定の定義とインクルード パスを使用するかどうかを指定します。 gcc スタイルの引数をサポートしないコンパイラが使用している場合にのみ、false にする必要があります。
- `rsyncCommandArgs`: rsync に渡される追加のコマンド ライン オプションのセットを指定します。
- `remoteCopySourcesExclusionList`:`array`ソース ファイルをコピーするときに除外するパスのリストを指定する A: パスは、ファイル/ディレクトリの名前、またはコピーのルートを基準とする相対パスです。 glob パターン マッチング用のワイルドカード \\\"*\\\" および \\\"?\\\" を使用できます。
- `cmakeExecutable`: CMake プログラムの実行可能ファイルへの完全なパスを指定します。ファイル名と拡張子を含めます。
- `remotePreGenerateCommand`: CMake を実行して*CMakeLists.txt*ファイルを解析する前に実行するコマンドを指定します。
- `remotePrebuildCommand`: ビルド前にリモート マシン上で実行するコマンドを指定します。
- `remotePostbuildCommand`: ビルド後にリモート マシン上で実行するコマンドを指定します。
- `variables`: **-D** *_name_=_value_* として CMake に渡される、CMake 変数の名前と値のペアを含みます。 CMake プロジェクトのビルド命令で*CMakeCache.txt*ファイルに直接変数を追加する方法を指定する場合は、代わりにここで追加することをお勧めします。 次の例は、14.14.26428 MSVC ツールセットに名前と値のペアを指定する方法を示しています。

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

`"type"`を定義しない場合、`"STRING"`型は既定で使用されます。

- `remoteCopyOptimizations`: リモート ターゲットへのソース コピーを制御するための**Visual Studio 2019 バージョン 16.5 以降**のプロパティ。 最適化は既定で有効になっています。 `remoteCopyUseOptimizations`、`rsyncSingleDirectoryCommandArgs`、および `remoteCopySourcesMaxSmallChange` を含みます。

## <a name="environments"></a><a name="environments"></a>環境

*環境*は、Visual Studio が cmake.exe を呼び出すために使用するプロセスで設定されている環境変数をカプセル化します。 MSVC プロジェクトの場合、変数は、特定のプラットフォームの[開発者コマンド プロンプト](building-on-the-command-line.md)で設定された変数です。 `msvc_x64_x64`たとえば、環境は VS **2017 の開発者コマンド プロンプト**を実行する場合と同じ **、VS 2019 の開発者コマンド プロンプト** **-arch=amd64 -host_arch=amd64**引数を使用します。 `env.{<variable_name>}` *CMakeSettings.json*の構文を使用して、フォルダーへのパスを構築する場合など、個々の環境変数を参照できます。  以下の定義済み環境が用意されています。

- linux_arm: リモートで ARM Linux をターゲットにします。
- linux_x64: リモートで x64 Linux をターゲットにします。
- linux_x86: リモートで x86 Linux をターゲットにします。
- msvc_arm: MSVC コンパイラを使用して ARM ウィンドウをターゲットにします。
- msvc_arm_x64: 64 ビット MSVC コンパイラを使用して ARM ウィンドウをターゲットにします。
- msvc_arm64: MSVC コンパイラを使用して ARM64 ウィンドウをターゲットにします。
- msvc_arm64_x64: 64 ビット MSVC コンパイラを使用して ARM64 Windows をターゲットにします。
- msvc_x64: MSVC コンパイラを使用して x64 ウィンドウをターゲットにします。
- msvc_x64_x64: 64 ビット MSVC コンパイラを使用して x64 Windows をターゲットにします。
- msvc_x86: MSVC コンパイラを使用して x86 の Windows をターゲットにします。
- msvc_x86_x64: 64 ビット MSVC コンパイラを使用して x86 Windows をターゲットにします。

### <a name="accessing-environment-variables-from-cmakeliststxt"></a>CMakeLists.txt から環境変数にアクセスする

CMakeLists.txt ファイルから、すべての環境変数は構文`$ENV{variable_name}`で参照されます。 環境で使用できる変数を表示するには、対応するコマンド プロンプトを開`SET`いて、「 」と入力します。 環境変数の情報の一部は、CMake システムイントロスペクション変数でも利用できますが、環境変数を使用すると便利な場合があります。 たとえば、MSVC コンパイラバージョンや Windows SDK バージョンは、環境変数を使用して簡単に取得できます。

### <a name="custom-environment-variables"></a>カスタム環境変数

では`CMakeSettings.json`、カスタム環境変数をグローバルに定義することも、`environments`アレイ内の構成ごとに定義することもできます。 カスタム環境は、事前定義された環境の代わりに使用できる一連のプロパティをグループ化したり、定義済み環境を拡張または変更したりするための便利な方法です。 `environments` 配列内の各項目は以下で構成されています。

- `namespace`: フォーム `namespace.variable` 内の構成から環境変数を参照できるように環境に名前を付けます。 既定の環境オブジェクトが呼`env`び出され、 を含む`%USERPROFILE%`特定のシステム環境変数が設定されます。
- `environment`: この変数グループを一意に識別します。 後で `inheritEnvironments` エントリでグループが継承できるようにします。
- `groupPriority`: これらの変数を評価するときに、これらの変数の優先順位を指定する整数。 数字が大きい大きい項目が最初に評価されます。
- `inheritEnvironments`: このグループによって継承される環境のセットを指定する値の配列。 この機能を使用すると、既定の環境を継承し、実行時に CMake.exe に渡されるカスタム環境変数を作成することができます。

**Visual Studio 2019 バージョン 16.4 以降:** デバッグ ターゲットは *、CMakeSettings.json*で指定した環境で自動的に起動されます。 [launch.vs.json](launch-vs-schema-reference-cpp.md)および[tasks.vs.json](tasks-vs-json-schema-reference-cpp.md)では、ターゲット単位またはタスク単位で環境変数をオーバーライドまたは追加できます。

次の例では、1 つのグローバル変数 **BuildDir** を定義します。これは、x86-Debug と x64-Debug の両方の構成で継承されます。 各構成は、この変数を使って、その構成の **buildRoot** プロパティの値を指定します。 各構成が **inheritEnvironments** プロパティを使ってその構成のみに適用される変数を指定する方法にも注意してください。

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
      // Since this configuration doesn't modify BuildDir, it inherits
      // from the one defined globally.
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

## <a name="macros"></a>マクロ

次のマクロは *、CMakeSettings.json*で使用できます。

- `${workspaceRoot}`– ワークスペースフォルダの完全パス
- `${workspaceHash}` – ワークスペースの場所のハッシュです。現在のワークスペースの一意識別子を作成するのに便利です (たとえば、フォルダーのパスで使用する場合)
- `${projectFile}` – ルート CMakeLists.txt ファイルの完全なパスです
- `${projectDir}` – ルート CMakeLists.txt ファイルのフォルダーの完全なパスです
- `${thisFile}` – `CMakeSettings.json` ファイルの完全なパスです
- `${name}` – 構成の名前です
- `${generator}` – この構成で使用される CMake ジェネレーターの名前です

*CMakeSettings.json*のマクロと環境変数へのすべての参照は、cmake.exe コマンド ラインに渡される前に展開されます。

## <a name="ninja-command-line-arguments"></a><a name="ninja"></a> Ninja のコマンド ライン引数

ターゲットを指定しないと、"default" ターゲットがビルドされます。

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
|   -t TOOL  | サブツールを実行します (サブツールを一覧表示するには -t list を使用)。 トップレベルのオプションを終了します。さらにフラグがツールに渡されます|
|   -w FLAG  | 警告を調整します (警告を一覧表示するには -w list を使用)|

::: moniker-end
