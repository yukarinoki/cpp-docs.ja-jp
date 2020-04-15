---
title: 起動.vs.json スキーマ リファレンス (C++)
ms.date: 08/20/2019
helpviewer_keywords:
- launch.vs.json file [C++]
ms.openlocfilehash: ff4713642ab95a9bbc31f1a06236de459e53f9c3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323050"
---
# <a name="launchvsjson-schema-reference-c"></a>起動.vs.json スキーマ リファレンス (C++)

デバッグ パラメーターを構成するには *、launch.vs.json*ファイルを使用します。 ファイルを作成します。 **ソリューション エクスプローラ**で実行可能ファイルを右クリックし、[**デバッグと起動の設定]** を選択します。 プロジェクトに最も近いオプションを選択し、必要に応じて次のプロパティを使用して構成を変更します。 CMake プロジェクトのデバッグの詳細については、「 [CMake デバッグ セッションの構成](/cpp/build/configure-cmake-debugging-sessions)」を参照してください。

## <a name="default-properties"></a>既定のプロパティ

||||
|-|-|-|
|**プロパティ**|**Type**|**説明**|
|`name`|string|[デバッグターゲット]ドロップダウンのエントリの名前を指定します。|
|`type`|string|プロジェクトが dll または .exe (既定では .exe) かどうかを指定します。|
|`project`|string|プロジェクト ファイルへの相対パスを指定します。|
|`projectTarget`|string|をビルド`project`するときに呼び出されるオプションのターゲットを指定します。 これは`projectTarget`既に存在し、[**デバッグターゲット**]ドロップダウンの名前と一致している必要があります。|
|`debugType`|string|コードの種類 (ネイティブ、マネージ、または混合) に従ってデバッグ モードを指定します。 このパラメータが設定されていない限り、この設定は自動的に検出されます。 許可される値: "ネイティブ"、"マネージ"、"混在"|
|`inheritEnvironments`|array|複数のソースから継承された環境変数のセットを指定します。 *CMakeSettings.json*や*CppProperties.json*などのファイルでいくつかの変数を定義し、コンテキストをデバッグするために使用できます。  **Visual Studio 16.4:**: 構文を使用して、ターゲットごとに`env.VARIABLE_NAME`環境変数を指定します。 変数を設定解除するには、"null" に設定します。|
|`args`|array|起動したプログラムに渡されるコマンド ライン引数を指定します。|
|`currentDir`|string|ビルド ターゲットへの完全なディレクトリ パスを指定します。 このパラメータが設定されていない限り、この設定は自動的に検出されます。|
|`noDebug`|boolean|起動されたプログラムをデバッグするかどうかを指定します。 このパラメーターのデフォルト値は、`false`指定されていない場合です。|
|`stopOnEntry`|boolean|プロセスが起動され、デバッガーがアタッチされるとすぐに中断するかどうかを指定します。 このパラメーターの既定値は です`false`。|
|`remoteMachine`|string|プログラムが起動されるリモート マシンの名前を指定します。|
|`env`|array| カスタム環境変数のキー値リストを指定します。 env:{"myEnv":"myVal"}。|
|`portName`|string|実行中のプロセスにアタッチするときのポートの名前を指定します。|
|`buildConfigurations`|array| 構成を適用するビルド モードの名前を指定するキーと値のペア。 たとえば、`Debug`選択`Release`したビルド モードに従って使用する構成や構成を指定します。

## <a name="c-linux-properties"></a>C++ Linux のプロパティ

