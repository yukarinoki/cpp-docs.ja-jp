---
title: Visual Studio で Linux MSBuild C++ プロジェクトを配置、実行、デバッグする
description: Visual Studio で MSBuild ベースの Linux C++ プロジェクト内からリモート ターゲット上のコードをコンパイル、実行、デバッグする方法について説明します。
ms.date: 08/08/2020
ms.assetid: f7084cdb-17b1-4960-b522-f84981bea879
ms.openlocfilehash: a9feffbc86b50d510647776de6f1030f6986bef7
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921712"
---
# <a name="deploy-run-and-debug-your-linux-msbuild-project"></a>Linux MSBuild プロジェクトのデプロイ、実行、デバッグ

::: moniker range="msvc-140"
Linux サポートは Visual Studio 2017 以降で使用できます。 これらのバージョンのドキュメントを表示するには、目次の上にある **[バージョン]** ドロップダウンを **Visual Studio 2017** または **Visual Studio 2019** に設定します。
::: moniker-end

Visual Studio で MSBuild ベースの Linux C++ プロジェクトを作成し、[Linux 接続マネージャー](connect-to-your-remote-linux-computer.md)でプロジェクトに接続したら、プロジェクトを実行し、デバッグできます。 リモート ターゲットでコードをコンパイル、実行、デバッグします。

::: moniker range="msvc-160"

