---
title: Visual Studio での C++ クロス プラットフォーム プロジェクトを作成します。
description: このチュートリアルでは、セットアップ、コンパイル、および Linux と Windows の両方を対象とする Visual Studio で C++ オープン ソースの CMake プロジェクトをデバッグする方法を示します。
author: mikeblome
ms.topic: tutorial
ms.date: 03/05/2019
ms.openlocfilehash: deb2c91d6d09d8945e5eb57a7ac742c5b1705e83
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826380"
---
# <a name="tutorial-create-c-cross-platform-projects-in-visual-studio"></a>チュートリアル: Visual Studio での C++ クロス プラットフォーム プロジェクトを作成します。 

Visual Studio C および C++ の開発は、単に Windows できなくなります。 このチュートリアルでは、C++ クロス プラットフォーム開発の作成または Visual Studio プロジェクトを生成しなくても、CMake に基づいて Visual Studio を使用する方法を示します。 Visual Studio が IntelliSense およびビルド設定を構成する CMakeLists.txt ファイルが含まれるフォルダーを開くときに自動的にします。 編集、構築、および Windows では、ローカルにコードのデバッグをする素早く切り替えて、Visual Studio 内からすべては linux では、同じように構成します。

このチュートリアルでは、次の作業を行う方法について説明します。

> [!div class="checklist"]
> * GitHub からのオープン ソース CMake プロジェクトを複製します。
> * Visual Studio でプロジェクトを開きます 
> * ビルドし、デバッグの Windows で実行可能ファイルのターゲット
> * Linux マシンに接続を追加します。
> * ビルドし、Linux 上の同じターゲットのデバッグ

## <a name="prerequisites"></a>必須コンポーネント

