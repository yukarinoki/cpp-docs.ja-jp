---
title: Visual Studio で CMake デバッグ セッションを構成する
description: Visual Studio を使用して CMake デバッガーの設定を構成する方法について説明します。
ms.date: 04/02/2020
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: 8364e5b3dd3316a4ed7e754a104a14373040aa6e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328856"
---
# <a name="configure-cmake-debugging-sessions"></a>CMake デバッグ セッションを構成する

::: moniker range="vs-2015"

ネイティブ CMake サポートは、Visual Studio 2017 以降で使用できます。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end

::: moniker range=">=vs-2017"

すべての実行可能な CMake ターゲットが、**[全般]** ツール バーの **[スタートアップ アイテム]** ドロップダウンに表示されます。 デバッグ セッションを開始し、デバッガーを起動する場合は、1 つを選択します。

![C スタートアップ項目ドロップダウンを作成する](media/cmake-startup-item-dropdown.png "C スタートアップ項目ドロップダウンを作成する")

ソリューション エクスプローラーからデバッグ セッションを開始することもできます。 まず、**ソリューション エクスプローラー**ウィンドウで **[CMake ターゲット] ビュー**に切り替えます。

![CMake ターゲット ビュー ボタン](media/cmake-targets-view.png  "C[ターゲットの選択] メニュー項目")

次に、実行可能ファイルを右クリックし、[**デバッグ**] を選択します。 このコマンドは、アクティブな構成に基づいて、選択したターゲットのデバッグを自動的に開始します。

## <a name="customize-debugger-settings"></a>デバッガー設定をカスタマイズする

プロジェクト内の実行可能な CMake ターゲットのデバッガー設定をカスタマイズできます。 これらのファイルは、プロジェクトルートのフォルダにある*launch.vs.json*という名前*`.vs`* の設定ファイルにあります。 起動構成ファイルは、デバッグセットアップの詳細を構成および保存できるため、ほとんどのデバッグ シナリオで役立ちます。 このファイルには、次の 3 つのエントリ ポイントがあります。

- **デバッグメニュー:** メイン メニューから **[デバッグ>と起動設定]** をメイン メニューから選択して、アクティブなデバッグ ターゲットに固有のデバッグ構成をカスタマイズします。 デバッグターゲットが選択されていない場合、このオプションはグレー表示されます。

![デバッグ メニューのエントリ ポイント](media/cmake-debug-menu.png "デバッグ メニューのエントリ ポイント")

- **ターゲットビュー:** ソリューション エクスプローラーの **[ターゲット ビュー]** に移動します。 次に、デバッグ ターゲットを右クリックし、[**デバッグ構成の追加**] を選択して、選択したターゲットに固有のデバッグ構成をカスタマイズします。

![ターゲット ビューのエントリ ポイント](media/cmake-targets-add-debug-configuration.png "ターゲット ビューのエントリ ポイント")

- **ルート CMakeLists.txt:** ルート*CMakeLists.txt*を右クリックし、[**デバッグ構成の追加**] を選択して **[デバッガーの選択**] ダイアログ ボックスを開きます。 このダイアログでは *、任意*の種類のデバッグ構成を追加できますが、プロパティを使用して呼び出す CMake`projectTarget`ターゲットを手動で指定する必要があります。

![[デバッガーの選択] ダイアログ ボックス](media/cmake-select-a-debugger.png "[デバッガーの選択] ダイアログ ボックス")

*launch.vs.json*ファイルを編集して、任意の数の CMake ターゲットのデバッグ構成を作成できます。 ファイルを保存すると、Visual Studio は **[スタートアップ項目]** ドロップダウンに新しい各構成のエントリを作成します。

## <a name="reference-keys-in-cmakesettingsjson"></a>キーを参照する

*CMakeSettings.json*ファイル内の任意のキーを参照するには`cmake.`、そのキーの前に*launch.vs.json*を追加します。 次の例は、現在選択されている構成の*CMakeSettings.json*ファイル内の`remoteCopySources`キーの値を取得する単純な*launch.vs.json*ファイルを示しています。

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

*CMakeSettings.json*で定義された`${env.VARIABLE_NAME}`**環境変数**は、構文を使用して launch.vs.json でも使用できます。 Visual Studio 2019 バージョン 16.4 以降では *、CMakeSettings.json*で指定した環境を使用してデバッグ ターゲットが自動的に起動されます。 環境変数を**null**に設定すると、設定を解除できます。

