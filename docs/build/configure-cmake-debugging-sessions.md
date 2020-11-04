---
title: Visual Studio で CMake デバッグ セッションを構成する
description: Visual Studio を使用して CMake デバッガー設定を構成する方法について説明します。
ms.date: 04/02/2020
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: a790e26e5bf3980ffb81a3ba778577afacff95b4
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922232"
---
# <a name="configure-cmake-debugging-sessions"></a>CMake デバッグ セッションを構成する

::: moniker range="msvc-140"

CMake のネイティブ サポートは Visual Studio 2017 以降で利用できます。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **バージョン** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end

::: moniker range=">=msvc-150"

すべての実行可能な CMake ターゲットが、 **[全般]** ツール バーの **[スタートアップ アイテム]** ドロップダウンに表示されます。 1 つを選択してデバッグ セッションを開始し、デバッガーを起動します。

![CMake のスタートアップ アイテム](media/cmake-startup-item-dropdown.png "CMake の [スタートアップ アイテム] ドロップダウン")

ソリューション エクスプローラーからデバッグ セッションを開始することもできます。 まず、 **[ソリューション エクスプローラー]** ウィンドウで **[CMake ターゲット ビュー]** に切り替えます。

![[CMake ターゲット ビュー] ボタン](media/cmake-targets-view.png  "[CMake ターゲット ビュー] メニュー項目")

次に、実行可能ファイルを右クリックして **[デバッグ]** を選択します。 このコマンドにより、アクティブな構成に基づいて、選択したターゲットのデバッグが自動的に開始されます。

## <a name="customize-debugger-settings"></a>デバッガー設定をカスタマイズする

プロジェクト内の任意の実行可能な CMake ターゲットのデバッガー設定をカスタマイズできます。 これらの設定は、プロジェクト ルートの *`.vs`* フォルダー内にある *launch.vs.json* という構成ファイル内にあります。 起動構成ファイルは、デバッグ設定の詳細を構成して保存できるため、ほとんどのデバッグ シナリオで役立ちます。 このファイルには 3 つのエントリ ポイントがあります。

- **[デバッグ] メニュー:** メイン メニューから **[デバッグ] > [${activeDebugTarget} のデバッグおよび起動の設定]** を選択し、アクティブなデバッグ ターゲットに固有のデバッグ構成をカスタマイズします。 デバッグ ターゲットを選択していない場合、このオプションはグレー表示されます。

![[デバッグ] メニュー エントリ ポイント](media/cmake-debug-menu.png "[デバッグ] メニュー エントリ ポイント")

- **ターゲット ビュー:** ソリューション エクスプローラーで **ターゲット ビュー** に移動します。 次に、デバッグ ターゲットを右クリックし、 **[Add Debug Configuration]\(デバッグ構成の追加\)** を選び、選択したターゲットに固有のデバッグ構成をカスタマイズします。

![ターゲット ビュー エントリ ポイント](media/cmake-targets-add-debug-configuration.png "ターゲット ビュー エントリ ポイント")

- **ルートの CMakeLists.txt:** ルートの *CMakeLists.txt* を右クリックし、 **[Add Debug Configuration]\(デバッグ構成 の追加\)** を選んで **[デバッガーの選択]** ダイアログ ボックスを開きます。 このダイアログでは、" *すべての* " 種類のデバッグ構成を追加できますが、`projectTarget` プロパティを使用して、呼び出す CMake ターゲットを手動で指定する必要があります。

![[デバッガーの選択] ダイアログ ボックス](media/cmake-select-a-debugger.png "[デバッガーの選択] ダイアログ ボックス")

*launch.vs.json* ファイルを編集して、任意の数の CMake ターゲットに対してデバッグ構成を作成できます。 このファイルを保存すると、Visual Studio によって **[スタートアップ アイテム]** ドロップダウンに新しい構成ごとにエントリが作成されます。

## <a name="reference-keys-in-cmakesettingsjson"></a>CMakeSettings.json のキーを参照する

