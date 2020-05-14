---
title: tasks.vs.json スキーマ リファレンス (C++)
ms.date: 08/20/2019
helpviewer_keywords:
- tasks.vs.json file [C++]
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: cc6b2983d3cc3d40449357a554df5feee38c21d9
ms.sourcegitcommit: 6c1960089b92d007fc28c32af1e4bef0f85fdf0c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/31/2019
ms.locfileid: "75556657"
---
# <a name="tasksvsjson-schema-reference-c"></a>tasks.vs.json スキーマ リファレンス (C++)

"フォルダーを開く" プロジェクトのソース コードをビルドする方法を Visual Studio に伝えるには、*tasks.vs.json* ファイルを追加します。 ここでは任意のタスクを定義し、**ソリューション エクスプローラー**のコンテキスト メニューから呼び出すことができます。 すべてのビルド コマンドは *CMakeLists.txt* で指定されるため、CMake プロジェクトにはこのファイルが使用されません。 CMake 以外のビルド システムでは、*tasks.vs.json* でビルド コマンドを指定し、ビルド スクリプトを呼び出すことができます。 *tasks.vs.json* の使用の全般的な情報については、「["フォルダーを開く" の開発のためにビルド タスクとデバッグ タスクをカスタマイズする](/visualstudio/ide/customize-build-and-debug-tasks-in-visual-studio)」を参照してください。

タスクには、`default`、`launch`、`remote`、または `msbuild` という 4 つの値のいずれかを持つ `type` プロパティがあります。 リモート接続が必要な場合を除き、ほとんどのタスクでは `launch` を使用する必要があります。

## <a name="default-properties"></a>既定のプロパティ

既定のプロパティは、すべての種類のタスクで使用できます。

||||
|-|-|-|
|**Property**|**Type**|**説明**|
|`taskLabel`|string| (必須) ユーザー インターフェイスで使用されるタスク ラベルを指定します。|
|`appliesTo`|string| (必須) コマンドを実行できるファイルを指定します。 ワイルドカードの使用はサポートされています (例: " *"、"* .cpp"、"/*.txt")。|
|`contextType`|string| 使用できる値: "custom"、"build"、"clean"、"rebuild"。 タスクが表示されるコンテキスト メニュー内の場所を指定します。 既定値は "custom" です。|
|`output`|string| タスクへの出力タグを指定します。|
|`inheritEnvironments`|array| 複数のソースから継承された環境変数のセットを指定します。 *CMakeSettings.json* や *CppProperties.json* などのファイルで変数を定義し、タスク コンテキストに使用できるようにします。 **Visual Studio 16.4:** : `env.VARIABLE_NAME` 構文を使用して、タスクごとに環境変数を指定します。 変数の設定を解除するには、変数を "null" に設定します。|
|`passEnvVars`|boolean| タスク コンテキストに追加の環境変数を含めるかどうかを指定します。 これらの変数は、`envVars` プロパティを使用して定義された変数とは異なります。 既定値は "true" です。|

## <a name="launch-properties"></a>launch のプロパティ

タスクの種類が `launch` の場合、次のプロパティを使用できます。

||||
|-|-|-|
|**Property**|**Type**|**説明**|
|`command`|string| 起動するプロセスまたはスクリプトの完全なパスを指定します。|
|`args`|array| コマンドに渡される引数のコンマ区切りのリストを指定します。|
|`launchOption`|string| 使用できる値は以下の通りです。"None"、"ContinueOnError"、"IgnoreError"。 エラーが発生したときにコマンドを続行する方法を指定します。|
|`workingDirectory`|string| コマンドを実行するディレクトリを指定します。 既定値はプロジェクトの現在の作業ディレクトリです。|
|`customLaunchCommand`|string| コマンドを実行する前に適用するグローバル スコープのカスタマイズを指定します。 %PATH% などの環境変数の設定に役立ちます。|
|`customLaunchCommandArgs`|string| customLaunchCommand の引数を指定します (`customLaunchCommand` は必須です)。|
 `env`| カスタム環境変数のキーと値のリストを指定します。 例: "myEnv": "myVal"|
|`commands`|array| 順番に呼び出すコマンドのリストを指定します。|

### <a name="example"></a>例