## <a name="launchvsjson-reference"></a>起動.vs.json リファレンス

すべてのデバッグ シナリオをサポートする*launch.vs.json*プロパティは多数あります。 次のプロパティは、リモートとローカルの両方のすべてのデバッグ構成に共通です。

- `projectTarget`: プロジェクトのビルド時に呼び出す CMake ターゲットを指定します。 Visual Studio では、**デバッグ メニュー**またはターゲット ビュー から*launch.vs.json*と入力すると、このプロパティ**が自動的に設定されます**。 この値は、[**スタートアップ項目]** ドロップダウンリストに表示されている既存のデバッグ ターゲットの名前と一致する必要があります。

- `env`: 構文を使用して追加する追加の環境変数:

  ```json
  "env": {
        "DEBUG_LOGGING_LEVEL": "trace;info",
        "ENABLE_TRACING": "true"
      }
  ```

- `args`: デバッグするプログラムに渡されるコマンド ライン引数。

## <a name="launchvsjson-reference-for-remote-projects-and-wsl"></a>リモート プロジェクトと WSL の起動.vs.json リファレンス

Visual Studio 2019 バージョン 16.6 では、リモート`type: cppgdb`システムと WSL でのデバッグを簡略化するための新しいデバッグ構成が追加されました。 の古いデバッグ`type: cppdbg`構成は引き続きサポートされています。

### <a name="configuration-type-cppgdb"></a>コンフィギュレーション タイプ`cppgdb`

