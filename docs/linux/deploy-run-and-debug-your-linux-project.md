---
title: Visual Studio で C++ Linux プロジェクトを配置、実行、デバッグする
description: Visual Studio の Linux C++ プロジェクト内からリモート ターゲット上のコードをコンパイル、実行、デバッグする方法について説明します。
ms.date: 09/12/2018
ms.assetid: f7084cdb-17b1-4960-b522-f84981bea879
ms.openlocfilehash: cdafb064f8a6269c5ccae938e280b5f47bff3b00
ms.sourcegitcommit: b4645761ce5acf8c2fc7a662334dd5a471ea976d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "57562888"
---
# <a name="deploy-run-and-debug-your-linux-project"></a>Linux プロジェクトのデプロイ、実行、デバッグ

Visual Studio で Linux C++ プロジェクトを作成し、[Linux 接続マネージャー](connect-to-your-remote-linux-computer.md)でプロジェクトに接続したら、プロジェクトを実行し、デバッグできます。 リモート ターゲットでコードをコンパイル、実行、デバッグします。

Linux プロジェクトと対話してデバッグするには、いくつかの方法があります。

- ブレークポイント、ウォッチ ウィンドウ、変数をポイントするなど、従来の Visual Studio 機能でデバッグします。 これらの方法を利用し、他の種類のプロジェクトに通常するようにデバッグできます。

- 特別な Linux コンソール ウィンドウでターゲット コンピューターから出力を表示します。 このコンソールを利用し、ターゲット コンピューターに入力を送信することもできます。

## <a name="debug-your-linux-project"></a>Linux プロジェクトをデバッグする

1. **[デバッグ]** プロパティ ページでデバッグ モードを選びます。

   Linux で実行されているアプリケーションのデバッグには、GDB を使います。 GDB は 2 種類のモードで実行でき、プロジェクトの **[デバッグ]** プロパティ ページの **[デバッグ モード]** オプションで選ぶことができます。

   ![GDB のオプション](media/settings_debugger.png)

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

1. **F5** を押して (あるいは、**[デバッグ]、[デバッグの開始]** の順に選択し) デバッグを開始します。

   デバッグを開始するとき、開始前に、リモート ターゲットでアプリケーションがコンパイルされます。 コンパイル エラーは **[エラー一覧]** ウィンドウに表示されます。

   エラーがない場合、アプリが起動し、デバッガーはブレークポイントで一時停止します。

   ![ブレークポイントに到達する](media/hit_breakpoint.png)

   **F10** や **F11** などのコマンド キーを押すことで、現在の状態のアプリケーションと対話したり、変数を表示したり、コードをステップ実行したりできるようになりました。

1. Linux コンソールを利用してアプリと対話する場合、**[デバッグ]、[Linux コンソール]** の順に選びます。

   ![[Linux Console] (Linux コンソール) メニュー](media/consolemenu.png)

   このコンソールでは、ターゲット コンピューターからのコンソール出力が表示され、値を入力してターゲット コンピューターに送信できます。

   ![Linux コンソール ウィンドウ](media/consolewindow.png)

## <a name="configure-other-debugging-options"></a>その他のデバッグ オプションを構成する

- プロジェクトの **[デバッグ]** プロパティ ページの **[プログラムの引数]** 項目を使って、実行可能ファイルにコマンド ライン引数を渡すことができます。

   ![プログラムの引数](media/settings_programarguments.png)

- **[追加のデバッガー コマンド]** エントリを使って、特定のデバッガー オプションを GDB に渡すことができます。  たとえば、SIGILL (無効な命令) シグナルを無視することができます。  これを行うには、**handle** コマンドを使います。  上の図のように、次のコードを **[追加のデバッガー コマンド]** エントリに追加します。

   `handle SIGILL nostop noprint`

## <a name="next-steps"></a>次の手順

- Linux 上での ARM デバイスのデバッグについては、ブログの投稿「[Debugging an embedded ARM device in Visual Studio](https://blogs.msdn.microsoft.com/vcblog/2018/01/10/debugging-an-embedded-arm-device-in-visual-studio/)」 (Visual Studio での埋め込み ARM デバイスのデバッグ) を参照してください。

- **[プロセスにアタッチ]** コマンドを使用してデバッグする場合は、ブログの投稿「[Linux C++ Workload improvements to the Project System, Linux Console Window, rsync and Attach to Process](https://blogs.msdn.microsoft.com/vcblog/2018/03/13/linux-c-workload-improvements-to-the-project-system-linux-console-window-rsync-and-attach-to-process/)」(プロジェクト システム、Linux コンソール ウィンドウ、rsync およびプロセスへのアタッチに対する Linux C++ ワークロードの機能改善) を参照してください。

## <a name="see-also"></a>関連項目

[C++ デバッグ プロパティ (Linux C++)](prop-pages/debugging-linux.md)
