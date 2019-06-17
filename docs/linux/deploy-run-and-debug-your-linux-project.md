---
title: Visual Studio で C++ Linux プロジェクトを配置、実行、デバッグする
description: Visual Studio の Linux C++ プロジェクト内からリモート ターゲット上のコードをコンパイル、実行、デバッグする方法について説明します。
ms.date: 06/07/2019
ms.assetid: f7084cdb-17b1-4960-b522-f84981bea879
ms.openlocfilehash: 707915a502aafefee47af7e84b534e06ba678b3d
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821623"
---
# <a name="deploy-run-and-debug-your-linux-project"></a>Linux プロジェクトのデプロイ、実行、デバッグ

::: moniker range="vs-2015"

Linux サポートは Visual Studio 2017 以降で使用できます。

::: moniker-end

Visual Studio で Linux C++ プロジェクトを作成し、[Linux 接続マネージャー](connect-to-your-remote-linux-computer.md)でプロジェクトに接続したら、プロジェクトを実行し、デバッグできます。 リモート ターゲットでコードをコンパイル、実行、デバッグします。

::: moniker range="vs-2019"

**Visual Studio 2019 バージョン 16.1** さまざまな Linux システムを対象に、デバッグおよび構築することができます。 **[全般]** プロパティ ページでビルド マシンを指定し、 **[デバッグ]** プロパティ ページでデバッグ マシンを指定します。

::: moniker-end

Linux プロジェクトと対話してデバッグするには、いくつかの方法があります。

- ブレークポイント、ウォッチ ウィンドウ、変数をポイントするなど、従来の Visual Studio 機能でデバッグします。 これらの方法を利用し、他の種類のプロジェクトに通常するようにデバッグできます。

- Linux コンソール ウィンドウで対象のコンピューターからの出力を確認します。 このコンソールを利用し、ターゲット コンピューターに入力を送信することもできます。

## <a name="debug-your-linux-project"></a>Linux プロジェクトをデバッグする

1. **[デバッグ]** プロパティ ページでデバッグ モードを選びます。

   
   
   ::: moniker range="vs-2019"

   Linux で実行されているアプリケーションのデバッグには、GDB を使います。 (WSL ではない) リモート システムでデバッグを行う場合、GDB を 2 種類のモードで実行できます。これは、プロジェクトの **[デバッグ]** プロパティ ページの **[デバッグ モード]** オプションで選ぶことができます。

   ![GDB のオプション](media/vs2019-debugger-settings.png)

   ::: moniker-end

   ::: moniker range="vs-2017"

   Linux で実行されているアプリケーションのデバッグには、GDB を使います。 GDB は 2 種類のモードで実行でき、プロジェクトの **[デバッグ]** プロパティ ページの **[デバッグ モード]** オプションで選ぶことができます。

   ![GDB のオプション](media/vs2017-debugger-settings.png)

   ::: moniker-end


   - **gdbserver** モードでは、GDB はローカルに実行され、リモート システム上の gdbserver に接続します。  Linux コンソール ウィンドウはこのモードだけをサポートすることに注意してください。

   - **gdb** モードでは、Visual Studio デバッガーによりリモート システム上で GDB が実行されます。 GDB のローカル バージョンがターゲット コンピューターにインストールされているバージョンと互換性がない場合には、こちらの方が適切なオプションです。 |

   > [!NOTE]
   > gdbserver デバッグ モードでブレークポイントに到達できない場合、gdb モードを試してください。 最初にリモート ターゲットに gdb を[インストール](download-install-and-setup-the-linux-development-workload.md)する必要があります。

1. Visual Studio の標準**デバッグ** ツール バーでリモート ターゲットを選びます。

   リモート ターゲットが利用できるとき、名前または IP アドレスで一覧表示されます。

   ![リモート ターゲット](media/remote_target.png)

   リモート ターゲットに接続していない場合、[Linux 接続マネージャー](connect-to-your-remote-linux-computer.md)を利用してリモート ターゲットに接続するように求める指示が表示されます。

   ![リモート アーキテクチャ](media/architecture.png)

1. 実行することがわかっているコードの左端余白をクリックし、ブレークポイントを設定します。

   ブレークポイントを設定したコード行に赤い点が表示されます。

