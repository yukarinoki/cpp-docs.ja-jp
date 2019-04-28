---
title: Visual Studio で C++ クロスプラットフォーム プロジェクトを作成する
description: このチュートリアルでは、Linux と Windows の両方を対象とする C++ のオープンソース CMake プロジェクトを Visual Studio でセットアップ、コンパイル、およびデバッグする方法を示します。
author: mikeblome
ms.topic: tutorial
ms.date: 03/05/2019
ms.openlocfilehash: deb2c91d6d09d8945e5eb57a7ac742c5b1705e83
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196437"
---
# <a name="tutorial-create-c-cross-platform-projects-in-visual-studio"></a>チュートリアル: Visual Studio で C++ クロスプラットフォーム プロジェクトを作成する 

Visual Studio での C と C++ の開発は、Windows だけではなくなっています。 このチュートリアルでは、Visual Studio プロジェクトを作成または生成する必要がない、CMake に基づく C++ のクロスプラットフォーム開発に、Visual Studio を使用する方法を示します。 CMakeLists.txt ファイルが含まれるフォルダーを開くと、Visual Studio によって IntelliSense とビルド設定が自動的に構成されます。 Windows 上のローカル環境でコードを素早く編集、ビルド、デバッグした後、構成を切り替えて Linux 上で同じことを行うという一連の作業をすべて、Visual Studio 内から実行できます。

このチュートリアルでは、次の作業を行う方法について説明します。

> [!div class="checklist"]
> * GitHub からオープンソースの CMake プロジェクトを複製する
> * Visual Studio でプロジェクトを開く 
> * Windows 上で実行可能ターゲットをビルドしてデバッグする
> * Linux マシンへの接続を追加する
> * Linux 上で同じターゲットをビルドしてデバッグする

## <a name="prerequisites"></a>必須コンポーネント

