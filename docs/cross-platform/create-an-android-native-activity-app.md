---
title: Android Native Activity アプリの作成
ms.date: 10/17/2019
ms.assetid: 884014b1-5208-45ec-b0da-ad0070d2c24d
ms.openlocfilehash: f588c56acfd5c559e6b0bf1b8635e8b36c69548a
ms.sourcegitcommit: a673f6a54cc97e3d4cd032b10aa8dce7f0539d39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "79469939"
---
# <a name="create-an-android-native-activity-app"></a>Android Native Activity アプリの作成

クロスプラットフォームの **C++ によるモバイル開発**ワークロードをインストールすると、Visual Studio を使用して、フル機能を持つ Android Native Activity アプリを作成できます。 Android Native Development Kit (NDK) は、純粋な C/C++ コードを使用して Android アプリの大半を実装することを可能にするツールセットです。 いくつかの Java JNI コードはグルーとして機能し、C/C++ コードが Android とやり取りできるようにします。 Android NDK では、Android API レベル 9 を使用して Native Activity アプリを作成する機能が導入されました。 Native Activity コードは、Unreal Engine または OpenGL を使用したゲームやグラフィックス処理の多いアプリを作成できるので人気があります。 このトピックでは、OpenGL を使用した単純な Native Activity アプリの作成方法について説明します。 他のトピックでは、Native Activity コードの編集、ビルド、デバッグ、展開の開発ライフサイクルについて説明します。

## <a name="requirements"></a>要件

Android Native Activity アプリを作成する前に、すべてのシステム要件を満たし、Visual Studio の **C++ によるモバイル開発**ワークロードをインストールしていることを確認します。 詳細については、「[C++ によるクロスプラットフォーム モバイル開発をインストールする](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md)」を参照してください。 インストールに必要なサード パーティのツールと SDK が含まれていること、また Android Emulator がインストールされていることを確認してください。

## <a name="create-a-new-native-activity-project"></a>新しいネイティブ アクティビティ プロジェクトを作成する

このチュートリアルでは、まず新しい Android Native Activity プロジェクトを作成します。それから、既定のアプリを Android Emulator でビルドして実行します。

::: moniker range="vs-2017"

1. Visual Studio で、[**ファイル**>**新しい**>**プロジェクト**] を選択します。

1. **[新しいプロジェクト]** ダイアログボックスの **[テンプレート]** で **[ C++ Visual** >**クロスプラットフォーム**] を選択し、 **[ネイティブアクティビティアプリケーション (Android)]** テンプレートを選択します。

1. アプリに *MyAndroidApp* などの名前を付け、 **[OK]** を選択します。

   ![Native Activity プロジェクトを作成する](../cross-platform/media/cppmdd-newproject.png "Native Activity プロジェクトの作成")

   Visual Studio は新しいソリューションを作成し、ソリューション エクスプローラーを開きます。

   ![ソリューション エクスプローラーでの Native Activity プロジェクト](../cross-platform/media/cppmdd-rc-na-solutionexp.png "ソリューション エクスプローラーでの Native Activity プロジェクト")

::: moniker-end

::: moniker range=">=vs-2019"

1. Visual Studio で、[**ファイル**>**新しい**>**プロジェクト**] を選択します。

1. **[新しいプロジェクトの作成]** ダイアログ ボックスで、 **[Native-Activity アプリケーション (Android)]** テンプレートを選択し、 **[次へ]** を選択します。

1. **[新しいプロジェクトの構成]** ダイアログ ボックスで、 *[プロジェクト名]* に **MyAndroidApp** のような名前を入力し、 **[作成]** を選択します。

   Visual Studio は新しいソリューションを作成し、ソリューション エクスプローラーを開きます。

::: moniker-end

新しい Android Native Activity アプリのソリューションには、次の 2 つのプロジェクトが含まれています。

- `MyAndroidApp.NativeActivity` には、アプリが Android 上でネイティブ アクティビティとして動作するための参照とグルー コードが含まれています。 グルー コードからのエントリ ポイントの実装は *main.cpp* にあります。 プリコンパイル済みヘッダーは *pch.h* にあります。 この Native Activity アプリ プロジェクトは、共有ライブラリ ( *.so*) ファイルにコンパイルされ、Packaging プロジェクトで使用されます。

- `MyAndroidApp.Packaging` は、Android デバイスまたはエミュレーターに配置する *.apk* ファイルを作成します。 これには、リソースと、マニフェスト プロパティを設定する *AndroidManifest.xml* ファイルが含まれています。 Ant のビルド プロセスを制御する *build.xml* ファイルも含まれています。 それは既定でスタートアップ プロジェクトとして設定されているため、Visual Studio から直接、配置して実行できます。

## <a name="build-and-run-the-default-android-native-activity-app"></a>既定の Android Native Activity アプリをビルドして実行する

テンプレートによって生成されたアプリをビルドして実行し、インストールとセットアップを確認します。 この初期テストでは、Android Emulator によってインストールされているデバイス プロファイルのいずれかでアプリを実行します。 別の対象でアプリをテストする場合は、対象のエミュレーターを読み込むか、デバイスをコンピューターに接続してください。

## <a name="to-build-and-run-the-default-native-activity-app"></a>既定の Native Activity アプリをビルドして実行するには

1. 選択されていない場合は、 **[ソリューション プラットフォーム]** ドロップダウン リストから **[x86]** を選択します。

     ![ソリューション プラットフォーム ドロップダウン x86 の選択](../cross-platform/media/cppmdd-rc-na-solution-x86.png "ソリューション プラットフォーム ドロップダウン x86 の選択")

     **[ソリューション プラットフォーム]** リストが表示されない場合は、 **[ボタンの追加と削除]** リストから **[ソリューション プラットフォーム]** を選択してから、使用するプラットフォームを選択します。

1. メニュー バーで、 **[ビルド]**  >  **[ソリューションのビルド]** の順にクリックします。

     ソリューションに含まれる 2 つのプロジェクトのビルド プロセスの出力が [出力] ウィンドウに表示されます。

1. 配置ターゲットとして、いずれかの Android Emulator プロファイルを選択します。

     別のエミュレーターをインストールしてあるか、Android デバイスを接続してある場合は、配置対象のドロップダウン リストからそれらを選択できます。

1. **F5** キーを押してデバッグを開始するか、**Shift**+**F5** キーを押してデバッグなしで開始します。

   Android Emulator で、既定のアプリは次のようになります。

   ![アプリを実行するエミュレーター](../cross-platform/media/cppmdd-emulator-running-app.png "アプリを実行するエミュレーター")

   Visual Studio によってエミュレーターが起動されます。コードを読み込んで配置するのに数秒かかります。 アプリが開始されると、ブレークポイントの設定や、デバッガーを使用したステップ実行、ローカルの確認、値のウォッチができるようになります。

1. **Shift**+**F5** キーを押してデバッグを停止します。

   エミュレーターは実行され続ける独立したプロセスです。 同じエミュレーターに対して、コードを何度も編集、コンパイル、配置できます。
