---
title: Visual Studio で C++ クロスプラットフォーム プロジェクトを作成する
description: Linux と Windows の両方を対象とする Visual Studio で C++ オープンソース CMake プロジェクトをセットアップ、コンパイル、およびデバッグする方法。
ms.topic: tutorial
ms.date: 01/08/2020
ms.openlocfilehash: aac536f488cf22adf5aa835c9fe5b884fc5d7298
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328745"
---
# <a name="tutorial-create-c-cross-platform-projects-in-visual-studio"></a>チュートリアル: Visual Studio で C++ クロスプラットフォーム プロジェクトを作成する

Visual Studio での C と C++ の開発は、Windows だけではなくなっています。 このチュートリアルでは、Windows と Linux での Visual Studio for C++ クロス プラットフォーム開発の使用方法を示します。 これは CMake に基づいているため、Visual Studio プロジェクトを作成または生成する必要はありません。 CMakeLists.txt ファイルを含むフォルダーを開くと、自動的に IntelliSense とビルドの設定が構成されます。 Windows 上でコードの編集、ビルド、デバッグを簡単に開始できます。 次に、Visual Studio 内から、Linux で同じ操作を行うために構成を切り替えます。

このチュートリアルでは、以下の内容を学習します。

> [!div class="checklist"]
>
> * GitHub からオープンソースの CMake プロジェクトを複製する
> * Visual Studio でプロジェクトを開く
> * Windows 上で実行可能ターゲットをビルドしてデバッグする
> * Linux マシンへの接続を追加する
> * Linux 上で同じターゲットをビルドしてデバッグする

## <a name="prerequisites"></a>前提条件

