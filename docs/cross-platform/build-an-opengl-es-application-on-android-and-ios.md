---
title: Android および iOS での OpenGL ES アプリケーションのビルド
ms.date: 10/09/2019
ms.assetid: 76a67886-df57-4a81-accb-2e3c2eaf607b
ms.openlocfilehash: 23dd9dbb1ff32050494e0d1d105cd55de3123fbb
ms.sourcegitcommit: a673f6a54cc97e3d4cd032b10aa8dce7f0539d39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "79470077"
---
# <a name="build-an-opengl-es-application-on-android-and-ios"></a>Android および iOS での OpenGL ES アプリケーションのビルド

共通コードを共有する iOS アプリ用および Android アプリ用の Visual Studio ソリューションおよびプロジェクトを作成できます。 この記事では、結合されたソリューションテンプレートについて説明します。 IOS アプリと Android Native Activity アプリの両方が作成されます。 これらのアプリには、OpenGL ES を使用して各プラットフォームで同じアニメーション回転キューブを表示する共通の C++ コードがあります。 OpenGL ES (埋め込みシステムの OpenGL) は、2D および3D グラフィックス API です。 多くのモバイルデバイスでサポートされています。

## <a name="requirements"></a>要件

IOS および Android 用の OpenGL ES アプリを作成するためのすべてのシステム要件を満たしていること。 C++ によるモバイル開発ワークロードをまたインストールしていない場合は、Visual Studio インストーラーにインストールします。 OpenGL ES テンプレートを取得し、iOS 用にビルドするには、オプションの C++ iOS 開発ツールを含めます。 Android 用にビルドするにはC++ 、android 開発ツールと、必要なサードパーティ製ツール (android NDK、Apache Ant、Google Android Emulator) をインストールします。

Intel プラットフォームでのエミュレーターのパフォーマンスを向上させるには、Intel Hardware Accelerated Execution Manager (HAXM) をインストールする方法があります。 詳細な手順については、「[を使用しC++たクロスプラットフォームモバイル開発のインストール](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md)」を参照してください。

IOS アプリをビルドしてテストするには、Mac コンピューターが必要です。 インストール手順に従ってセットアップします。 iOS 開発の設定方法について詳しくは、[iOS を使用してビルドするためのツールのインストールと構成](../cross-platform/install-and-configure-tools-to-build-using-ios.md)に関するページをご覧ください。

## <a name="create-a-new-opengles-application-project"></a>新しい OpenGLES アプリケーション プロジェクトの作成

このチュートリアルでは、まず新しい OpenGL ES アプリケーション プロジェクトを作成します。 その後、Android Emulator で既定のアプリをビルドして実行します。 次に、iOS 用アプリをビルドし、iOS デバイスでアプリを実行します。

::: moniker range="vs-2017"

1. Visual Studio で、[**ファイル**>**新しい**>**プロジェクト**] を選択します。

1. **[新しいプロジェクト]** ダイアログボックスの **[テンプレート]** で **[ C++ Visual** >**クロスプラットフォーム**] を選択し、 **[OpenGLES アプリケーション (Android、iOS)]** テンプレートを選択します。

1. アプリに *MyOpenGLESApp* などの名前を付け、 **[OK]** を選択します。

   ![新しい OpenGLES アプリケーション プロジェクト](../cross-platform/media/cppmdd-opengles-newproj.png "新しい OpenGLES アプリケーション プロジェクト")

   Visual Studio は新しいソリューションを作成し、ソリューション エクスプローラーを開きます。

   ![ソリューション エクスプローラーの MyOpenGLESApp](../cross-platform/media/cppmdd-opengles-solexpl.png "ソリューション エクスプローラーの MyOpenGLESApp")

::: moniker-end

::: moniker range=">=vs-2019"

1. Visual Studio で、[**ファイル**>**新しい**>**プロジェクト**] を選択します。

1. **[新しいプロジェクトの作成]** ダイアログ ボックスで、 **[OpenGLES アプリケーション (Android, iOS)]** テンプレートを選択し、 **[次へ]** を選択します。

1. **[新しいプロジェクトの構成]** ダイアログ ボックスで、*プロジェクト名*に **MyOpenGLESApp** のような名前を入力し、 **[作成]** を選択します。

   Visual Studio は新しいソリューションを作成し、ソリューション エクスプローラーを開きます。

   ![ソリューション エクスプローラーの MyOpenGLESApp](../cross-platform/media/cppmdd-opengles-solexpl.png "ソリューション エクスプローラーの MyOpenGLESApp")

::: moniker-end