1. **F5** を押して (あるいは、 **[デバッグ]、[デバッグの開始]** の順に選択し) デバッグを開始します。

   デバッグを開始するとき、開始前に、リモート ターゲットでアプリケーションがコンパイルされます。 コンパイル エラーは **[エラー一覧]** ウィンドウに表示されます。

   エラーがない場合、アプリが起動し、デバッガーはブレークポイントで一時停止します。

   ![ブレークポイントに到達する](media/hit_breakpoint.png)

   **F10** や **F11** などのコマンド キーを押すことで、現在の状態のアプリケーションと対話したり、変数を表示したり、コードをステップ実行したりできるようになりました。

1. Linux コンソールを利用してアプリと対話する場合、 **[デバッグ]、[Linux コンソール]** の順に選びます。

   ![[Linux Console] (Linux コンソール) メニュー](media/consolemenu.png)

   このコンソールでは、ターゲット コンピューターからのコンソール出力が表示され、値を入力してターゲット コンピューターに送信できます。

   ![Linux コンソール ウィンドウ](media/consolewindow.png)

## <a name="configure-other-debugging-options"></a>その他のデバッグ オプションを構成する

- プロジェクトの **[デバッグ]** プロパティ ページの **[プログラムの引数]** 項目を使って、実行可能ファイルにコマンド ライン引数を渡すことができます。

   ![プログラムの引数](media/settings_programarguments.png)

- **[追加のデバッガー コマンド]** エントリを使って、特定のデバッガー オプションを GDB に渡すことができます。  たとえば、SIGILL (無効な命令) シグナルを無視することができます。  これを行うには、**handle** コマンドを使います。  上の図のように、次のコードを **[追加のデバッガー コマンド]** エントリに追加します。

   `handle SIGILL nostop noprint`

## <a name="debug-with-attach-to-process"></a>[プロセスにアタッチ] を使用してデバッグする

Visual Studio プロジェクトの [[デバッグ]](prop-pages/debugging-linux.md) プロパティ ページと CMake プロジェクトの **Launch.vs.json** 設定には、実行中のプロセスにアタッチするための設定があります。 これらで可能な設定以上の制御を行いたい場合、ソリューションまたはワークスペースのルートに `Microsoft.MIEngine.Options.xml` という名前のファイルを配置します。 次に、簡単な例を示します。

```xml
<?xml version="1.0" encoding="utf-8"?>
<SupplementalLaunchOptions>
    <AttachOptions>
      <AttachOptionsForConnection AdditionalSOLibSearchPath="/home/user/solibs">
        <ServerOptions MIDebuggerPath="C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise\Common7\IDE\VC\Linux\bin\gdb\7.9\x86_64-linux-gnu-gdb.exe"
ExePath="C:\temp\ConsoleApplication17\ConsoleApplication17\bin\x64\Debug\ConsoleApplication17.out"/>
        <SetupCommands>
          <Command IgnoreFailures="true">-enable-pretty-printing</Command>
        </SetupCommands>
      </AttachOptionsForConnection>
    </AttachOptions>
</SupplementalLaunchOptions>
```

**AttachOptionsForConnection** には必要な多くの属性があります。 上記の例は、追加の .so ライブラリを検索する場所を指定する方法を示しています。 子要素 **ServerOptions** を使用すると、代わりに gdbserver でリモート プロセスをアタッチできます。 これを実行するには、ローカルの gdb クライアントと (Visual Studio 2017 で出荷されているものは上のとおりです)、バイナリのローカル コピーをシンボルと共に指定する必要があります。 **SetupCommands** 要素を使用すると、コマンドを gdb に直接渡すことができます。 使用可能なすべてのオプションは、GitHub の [LaunchOptions.xsd schema](https://github.com/Microsoft/MIEngine/blob/master/src/MICore/LaunchOptions.xsd) にあります。

## <a name="next-steps"></a>次の手順

- Linux 上での ARM デバイスのデバッグについては、ブログの投稿「[Debugging an embedded ARM device in Visual Studio](https://blogs.msdn.microsoft.com/vcblog/2018/01/10/debugging-an-embedded-arm-device-in-visual-studio/)」 (Visual Studio での埋め込み ARM デバイスのデバッグ) を参照してください。

## <a name="see-also"></a>関連項目

[C++ デバッグ プロパティ (Linux C++)](prop-pages/debugging-linux.md)
