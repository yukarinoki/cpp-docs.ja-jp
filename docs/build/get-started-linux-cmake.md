---
title: Visual Studio で C++ クロスプラットフォーム プロジェクトを作成する
description: Linux と Windows の両方を対象とする C++ のオープンソース CMake プロジェクトを Visual Studio でセットアップ、コンパイル、デバッグする方法。
ms.topic: tutorial
ms.date: 01/08/2020
ms.openlocfilehash: c420e0ee04e85d49ad752da085d38b2c5ff9d4fa
ms.sourcegitcommit: d77159732a8e782b2a1b7abea552065f2b6f61c1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2020
ms.locfileid: "93344658"
---
# <a name="tutorial-create-c-cross-platform-projects-in-visual-studio"></a>チュートリアル: Visual Studio で C++ クロスプラットフォーム プロジェクトを作成する

Visual Studio での C と C++ の開発は、Windows だけではなくなっています。 このチュートリアルでは、Windows および Linux での C++ クロス プラットフォーム開発に Visual Studio を使用する方法について説明します。 これは CMake に基づいているため、Visual Studio プロジェクトを作成したり生成したりする必要はありません。 CMakeLists.txt ファイルが含まれるフォルダーを開くと、Visual Studio によって IntelliSense とビルド設定が自動的に構成されます。 Windows でローカルにコードの編集、ビルド、およびデバッグをすばやく開始できます。 その後、構成を切り替えて、Linux 上でも同じことをすべて Visual Studio 内から実行します。

このチュートリアルでは、次の作業を行う方法について説明します。

> [!div class="checklist"]
>
> * GitHub からオープンソースの CMake プロジェクトを複製する
> * Visual Studio でプロジェクトを開く
> * Windows 上で実行可能ターゲットをビルドしてデバッグする
> * Linux マシンへの接続を追加する
> * Linux 上で同じターゲットをビルドしてデバッグする

## <a name="prerequisites"></a>必須コンポーネント