**Visual Studio 2019 バージョン 16.1** さまざまな Linux システムを対象に、デバッグおよび構築することができます。 たとえば、IoT シナリオをターゲットにするときに、.x64 でクロスコンパイルを行い、ARM デバイスに配置できます。 詳細については、この記事で後述する「[ビルド用とデバッグ用に異なるコンピューターを指定する](#separate_build_debug)」を参照してください。

::: moniker-end

Linux プロジェクトと対話してデバッグするには、いくつかの方法があります。

- ブレークポイント、ウォッチ ウィンドウ、変数をポイントするなど、従来の Visual Studio 機能でデバッグします。 これらの方法を利用し、他の種類のプロジェクトに通常するようにデバッグできます。

- Linux コンソール ウィンドウでターゲットコンピューターからの出力を確認します。 このコンソールを利用し、ターゲット コンピューターに入力を送信することもできます。

## <a name="debug-your-linux-project"></a>Linux プロジェクトをデバッグする

1. **[デバッグ]** プロパティ ページでデバッグ モードを選びます。

   ::: moniker range="msvc-160"

   Linux で実行されているアプリケーションのデバッグには、GDB を使います。 (WSL ではない) リモート システムでデバッグを行う場合、GDB を 2 種類のモードで実行できます。これは、プロジェクトの **[デバッグ]** プロパティ ページの **[デバッグ モード]** オプションで選ぶことができます。

   ![[構成プロパティ] > [デバッグ] が選択され、[デバッグ モード] が強調表示され、ドロップダウン リストから G B D が選択および強調表示されている Visual Studio 2019 Linux コンソール アプリ プロパティ ページのスクリーンショット。](media/vs2019-debugger-settings.png)

   ::: moniker-end

   ::: moniker range="msvc-150"

   Linux で実行されているアプリケーションのデバッグには、GDB を使います。 GDB は 2 種類のモードで実行でき、プロジェクトの **[デバッグ]** プロパティ ページの **[デバッグ モード]** オプションで選ぶことができます。

   ![[構成プロパティ] > [デバッグ] が選択され、[デバッグ モード] が強調表示され、ドロップダウン リストから G B D が選択および強調表示されている Visual Studio 2017 Linux コンソール アプリ プロパティ ページのスクリーンショット。](media/vs2017-debugger-settings.png)

   ::: moniker-end

   - **gdbserver** モードでは、GDB はローカルに実行され、リモート システム上の gdbserver に接続します。

   - **gdb** モードでは、Visual Studio デバッガーによりリモート システム上で GDB が実行されます。 GDB のローカル バージョンがターゲット コンピューターにインストールされているバージョンと互換性がない場合には、こちらの方が適切なオプションです。 Linux コンソール ウィンドウではこのモードだけがサポートされています。

   > [!NOTE]
   > gdbserver デバッグ モードでブレークポイントに到達できない場合、gdb モードを試してください。 最初にリモート ターゲットに gdb を[インストール](download-install-and-setup-the-linux-development-workload.md)する必要があります。

1. Visual Studio の標準 **デバッグ** ツール バーでリモート ターゲットを選びます。

   リモート ターゲットが利用できるとき、名前または IP アドレスで一覧表示されます。

   ![リモート ターゲット](media/remote_target.png)

   リモート ターゲットにまだ接続していない場合、[Linux 接続マネージャー](connect-to-your-remote-linux-computer.md)を利用してリモート ターゲットに接続するように求める指示が表示されます。

   ![リモート アーキテクチャ](media/architecture.png)

1. 実行することがわかっているコードの左端余白をクリックし、ブレークポイントを設定します。

   ブレークポイントを設定したコード行に赤い点が表示されます。

1. **F5** を押して (または、 **[デバッグ]、[デバッグの開始]** の順に選択して) デバッグを開始します。

   デバッグを開始するとき、開始前に、リモート ターゲットでアプリケーションがコンパイルされます。 コンパイル エラーは **[エラー一覧]** ウィンドウに表示されます。

   エラーがない場合、アプリが起動し、デバッガーはブレークポイントで一時停止します。

   ![ブレークポイントに到達する](media/hit_breakpoint.png)

   **F10** や **F11** などのコマンド キーを押すことで、現在の状態のアプリケーションと対話したり、変数を表示したり、コードをステップ実行したりできるようになりました。

1. Linux コンソールを利用してアプリと対話する場合、 **[デバッグ]、[Linux コンソール]** の順に選びます。

   ![[Linux Console] (Linux コンソール) メニュー](media/consolemenu.png)

   このコンソールでは、ターゲット コンピューターからのコンソール出力が表示され、値を入力してターゲット コンピューターに送信できます。

   ![Linux コンソール ウィンドウ](media/consolewindow.png)

## <a name="configure-other-debugging-options-msbuild-projects"></a>その他のデバッグ オプションを構成する (MSBuild プロジェクト)

- プロジェクトの **[デバッグ]** プロパティ ページの **[プログラムの引数]** 項目を使って、実行可能ファイルにコマンド ライン引数を渡すことができます。
- プロジェクトの **[デバッグ]** プロパティ ページの **[起動前コマンド]** を使用して、`DISPLAY` 環境変数をエクスポートできます。 例: `export DISPLAY=:0.0`

   ![プログラムの引数](media/settings_programarguments.png)

- **[追加のデバッガー コマンド]** エントリを使って、特定のデバッガー オプションを GDB に渡すことができます。  たとえば、SIGILL (無効な命令) シグナルを無視することができます。  **handle** コマンドを使用してこれを実現できます。上の図のように、以下を **[追加のデバッガー コマンド]** エントリに追加します。

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

**AttachOptionsForConnection** には、必要となる多くの属性があります。 上記の例は、追加の .so ライブラリを検索する場所を指定する方法を示しています。 子要素 **ServerOptions** を使用すると、代わりに gdbserver でリモート プロセスをアタッチできます。 これを実行するには、ローカルの gdb クライアントと (Visual Studio 2017 で出荷されているものは上のとおりです)、バイナリのローカル コピーをシンボルと共に指定する必要があります。 **SetupCommands** 要素を使用すると、コマンドを gdb に直接渡すことができます。 使用可能なすべてのオプションは、GitHub の [LaunchOptions.xsd schema](https://github.com/Microsoft/MIEngine/blob/master/src/MICore/LaunchOptions.xsd) にあります。

::: moniker range="msvc-160"

## <a name="specify-different-machines-for-building-and-debugging-in-msbuild-based-linux-projects"></a><a name="separate_build_debug"></a> MSBuild ベースの Linux プロジェクトでビルド用とデバッグ用に異なるコンピューターを指定する

Visual Studio 2019 バージョン 16.1 では、MSBuild ベースの Linux プロジェクトとリモート Linux マシンをターゲットとする CMake プロジェクトの両方で、リモート ビルド マシンとリモート デバッグ マシンを分離できます。 たとえば、IoT シナリオをターゲットにするときに、.x64 でクロスコンパイルを行い、ARM デバイスに配置できます。

既定では、リモート デバッグ マシンはリモート ビルド マシンと同じです ( **[構成プロパティ]**  >  **[全般]**  >  **[リモート ビルド マシン]** )。 新しいリモート デバッグ マシンを指定するには、 **ソリューション エクスプローラー** でプロジェクトを右クリックし、 **[構成プロパティ]** > **[デバッグ]** > **[リモート デバッグ マシン]** に移動します。  

![Linux リモート デバッグ マシン](media/linux-remote-debug-machine.png)

**[リモート デバッグ マシン]** ドロップダウン メニューには、確立済みのすべてのリモート接続が表示されています。 新しいリモート接続を追加するには、 **[ツール]**  >  **[オプション]**  >  **[クロス プラットフォーム]**  >  **[接続マネージャー]** に移動するか、 **[クイック起動]** で「接続マネージャー」を検索します。 新しいリモート配置ディレクトリをプロジェクトのプロパティ ページに指定することもできます ( **[構成プロパティ]**  >  **[全般]**  >  **[リモート配置ディレクトリ]** )。

既定では、リモート デバッグ マシンには、デバッグ プロセスにとって必要なファイルのみが配置されます。 **ソリューション エクスプローラー** を使用して、リモート デバッグ マシンに配置されるソース ファイルを構成できます。 ソース ファイルをクリックすると、そのファイルのプロパティのプレビューがソリューション エクスプローラーのすぐ下に表示されます。

![Linux の配置可能ファイル](media/linux-deployable-content.png)

**Content** プロパティは、ファイルがリモート デバッグ マシンに配置されるかどうかを指定します。 **[プロパティ ページ]**  >  **[構成マネージャー]** に移動し、目的の構成に対する **[配置]** をオフにすることで、配置全体を無効にできます。

場合によっては、プロジェクトの配置を細かく制御する必要があります。 たとえば、配置するいくつかのファイルが自分のソリューションに含まれていないときや、リモート配置ディレクトリをファイルまたはディレクトリごとにカスタマイズしたい場合です。 このような場合は、.vcxproj ファイルに次のコード ブロックを追加し、"example.cpp" を実際のファイルの名前に置き換えます。

```xml

<ItemGroup>
   <RemoteDeploy Include="__example.cpp">
<!-- This is the source Linux machine, can be empty if DeploymentType is LocalRemote -->
      <SourceMachine>$(RemoteTarget)</SourceMachine>
      <TargetMachine>$(RemoteDebuggingTarget)</TargetMachine>
      <SourcePath>~/example.cpp</SourcePath>
      <TargetPath>~/example.cpp</TargetPath>
<!-- DeploymentType can be LocalRemote, in which case SourceMachine will be empty and SourcePath is a local file on Windows -->
      <DeploymentType>RemoteRemote</DeploymentType>
<!-- Indicates whether the deployment contains executables -->
      <Executable>true</Executable>
   </RemoteDeploy>
</ItemGroup>
```

### <a name="cmake-projects"></a>CMake プロジェクト

リモート Linux マシンをターゲットとする CMake プロジェクトの場合は、新しいリモート デバッグ マシンを launch.vs.json に指定できます。 既定では、"remoteMachineName" の値は CMakeSettings.json 内の "remoteMachineName" プロパティと同期され、それはリモート ビルド マシンに対応しています。 これらのプロパティを一致させる必要はなくなり、launch.vs.json 内の "remoteMachineName" の値は、どのリモート マシンが配置とデバッグで使用されるかを指示します。

![CMake リモート デバッグ マシン](media/cmake-remote-debug-machine.png)

IntelliSense では、確立済みのすべてのリモート接続の一覧が提案されます。 **[ツール]**  >  **[オプション]**  >  **[クロス プラットフォーム]**  >  **[接続マネージャー]** に移動するか、 **[クイック起動]** で「接続マネージャー」を検索することで、新しいリモート接続を追加できます。

配置を完全に制御する場合は、launch.vs.json ファイルに次のコード ブロックを追加できます。 プレースホルダーを必ず実際の値に置き換えてください。

```json
"disableDeploy": false,
"deployDirectory": "~\foo",
"deploy" : [
   {
      "sourceMachine": "127.0.0.1 (username=example1, port=22, authentication=Password)",
      "targetMachine": "192.0.0.1 (username=example2, port=22, authentication=Password)",
      "sourcePath": "~/example.cpp",
      "targetPath": "~/example.cpp",
      "executable": "false"
   }
]
```

::: moniker-end

## <a name="next-steps"></a>次の手順

- Linux 上での ARM デバイスのデバッグについては、ブログの投稿「[Debugging an embedded ARM device in Visual Studio](https://devblogs.microsoft.com/cppblog/debugging-an-embedded-arm-device-in-visual-studio/)」 (Visual Studio での埋め込み ARM デバイスのデバッグ) を参照してください。

## <a name="see-also"></a>関連項目

[C++ デバッグ プロパティ (Linux C++)](prop-pages/debugging-linux.md)