新しい OpenGL ES アプリケーション ソリューションには、次の 3 つのライブラリ プロジェクトと 2 つのアプリケーション プロジェクトが含まれています。 ライブラリフォルダーには、共有コードプロジェクトが含まれています。 また、共有コードを参照するプラットフォーム固有のプロジェクトが2つあります。

- `MyOpenGLESApp.Android.NativeActivity` には、Android 上の Native Activity としてアプリを実装する参照とグルー コードが含まれています。 グルー コードからのエントリ ポイントは、*main.cpp* に実装され、これには `MyOpenGLESApp.Shared` に共通の共有コードが含まれています。 プリコンパイル済みヘッダーは *pch.h* にあります。 この Native Activity アプリ プロジェクトは、共有ライブラリ ( *.so*) ファイルにコンパイルされ、`MyOpenGLESApp.Android.Packaging` プロジェクトで使用されます。

- `MyOpenGLESApp.iOS.StaticLibrary` は、 *に共有コードが含まれている iOS スタティック ライブラリ (* .a`MyOpenGLESApp.Shared`) ファイルを作成します。 それは `MyOpenGLESApp.iOS.Application` プロジェクトで作成されたアプリにリンクされます。

- `MyOpenGLESApp.Shared` には、プラットフォーム間で機能する共有コードが含まれています。 プラットフォーム固有のコードの条件付きコンパイルにプリプロセッサ マクロを使用します。 共有コードは、`MyOpenGLESApp.Android.NativeActivity` と `MyOpenGLESApp.iOS.StaticLibrary` の両方のプロジェクト参照によって使用されます。

ソリューションには、Android および iOS プラットフォーム用のアプリを構築するための 2 つのプロジェクトがあります。

- `MyOpenGLESApp.Android.Packaging` は、Android デバイスまたはエミュレーターに配置する *.apk* ファイルを作成します。 このファイルには、リソースと、マニフェスト プロパティを設定した AndroidManifest.xml ファイルが含まれています。 Ant のビルド プロセスを制御する *build.xml* ファイルも含まれています。 それは既定でスタートアップ プロジェクトとして設定されているため、Visual Studio から直接、配置して実行できます。

- `MyOpenGLESApp.iOS.Application` には、`MyOpenGLESApp.iOS.StaticLibrary` で C++ スタティック ライブラリ コードにリンクする iOS アプリを作成するためのリソースと Objective-C グルー コードが含まれています。 このプロジェクトは、Visual Studio およびリモート エージェントによってご使用の Mac に転送されるビルド パッケージを作成します。 このプロジェクトをビルドする場合、Visual Studio はファイルとコマンドを送信して、アプリを Mac でビルドおよび配置します。

## <a name="build-and-run-the-android-app"></a>Android アプリのビルドと実行

テンプレートで作成したソリューションは、既定のプロジェクトとして、Android アプリを設定します。  インストールとセットアップを確認するために、このアプリをビルドおよび実行できます。 初期テストでは、Android 用エミュレーターによってインストールされているデバイス プロファイルのいずれかでアプリを実行します。 別のターゲットでアプリをテストする場合は、ターゲットエミュレーターを読み込むことができます。 または、デバイスをコンピューターに接続します。

### <a name="to-build-and-run-the-android-native-activity-app"></a>Android Native Activity アプリをビルドして実行するには

1. まだ選択されていない場合は、 **[ソリューション プラットフォーム]** ドロップダウン リストから **[x86]** を選択します。

   ![ソリューション プラットフォームを x86 に設定する](../cross-platform/media/cppmdd-opengles-solutionplat.png "ソリューション プラットフォームを x86 に設定する")

   x86 を使用してエミュレーターを対象とします。 デバイスを対象とするには、デバイス プロセッサに基づいてソリューション プラットフォームを選択します。 **[ソリューション プラットフォーム]** リストが表示されない場合は、 **[ボタンの追加と削除]** リストから **[ソリューション プラットフォーム]** を選択してから、使用するプラットフォームを選択します。

1. **ソリューション エクスプローラー**で `MyOpenGLESApp.Android.Packaging` プロジェクトのショートカット メニューを開き、 **[ビルド]** を選択します。

   ![Android パッケージ化プロジェクトのビルド](../cross-platform/media/cppmdd-opengles-andbuild.png "Android パッケージ化プロジェクトのビルド")

   Android 共有ライブラリと Android アプリ用のビルド プロセスの出力が [出力] ウィンドウに表示されます。

   ![Android プロジェクト用の出力のビルド](../cross-platform/media/cppmdd-opengles-andoutput.png "Android プロジェクト用の出力のビルド")