- クロスプラットフォームの C++ 開発用に Visual Studio をセットアップする
    - 最初に、[Visual Studio をインストールする](https://visualstudio.microsoft.com/vs/)必要があります。 次に、**C++ によるデスクトップ開発**ワークロードと **C++ による Linux 開発**ワークロードがインストールされていることを確認します。 この最小限のインストールはわずか 3 GB で、ダウンロードの速さにもよりますが、インストールに 10 分以上はかからないはずです。
- クロスプラットフォームの C++ 開発用に Linux マシンをセットアップする
    - Visual Studio に Linux の特定のディストリビューションは必要ありません。 物理マシン、VM、クラウド、または Windows Subsystem for Linux (WSL) で、OS を実行できます。 ただし、このチュートリアルではグラフィカル環境が必要であるため、主にコマンド ライン操作用の WSL はお勧めできません。
    - Linux マシン上で Visual Studio に必要なツールは次のとおりです。C++ コンパイラ、GDB、ssh、zip。 Debian ベースのシステムでは、次のようにしてこれらの依存関係をインストールできます。
    
    ```cmd
        sudo apt install -y openssh-server build-essential gdb zip
    ```
    - Visual Studio では、サーバー モードが有効になっている最近のバージョンの CMake (少なくとも 3.8) が Linux マシンに存在する必要があります。 Microsoft が生成した CMake のユニバーサル ビルドを、任意の Linux ディストリビューションにインストールできます。 最新の機能を利用するには、このビルドを使うことをお勧めします。 CMake のバイナリは、GitHub の [CMake リポジトリの Microsoft フォーク](https://github.com/Microsoft/CMake/releases)から入手できます。 そのページに移動し、Linux マシンのシステム アーキテクチャと一致するバージョンをダウンロードして、それを実行可能にします。
    
    ```cmd
        wget <path to binary>
        chmod +x cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh
    ```
    - スクリプトを実行するためのオプションは、`-–help` で確認できます。 `–prefix` オプションを使用して、**/usr/local** パスへのインストールを指定することをお勧めします。これが、Visual Studio での CMake の既定の参照場所です。 次の例では Linux-x86_64 スクリプトを示します。 別のターゲット プラットフォームを使用している場合は、必要に応じて変更してください。 
    
    ```cmd
        sudo ./cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh --skip-license --prefix=/usr/local
    ```
- Windows マシンにインストールされている Git for Windows。
- GitHub アカウント。

## <a name="clone-an-open-source-cmake-project-from-github"></a>GitHub からオープンソースの CMake プロジェクトを複製する

このチュートリアルでは、GitHub の Bullet Physics SDK を使用します。この SDK では、さまざまなアプリケーション用に、衝突の検出および物理現象のシミュレーションが提供されています。 それには、コードを追加しなくてもコンパイルして実行できるサンプルの実行可能プログラムが含まれます。 このチュートリアルでは、ソース コードまたはスクリプトを変更することはありません。 始めるには、GitHub から Visual Studio がインストールされているマシンに、bullet3 リポジトリを複製します。 

```cmd

git clone https://github.com/bulletphysics/bullet3.git

```

1. Visual Studio のメイン メニューから **[ファイル] > [開く] > [CMake]** を選択し、ダウンロードした bullet3 リポジトリのルート内の CMakeLists.txt ファイルに移動します。

    ![Visual Studio の [ファイル] > [開く] > [CMake] メニュー](media/cmake-open-cmake.png)

    フォルダーを開くとすぐに、フォルダー構造が**ソリューション エクスプローラー**に表示されます。

    ![Visual Studio のソリューション エクスプローラーのフォルダー ビュー](media/cmake-bullet3-solution-explorer.png)

    このビューには、論理的なビューやフィルター処理されたビューではなく、ディスク上にあるものがそのまま表示されます。 既定では、隠しファイルは表示されません。 

2. フォルダー内のすべてのファイルを表示するには、**[すべてのファイルを表示]** ボタンをクリックします。

    ![Visual Studio のソリューション エクスプローラーの [すべてのファイルを表示] ボタン](media/cmake-bullet3-show-all-files.png)

## <a name="switch-to-targets-view"></a>ターゲット ビューに切り替える

CMake を使用しているフォルダーを開くと、Visual Studio で CMake キャッシュが自動的に生成されます。 プロジェクトのサイズによっては、この操作にしばらくかかる場合があります。 

1. **[出力ウィンドウ]** で **[Show output from]\(出力元\)** を選択してから、**[CMake]** を選択して、キャッシュ生成処理の状態を監視します。 操作が完了すると、"ターゲット情報の抽出が完了しました" というメッセージが表示されます。

    ![CMake からの出力が表示された Visual Studio の出力ウィンドウ](media/cmake-bullet3-output-window.png)

    この操作が完了した後、IntelliSense が構成されて、プロジェクトをビルドし、アプリケーションをデバッグできるようになります。 Visual Studio では、CMakeLists ファイルで指定されているターゲットに基づいてソリューションの論理ビューを提供できるようになります。 

2. **ソリューション エクスプローラー**の **[ソリューションおよびフォルダー]** ボタンを使用して、CMake のターゲット ビューに切り替えます。

    ![CMake のターゲット ビューを表示するためのソリューション エクスプローラーの [ソリューションおよびフォルダー] ボタン](media/cmake-bullet3-show-targets.png)

    Bullet SDK でのビューの表示は次のようになります。

    ![ソリューション エクスプローラーの CMake ターゲット ビュー](media/cmake-bullet3-targets-view.png)

    ターゲット ビューでは、このソース ベースの内容に関するさらに直感的なビューが提供されます。 一部のターゲットはライブラリで、他は実行可能ファイルであることがわかります。 

3. CMake ターゲット ビューでノードを展開すると、そのソース コード ファイルが表示されます。それらのファイルがディスク上のどこにあってもかまいません。

## <a name="set-a-breakpoint-build-and-run"></a>ブレークポイントを設定し、ビルドして、実行する

このステップでは、Bullet Physics ライブラリのデモを行うサンプル プログラムをデバッグします。
  
1. **ソリューション エクスプローラー**で AppBasicExampleGui を選択して展開します。 
1. `BasicExample.cpp` ファイルを開きます。 
1. 実行中のアプリケーションをクリックするとヒットするブレークポイントを設定します。 クリック イベントは、ヘルパー クラスのメソッドで処理されます。 すばやく移動するには:

    1. 30 行目あたりの構造体 `BasicExample` が派生している `CommonRigidBodyBase` を選択します。
    1. 右クリックし、**[定義へ移動]** を選択します。 これで、ヘッダー CommonRigidBodyBase.h 内にいます。 
    1. 上のブラウザー ビューでは、表示されているソースで `CommonRigidBodyBase` 内にいることがわかります。 右側で、調べるメンバーを選択できます。 ドロップダウンをクリックし、`mouseButtonCallback` を選択して、ヘッダー内でその関数の定義に移動します。

        ![Visual Studio のメンバーの一覧ツール バー](media/cmake-bullet3-member-list-toolbar.png)

1. この関数の最初の行にブレークポイントを設定します。 これにより、Visual Studio デバッガーで起動して、アプリケーションのウィンドウ内でマウス ボタンをクリックするとヒットします。

1. アプリケーションを起動するには、ツール バーの [スタートアップ アイテムの選択] と表示されている再生アイコンで起動ドロップダウンを選択します。 ドロップダウンで AppBasicExampleGui.exe を選択します。 実行可能ファイルの名前が起動ボタンに表示されます。

    ![Visual Studio ツール バーの [スタートアップ アイテムの選択] の起動ドロップダウン](media/cmake-bullet3-launch-button.png)

5.  起動ボタンをクリックしてアプリケーションと必要な依存関係をビルドし、アタッチされている Visual Studio デバッガーで起動します。 しばらくすると、実行中のアプリケーションが表示されます。

    ![Windows アプリケーションをデバッグしている Visual Studio](media/cmake-bullet3-launched.png)

6. アプリケーション ウィンドウ内にマウスを移動し、ボタンをクリックしてブレークポイントをトリガーします。 これにより、Visual Studio が再び前面に表示され、実行が一時停止している行がエディターで示されます。 アプリケーションの変数、オブジェクト、スレッド、メモリを調べることができます。 対話形式で、コードをステップ実行することができます。 **[続行]** をクリックしてアプリケーションを再開し通常どおりに終了したり、停止ボタンを使用して Visual Studio 内で実行を終了させたりできます。

## <a name="add-an-explicit-windows-x64-debug-configuration"></a>明示的な Windows x64-Debug 構成を追加する

ここまでは、Windows 用の既定の **x64-Debug** 構成を使用してきました。 構成により、Visual Studio は CMake に使用するプラットフォーム ターゲットを認識します。 既定の構成は、ディスク上では表されません。 構成を明示的に追加すると、Visual Studio で CMakeSettings.json という名前のファイルが作成されて、指定したすべての構成が設定されます。 

1. ツール バーの [構成] ドロップダウンをクリックして **[構成の管理...]** を選択することで、新しい構成を追加します

    ![[構成の管理] ドロップダウン](media/cmake-bullet3-manage-configurations.png)

    **[構成を CMakeSettings に追加する]** ダイアログが表示されます。

    ![[構成を CMakeSettings に追加する] ダイアログ](media/cmake-bullet3-add-configuration-x64-debug.png)

    このダイアログには、Visual Studio に含まれるすべての構成と、ユーザーが作成したカスタム構成が表示されます。 既定の **x64-Debug** 構成を引き続き使用したい場合は、それを最初に追加する必要があります。 その構成を追加することにより、Windows と Linux の構成をどちらにでも切り替えることができます。 **x64-Debug** を選択して、**[選択]** をクリックします。 これにより、**x64-Debug** 用の構成を含む CMakeSettings.json ファイルが作成されて、Visual Studio は既定ではなくその構成を使用するように切り替わります。 構成ドロップダウンの名前の一部として [(既定)] と表示されなくなります。 CMakeSettings.json で名前パラメーター直接変更することで、構成に好きな名前を使用できます。

##  <a name="add-a-linux-configuration-and-connect-to-the-remote-machine"></a>Linux の構成を追加してリモート コンピューターに接続する

1. 次に、Linux の構成を追加します。 **ソリューション エクスプローラー** ビューで CMakeSettings.json ファイルを右クリックし、**[構成の追加]** を選択します。 前と同じ [構成を CMakeSettings に追加する] ダイアログが表示されます。 今度は **Linux-Debug** を選択してから、CMakeSettings.json ファイルを保存します。 
2. 構成ドロップダウンで **Linux-Debug** を選択します。

    ![X64-Debug オプションと Linux-Debug オプションが含まれる起動構成ドロップダウン](media/cmake-bullet3-linux-configuration-item.png)

    Linux システムに初めて接続する場合は、**[リモート システムへの接続]** ダイアログが表示されます。

    ![Visual Studio の [リモート システムへの接続] ダイアログ](media/cmake-bullet3-connection-manager.png)

    リモート接続を既に追加している場合は、**[ツール] > [オプション] > [クロス プラットフォーム] > [接続マネージャー]** に移動して、このウィンドウを開くことができます。
 
3. Linux マシンへの接続情報を入力し、**[接続]** をクリックします。 **Linux-Debug** に対する既定値として、CMakeSettings.json にそのマシンが追加されます。 また、リモート マシンからヘッダーも取得され、そのマシン固有の IntelliSense が表示されます。 Visual Studio は、リモート マシンにファイルを送信した後、CMake キャッシュを生成し、それが完了すると、リモート Linux マシンと同じソース ベースを使用するように構成されます。 ネットワークの速度とリモート マシンの能力によっては、これらの処理に時間がかかる場合があります。 CMake 出力ウィンドウに "ターゲット情報の抽出が完了しました" というメッセージが表示されると、完了したことがわかります。

## <a name="set-a-breakpoint-build-and-run-on-linux"></a>Linux でブレークポイントを設定し、ビルドして、実行する

これはデスクトップ アプリケーションであるため、デバッグ構成に追加の構成情報をいくつか提供する必要があります。 

1. CMake ターゲット ビューで AppBasicExampleGui を右クリックし、**[デバッグ設定と起動設定]** を選択して、非表示の **.vs** サブフォルダーにある launch.vs.json ファイルを開きます。 このファイルは、開発環境に対してローカルに存在します。 チームでファイルをチェックインおよび保存したい場合は、プロジェクトのルートにそれを移動できます。 このファイルには、AppBasicExampleGui の構成が追加されています。 これらの既定の設定はほとんどの場合に機能しますが、これはデスクトップ アプリケーションなので、Linux マシンで表示できる方法でプログラムを起動するには、いくつかの情報を追加する必要があるます。 
2. Linux マシンでの `DISPLAY` 環境変数の値を知る必要があります。それを取得するには、次のコマンドを実行します。

    ```cmd
    echo $DISPLAY
    ```

    AppBasicExampleGui の構成には、パラメーター配列 "pipeArgs" があります。 その中に、"${debuggerCommand}" という行があります。 これは、リモート マシン上で gdb を起動するコマンドです。 Visual Studio では、そのコマンドを実行する前に、このコンテキストに表示をエクスポートする必要があります。 たとえば、表示の値が :1 の場合は、その行を次のように変更します。

    ```cmd
    "export DISPLAY=:1;${debuggerCommand}",
    ```
3. アプリケーションを起動してデバッグするには、ツール バーの **[スタートアップ アイテムの選択]** ドロップダウンを選択し、AppBasicExampleGui を選択します。 そのボタンをクリックするか、**F5** キーを押します。 これにより、リモート Linux マシン上でアプリケーションとその依存関係がビルドされ、アタッチされている Visual Studio デバッガーで起動されます。 リモート Linux マシンに、アプリケーションのウィンドウが表示されます。

4. アプリケーション ウィンドウ内にマウスを移動してボタンをクリックすると、ブレークポイントがヒットします。 ブレークポイントの位置でプログラムの実行が一時停止し、Visual Studio が前面に表示されます。 Visual Studio には Linux コンソール ウィンドウも表示されます。 このウィンドウにはリモート Linux マシンからの出力が表示され、`stdin` に対して入力することもできます。 他の Visual Studio ウィンドウと同様に、表示したい場所にドッキングでき、後のセッションでもその位置は維持されます。

    ![Visual Studio の Linux コンソール ウィンドウ](media/cmake-bullet3-linux-console.png)

5. Visual Studio を使用して、アプリケーションの変数、オブジェクト、スレッド、メモリを調べたり、対話式にコードをステップ実行したりできます。 ただし今度は、このすべては、ローカルの Windows 環境ではなく、リモート Linux マシンで行われています。 **[続行]** をクリックしてアプリケーションを再開し通常どおりに終了したり、ローカル実行と同じように停止ボタンをクリックしたりできます。

6. Visual Studio では Linux 上のアプリケーションが起動されているため、[呼び出し履歴] ウィンドウを見ると、`x11OpenGLWindow` の呼び出しが表示されています。

    ![Linux の呼び出し履歴が表示されている [呼び出し履歴] ウィンドウ](media/cmake-bullet3-linux-callstack.png)

## <a name="what-you-learned"></a>学習内容 

このチュートリアルでは、GitHub から直接複製されたコード ベースを確認し、何も変更しないで、Windows 上でビルド、実行、デバッグを行いました。 この同じコード ベースで、構成を少し変更し、リモート Linux マシン上でビルド、実行、デバッグを行いました。 

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