次のタスクでは、[CppProperties.json スキーマ リファレンス](cppproperties-schema-reference.md#user_defined_environments)に示すように、フォルダーにメイクファイルが指定され、`Mingw64` 環境が *CppProperties.json* で定義されている場合に、*make.exe* を呼び出します。

```json
 {
  "version": "0.2.1",
  "tasks": [
    {
      "taskLabel": "gcc make",
      "appliesTo": "*.cpp",
      "type": "launch",
      "contextType": "custom",
      "inheritEnvironments": [
        "Mingw64"
      ],
      "command": "make"
    },
    {
      "taskLabel": "gcc clean",
      "appliesTo": "*.cpp",
      "type": "launch",
      "contextType": "custom",
      "inheritEnvironments": [
        "Mingw64"
      ],
      "command": "make",
      "args": ["clean"]
    }
  ]
}
```

**ソリューション エクスプローラー**で *.cpp* ファイルを右クリックすると、コンテキスト メニューからこれらのタスクを呼び出すことができます。

## <a name="remote-properties"></a>remote のプロパティ

C++ ワークロードを含む Linux 開発をインストールし、Visual Studio 接続マネージャーを使用してリモート マシンへの接続を追加すると、リモート タスクが有効になります。 リモート タスクを使用すると、リモート システム上でコマンドを実行できます。また、そこにファイルをコピーすることもできます。

タスクの種類が `remote` の場合、次のプロパティを使用できます。

||||
|-|-|-|
|**Property**|**Type**|**説明**|
|`remoteMachineName`|string|リモート マシンの名前。 **接続マネージャー**のマシン名と一致している必要があります。|
|`command`|string|リモート マシンに送信するコマンド。 既定では、コマンドはリモート システム上の $HOME ディレクトリで実行されます。|
|`remoteWorkingDirectory`|string|リモート マシンの現在の作業ディレクトリ。|
|`localCopyDirectory`|string|リモート マシンにコピーするローカル ディレクトリ。 既定値は現在の作業ディレクトリです。|
|`remoteCopyDirectory`|string|`localCopyDirectory` がコピーされるリモート マシン上のディレクトリ。|
|`remoteCopyMethod`|string| コピーに使用するメソッド。 使用できる値: "none"、"sftp"、"rsync"。 大規模なプロジェクトの場合は rsync をお勧めします。|
|`remoteCopySourcesOutputVerbosity`|string| 使用できる値は以下の通りです。"Normal"、"Verbose"、"Diagnostic"。|
|`rsyncCommandArgs`|string|既定値は "-t --delete" です。|
|`remoteCopyExclusionList`|array|コピー操作から除外する `localCopyDirectory` 内のファイルのコンマ区切りリスト。|

### <a name="example"></a>例

**ソリューション エクスプローラー**で *main.cpp* を右クリックすると、次のタスクがコンテキスト メニューに表示されます。 これは、**接続マネージャー**の `ubuntu` というリモート マシンによって変わります。 このタスクによって、Visual Studio で現在開いているフォルダーがリモート マシンの `sample` ディレクトリにコピーされ、g++ が呼び出され、プログラムがビルドされます。

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskLabel": "Build",
      "appliesTo": "main.cpp",
      "type": "remote",
      "contextType": "build",
      "command": "g++ main.cpp",
      "remoteMachineName": "ubuntu",
      "remoteCopyDirectory": "~/sample",
      "remoteCopyMethod": "sftp",
      "remoteWorkingDirectory": "~/sample/hello",
      "remoteCopySourcesOutputVerbosity": "Verbose"
    }
  ]
}
```

## <a name="msbuild-properties"></a>MSBuild プロパティ

タスクの種類が `msbuild` の場合、次のプロパティを使用できます。

||||
|-|-|-|
|**Property**|**Type**|**説明**|
|`verbosity`|string| MSBuild プロジェクトのビルド出力の verbosityAllowed 値を指定します ("Quiet"、"Minimal"、"Normal"、"Detailed"、"Diagnostic")。|
|`toolsVersion`|string| プロジェクトをビルドするツールセットのバージョンを指定します (例: "2.0"、"3.5"、"4.0"、"Current")。 既定値は "Current" です。|
|`globalProperties`|object|プロジェクトに渡すグローバル プロパティのキーと値のリストを指定します (例: "Configuration":"Release")|
|`properties`|object| 追加のプロジェクトのみのプロパティのキーと値のリストを指定します。|
|`targets`|array| プロジェクトで呼び出すターゲットのリストを順番に指定します。 何も指定されていない場合は、プロジェクトの既定のターゲットが使用されます。|