*CMakeSettings.json* ファイル内の任意のキーを参照するには、 *launch.vs.json* 内でそのキーの先頭に `cmake.` を追加します。 次に示す簡単な *launch.vs.json* ファイルの例では、現在選択されている構成に対して、 *CMakeSettings.json* ファイル内の `remoteCopySources` キーの値を取得しています。

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "project": "CMakeLists.txt",
      "projectTarget": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "name": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "args": ["${cmake.remoteCopySources}"]
    }
  ]
}
```

また、構文 `${env.VARIABLE_NAME}` を使用して、 *CMakeSettings.json* で定義されている **環境変数** を launch.vs.json で使用することもできます。 Visual Studio 2019 バージョン 16.4 以降では、 *CMakeSettings.json* で指定した環境を使用して、デバッグ ターゲットが自動的に起動されます。 環境変数は、 **null** に設定することで、設定解除できます。

## <a name="launchvsjson-reference"></a>Launch.vs.json の参照

*launch.vs.json* には、あらゆるデバッグ シナリオをサポートするためのプロパティが多数あります。 次のプロパティは、リモートとローカルの両方において、すべてのデバッグ構成に共通です。

- `projectTarget`:プロジェクトのビルド時に呼び出す CMake ターゲットを指定します。 **[デバッグ] メニュー** または **ターゲット ビュー** から *launch.vs.json* にアクセスすると、Visual Studio によって、このプロパティが自動的に設定されます。 この値は、 **[スタートアップ アイテム]** ドロップダウンに表示されている既存のデバッグ ターゲットの名前と一致する必要があります。

- `env`:次の構文を使用して追加する追加の環境変数。

  ```json
  "env": {
        "DEBUG_LOGGING_LEVEL": "trace;info",
        "ENABLE_TRACING": "true"
      }
  ```

- `args`:デバッグするプログラムに渡されるコマンド ライン引数。

## <a name="launchvsjson-reference-for-remote-projects-and-wsl"></a>リモート プロジェクトおよび WSL 用の Launch.vs.json の参照

Visual Studio 2019 バージョン 16.6 では、リモート システムおよび WSL でのデバッグを簡略化するために、新しいデバッグ構成の `type: cppgdb` が追加されました。 古いデバッグ構成の `type: cppdbg` は引き続きサポートされます。

### <a name="configuration-type-cppgdb"></a>構成の種類 `cppgdb`

- `name`: **[スタートアップ アイテム]** ドロップダウンで構成を識別するためのフレンドリ名。
- `project`:プロジェクト ファイルへの相対パスを指定します。 通常、CMake プロジェクトをデバッグするときに、このパスを変更する必要はありません。
- `projectTarget`:プロジェクトのビルド時に呼び出す CMake ターゲットを指定します。 **[デバッグ] メニュー** または **ターゲット ビュー** から *launch.vs.json* にアクセスすると、Visual Studio によって、このプロパティが自動的に設定されます。 このターゲット値は、 **[スタートアップ アイテム]** ドロップダウンに表示されている既存のデバッグ ターゲットの名前と一致している必要があります。
- `debuggerConfiguration`:使用するデバッグの既定値のセットを指定します。 Visual Studio 2019 バージョン 16.6 では、有効なオプションは `gdb`のみです。 Visual Studio 2019 バージョン 16.7 以降は `gdbserver` もサポートしています。
- `args`:スタートアップ時にデバッグ中のプログラムに渡されるコマンド ライン引数。
- `env`:デバッグ中のプログラムに渡される追加の環境変数。 たとえば、`{"DISPLAY": "0.0"}` のようにします。
- `processID`:アタッチする Linux プロセス ID。 リモート プロセスにアタッチする場合にのみ使用されます。 詳細については、「[GDB を使用したプロセスへのアタッチのトラブルシューティング](https://github.com/Microsoft/MIEngine/wiki/Troubleshoot-attaching-to-processes-using-GDB)」を参照してください。

#### <a name="additional-options-for-the-gdb-configuration"></a>`gdb` 構成の追加オプション

- `program`:既定値は `"${debugInfo.fullTargetPath}"` です。 デバッグするアプリケーションへの UNIX パス。 ビルドまたは配置場所のターゲット実行可能ファイルと異なる場合にのみ必須です。
- `remoteMachineName`:既定値は `"${debugInfo.remoteMachineName}"` です。 デバッグするプログラムをホストするリモート システムの名前。 ビルド システムと異なる場合にのみ必須です。 [接続マネージャー](../linux/connect-to-your-remote-linux-computer.md)に既存のエントリがなければなりません。 **Ctrl + Space** キーを押して、すべての既存のリモート接続を一覧表示します。
- `cwd`:既定値は `"${debugInfo.defaultWorkingDirectory}"` です。 `program` が実行されるリモート システム上のディレクトリへの UNIX パス。 ディレクトリは存在している必要があります。
- `gdbpath`:既定値は `/usr/bin/gdb` です。 デバッグに使用される `gdb` への完全な UNIX パス。 `gdb` のカスタム バージョンを使用する場合にのみ必須です。
- `preDebugCommand`:`gdb` を呼び出す直前に実行する Linux コマンド。 このコマンドが完了するまで `gdb` は開始されません。 このオプションを使用すると、`gdb` の実行前にスクリプトを実行できます。

#### <a name="additional-options-allowed-with-the-gdbserver-configuration-167-or-later"></a>`gdbserver` 構成で使用できるその他のオプション (16.7 以降)

- `program`:既定値は `"${debugInfo.fullTargetPath}"` です。 デバッグするアプリケーションへの UNIX パス。 ビルドまたは配置場所のターゲット実行可能ファイルと異なる場合にのみ必須です。
- `remoteMachineName`:既定値は `"${debugInfo.remoteMachineName}"` です。 デバッグするプログラムをホストするリモート システムの名前。 ビルド システムと異なる場合にのみ必須です。 [接続マネージャー](../linux/connect-to-your-remote-linux-computer.md)に既存のエントリがなければなりません。 **Ctrl + Space** キーを押して、すべての既存のリモート接続を一覧表示します。
- `cwd`:既定値は `"${debugInfo.defaultWorkingDirectory}"` です。 `program` が実行されるリモート システム上のディレクトリへの完全な UNIX パス。 ディレクトリは存在している必要があります。
- `gdbPath`:既定値は `${debugInfo.vsInstalledGdb}` です。 デバッグに使用される `gdb` の完全な Windows パス。 既定値は、C および C++ ワークロードを使用する Linux 開発でインストールされる `gdb` です。
- `gdbserverPath`:既定値は `usr/bin/gdbserver` です。 デバッグに使用される `gdbserver` への完全な UNIX パス。
- `preDebugCommand`:`gdbserver` を呼び出す直前に実行する Linux コマンド。 このコマンドが完了するまで `gdbserver` は開始されません。

#### <a name="deployment-options"></a>配置オプション

次のオプションを使用して、リモート デバッグ マシンからビルド マシン (CMakeSettings.json で定義) を分離します。

- `remoteMachineName`:リモート デバッグ マシン。 ビルド マシンと異なる場合にのみ必須です。 [接続マネージャー](../linux/connect-to-your-remote-linux-computer.md)に既存のエントリがなければなりません。 **Ctrl + Space** キーを押して、すべての既存のリモート接続を一覧表示します。
- `disableDeploy`:既定値は **`false`** です。 ビルドとデバッグの分離が無効になっているかどうかを示します。 このオプションが **`false`** の場合、2 つの異なるマシンでビルドとデバッグを実行できます。
- `deployDirectory`:実行可能ファイルがコピーされる `remoteMachineName` 上のディレクトリへの完全な UNIX パス。
- `deploy`:配置の詳細設定の配列。 配置プロセスをより細かく制御する場合にのみ、これらの設定を構成する必要があります。 既定では、リモート デバッグ マシンには、デバッグ プロセスに必要なファイルのみが配置されます。
  - `sourceMachine`:ファイルまたはディレクトリのコピー元のマシン。 **Ctrl + Space** キーを押して、接続マネージャーに格納されているすべてのリモート接続を一覧表示します。 WSL でネイティブにビルドする場合、このオプションは無視されます。
  - `targetMachine`:ファイルまたはディレクトリのコピー先のマシン。 **Ctrl + Space** キーを押して、接続マネージャーに格納されているすべてのリモート接続を一覧表示します。
  - `sourcePath`:`sourceMachine` 上のファイルまたはディレクトリの場所。
  - `targetPath`:`targetMachine` 上のファイルまたはディレクトリの場所。
  - `deploymentType`:配置の種類の説明。 `LocalRemote` と `RemoteRemote` がサポートされています。 `LocalRemote` は、ローカル システムから、 *launch.vs.json* の `remoteMachineName` で指定されたリモート システムへのコピーを意味します。 `RemoteRemote` は、 *CMakeSettings.json* に指定されたリモート ビルド システムから、 *launch.vs.json* に指定された別のリモート システムへのコピーを意味します。
  - `executable`:配置されたファイルが実行可能ファイルであるかどうかを示します。

### <a name="execute-custom-gdb-commands"></a>カスタムの `gdb` コマンドを実行する

Visual Studio では、基になるデバッガーを直接操作するカスタムの `gdb` コマンドの実行がサポートされています。 詳細については、「[カスタムの `gdb` lldb コマンドの実行](https://github.com/microsoft/MIEngine/wiki/Executing-custom-gdb-lldb-commands)」を参照してください。

### <a name="enable-logging"></a>ログの有効化

`gdb` に送信されるコマンド、`gdb` から返される出力、各コマンドの所要時間を確認するには、MIEngine ログを有効にします。 [詳細を表示](https://github.com/microsoft/MIEngine/wiki/Logging)

### <a name="configuration-type-cppdbg"></a>構成の種類 `cppdbg`

構成の種類 `cppdbg` を使用してリモート システムまたは WSL でデバッグする場合は、次のオプションを使用できます。 Visual Studio 2019 バージョン 16.6 以降では、構成の種類 `cppgdb` をお勧めします。

- `name`: **[スタートアップ アイテム]** ドロップダウンで構成を識別するためのフレンドリ名。

- `project`:プロジェクト ファイルへの相対パスを指定します。 通常、CMake プロジェクトをデバッグするときに、この値を変更する必要はありません。

- `projectTarget`:プロジェクトのビルド時に呼び出す CMake ターゲットを指定します。 **[デバッグ] メニュー** または **ターゲット ビュー** から *launch.vs.json* にアクセスすると、Visual Studio によって、このプロパティが自動的に設定されます。 この値は、 **[スタートアップ アイテム]** ドロップダウンに表示されている既存のデバッグ ターゲットの名前と一致する必要があります。

- `args`:スタートアップ時にデバッグ中のプログラムに渡されるコマンド ライン引数。

- `processID`:アタッチする Linux プロセス ID。 リモート プロセスにアタッチする場合にのみ使用されます。 詳細については、「[GDB を使用したプロセスへのアタッチのトラブルシューティング](https://github.com/Microsoft/MIEngine/wiki/Troubleshoot-attaching-to-processes-using-GDB)」を参照してください。

- `program`:既定値は `"${debugInfo.fullTargetPath}"` です。 デバッグするアプリケーションへの UNIX パス。 ビルドまたは配置場所のターゲット実行可能ファイルと異なる場合にのみ必須です。

- `remoteMachineName`:既定値は `"${debugInfo.remoteMachineName}"` です。 デバッグするプログラムをホストするリモート システムの名前。 ビルド システムと異なる場合にのみ必須です。 [接続マネージャー](../linux/connect-to-your-remote-linux-computer.md)に既存のエントリがなければなりません。 **Ctrl + Space** キーを押して、すべての既存のリモート接続を一覧表示します。

- `cwd`:既定値は `"${debugInfo.defaultWorkingDirectory}"` です。 `program` が実行されるリモート システム上のディレクトリへの完全な UNIX パス。 ディレクトリは存在している必要があります。

- `environment`:デバッグ中のプログラムに渡される追加の環境変数。 たとえば、オブジェクトに適用された

  ```json
    "environment": [
        {
          "name": "ENV1",
          "value": "envvalue1"
        },
        {
          "name": "ENV2",
          "value": "envvalue2"
        }
      ]
  ```

- `pipeArgs`:接続を構成するためにパイプ プログラムに渡されるコマンド ライン引数の配列。 パイプ プログラムは、Visual Studio と `gdb` の間で標準の入出力をリレーするために使用されます。 この配列の大部分は、CMake プロジェクトをデバッグするときに **カスタマイズする必要はありません** 。 リモート システムで`gdb` を起動する `${debuggerCommand}` コマンドは例外です。 これは、次の操作を行うように変更できます。

  - 環境変数 DISPLAY の値を Linux システムにエクスポートします。 次の例では、この値は `:1` です。

    ```json
    "pipeArgs": [
        "/s",
        "${debugInfo.remoteMachineId}",
        "/p",
        "${debugInfo.parentProcessId}",
        "/c",
        "export DISPLAY=:1;${debuggerCommand}",
        "--tty=${debugInfo.tty}"
      ],
    ```

  - `gdb` の実行前にスクリプトを実行します。 スクリプトに実行権限が設定されていることを確認してください。

    ```json
    "pipeArgs": [
        "/s",
        "${debugInfo.remoteMachineId}",
        "/p",
        "${debugInfo.parentProcessId}",
        "/c",
        "/path/to/script.sh;${debuggerCommand}",
        "--tty=${debugInfo.tty}"
      ],
    ```

- `stopOnEntry`:プロセスの起動時にすぐに中断するかどうかを指定するブール値。 既定値は false です。

- `visualizerFile`:このプロセスをデバッグするときに使用する [.natvis ファイル](/visualstudio/debugger/create-custom-views-of-native-objects)。 このオプションは `gdb` 再フォーマットと互換性がありません。 このプロパティを設定する場合は `showDisplayString` も設定します。

- `showDisplayString`:`visualizerFile` が指定されている場合に表示文字列を有効にするブール値。 このオプションを **`true`** に設定すると、デバッグ中にパフォーマンスが低下する可能性があります。

- `setupCommands`:基になるデバッガーを設定するために実行する 1 つ以上の `gdb` コマンド。

- `miDebuggerPath`:`gdb` の完全なパス。 指定しない場合、Visual Studio では、デバッガーのパスを最初に検索します。

- 最後に、構成の種類 `cppgdb` に対して定義されたすべての配置オプションは、構成の種類 `cppdbg` でも使用できます。

### <a name="debug-using-gdbserver"></a>`gdbserver` を使用してデバッグする

`gdbserver` を使用してデバッグするように、`cppdbg` 構成を構成できます。 詳細情報とサンプルの起動構成については、Microsoft C++ チームのブログ「[`gdbserver` を使用した Linux CMake プロジェクトのデバッグ](https://devblogs.microsoft.com/cppblog/debugging-linux-cmake-projects-with-gdbserver/)」を参照してください。

::: moniker-end

::: moniker range=">=msvc-150"

## <a name="see-also"></a>関連項目

[Visual Studio の CMake プロジェクト](cmake-projects-in-visual-studio.md)\
[Linux CMake プロジェクトを構成する](../linux/cmake-linux-project.md)\
[リモートの Linux コンピューターに接続する](../linux/connect-to-your-remote-linux-computer.md)\
[CMake のビルド設定をカスタマイズする](customize-cmake-settings.md)\
[CMake デバッグ セッションを構成する](configure-cmake-debugging-sessions.md)\
[Linux プロジェクトの配置、実行、デバッグ](../linux/deploy-run-and-debug-your-linux-project.md)\
[CMake 定義済み構成リファレンス](cmake-predefined-configuration-reference.md)

::: moniker-end
