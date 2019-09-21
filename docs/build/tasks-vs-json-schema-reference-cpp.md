---
title: tasks. json スキーマリファレンス (C++)
ms.date: 08/20/2019
helpviewer_keywords:
- tasks.vs.json file [C++]
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: 1e533babafad554e8f7413d2bc1a88933a6eca42
ms.sourcegitcommit: ace42fa67e704d56d03c03745b0b17d2a5afeba4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69975925"
---
# <a name="tasksvsjson-schema-reference-c"></a>tasks. json スキーマリファレンス (C++)

オープンフォルダープロジェクトでソースコードをビルドする方法を Visual Studio に指示するには、*タスクと json*ファイルを追加します。 ここで任意のタスクを定義し、**ソリューションエクスプローラー**のショートカットメニューから呼び出すことができます。 CMake プロジェクトは、すべてのビルドコマンドが*Cmakelists*で指定されているため、このファイルを使用しません。 CMake 以外のビルドシステムの場合は、ビルドコマンドを指定し、ビルドスクリプトを呼び出すことができ*ます。* *タスク*の使用に関する一般的な情報については、「[フォルダーを開く」開発のビルドおよびデバッグタスクのカスタマイズ](/visualstudio/ide/customize-build-and-debug-tasks-in-visual-studio)に関する説明を参照してください。

タスクには`default`、 `type` 、、 `remote`、または`msbuild`の4つの値`launch`のいずれかを持つことができるプロパティがあります。 リモート接続が必要`launch`な場合を除き、ほとんどのタスクでを使用する必要があります。

## <a name="default-properties"></a>既定のプロパティ

既定のプロパティは、すべての種類のタスクで使用できます。

||||
|-|-|-|
|**Property**|**Type**|**説明**|
|`taskLabel`|string| (必須) ユーザーインターフェイスで使用されるタスクラベルを指定します。|
|`appliesTo`|string| (必須) コマンドを実行できるファイルを指定します。 ワイルドカードの使用がサポートされています。例: " *"、"* .cpp"、"/* .txt"|
|`contextType`|string| 使用できる値: "custom"、"build"、"clean"、"rebuild"。 タスクが表示されるコンテキストメニュー内の場所を決定します。 既定値は "custom" です。|
|`output`|string| タスクの出力タグを指定します。|
|`inheritEnvironments`|array| 複数のソースから継承された環境変数のセットを指定します。 変数は、 *Cmakesettings. json*や*cmakesettings. json*などのファイルで定義し、タスクコンテキストで使用できるようにすることができます。|
|`passEnvVars`|boolean| タスクコンテキストに追加の環境変数を含めるかどうかを指定します。 これらの変数は、 `envVars`プロパティを使用して定義されているものとは異なります。 既定値は "true" です。|

## <a name="launch-properties"></a>起動プロパティ

タスクの種類が`launch`の場合、次のプロパティを使用できます。

||||
|-|-|-|
|**Property**|**Type**|**説明**|
|`command`|string| 起動するプロセスまたはスクリプトの完全なパスを指定します。|
|`args`|array| コマンドに渡される引数のコンマ区切りのリストを指定します。|
|`launchOption`|string| 許可値:"None"、"ContinueOnError"、"IgnoreError"。 エラーが発生したときにコマンドを続行する方法を指定します。|
|`workingDirectory`|string| コマンドを実行するディレクトリを指定します。 既定では、プロジェクトの現在の作業ディレクトリが使用されます。|
|`customLaunchCommand`|string| コマンドを実行する前に適用するグローバルスコープのカスタマイズを指定します。 % PATH% などの環境変数を設定する場合に便利です。|
|`customLaunchCommandArgs`|string| CustomLaunchCommand の引数を指定します。 (が`customLaunchCommand`必要です)。|
 `env`| カスタム環境変数のキーと値の一覧を指定します。 たとえば、"myEnv": "Myenv" のようになります。|
|`commands`|array| 順番に呼び出すコマンドのリストを指定します。|

### <a name="example"></a>例

次のタスクでは、メイクファイルがフォルダー `Mingw64`に指定され、環境が cppproperties. jsonで定義されている場合に、次のように .exe を呼び出します[。](cppproperties-schema-reference.md#user_defined_environments)

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

これらのタスクは、**ソリューションエクスプローラー**で *.cpp*ファイルを右クリックしたときに、コンテキストメニューから呼び出すことができます。

## <a name="remote-properties"></a>リモートプロパティ

リモートタスクは、ワークロードを使用C++して Linux 開発をインストールし、Visual Studio 接続マネージャーを使用してリモートコンピューターに接続を追加するときに有効になります。 リモートタスクは、リモートシステム上でコマンドを実行し、ファイルをコピーすることもできます。

タスクの種類が`remote`の場合、次のプロパティを使用できます。

||||
|-|-|-|
|**Property**|**Type**|**説明**|
|`remoteMachineName`|string|リモートコンピューターの名前。 **接続マネージャー**のコンピューター名と一致している必要があります。|
|`command`|string|リモートコンピューターに送信するコマンド。 既定では、コマンドはリモートシステム上の $HOME ディレクトリで実行されます。|
|`remoteWorkingDirectory`|string|リモートコンピューター上の現在の作業ディレクトリ。|
|`localCopyDirectory`|string|リモートコンピューターにコピーするローカルディレクトリ。 既定では、現在の作業ディレクトリが使用されます。|
|`remoteCopyDirectory`|string|がコピーされる`localCopyDirectory`リモートコンピューター上のディレクトリ。|
|`remoteCopyMethod`|string| コピーに使用するメソッド。 使用可能な値: "none"、"sftp"、"rsync"。 大規模なプロジェクトの場合は rsync をお勧めします。|
|`remoteCopySourcesOutputVerbosity`|string| 許可値:"Normal"、"Verbose"、"Diagnostic"。|
|`rsyncCommandArgs`|string|既定値は "-t--delete" です。|
|`remoteCopyExclusionList`|array|コピー操作から除外する内`localCopyDirectory`のファイルのコンマ区切りリスト。|

### <a name="example"></a>例

**ソリューションエクスプローラー**で*メインの .cpp*を右クリックすると、次のタスクがショートカットメニューに表示されます。 これは、**接続マネージャー**で呼び出さ`ubuntu`れるリモートコンピューターに依存します。 このタスクは、Visual Studio の現在開いているフォルダー `sample`をリモートコンピューター上のディレクトリにコピーし、g + + を呼び出してプログラムをビルドします。

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

タスクの種類が`msbuild`の場合、次のプロパティを使用できます。

||||
|-|-|-|
|**Property**|**Type**|**説明**|
|`verbosity`|string| MSBuild プロジェクトビルドの出力 verbosityAllowed 値を指定します。"Quiet"、"最小"、"Normal"、"Detailed"、"Diagnostic"。|
|`toolsVersion`|string| プロジェクトをビルドするためのツールセットのバージョンを指定します。たとえば、"2.0"、"3.5"、"4.0"、"Current" などです。 既定値は "Current" です。|
|`globalProperties`|オブジェクト|プロジェクトに渡すグローバルプロパティのキーと値のリストを指定します。たとえば、"Configuration": "Release" のように指定します。|
|`properties`|オブジェクト| 追加のプロジェクト専用プロパティのキー値リストを指定します。|
|`targets`|array| プロジェクトで順番に呼び出すターゲットの一覧を指定します。 プロジェクトの既定のターゲットは、何も指定されていない場合に使用されます。|