* クロスプラットフォームの C++ 開発用に Visual Studio をセットアップする
  * まず[、Visual Studio をインストール](https://visualstudio.microsoft.com/vs/)し、C++ および Linux**開発と C++ ワークロードを使用したデスクトップ****開発を**選択します。 この最小インストールは 3 GB のみです。 ダウンロード速度によっては、インストールに10分以上かかる必要はありません。

* クロスプラットフォームの C++ 開発用に Linux マシンをセットアップする
  * Visual Studio に Linux の特定のディストリビューションは必要ありません。 OS は物理マシン、VM、またはクラウドで実行できます。 また、Linux 用の Windows サブシステム (WSL) を使用することもできます。 ただし、このチュートリアルでは、グラフィカルな環境が必要です。 WSL は、主にコマンド ライン操作を目的としているため、ここではお勧めしません。
  * Visual Studio では、Linux コンピューター上でこれらのツールが必要です: C++ コンパイラ、gdb、ssh、rsync、忍者、および zip。 Debian ベースのシステムでは、次のコマンドを使用してこれらの依存関係をインストールできます。

    ```cmd
    sudo apt install -y openssh-server build-essential gdb rsync ninja-build zip
    ```

  * Visual Studio では、サーバー モードが有効になっている Linux コンピューター上の最新バージョンの CMake が必要です (少なくとも 3.8)。 Microsoft が生成した CMake のユニバーサル ビルドを、任意の Linux ディストリビューションにインストールできます。 このビルドを使用して、最新の機能を使用することをお勧めします。 CMake のバイナリは、GitHub の [CMake リポジトリの Microsoft フォーク](https://github.com/Microsoft/CMake/releases)から入手できます。 そのページに移動し、Linux マシン上のシステムアーキテクチャに一致するバージョンをダウンロードし、実行可能ファイルとしてマークします。

    ```cmd
    wget <path to binary>
    chmod +x cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh
    ```

  * スクリプトを実行するためのオプションは、`-–help` で確認できます。 **/usr/bin** `–prefix`は Visual Studio が CMake を検索する既定の場所であるため **、/usr**パスでのインストールを指定するオプションを使用することをお勧めします。 次の例では Linux-x86_64 スクリプトを示します。 別のターゲット プラットフォームを使用している場合は、必要に応じて変更します。

    ```cmd
    sudo ./cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh --skip-license --prefix=/usr
    ```

* Windows マシンにインストールされている Git for Windows。
* GitHub アカウント。

## <a name="clone-an-open-source-cmake-project-from-github"></a>GitHub からオープンソースの CMake プロジェクトを複製する

このチュートリアルでは、GitHub のブレット物理 SDK を使用します。 多くのアプリケーションに衝突検出と物理シミュレーションを提供します。 SDK には、追加のコードを記述せずにコンパイルおよび実行するサンプル実行可能プログラムが含まれています。 このチュートリアルでは、ソース コードやビルド スクリプトは変更されません。 開始するには、Visual Studio がインストールされているコンピューター上の GitHub から*bullet3*リポジトリを複製します。

```cmd
git clone https://github.com/bulletphysics/bullet3.git
```

1. Visual Studio のメイン メニューで、[**ファイル] > [CMake] >開く**] を選択します。 ダウンロードした bullet3 レポのルートにある CMakeLists.txt ファイルに移動します。

    ![Visual Studio の [ファイル] > [開く] > [CMake] メニュー](media/cmake-open-cmake.png)

    フォルダを開くと、すぐにフォルダ構造が**ソリューション エクスプローラ**に表示されます。

    ![Visual Studio のソリューション エクスプローラーのフォルダー ビュー](media/cmake-bullet3-solution-explorer.png)

    このビューには、論理的なビューやフィルター処理されたビューではなく、ディスク上にあるものがそのまま表示されます。 既定では、隠しファイルは表示されません。

1. [**すべてのファイルを表示**] ボタンを選択すると、フォルダ内のすべてのファイルが表示されます。

    ![Visual Studio のソリューション エクスプローラーの [すべてのファイルを表示] ボタン](media/cmake-bullet3-show-all-files.png)

## <a name="switch-to-targets-view"></a>ターゲット ビューに切り替える

CMake を使用しているフォルダーを開くと、Visual Studio で CMake キャッシュが自動的に生成されます。 プロジェクトのサイズによっては、この操作にしばらくかかる場合があります。

1. **[出力ウィンドウ]** で **[Show output from]\(出力元\)** を選択してから、**[CMake]** を選択して、キャッシュ生成処理の状態を監視します。 操作が完了すると、"ターゲット情報の抽出が完了しました" というメッセージが表示されます。

   ![CMake からの出力が表示された Visual Studio の出力ウィンドウ](media/cmake-bullet3-output-window.png)

   この操作が完了すると、IntelliSense が構成されます。 プロジェクトをビルドし、アプリケーションをデバッグできます。 CMakeLists ファイルで指定されたターゲットに基づいて、ソリューションの論理ビューが表示されるようになりました。

1. **ソリューション エクスプローラー**の **[ソリューションおよびフォルダー]** ボタンを使用して、CMake のターゲット ビューに切り替えます。

   ![CMake のターゲット ビューを表示するためのソリューション エクスプローラーの [ソリューションおよびフォルダー] ボタン](media/cmake-bullet3-show-targets.png)

   Bullet SDK でのビューの表示は次のようになります。

   ![ソリューション エクスプローラーの CMake ターゲット ビュー](media/cmake-bullet3-targets-view.png)

   ターゲット ビューでは、このソース ベースの内容に関するさらに直感的なビューが提供されます。 一部のターゲットはライブラリで、他は実行可能ファイルであることがわかります。

1. CMake ターゲット ビューでノードを展開すると、そのソース コード ファイルが表示されます。それらのファイルがディスク上のどこにあってもかまいません。

## <a name="add-an-explicit-windows-x64-debug-configuration"></a>明示的な Windows x64-Debug 構成を追加する

Visual Studio は、Windows の既定**の x64 デバッグ**構成を作成します。 構成により、Visual Studio は CMake に使用するプラットフォーム ターゲットを認識します。 既定の構成は、ディスク上では表されません。 構成を明示的に追加すると *、CMakeSettings.json*という名前のファイルが作成されます。 指定したすべての構成の設定が設定されます。

1. 新しい構成を追加します。 ツールバーの [**コンフィグレーション**] ドロップダウンを開き、[**コンフィグレーションの管理**] を選択します。

   ![[構成の管理] ドロップダウン](media/cmake-bullet3-manage-configurations.png)

   [CMake 設定エディタ](customize-cmake-settings.md)が開きます。 エディタの左側にある緑色のプラス記号を選択して、新しい設定を追加します。 **[CMakeSettings に構成を追加]** ダイアログ ボックスが表示されます。

   ![[構成を CMakeSettings に追加する] ダイアログ](media/cmake-bullet3-add-configuration-x64-debug.png)

   このダイアログには、Visual Studio に含まれるすべての構成と、作成したカスタム構成が表示されます。 **x64-Debug**構成を引き続き使用する場合は、最初に追加する必要があります。 **[x64-Debug]** を選択し、[選択] ボタンを**クリック**します。 **X64 デバッグ**の構成を使用して CMakeSettings.json ファイルを作成し、ディスクに保存します。 CMakeSettings.json で名前パラメーター直接変更することで、構成に好きな名前を使用できます。

## <a name="set-a-breakpoint-build-and-run-on-windows"></a>Windows でのブレークポイントの設定、ビルド、および実行

このステップでは、Bullet Physics ライブラリのデモを行うサンプル プログラムをデバッグします。
  
1. **ソリューション エクスプローラー**で AppBasicExampleGui を選択して展開します。

1. ファイル `BasicExample.cpp`を開きます。

1. 実行中のアプリケーションをクリックするとヒットするブレークポイントを設定します。 クリック イベントは、ヘルパー クラスのメソッドで処理されます。 すばやく移動するには:

   1. 構造体`CommonRigidBodyBase``BasicExample`の派生元を選択します。 30行目の周りにあります。

   1. 右クリックし、**[定義へ移動]** を選択します。 これで、ヘッダーが一般的に作成されます。

   1. ソースの上にあるブラウザ ビューで、 が表示されていることを確認する`CommonRigidBodyBase`必要があります。 右側で、調べるメンバーを選択できます。 ドロップダウンを開き、ヘッダー内`mouseButtonCallback`の関数の定義に移動するを選択します。

      ![Visual Studio のメンバーの一覧ツール バー](media/cmake-bullet3-member-list-toolbar.png)

1. この関数の最初の行にブレークポイントを設定します。 アプリケーションのウィンドウ内でマウス ボタンをクリックすると、Visual Studio デバッガーで実行すると、このボタンがヒットします。

1. アプリケーションを起動するには、ツールバーの起動ドロップダウンを選択します。 これは、「スタートアップ項目を選択」と言う緑色の再生アイコンを持つものです。 ドロップダウンで、[アプリベーシックギグ.exe] を選択します。 実行可能ファイルの名前が起動ボタンに表示されます。

   ![Visual Studio ツール バーの [スタートアップ アイテムの選択] の起動ドロップダウン](media/cmake-bullet3-launch-button.png)

1. 起動ボタンを選択してアプリケーションと必要な依存関係をビルドし、Visual Studio デバッガをアタッチして起動します。 しばらくすると、実行中のアプリケーションが表示されます。

   ![Windows アプリケーションをデバッグしている Visual Studio](media/cmake-bullet3-launched.png)

1. アプリケーション ウィンドウ内にマウスを移動し、ボタンをクリックしてブレークポイントをトリガーします。 ブレークポイントを使用すると、Visual Studio がフォアグラウンドに戻り、エディターに実行が一時停止された行が表示されます。 アプリケーション変数、オブジェクト、スレッド、およびメモリを検査したり、コードを対話的にステップ実行したりできます。 [**続行]** を選択してアプリケーションを再開し、通常どおりに終了します。 または、停止ボタンを使用して、Visual Studio 内の実行を停止します。

## <a name="add-a-linux-configuration-and-connect-to-the-remote-machine"></a>Linux の構成を追加してリモート コンピューターに接続する

1. Linux の構成を追加します。 **ソリューション エクスプローラー** ビューで CMakeSettings.json ファイルを右クリックし、**[構成の追加]** を選択します。 前と同じ [構成を CMakeSettings に追加する] ダイアログが表示されます。 [今回**は Linux デバッグ**] を選択し、CMakeSettings.json ファイル (ctrl + s) を保存します。

1. 構成ドロップダウンで**Linux デバッグ**を選択します。

   ![X64-Debug オプションと Linux-Debug オプションが含まれる起動構成ドロップダウン](media/cmake-bullet3-linux-configuration-item.png)

   初めて Linux システムに接続する場合は、[**リモート システムに接続**] ダイアログボックスが表示されます。

   ![Visual Studio の [リモート システムへの接続] ダイアログ](media/cmake-bullet3-connection-manager.png)

   リモート接続を既に追加している場合は、[**ツール] > オプション >クロス プラットフォーム>接続マネージャ**に移動して、このウィンドウを開くことができます。

1. Linux[マシンへの接続情報を](/cpp/linux/connect-to-your-remote-linux-computer)入力し、[**接続**] を選択します。 そのマシンを**Linux デバッグ**の既定の接続として CMakeSettings.json に追加します。 また、リモート マシンからヘッダーをプルするので、[そのリモート接続に固有の IntelliSense](/cpp/linux/configure-a-linux-project?view=vs-2019#remote_intellisense)を取得します。 次に、Visual Studio は、リモート コンピューターにファイルを送信し、リモート システム上の CMake キャッシュを生成します。 これらの手順は、ネットワークの速度とリモート コンピュータの電源に応じて、時間がかかる場合があります。 CMake 出力ウィンドウに 「ターゲット情報の抽出が完了しました」というメッセージが表示されたら、それが完了したことを知ることができます。

## <a name="set-a-breakpoint-build-and-run-on-linux"></a>Linux でのブレークポイントの設定、ビルド、実行

デスクトップ アプリケーションであるため、デバッグ構成に追加の構成情報を提供する必要があります。

1. CMake ターゲット ビューで、AppBasicExampleGui を右クリックし、[**デバッグと起動の設定]** を選択して、非表示の **.vs.vs**サブフォルダーにある launch.vs.json ファイルを開きます。 このファイルは、開発環境に対してローカルに存在します。 チームでファイルをチェックインおよび保存したい場合は、プロジェクトのルートにそれを移動できます。 このファイルには、構成が追加されました。 これらの既定の設定は、ほとんどの場合、機能しますが、ここでは機能しません。 デスクトップアプリケーションなので、Linuxマシンで見ることができるように、プログラムを起動するための追加情報を提供する必要があります。

1. ご使用の Linux マシンで`DISPLAY`環境変数の値を検索するには、次のコマンドを実行します。

   ```cmd
   echo $DISPLAY
   ```

   構成では、パラメーター配列 "パイプ引数" があります。 これには、"${デバッガーコマンド}" という行が含まれています。 これは、リモートマシンで gdb を起動するコマンドです。 Visual Studio は、このコンテキストに表示をエクスポートしてから、コマンドを実行する必要があります。 たとえば、ディスプレイの値が の場合は`:1`、次のようにその行を変更します。

   ```cmd
   "export DISPLAY=:1;${debuggerCommand}",
   ```

1. アプリケーションを起動してデバッグします。 ツール バーの **[スタートアップ項目の選択**] ドロップダウンを開き **、[AppBasicExampleGui]** を選択します。 次に、ツールバーの緑色の再生アイコンを選択するか **、F5**キーを押します。 アプリケーションとその依存関係は、リモートの Linux マシン上に構築され、Visual Studio デバッガーがアタッチされた状態で起動されます。 リモート Linux マシンに、アプリケーションのウィンドウが表示されます。

1. マウスをアプリケーション ウィンドウに移動し、ボタンをクリックします。 ブレークポイントにヒットします。 プログラムの実行が一時停止すると、Visual Studio がフォアグラウンドに戻り、ブレークポイントが表示されます。 Visual Studio には Linux コンソール ウィンドウも表示されます。 このウィンドウはリモート Linux マシンからの出力を提供し、入力を`stdin`受け入れることもできます。 他の Visual Studio ウィンドウと同様に、表示する場所にドッキングできます。 その位置は、将来のセッションで保持されます。

   ![Visual Studio の Linux コンソール ウィンドウ](media/cmake-bullet3-linux-console.png)

1. Visual Studio を使用して、アプリケーションの変数、オブジェクト、スレッド、メモリを調べたり、対話式にコードをステップ実行したりできます。 しかし今回は、ローカルのWindows環境ではなく、リモートのLinuxマシンですべてを行っています。 [**続行]** を選択して、アプリケーションを再開して正常に終了するか、ローカル実行と同様に停止ボタンを選択できます。

1. Visual Studio では Linux 上のアプリケーションが起動されているため、[呼び出し履歴] ウィンドウを見ると、`x11OpenGLWindow` の呼び出しが表示されています。

   ![Linux の呼び出し履歴が表示されている [呼び出し履歴] ウィンドウ](media/cmake-bullet3-linux-callstack.png)

## <a name="what-you-learned"></a>学習内容

このチュートリアルでは、GitHub から直接コード ベースを複製しました。 Windows でビルド、実行、およびデバッグを行いました。 次に、同じコード ベースを使用して、構成の変更を小さな変更を加え、リモート Linux マシンでビルド、実行、およびデバッグを行いました。

## <a name="next-steps"></a>次のステップ

Visual Studio での CMake プロジェクトの構成とデバッグについてさらに学習します。

> [!div class="nextstepaction"]
> [C メイク プロジェクトのビジュアル スタジオ](cmake-projects-in-visual-studio.md)<br/><br/>
> [Linux CMake プロジェクトを構成する](../linux/cmake-linux-project.md)<br/><br/>
> [リモートの Linux コンピューターに接続する](../linux/connect-to-your-remote-linux-computer.md)<br/><br/>
> [CMake のビルド設定をカスタマイズする](customize-cmake-settings.md)<br/><br/>
> [CMake デバッグ セッションを構成する](configure-cmake-debugging-sessions.md)<br/><br/>
> [Linux プロジェクトの配置、実行、デバッグ](../linux/deploy-run-and-debug-your-linux-project.md)<br/><br/>
> [CMake 定義済み構成リファレンス](cmake-predefined-configuration-reference.md)
>