1. 配置ターゲットとして、いずれかのエミュレートされた Android デバイス プロファイルを選択します。

   ![配置ターゲットの選択](../cross-platform/media/cppmdd-opengles-pickemulator.png "配置ターゲットの選択")

   他のエミュレーターをインストールしたか、Android デバイスに接続している可能性があります。 デプロイ先のドロップダウンリストで選択できます。 アプリを実行するには、ビルドしたソリューション プラットフォームが、ターゲット デバイスのプラットフォームと一致している必要があります。

1. **F5** キーを押してデバッグを開始するか、**Shift**+**F5** キーを押してデバッグなしで開始します。

   Visual Studio によってエミュレーターが起動されます。コードを読み込んで配置するのに数秒かかります。 エミュレーターでアプリがどのように表示されるかを次に示します。

   ![Android Emulator で実行されているアプリ](../cross-platform/media/cppmdd-opengles-andemulator.png "Android エミュレーターで実行されているアプリ")

   アプリが開始されると、ブレークポイントの設定や、デバッガーを使用したステップ実行、ローカルの確認、値のウォッチができるようになります。

1. **Shift**+**F5** キーを押してデバッグを停止します。

   エミュレーターは実行され続ける独立したプロセスです。 同じエミュレーターに対して、コードを何度も編集、コンパイル、配置できます。 アプリはエミュレーターのアプリ コレクションに表示され、そこから直接起動することができます。

   生成された Android Native Activity アプリとライブラリプロジェクトC++は、共有コードをダイナミックライブラリに配置します。 Android プラットフォームとのインターフェイスを持つ "グルー" コードが含まれています。 ほとんどのアプリコードはライブラリにあります。 マニフェスト、リソース、およびビルド手順は、パッケージプロジェクトに含まれています。 共有コードは、NativeActivity プロジェクトの main.cpp から呼び出されます。 Android Native Activity をプログラムする方法の詳細については、Android NDK Developer の「 [Concepts](https://developer.android.com/ndk/guides/concepts.html) 」ページを参照してください。

   Visual Studio は、android NDK を使用して Android Native Activity プロジェクトをビルドします。 プラットフォームツールセットとして Clang を使用します。 Visual Studio は、プロジェクトのプロパティを、ターゲットプラットフォームのコンパイル、リンク、およびデバッグコマンドにマップします。 詳細については、MyOpenGLESApp.Android.NativeActivity プロジェクトの **[プロパティ ページ]** ダイアログを参照してください。 コマンド ライン スイッチの詳細については、「[Clang Compiler User's Manual](http://clang.llvm.org/docs/UsersManual.html)」 (Clang コンパイラ ユーザーズ マニュアル) を参照してください。

## <a name="build-and-run-the-ios-app-on-an-ios-device"></a>iOS デバイスで iOS アプリをビルドして実行する

IOS アプリプロジェクトを作成し、Visual Studio で編集します。 ライセンスの制限のため、Mac から構築して展開する必要があります。 Visual Studio は、Mac で実行するリモート エージェントと通信して、プロジェクト ファイルを転送し、ビルド、配置、デバッグのコマンドを実行します。 iOS アプリをビルドするには、その前に Mac と Visual Studio が通信できるように設定および構成します。 手順の詳細については、[iOS を使用してビルドするためのツールのインストールと構成](../cross-platform/install-and-configure-tools-to-build-using-ios.md)に関するページをご覧ください。 Mac でリモートエージェントを実行し、Visual Studio とペアリングします。 その後、iOS アプリをビルドして実行し、インストールとセットアップを確認することができます。

アプリを iOS デバイスに展開するには、まず Xcode で自動署名を設定します。 自動署名を行うと、アプリのビルドに署名するためのプロビジョニングプロファイルが作成されます。

### <a name="to-set-up-automatic-signing-on-xcode"></a>Xcode の自動署名を設定するには

1. [Xcode](https://developer.apple.com/xcode/) をまだ Mac にインストールしていない場合は、インストールします。

1. Mac で Xcode アプリを開きます。

1. 新しい **Single View Application** Xcode プロジェクトを作成ます。 プロジェクトの作成中に、必須フィールドに入力します。 この値は、後でアプリのビルドに署名するために使用するプロビジョニング プロファイルの作成にのみ使用されるため、任意で指定できます。

1. [Apple Developer Program](https://developer.apple.com/programs/) アカウントに登録されている Apple ID を Xcode に追加します。 Apple ID は、アプリに署名するための署名 ID として使用されます。 Xcode で署名 ID を追加するには、 **[Xcode]** メニューを開き、 **[Preferences]\(環境設定\)** を選択します。 **[Accounts]\(アカウント\)** を選択し、[Add]\(追加\) ボタン (+) をクリックして Apple ID を追加します。 詳しい手順については、「[Add your Apple ID account](https://help.apple.com/xcode/mac/current/#/devaf282080a)」 (Apple ID アカウントを追加する) を参照してください。

1. Xcode プロジェクトの [General]\(全般\) 設定から、 **[Bundle Identifier]\(バンドル識別子\)** の値を `com.<NameOfVSProject>` に変更します。ここで、`<NameOfVSProject>` は作成した Visual Studio ソリューションのプロジェクトと同じ名前です。 たとえば、Visual Studio で `MyOpenGLESApp` という名前のプロジェクトを作成した場合、 **[Bundle Identifier]\(バンドル識別子\)** を `com.MyOpenGLESApp` に設定します。

   ![Xcode バンドル識別子](../cross-platform/media/cppmdd-opengles-iosxcodeid.png "Xcode バンドル識別子")

1. 自動署名を有効にするには、 [Automatically manage signing**]\(署名の自動管理\) をオンにします。

   ![Xcode の自動署名](../cross-platform/media/cppmdd-opengles-iosxcodesign.png "Xcode 自動署名")

1. 開発**チーム**として追加した Apple ID のチーム名を選択します。

   ![Xcode チーム](../cross-platform/media/cppmdd-opengles-iosxcodeteam.png "Xcode チーム")

### <a name="to-build-and-run-the-ios-app-on-an-ios-device"></a>iOS デバイスで iOS アプリをビルドして実行するには

1. Mac でリモート エージェントを実行し、Visual Studio がリモート エージェントとペアリングされていることを確認します。 リモート エージェントを開始するには、ターミナル アプリのウィンドウを開き、「 `vcremote`」を参照してください。 詳細については、「[Visual Studio でリモート エージェントを構成する](../cross-platform/install-and-configure-tools-to-build-using-ios.md#ConfigureVS)」を参照してください。

   ![Vcremote が実行されている Mac ターミナル ウィンドウ](../cross-platform/media/cppmdd-common-vcremote.png "Vcremote を実行している Mac ターミナル ウィンドウ")

1. iOS デバイスを Mac に接続します。 デバイスを初めてコンピューターに接続すると、アラートで、デバイスにアクセスするコンピューターを信頼するかどうかがたずねられます。 デバイスが Mac コンピューターを信頼するようにできます。

1. Visual Studio で、まだ選択されていない場合は、デバイス プロセッサに基づいて、 **[ソリューション プラットフォーム]** ドロップダウン リストから、ソリューション プラットフォームを選択します。 この例では、それは **ARM64** プロセッサになります。

   ![ソリューション プラットフォームを ARM64 に設定する](../cross-platform/media/cppmdd-opengles-pickplatformarm64.png "ソリューションプラットフォームを ARM64 に設定します。")

1. ソリューション エクスプローラーで、MyOpenGLESApp.iOS.Application プロジェクトのショートカット メニューを開き、 **[プロジェクトのアンロード]** を選択して、プロジェクトをアンロードします。

1. 再度、アンロードした MyOpenGLESApp.iOS.Application プロジェクトのショートカット メニューを開き、 **[Edit project.pbxproj]\(project.pbxproj の編集\)** を選択して、プロジェクト ファイルを編集します。 `project.pbxproj` ファイルで、`buildSettings` 属性を探し、Apple チーム ID を使用して、`DEVELOPMENT_TEAM` を追加します。 次のスクリーンショットに、Apple チーム ID の `123456ABC` の値の例を示します。 Xcode から Apple チーム ID の値を見つけることができます。 **[ビルド設定]** に移動し、開発チーム名にマウス ポインターを移動して、ヒントを表示します。 ヒントに、チーム ID が表示されます。

   ![開発チームを設定する](../cross-platform/media/cppmdd-opengles-iosdevelopmentteam.png "開発チームの設定")

1. `project.pbxproj` ファイルを閉じてから、アンロードした MyOpenGLESApp.iOS.Application プロジェクトのショートカット メニューを開き、 **[プロジェクトの再読み込み]** を選択して、プロジェクトを再読み込みします。

1. ここで、プロジェクトのショートカット メニューを開き、 **[ビルド]** を選択して、MyOpenGLESApp.iOS.Application プロジェクトをビルドします。

   ![iOS アプリケーション プロジェクトのビルド](../cross-platform/media/cppmdd-opengles-iosbuild.png "iOS アプリケーション プロジェクトのビルド")

   [出力] ウィンドウに、ビルドプロセスの出力が表示されます。 IOS スタティックライブラリと iOS アプリの結果が表示されます。 Mac でリモート エージェントを実行しているターミナル ウィンドウに、コマンドおよびファイル転送アクティビティが表示されます。

   Mac コンピューターで、codesign にキーチェーンへのアクセスを許可するように求められることがあります。 **[許可]** を選択して続行します。

1. ツールバーで、iOS デバイスを選択し、Mac に接続されているデバイスでアプリを実行します。 アプリが起動しない場合、デバイスによって、デプロイされたアプリケーションに、デバイス上で実行するためのアクセス許可が付与されていることを確認します。 このアクセス許可を設定するには、デバイスで **[Settings]\(設定\)**  >  **[General]\(全般\)**  >  **[Device Management]\(デバイス管理\)** に移動します。 デベロッパ APP のアカウントを選択し、アカウントを信頼して、アプリを確認します。 Visual Studio からアプリの再実行を試行します。

   ![iOS デバイス上の iOS アプリ](../cross-platform/media/cppmdd-opengles-iosdevice.png "ios デバイスでの iOS アプリ")

   アプリが開始されたら、ブレークポイントを設定し、Visual Studio デバッガーを使用してローカルを確認したり、呼び出し履歴を確認したり、値を観察したりできます。

   ![iOS アプリのブレークポイントにあるデバッガー](../cross-platform/media/cppmdd-opengles-iosdebug.png "iOS アプリのブレークポイントにあるデバッガー")

1. **Shift**+**F5** キーを押してデバッグを停止します。

   生成された iOS アプリとライブラリのプロジェクトは、共有コードのみを実装するスタティック ライブラリに C++ コードを配置します。 アプリケーション コードのほとんどは、`Application` プロジェクトに配置されます。 このテンプレート プロジェクトの共有ライブラリ コードへの呼び出しは、*GameViewController.m* ファイルで実行されます。 iOS アプリをビルドするために、Visual Studio は Xcode プラットフォーム ツールセットを使用します。これは、Mac で実行されるリモート クライアントと通信する必要があります。

   Visual Studio は、プロジェクトファイルをリモートクライアントに転送します。 次に、Xcode を使用してアプリをビルドするためのコマンドを送信します。 リモート クライアントは、ビルドの状態情報を Visual Studio に返します。 アプリが正常にビルドされると、Visual Studio はアプリを実行してデバッグするためのコマンドを送信できます。 Visual Studio のデバッガーによって、Mac に接続されている iOS デバイスで実行されているアプリが制御されます。 Visual Studio は、プロジェクトのプロパティを、ターゲット iOS プラットフォームでコンパイル、リンク、デバッグするために使用されるオプションにマップします。 コンパイラ コマンド ライン オプションの詳細については、MyOpenGLESApp.iOS.StaticLibrary プロジェクトの **[プロパティ ページ]** ダイアログを開いてください。

## <a name="customize-your-apps"></a>アプリのカスタマイズ

共通機能を追加または変更するために、共有 C++ コードを変更することができます。 `MyOpenGLESApp.Android.NativeActivity` プロジェクトと `MyOpenGLESApp.iOS.Application` プロジェクト内の共有コードへの呼び出しを、一致するように変更します。 プリプロセッサ マクロを使用して、共通コードにおけるプラットフォーム固有のセクションを指定することができます。 Android 用にビルドする場合は、プリプロセッサ マクロ `__ANDROID__` が事前に定義されます。 iOS 用にビルドする場合は、プリプロセッサ マクロ `__APPLE__` が事前に定義されます。

特定のプロジェクトプラットフォームの IntelliSense を表示するには、コンテキストスイッチャーのドロップダウンでプロジェクトを選択します。 これは、エディターウィンドウの上部にあるナビゲーションバーに表示されます。

![エディターのプロジェクト コンテキスト スイッチャーのドロップダウン](../cross-platform/media/cppmdd-opengles-contextswitcher.png)

現在のプロジェクトで使用されているコードの IntelliSense の問題が、赤色の波線でマークされます。 紫色の波線は、他のプロジェクトでの問題を示しています。 Visual Studio では、Java または Objective-C ファイルのコードの色付けや IntelliSense がサポートされていません。 ただし、ソースファイルとリソースを変更することはできます。 それらを使用して、アプリケーション名、アイコン、およびその他の実装の詳細を設定します。