||||
|-|-|-|
|**プロパティ**|**Type**|**説明**|
|`program`|string|リモート コンピュータ上のプログラム実行可能ファイルへの完全パス。 CMake を使用する場合`${debugInfo.fullTargetPath}`、このフィールドの値としてマクロを使用できます。|
|`processId`|整数 (integer)|デバッガーをアタッチするオプションのプロセス ID。|
|`sourceFileMap`|object|デバッグ エンジンに渡されるオプションのソース ファイル マッピング。 形式: `{ "\<Compiler source location>": "\<Editor source location>" }` `{ "\<Compiler source location>": { "editorPath": "\<Editor source location>", "useForBreakpoints": true } }`または 。 例: `{ "/home/user/foo": "C:\\foo" }` または `{ "/home/user/foo": { "editorPath": "c:\\foo", "useForBreakpoints": true } }`。 [ソース ファイル マップ オプション](#source_file_map_options)を参照してください。|
|`additionalProperties`|string|ソースファイルマップオプションの1つ。 (以下を参照してください。)|
|`MIMode`|string|MIDebugEngine が接続する MI 対応コンソール デバッガーの種類を示します。 指定できる値は "gdb" です。|
|`args`|array|プログラムに渡されるコマンド ライン引数。|
|`environment`|array|プログラムの環境に追加する環境変数。 例: [ { "name": "squid", "値": "clam"} ]|
|`targetArchitecture`|string|デバッグ対象のアーキテクチャ。 このパラメータが設定されていない限り、この設定は自動的に検出されます。 許容値は、x86、腕、arm64、ミップ、x64、amd64、x86_64です。|
|`visualizerFile`|string|このプロセスをデバッグするときに使用する .natvis ファイル。 このオプションは GDB のプリティ印刷と互換性がありません。 この設定を使用する場合は、「表示文字列を表示」を参照してください。|
|`showDisplayString`|boolean|ビジュアライザー ファイルが指定されている場合は、表示文字列を有効にします。 このオプションをオンにすると、デバッグ中のパフォーマンスが低下する可能性があります。|
|`remoteMachineName`|string|gdb をホストするリモート Linux マシンとデバッグするプログラム。 新しい Linux マシンを追加するには、接続マネージャーを使用します。 CMake を使用する場合`${debugInfo.remoteMachineName}`、このフィールドの値としてマクロを使用できます。|
|`cwd`|string|リモート コンピュータ上のターゲットの作業ディレクトリ。 CMake を使用する場合`${debugInfo.defaultWorkingDirectory}`、このフィールドの値としてマクロを使用できます。 *CMakeLists.txt*ファイルで上書きされない限り、既定値はリモート ワークスペース ルートです。|
|`miDebuggerPath`|string|MI 対応デバッガへのパス (gdb など)。 指定しないと、まず PATH を検索してデバッガーを検索します。|
|`miDebuggerServerAddress`|string|接続先の MI 対応デバッガー サーバーのネットワーク アドレス。 例: ローカルホスト:1234。|
|`setupCommands`|array|基になるデバッガーを設定するために実行する 1 つ以上の GDB/LLDB コマンド。 例: `"setupCommands": [ { "text": "-enable-pretty-printing", "description": "Enable GDB pretty printing", "ignoreFailures": true }]`. [セットアップ コマンドの起動](#launch_setup_commands)を参照してください。|
|`customLaunchSetupCommands`|array|指定した場合、ターゲットを起動するために使用されるデフォルトのコマンドは、他のコマンドに置き換えられます。 たとえば、ターゲットプロセスにアタッチするために「ターゲットアタッチ」できます。 空のコマンド リストは起動コマンドを何も使用しません。 例: `"customLaunchSetupCommands": [ { "text": "target-run", "description": "run target", "ignoreFailures": false }]`.|
|`launchCompleteCommand`|string|デバッガーが完全にセットアップされた後に実行するコマンド。 指定できる値は、"exec-run"、"exec-continue"、"なし"です。 デフォルト値は"exec-run"です。|
|`debugServerPath`|string|起動するデバッグ サーバーへのフル パス (省略可能)。 既定値は null です。|
|`debugServerArgs`|string|オプションのデバッグ サーバー引数。 既定値は null です。|
|`filterStderr`|boolean|サーバー起動パターンの検索 stderr ストリームとデバッグ出力のログ stderr。 既定値は `false` です。|
|`coreDumpPath`|string|指定したプログラムのコア ダンプ ファイルへの省略可能な完全パス。 既定値は null です。|
外部コンソール|boolean|true の場合、デバッグ対象のコンソールが起動されます。 の`false`場合、コンソールは起動されません。 既定値は `false` です。 注: このオプションは、技術的な理由により無視される場合があります。|
|`pipeTransport`|string|この場合、Visual Studio と MI 対応デバッガ (gdb など) 間で標準入出力を中継するパイプとして、別の実行可能ファイルを使用してリモート コンピューターに接続するようにデバッガーに指示します。 許可値: 1 つ以上の[パイプトランスポートオプション](#pipe_transport_options)。|

## <a name="launch-setup-commands"></a><a name="launch_setup_commands"></a>セットアップ コマンドを起動する

プロパティと共`setupCommands`に使用します。

||||
|-|-|-|
|`text`|string|実行するデバッガー コマンド。|
|`description`|string|コマンドの説明 (省略可能)。|
|`ignoreFailures`|boolean|true の場合、コマンドの失敗は無視されます。 既定値は `false` です。|

## <a name="pipe-transport-options"></a><a name = "pipe_transport_options"></a>パイプトランスポートオプション

プロパティと共`pipeTransport`に使用します。

||||
|-|-|-|
|`pipeCwd`|string|パイプ プログラムの作業ディレクトリへの完全修飾パス。|
|`pipeProgram`|string|実行する完全修飾パイプ・コマンド。|
|`pipeArgs`|array|接続を構成するためにパイプ・プログラムに渡されるコマンド行引数。|
|`debuggerPath`|string|ターゲット コンピューター上のデバッガーへの完全パス (例: /usr/bin/gdb)。|
|`pipeEnv`|object|パイプ プログラムに渡される環境変数。|
|`quoteArgs`|boolean|個々の引数に文字 (スペースやタブなど) が含まれている場合、引用符で囲む必要がありますか? の`false`場合、デバッガー コマンドは自動的に引用符で囲まれません。 既定値は `true` です。|

## <a name="source-file-map-options"></a><a name="source_file_map_options"></a>ソース ファイル マップ オプション

`sourceFileMap`プロパティで使用します。

||||
|-|-|-|
|`editorPath`|string|エディターが検索するソース コードの場所。|
|`useForBreakpoints`|boolean|ブレークポイントを設定する場合は、このソース マッピングを使用する必要があります。 の`false`場合、ブレークポイントの設定にはファイル名と行番号のみが使用されます。 の`true`場合、このソース マッピングが使用されている場合にのみ、ファイルへの完全パスと行番号を使用してブレークポイントが設定されます。 それ以外の場合は、ブレークポイントを設定するときにファイル名と行番号が使用されます。 既定値は `true` です。|