- クロス プラットフォームの C++ 開発用の Visual Studio のセットアップします。
    - させる必要がありますまず[Visual Studio がインストールされている](https://visualstudio.microsoft.com/vs/)します。 次に、いることを確認して、 **C++ によるデスクトップ開発**と**C++ ワークロードによる Linux 開発**をインストールします。 この最小限のインストールは 3 GB だけで、速度のインストール、ダウンロードによって 10 分以上を実行しないでください。
- クロス プラットフォームの C++ 開発用の Linux マシンの設定します。
    - Visual Studio では、Linux の特定の配布を必要としません。 OS は、for Linux (WSL)、VM、クラウド、または Windows サブシステムでの物理マシンで実行することができます。 ただし、このチュートリアルでは、グラフィカルな環境が必要です。そのため WSL は、主にコマンドライン操作に必要なのでお勧めしません。
    - Linux マシンで Visual Studio が必要とするツールは次のとおりです。C++ コンパイラ、GDB、ssh、および zip です。 Debian ベースのシステムでは、次のように、これらの依存関係をインストールできます。
    
    ```cmd
        sudo apt install -y openssh-server build-essential gdb zip
    ```
    - Visual Studio では、Linux マシンに最新バージョンの CMake サーバー モードが有効になっている (少なくとも 3.8) になっている必要があります。 Microsoft では、すべての Linux ディストリビューションをインストールすることができます CMake のユニバーサル ビルドを生成します。 このビルドを使用して、最新の機能があることを確認することをお勧めします。 CMake バイナリを取得できます[、Microsoft リポジトリのフォーク、CMake](https://github.com/Microsoft/CMake/releases) GitHub でします。 そのページに移動し、Linux コンピューターに、システムのアーキテクチャと一致し、実行可能ファイルとしてマークするバージョンをダウンロードします。
    
    ```cmd
        wget <path to binary>
        chmod +x cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh
    ```
    - スクリプトを実行するためのオプションが表示できる`-–help`します。 使用することをお勧め、`–prefix`オプションでインストールを指定する場合、 **usr/ローカル**パス CMake の Visual Studio では、既定の場所であるためです。 次の例では、Linux x86_64 スクリプトを示します。 別のターゲット プラットフォームを使用している場合、必要に応じて変更します。 
    
    ```cmd
        sudo ./cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh --skip-license --prefix=/usr/local
    ```
- Git for windows、Windows コンピューターにインストールされています。
- GitHub アカウント。

## <a name="clone-an-open-source-cmake-project-from-github"></a>GitHub からのオープン ソース CMake プロジェクトを複製します。

このチュートリアルでは、github のさまざまなアプリケーションの競合の検出および物理学のシミュレーションを提供する箇条書き物理学の SDK を使用します。 サンプルの実行可能プログラム コンパイルして、追加のコードを記述することがなく実行にはが含まれています。 このチュートリアルは、任意のソース コードを変更またはスクリプトを作成しません。 開始するには Visual Studio をインストールする必要があるコンピューターの GitHub から、bullet3 リポジトリを複製します。 

```cmd

git clone https://github.com/bulletphysics/bullet3.git

```

1. Visual Studio のメイン メニューから選択**ファイル > オープン > CMake**ダウンロードした bullet3 リポジトリのルート内の CMakeLists.txt ファイルに移動します。

    ![ファイルの visual Studio メニュー > オープン > CMake](media/cmake-open-cmake.png)

    フォルダー構造が表示されます、フォルダーを開くとすぐに、**ソリューション エクスプ ローラー**します。

    ![Visual Studio ソリューション エクスプ ローラーのフォルダー ビュー](media/cmake-bullet3-solution-explorer.png)

    このビューには、論理的またはフィルター選択されたビューではなく、ディスクにあるものだけが表示されます。 既定では、隠しファイルは表示されません。 

2. キーを押して、**ファイルをすべて表示**フォルダー内のすべてのファイルを表示するボタンをクリックします。

    ![Visual Studio ソリューション エクスプ ローラーを表示するすべてのファイル](media/cmake-bullet3-show-all-files.png)

## <a name="switch-to-targets-view"></a>ターゲット ビューに切り替える

CMake を使用しているフォルダーを開くと、Visual Studio で CMake キャッシュが自動的に生成されます。 この操作は、プロジェクトのサイズによってはわずかな時間をかかる場合があります。 

1. **出力ウィンドウ**を選択します**から出力の表示**選び、 **CMake**キャッシュの生成処理の状態を監視します。 操作が完了したら、「ターゲット情報の抽出が完了しました」というメッセージします。

    ![Visual Studio の出力ウィンドウが CMake から出力を表示](media/cmake-bullet3-output-window.png)

    この操作の完了後は、IntelliSense が構成されているし、プロジェクトをビルド、アプリケーションをデバッグすることができます。 Visual Studio では、Cmakelist ファイルで指定されたターゲットに基づいているソリューションの論理ビューを提供できるようになりました。 

2. 使用して、**ソリューションおよびフォルダー**ボタン、**ソリューション エクスプ ローラー** CMake ターゲット ビューに切り替えます。

    ![CMake を表示するソリューション エクスプ ローラーでソリューションおよびフォルダー ボタンのターゲット ビュー](media/cmake-bullet3-show-targets.png)

    どのような箇条書き sdk のようになりますビューを次に示します。

    ![ソリューション エクスプ ローラーの CMake ターゲット ビュー](media/cmake-bullet3-targets-view.png)

    ターゲット ビューは、このソース ベースでのより直感的なビューを提供します。 いくつかのターゲットは、ライブラリ、その他実行可能ファイルを確認できます。 

3. これらのファイルがディスク上にある可能性がある任意の場所をそのソース コード ファイルを表示する CMake ターゲット ビュー内のノードを展開します。

## <a name="set-a-breakpoint-build-and-run"></a>ブレークポイント、ビルド、および実行を設定します。

この手順でを物理運動の行頭文字ライブラリを示すサンプル プログラムをデバッグします。
  
1. **ソリューション エクスプ ローラー**AppBasicExampleGui を選び、展開します。 
1. ファイルを開く`BasicExample.cpp`します。 
1. 実行中のアプリケーションをクリックするとヒットするブレークポイントを設定します。 クリック イベントは、ヘルパー クラスのメソッドで処理されます。 迅速に取得するがあります。

    1. 選択`CommonRigidBodyBase`を構造体`BasicExample`30 の行の付近から派生します。
    1. 右クリックし、**定義へ移動**します。 ヘッダー CommonRigidBodyBase.h するようになりました。 
    1. ソース上のブラウザー ビューであることを確認する必要があります、`CommonRigidBodyBase`します。 右側には、メンバーを確認するを選択できます。 ドロップダウン リストをクリックし、`mouseButtonCallback`ヘッダーには、その関数の定義に移動します。

        ![Visual Studio のメンバー リスト ツールバー](media/cmake-bullet3-member-list-toolbar.png)

1. この関数内で最初の行にブレークポイントを設定します。 これは、Visual Studio デバッガーで起動すると、アプリケーションのウィンドウ内でマウス ボタンをクリックするとヒットされます。

1. アプリケーションを起動するには、起動時に、再生アイコンがツールバーの「スタートアップ アイテムの選択」を示すドロップダウンを選択します。 でドロップダウンの選択 AppBasicExampleGui.exe します。 実行可能ファイル名は、今すぐ起動ボタンで表示されます。

    ![Visual Studio のツールバーの起動のスタートアップ項目の選択のドロップダウン](media/cmake-bullet3-launch-button.png)

5.  アプリケーションと必要な依存関係を構築する [起動] をクリックし、付属の Visual Studio デバッガーで起動します。 しばらくすると、実行中のアプリケーションが表示されます。

    ![Visual Studio の Windows アプリケーションのデバッグ](media/cmake-bullet3-launched.png)

6. アプリケーション ウィンドウに、マウスを移動し、ブレークポイントをトリガーするボタンをクリックします。 実行が一時停止している行を表示するエディターを使用して、フォア グラウンドに Visual Studio が表示されます。 アプリケーション変数、オブジェクト、スレッド、およびメモリを検査することができます。 対話形式で、コードをステップすることができます。 クリックすることができます**続行**アプリケーションを再開しが通常どおりに終了または停止 ボタンを使用して Visual Studio 内で実行を終了します。

## <a name="add-an-explicit-windows-x64-debug-configuration"></a>明示的な Windows x64 デバッグ構成を追加します。

ここまでは、使用している既定の**x64 デバッグ**Windows を構成します。 構成は、Visual Studio がどのようなプラットフォームを認識する方法をターゲットが CMake を使用するとなります。 既定の構成は、ディスク上で表されていません。 構成を明示的に追加すると、Visual Studio を指定するすべての構成設定で設定される CMakeSettings.json をという名前のファイルを作成します。 

1. クリックして新しい構成を追加、構成、ツールバーのドロップダウンを選択**構成を管理しています.**

    ![ドロップダウン リストの構成を管理します。](media/cmake-bullet3-manage-configurations.png)

    **CMakeSettings に構成を追加**ダイアログが表示されます。

    ![CMakeSettings ダイアログ ボックスに構成を追加します。](media/cmake-bullet3-add-configuration-x64-debug.png)

    このダイアログには、作成するカスタムの構成と同様に、Visual Studio に含まれているすべての構成が表示されます。 既定値を使用する継続を希望する場合**x64 デバッグ**に構成された 1 つ目を追加する必要があります。 その構成を追加すると、構成の Windows と Linux 間を行き来切り替えことができます。 選択**x64 デバッグ** をクリック**選択**します。 構成を持つ CMakeSettings.json ファイルが作成されます**x64 デバッグ**して、既定ではなく、その構成を使用する Visual Studio に切り替えます。 構成ドロップダウンが不要になった「(既定値)」をという名前の一部として表示されます。 Name パラメーター CMakeSettings.json で直接変更することで、構成の好きな名前を使用できます。

##  <a name="add-a-linux-configuration-and-connect-to-the-remote-machine"></a>Linux の構成を追加し、リモート コンピューターに接続

1. Linux の構成を追加します。 CMakeSettings.json ファイルを右クリックし、**ソリューション エクスプ ローラー**表示および選択**構成の追加**します。 同じ追加の構成する前として CMakeSettings ダイアログを参照してください。 選択**Linux デバッグ**CMakeSettings.json ファイルを保存し、この時間。 
2. 今すぐ選択**Linux デバッグ**構成ドロップダウンします。

    ![X64 デバッグと、Linux デバッグ オプションのドロップダウン リストの構成を起動します。](media/cmake-bullet3-linux-configuration-item.png)

    これは、初めての Linux システムに接続している場合、**リモート システムへの接続**ダイアログが表示されます。

    ![Visual Studio はリモート システム ダイアログに接続](media/cmake-bullet3-connection-manager.png)

    リモート接続を既に追加している場合に移動して、このウィンドウを開くことができます**ツール > オプション > クロス プラットフォーム > 接続マネージャー**します。
 
3. Linux マシンへの接続情報を入力し、クリックして**Connect**します。 Visual Studio の既定値として CMakeSettings.json に関しては、そのマシンを追加します**Linux デバッグ**します。 取得するため IntelliSense 特定そのマシンに使用すると、リモート コンピューターからヘッダーをダウンもプルされます。 Visual Studio はリモートのコンピューターにファイルを送信後、CMake キャッシュを生成し、それが完了したら、Visual Studio がリモート Linux コンピューターを同じソースを使用するため構成されます。 次の手順では、によって、ネットワークの速度と、リモート コンピューターの電源は、時間をかかる場合があります。 CMake の [出力] ウィンドウで「ターゲット情報の抽出が完了しました」というメッセージが表示されたら、この確認が完了することがわかります。

## <a name="set-a-breakpoint-build-and-run-on-linux"></a>ブレークポイントを設定、ビルド、および Linux で実行

これは、デスクトップ アプリケーションであるために、デバッグ構成に追加の構成情報を提供する必要があります。 

1. CMake ターゲット ビューで AppBasicExampleGui を右クリックし、選択**デバッグ設定と起動設定**launch.vs.json ファイルが非表示を開く **.vs**サブフォルダーです。 このファイルは、ローカル開発環境にします。 チームで保存し、確認する場合、プロジェクトのルートにそれを移動できます。 このファイル AppBasicExampleGui の構成が追加されました。 ほとんどの場合、これらの既定の設定が機能が、この方法でプログラムを起動するいくつかの追加情報を提供する必要があるデスクトップ アプリケーションであるため、Linux マシンで表示できます。 
2. 環境変数の値を把握する必要がある`DISPLAY`Linux コンピューターにそれを取得するには、このコマンドを実行します。

    ```cmd
    echo $DISPLAY
    ```

    AppBasicExampleGui の構成では、パラメーター配列"pipeArgs"があります。 そこでは、「${debuggerCommand}」です。 これは、リモート コンピューター上の gdb を起動するコマンドです。 Visual Studio では、コマンドの実行前に、このコンテキストに表示をエクスポートする必要があります。 たとえば場合、表示の値: 1、その行を次のように変更します。

    ```cmd
    "export DISPLAY=:1;${debuggerCommand}",
    ```
3. これを起動し、アプリケーションをデバッグするには次のように選択します。、**スタートアップ アイテムの選択**ツールバーのドロップダウンを選び、AppBasicExampleGui します。 今すぐそのボタンを押すか、ヒット**F5**します。 これは、アプリケーションをビルドし、その依存関係をリモートの Linux コンピューターで起動し、付属の Visual Studio デバッガーでします。 リモート Linux マシン、アプリケーション ウィンドウを表示が表示されます。

4. アプリケーション ウィンドウに、マウスを移動 をクリックし、ブレークポイントがヒットします。 プログラム実行一時停止し、Visual Studio は、前面に戻ったし、ブレークポイントになります。 Visual Studio で表示 Linux コンソール ウィンドウも表示されます。 このウィンドウは、リモートの Linux コンピューターからの出力との入力を受け入れることもできますが`stdin`します。 任意の Visual Studio ウィンドウと同様にドッキングできる場所を確認して、今後のセッションでの位置を永続化されます。

    ![Visual Studio Linux コンソール ウィンドウ](media/cmake-bullet3-linux-console.png)

5. アプリケーション変数、オブジェクト、スレッド、メモリ、および手順は、対話的に Visual Studio を使用して、コードを検査できます。 ただし、今度はこれを実行するすべてリモート Linux マシンで、ローカルの Windows 環境ではなく。 クリックすることができます**続行**アプリケーションを再開し、通常、終了またはローカル実行と同様に、停止 ボタンを押すことができます。

6. 呼び出し履歴 ウィンドウを確認しへの呼び出しを表示`x11OpenGLWindow`Visual Studio は、Linux 上のアプリケーションを起動するためです。

    ![呼び出し履歴 ウィンドウが Linux 呼び出し履歴の表示](media/cmake-bullet3-linux-callstack.png)

## <a name="what-you-learned"></a>学習内容 

このチュートリアルでは、コードを直接 GitHub から複製されたし、ビルド、実行、およびデバッグ対象を変更なしで Windows の基本を説明しました。 これは、付属のコード ベース、少しの構成変更が構築された、実行され、リモート Linux マシンでデバッグします。 

## <a name="next-steps"></a>次の手順

構成して、Visual Studio で CMake プロジェクトのデバッグについて説明します。

> [!div class="nextstepaction"]
> [Visual Studio で CMake プロジェクト](cmake-projects-in-visual-studio.md)<br/><br/>
> [Linux CMake プロジェクトを構成する](../linux/cmake-linux-project.md)<br/><br/>
> [リモートの Linux コンピューターに接続する](../linux/connect-to-your-remote-linux-computer.md)<br/><br/>
> [CMake のビルド設定をカスタマイズする](customize-cmake-settings.md)<br/><br/>
> [CMake デバッグ セッションを構成する](configure-cmake-debugging-sessions.md)<br/><br/>
> [Linux プロジェクトの配置、実行、デバッグ](../linux/deploy-run-and-debug-your-linux-project.md)<br/><br/>
> [定義済みの CMake 構成リファレンス](cmake-predefined-configuration-reference.md)
> 