* クロスプラットフォームの C++ 開発用に Visual Studio をセットアップする
  * まず、[Visual Studio をインストール](https://visualstudio.microsoft.com/vs/)し、 **[C++ によるデスクトップ開発]** および **[C++ による Linux 開発]** ワークロードを選択します。 この最小インストールはわずか 3 GB です。 ダウンロードの速度によりますが、インストールに 10 分以上はかからないはずです。

* クロスプラットフォームの C++ 開発用に Linux マシンをセットアップする
  * Visual Studio に Linux の特定のディストリビューションは必要ありません。 OS は、物理マシン、VM、またはクラウドで実行できます。 Linux 用 Windows サブシステム (WSL) を使用することもできます。 ただし、このチュートリアルでは、グラフィカルな環境が必要です。 WSL は、主にコマンド ライン操作用であるため、ここでは推奨されません。
  * Visual Studio には、Linux マシン上に次のツールが必要です。C++ コンパイラ、gdb、ssh、rsync、make、zip。 Debian ベースのシステムでは、次のコマンドを使用して、これらの依存関係をインストールできます。

    ```cmd
    sudo apt install -y openssh-server build-essential gdb rsync make zip
    ```

  * Visual Studio には、サーバー モードが有効になっている最近のバージョンの CMake (少なくとも 3.8) が、Linux マシン上に必要です。 Microsoft が生成した CMake のユニバーサル ビルドを、任意の Linux ディストリビューションにインストールできます。 最新の機能を確実に利用するには、このビルドを使用することをお勧めします。 CMake のバイナリは、GitHub の [CMake リポジトリの Microsoft フォーク](https://github.com/Microsoft/CMake/releases)から入手できます。 そのページに移動し、Linux マシンのシステム アーキテクチャと一致するバージョンをダウンロードして、それを実行可能にします。

    ```cmd
    wget <path to binary>
    chmod +x cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh
    ```

  * スクリプトを実行するためのオプションは、`-–help` で確認できます。 **/usr/bin** が Visual Studio での CMake の既定の参照場所であるため、`–prefix` オプションを使用して、 **/usr** パスへのインストールを指定することをお勧めします。 次の例では Linux-x86_64 スクリプトを示します。 別のターゲット プラットフォームを使用している場合は、必要に応じて変更してください。

    ```cmd
    sudo ./cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh --skip-license --prefix=/usr
    ```

* Windows マシンにインストールされている Git for Windows。
* GitHub アカウント。

## <a name="clone-an-open-source-cmake-project-from-github"></a>GitHub からオープンソースの CMake プロジェクトを複製する

このチュートリアルでは、GitHub の Bullet Physics SDK を使用します。 これには、多くのアプリケーション向けの衝突の検出および物理現象のシミュレーションが用意されています。 この SDK には、コードを追加しなくてもコンパイルして実行できるサンプルの実行可能プログラムが含まれています。 このチュートリアルでは、ソース コードもビルド スクリプトも変更しません。 始めるには、GitHub から Visual Studio がインストールされているマシンに、*bullet3* リポジトリをクローンします。

```cmd
git clone https://github.com/bulletphysics/bullet3.git
```

1. Visual Studio のメイン メニューで **[ファイル] > [開く] > [CMake]** を選択します。 ダウンロードした bullet3 リポジトリのルートにある CMakeLists.txt ファイルに移動します。

    ![Visual Studio の [ファイル] > [開く] > [CMake] メニュー](media/cmake-open-cmake.png)

    フォルダーを開くとすぐに、フォルダー構造が **ソリューション エクスプローラー** に表示されます。

    ![Visual Studio のソリューション エクスプローラーのフォルダー ビュー](media/cmake-bullet3-solution-explorer.png)

    このビューには、論理的なビューやフィルター処理されたビューではなく、ディスク上にあるものがそのまま表示されます。 既定では、隠しファイルは表示されません。

1. フォルダー内のすべてのファイルを表示するには、 **[すべてのファイルを表示]** ボタンを選択します。

    ![Visual Studio のソリューション エクスプローラーの [すべてのファイルを表示] ボタン](media/cmake-bullet3-show-all-files.png)

## <a name="switch-to-targets-view"></a>ターゲット ビューに切り替える

CMake を使用しているフォルダーを開くと、Visual Studio で CMake キャッシュが自動的に生成されます。 プロジェクトのサイズによっては、この操作にしばらくかかる場合があります。

1. **[出力ウィンドウ]** で **[Show output from]\(出力元\)** を選択してから、 **[CMake]** を選択して、キャッシュ生成処理の状態を監視します。 操作が完了すると、"ターゲット情報の抽出が完了しました" というメッセージが表示されます。

   ![CMake からの出力が表示された Visual Studio の出力ウィンドウ](media/cmake-bullet3-output-window.png)

   この操作が完了すると、IntelliSense が構成されます。 プロジェクトをビルドし、アプリケーションをデバッグできます。 Visual Studio では、CMakeLists ファイルで指定されているターゲットに基づいて、ソリューションの論理ビューが表示されるようになりました。

1. **ソリューション エクスプローラー** の **[ソリューションおよびフォルダー]** ボタンを使用して、CMake のターゲット ビューに切り替えます。

   ![CMake のターゲット ビューを表示するためのソリューション エクスプローラーの [ソリューションおよびフォルダー] ボタン](media/cmake-bullet3-show-targets.png)

   Bullet SDK でのビューの表示は次のようになります。

   ![ソリューション エクスプローラーの CMake ターゲット ビュー](media/cmake-bullet3-targets-view.png)

   ターゲット ビューでは、このソース ベースの内容に関するさらに直感的なビューが提供されます。 一部のターゲットはライブラリで、他は実行可能ファイルであることがわかります。

1. CMake ターゲット ビューでノードを展開すると、そのソース コード ファイルが表示されます。それらのファイルがディスク上のどこにあってもかまいません。

## <a name="add-an-explicit-windows-x64-debug-configuration"></a>明示的な Windows x64-Debug 構成を追加する

Visual Studio では、Windows 用の既定の **x64-Debug** 構成が作成されます。 構成により、Visual Studio は CMake に使用するプラットフォーム ターゲットを認識します。 既定の構成は、ディスク上では表されません。 構成を明示的に追加すると、Visual Studio では *CMakeSettings.json* というファイルが作成されます。 ユーザーが指定したすべての構成の設定がこれに取り込まれます。

1. 新しい構成を追加します。 ツール バーの **[構成]** ドロップダウンを開き、 **[構成の管理]** を選択します。

   ![[構成の管理] ドロップダウン](media/cmake-bullet3-manage-configurations.png)

   [CMake 設定エディター](customize-cmake-settings.md)が開きます。 エディターの左側にある緑色のプラス記号を選択して、新しい構成を追加します。 **[構成を CMakeSettings に追加する]** ダイアログが表示されます。

   ![[構成を CMakeSettings に追加する] ダイアログ](media/cmake-bullet3-add-configuration-x64-debug.png)

   このダイアログには、Visual Studio に含まれるすべての構成と、ユーザーが作成したカスタム構成が表示されます。 **x64-Debug** 構成を引き続き使用する場合は、それを最初に追加する必要があります。 **[x64-Debug]** を選択し、 **[選択]** ボタンを選択します。 Visual Studio で、**x64-Debug** 用の構成を含む CMakeSettings.json ファイルが作成され、ディスクに保存されます。 CMakeSettings.json で名前パラメーター直接変更することで、構成に好きな名前を使用できます。

## <a name="set-a-breakpoint-build-and-run-on-windows"></a>Windows でブレークポイントを設定し、ビルドして、実行する

このステップでは、Bullet Physics ライブラリのデモを行うサンプル プログラムをデバッグします。
  
1. **ソリューション エクスプローラー** で AppBasicExampleGui を選択して展開します。

1. `BasicExample.cpp` ファイルを開きます。

1. 実行中のアプリケーションをクリックするとヒットするブレークポイントを設定します。 クリック イベントは、ヘルパー クラスのメソッドで処理されます。 すばやく移動するには:

   1. 構造体 `BasicExample` の派生元である `CommonRigidBodyBase` を選択します。 これは 30 行目あたりにあります。

   1. 右クリックし、 **[定義へ移動]** を選択します。 これで、ヘッダー CommonRigidBodyBase.h 内に移動しました。

   1. ソースの上のブラウザー ビューで、`CommonRigidBodyBase` 内にいることがわかります。 右側で、調べるメンバーを選択できます。 ドロップダウンを開き、`mouseButtonCallback` を選択して、ヘッダー内にあるその関数の定義に移動します。

      ![Visual Studio のメンバーの一覧ツール バー](media/cmake-bullet3-member-list-toolbar.png)

1. この関数の最初の行にブレークポイントを設定します。 これは、Visual Studio デバッガーでの実行時にアプリケーションのウィンドウ内でマウス ボタンをクリックするとヒットします。

1. アプリケーションを起動するために、ツール バーの起動ドロップダウンを選択します。 これは、[スタートアップ アイテムの選択] と表示されている緑色の再生アイコンが付いたものです。 ドロップダウンで AppBasicExampleGui.exe を選択します。 実行可能ファイルの名前が起動ボタンに表示されます。

   ![Visual Studio ツール バーの [スタートアップ アイテムの選択] の起動ドロップダウン](media/cmake-bullet3-launch-button.png)

1. 起動ボタンを選択してアプリケーションと必要な依存関係をビルドし、Visual Studio デバッガーがアタッチされた状態でそれを起動します。 しばらくすると、実行中のアプリケーションが表示されます。

   ![Windows アプリケーションをデバッグしている Visual Studio](media/cmake-bullet3-launched.png)

1. アプリケーション ウィンドウ内にマウスを移動し、ボタンをクリックしてブレークポイントをトリガーします。 ブレークポイントにより、Visual Studio が前面表示に戻され、実行が一時停止している行がエディターで示されます。 アプリケーションの変数、オブジェクト、スレッド、メモリを調べたり、対話式にコードをステップ実行したりできます。 **[続行]** を選択してアプリケーションを再開させてから、通常どおりに終了します。 または、停止ボタンを使用して、Visual Studio 内での実行を停止します。

## <a name="add-a-linux-configuration-and-connect-to-the-remote-machine"></a>Linux の構成を追加してリモート コンピューターに接続する

1. Linux の構成を追加します。 **ソリューション エクスプローラー** ビューで CMakeSettings.json ファイルを右クリックし、 **[構成の追加]** を選択します。 前と同じ [構成を CMakeSettings に追加する] ダイアログが表示されます。 今度は **[Linux-Debug]** を選択してから、CMakeSettings.json ファイルを保存します (Ctrl + S)。

1. **Visual Studio 2019 バージョン 16.6 以降** CMake 設定エディターの一番下までスクロールし、 **[詳細設定の表示]** 選択します。 **[CMake ジェネレーター]** として **[Unix Makefiles]\(Unix メイクファイル\)** を選択し、CMakeSettings.json ファイルを保存します (Ctrl + S)。

1. 構成ドロップダウンで **[Linux-Debug]** を選択します。

   ![X64-Debug オプションと Linux-Debug オプションが含まれる起動構成ドロップダウン](media/cmake-bullet3-linux-configuration-item.png)

   Linux システムに初めて接続する場合は、 **[リモート システムへの接続]** ダイアログが表示されます。

   ![Visual Studio の [リモート システムへの接続] ダイアログ](media/cmake-bullet3-connection-manager.png)

   リモート接続を既に追加している場合は、 **[ツール] > [オプション] > [クロス プラットフォーム] > [接続マネージャー]** に移動して、このウィンドウを開くことができます。

1. [Linux マシンへの接続情報](../linux/connect-to-your-remote-linux-computer.md)を入力し、 **[接続]** を選択します。 Visual Studio により、そのマシンが **Linux-Debug** の既定の接続として CMakeSettings.json に追加されます。 また、リモート マシンからヘッダーが取得され、[そのリモート接続に固有の IntelliSense](../linux/configure-a-linux-project.md#remote_intellisense) を利用できます。 次に、Visual Studio によって対象ファイルがリモート マシンに送信され、リモート システム上に CMake キャッシュが生成されます。 ネットワークの速度とリモート マシンの能力によっては、これらのステップに時間がかかる場合があります。 CMake 出力ウィンドウに "ターゲット情報の抽出が完了しました" というメッセージが表示されると、完了したことがわかります。

## <a name="set-a-breakpoint-build-and-run-on-linux"></a>Linux でブレークポイントを設定し、ビルドして、実行する

これはデスクトップ アプリケーションであるため、デバッグ構成に追加の構成情報をいくつか指定する必要があります。

1. CMake ターゲット ビューで AppBasicExampleGui を右クリックし、 **[デバッグ設定と起動設定]** を選択して、非表示の **.vs** サブフォルダーにある launch.vs.json ファイルを開きます。 このファイルは、開発環境に対してローカルに存在します。 チームでファイルをチェックインおよび保存したい場合は、プロジェクトのルートにそれを移動できます。 このファイルには、AppBasicExampleGui の構成が追加されています。 これらの既定の設定は、ほとんどの場合に機能しますが、ここでは機能しません。 これはデスクトップ アプリケーションなので、Linux マシンで表示できるようにプログラムを起動するには、いくつかの情報を追加する必要があります。

1. Linux マシンで `DISPLAY` 環境変数の値を見つけるには、次のコマンドを実行します。

   ```cmd
   echo $DISPLAY
   ```

   AppBasicExampleGui の構成には、パラメーター配列 "pipeArgs" があります。 その中に、"${debuggerCommand}" という行があります。 これは、リモート マシン上で gdb を起動するコマンドです。 Visual Studio では、そのコマンドを実行する前に、このコンテキストに表示をエクスポートする必要があります。 たとえば、表示の値が `:1` の場合は、その行を次のように変更します。

   ```cmd
   "export DISPLAY=:1;${debuggerCommand}",
   ```

1. アプリケーションを起動してデバッグします。 ツール バーの **[スタートアップ アイテムの選択]** ドロップダウン を開き、 **[AppBasicExampleGui]** を選択します。 次に、ツール バーの緑色の再生アイコンを選択するか、**F5** キーを押します。 アプリケーションとその依存関係がリモート Linux マシン上でビルドされ、Visual Studio デバッガーがアタッチされた状態で起動されます。 リモート Linux マシンに、アプリケーションのウィンドウが表示されます。

1. アプリケーション ウィンドウ内にマウスを移動し、ボタンをクリックします。 ブレークポイントにヒットします。 プログラムの実行が一時停止し、Visual Studio が前面表示に戻り、ブレークポイントが表示されます。 Visual Studio には Linux コンソール ウィンドウも表示されます。 このウィンドウにはリモート Linux マシンからの出力が表示され、`stdin` に対して入力することもできます。 他の Visual Studio ウィンドウと同様に、表示したい場所にドッキングできます。 その位置は、以降のセッションで維持されます。

   ![Visual Studio の Linux コンソール ウィンドウ](media/cmake-bullet3-linux-console.png)

1. Visual Studio を使用して、アプリケーションの変数、オブジェクト、スレッド、メモリを調べたり、対話式にコードをステップ実行したりできます。 ただし今度は、ローカルの Windows 環境ではなく、リモート Linux マシンでそれをすべて行います。 ローカル実行と同じように、 **[続行]** を選択してアプリケーションを再開させてから通常どおりに終了することも、停止ボタンを選択することもできます。

1. Visual Studio では Linux 上のアプリケーションが起動されているため、[呼び出し履歴] ウィンドウを見ると、`x11OpenGLWindow` の呼び出しが表示されています。

   ![Linux の呼び出し履歴が表示されている [呼び出し履歴] ウィンドウ](media/cmake-bullet3-linux-callstack.png)

## <a name="what-you-learned"></a>学習内容

このチュートリアルでは、GitHub から直接コード ベースをクローンしました。 それを変更することなく、Windows 上でビルド、実行、およびデバッグしました。 そして、同じコード ベースを使用して、構成を少し変更し、リモート Linux マシン上でビルド、実行、デバッグを行いました。

## <a name="next-steps"></a>次の手順

Visual Studio での CMake プロジェクトの構成とデバッグについてさらに学習します。

> [!div class="nextstepaction"]
> [Visual Studio の CMake プロジェクト](cmake-projects-in-visual-studio.md)<br/><br/>
> [Linux CMake プロジェクトを構成する](../linux/cmake-linux-project.md)<br/><br/>
> [リモートの Linux コンピューターに接続する](../linux/connect-to-your-remote-linux-computer.md)<br/><br/>
> [CMake のビルド設定をカスタマイズする](customize-cmake-settings.md)<br/><br/>
> [CMake デバッグ セッションを構成する](configure-cmake-debugging-sessions.md)<br/><br/>
> [Linux プロジェクトの配置、実行、デバッグ](../linux/deploy-run-and-debug-your-linux-project.md)<br/><br/>
> [CMake 定義済み構成リファレンス](cmake-predefined-configuration-reference.md)
>