- `name`:**スタートアップ項目**ドロップダウンで構成を識別するためのフレンドリ名。
- `project`: プロジェクト ファイルへの相対パスを指定します。 通常、CMake プロジェクトをデバッグするときにこのパスを変更する必要はありません。
- `projectTarget`: プロジェクトのビルド時に呼び出す CMake ターゲットを指定します。 Visual Studio では、**デバッグ メニュー**またはターゲット ビュー から*launch.vs.json*と入力すると、このプロパティ**が自動的に設定されます**。 このターゲット値は、[**スタートアップ項目]** ドロップダウンリストに表示されている既存のデバッグターゲットの名前と一致する必要があります。
- `debuggerConfiguration`: 使用するデバッグの既定値のセットを示します。 Visual Studio 2019 バージョン 16.6 では、`gdb`有効なオプションは . 以前のバージョンでは`gdbserver`、 もサポートしています。
- `args`: デバッグ中のプログラムに起動時に渡されるコマンドライン引数。
- `env`: デバッグ中のプログラムに渡される追加の環境変数。 たとえば、「 `{"DISPLAY": "0.0"}` 」のように入力します。
- `processID`: アタッチ先の Linux プロセス ID。 リモート プロセスにアタッチする場合にのみ使用されます。 詳細については、「 [GDB を使用したプロセスへのアタッチのトラブルシューティング](https://github.com/Microsoft/MIEngine/wiki/Troubleshoot-attaching-to-processes-using-GDB)」を参照してください。

#### <a name="additional-options-for-the-gdb-configuration"></a>`gdb`構成の追加オプション

- `program`: デフォルトは`"${debugInfo.fullTargetPath}"`. デバッグするアプリケーションへの Unix パス。 ビルドまたは配置の場所でターゲット実行可能ファイルと異なる場合にのみ必要です。
- `remoteMachineName`: デフォルトは`"${debugInfo.remoteMachineName}"`. デバッグするプログラムをホストするリモート・システムの名前。 ビルド システムと異なる場合にのみ必要です。 [接続マネージャ](../linux/connect-to-your-remote-linux-computer.md)に既存のエントリが必要です。 **Ctrl キーを押しながらスペースキー**を押して、既存のすべてのリモート接続のリストを表示します。
- `cwd`: デフォルトは`"${debugInfo.defaultWorkingDirectory}"`. 実行される`program`リモート システム上のディレクトリへの Unix パス。 ディレクトリは存在している必要があります。
- `gdbpath`: デフォルトは`/usr/bin/gdb`. デバッグに使用する`gdb`Unix の完全パス。 カスタム バージョンの を使用する`gdb`場合にのみ必要です。
- `preDebugCommand`: 呼び出す`gdb`直前に実行する Linux コマンド。 `gdb`コマンドが完了するまで開始されません。 オプションを使用して、 の実行前にスクリプトを実行`gdb`できます。

#### <a name="deployment-options"></a>デプロイ オプション

次のオプションを使用して、ビルド コンピューター (CMakeSettings.json で定義) をリモート デバッグ コンピューターから分離します。

- `remoteMachineName`: リモート デバッグ マシン。 ビルド コンピューターと異なる場合にのみ必要です。 [接続マネージャ](../linux/connect-to-your-remote-linux-computer.md)に既存のエントリが必要です。 **Ctrl キーを押しながらスペースキー**を押して、既存のすべてのリモート接続のリストを表示します。
- `disableDeploy`: デフォルトは`false`. ビルド/デバッグの分離が無効かどうかを示します。 この`false`オプションを使用すると、ビルドとデバッグを 2 つの別々のマシンで実行できます。
- `deployDirectory`: 実行可能ファイルのコピー`remoteMachineName`先ディレクトリへの完全な Unix パス。
- `deploy`: 拡張配置設定の配列。 展開プロセスをより細かく制御する場合にのみ、これらの設定を構成する必要があります。 既定では、プロセスがデバッグに必要なファイルのみがリモート デバッグ コンピューターに配置されます。
  - `sourceMachine`: ファイルまたはディレクトリのコピー元のマシン。 **Ctrl キーを押しながら Space キー**を押して、接続マネージャに格納されているすべてのリモート接続の一覧を表示します。 WSL 上でネイティブにビルドする場合、このオプションは無視されます。
  - `targetMachine`: ファイルまたはディレクトリのコピー先のコンピュータ。 **Ctrl キーを押しながら Space キー**を押して、接続マネージャに格納されているすべてのリモート接続の一覧を表示します。
  - `sourcePath`: 上のファイルまたはディレクトリ`sourceMachine`の場所。
  - `targetPath`: 上のファイルまたはディレクトリ`targetMachine`の場所。
  - `deploymentType`: 展開の種類の説明。 `LocalRemote`が`RemoteRemote`サポートされています。 `LocalRemote`は、ローカル ファイルシステムから *、launch.vs.json*で`remoteMachineName`指定されたリモート システムにコピーすることを意味します。 `RemoteRemote`*は、CMakeSettings.json*で指定されたリモート ビルド システムから *、launch.vs.json*で指定された別のリモート システムにコピーすることを意味します。
  - `executable`: 配置されたファイルが実行可能ファイルかどうかを示します。

### <a name="execute-custom-gdb-commands"></a>カスタム`gdb`コマンドの実行

Visual Studio では、`gdb`基になるデバッガーと直接対話するカスタム コマンドの実行がサポートされています。 詳しくは、[カスタム`gdb`lldb コマンドの実行を](https://github.com/microsoft/MIEngine/wiki/Executing-custom-gdb-lldb-commands)参照してください。

### <a name="enable-logging"></a>ログの有効化

MIEngine ロギングを有効にして`gdb`、どのコマンドが送信され`gdb`、どの出力が返され、各コマンドにかかる時間を確認します。 [詳細を表示](https://github.com/microsoft/MIEngine/wiki/Logging)

### <a name="configuration-type-cppdbg"></a>コンフィギュレーション タイプ`cppdbg`

次のオプションは、リモート システムまたは WSL で構成の種類`cppdbg`を使用してデバッグするときに使用できます。 Visual Studio 2019 バージョン 16.6 以降`cppgdb`では、構成の種類を推奨します。

- `name`:**スタートアップ項目**ドロップダウンで構成を識別するためのフレンドリ名。

- `project`: プロジェクト ファイルへの相対パスを指定します。 通常、CMake プロジェクトをデバッグするときにこの値を変更する必要はありません。

- `projectTarget`: プロジェクトのビルド時に呼び出す CMake ターゲットを指定します。 Visual Studio では、**デバッグ メニュー**またはターゲット ビュー から*launch.vs.json*と入力すると、このプロパティ**が自動的に設定されます**。 この値は、[**スタートアップ項目]** ドロップダウンリストに表示されている既存のデバッグ ターゲットの名前と一致する必要があります。

- `args`: デバッグ中のプログラムに起動時に渡されるコマンドライン引数。

- `processID`: アタッチ先の Linux プロセス ID。 リモート プロセスにアタッチする場合にのみ使用されます。 詳細については、「 [GDB を使用したプロセスへのアタッチのトラブルシューティング](https://github.com/Microsoft/MIEngine/wiki/Troubleshoot-attaching-to-processes-using-GDB)」を参照してください。

- `program`: デフォルトは`"${debugInfo.fullTargetPath}"`. デバッグするアプリケーションへの Unix パス。 ビルドまたは配置の場所でターゲット実行可能ファイルと異なる場合にのみ必要です。

- `remoteMachineName`: デフォルトは`"${debugInfo.remoteMachineName}"`. デバッグするプログラムをホストするリモート・システムの名前。 ビルド システムと異なる場合にのみ必要です。 [接続マネージャ](../linux/connect-to-your-remote-linux-computer.md)に既存のエントリが必要です。 **Ctrl キーを押しながらスペースキー**を押して、既存のすべてのリモート接続のリストを表示します。

- `cwd`: デフォルトは`"${debugInfo.defaultWorkingDirectory}"`. 実行される`program`リモート システム上のディレクトリへの完全な Unix パス。 ディレクトリは存在している必要があります。

- `environment`: デバッグ中のプログラムに渡される追加の環境変数。 たとえば、次のように入力します。

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

- `pipeArgs`: 接続を構成するためにパイプ プログラムに渡されるコマンド ライン引数の配列。 パイプ プログラムは、Visual Studio と`gdb`の間で標準の入出力を中継するために使用されます。 CMake プロジェクトをデバッグするときに、この配列の大部分**をカスタマイズする必要はありません**。 例外は`${debuggerCommand}`、リモート システムで起動`gdb`する 、 です。 次の設定に変更できます。

  - Linux システムで環境変数 DISPLAY の値をエクスポートします。 次の例では、この値は`:1`です。

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

  - の実行前にスクリプトを実行`gdb`します。 スクリプトに実行権限が設定されていることを確認します。

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

- `stopOnEntry`: プロセスが起動するとすぐに中断するかどうかを指定するブール値。 既定値は false です。

- `visualizerFile`: このプロセスをデバッグするときに使用する[.natvis ファイル](/visualstudio/debugger/create-custom-views-of-native-objects)。 このオプションは、美しい`gdb`印刷と互換性がありません。 このプロパティ`showDisplayString`を設定する場合も設定します。

- `showDisplayString`: a が指定されている場合に表示`visualizerFile`文字列を有効にするブール値。 このオプションを設定`true`すると、デバッグ中のパフォーマンスが低下する可能性があります。

- `setupCommands`: 実行する`gdb`1 つ以上のコマンドを実行し、基になるデバッガーを設定します。

- `miDebuggerPath`: への完全パス`gdb`。 指定されていない場合、デバッガーのパスが最初に検索されます。

- 最後に、`cppgdb`構成の種類に対して定義されているすべての展開オプションを構成の`cppdbg`種類でも使用できます。

### <a name="debug-using-gdbserver"></a>を使用してデバッグ`gdbserver`

を使用して`gdbserver`デバッグ`cppdbg`するように構成を構成できます。 詳細とサンプルの起動設定については、「Microsoft C++ チーム ブログ」の[「Linux CMake`gdbserver`プロジェクトのデバッグ 」を参照](https://devblogs.microsoft.com/cppblog/debugging-linux-cmake-projects-with-gdbserver/)してください。

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="see-also"></a>関連項目

[C プロジェクトを作成する](cmake-projects-in-visual-studio.md)\
[Linux CMake プロジェクトを構成する](../linux/cmake-linux-project.md)\
[リモート Linux コンピュータに接続する](../linux/connect-to-your-remote-linux-computer.md)\
[CMake ビルド設定のカスタマイズ](customize-cmake-settings.md)\
[CMake デバッグ セッションの構成](configure-cmake-debugging-sessions.md)\
[Linux プロジェクトのデプロイ、実行、デバッグ](../linux/deploy-run-and-debug-your-linux-project.md)\
[CMake 定義済み構成リファレンス](cmake-predefined-configuration-reference.md)

::: moniker-end
