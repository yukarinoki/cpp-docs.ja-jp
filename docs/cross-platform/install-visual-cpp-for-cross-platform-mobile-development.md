---
title: C++ によるクロスプラットフォーム モバイル開発をインストールする
ms.date: 10/17/2019
ms.assetid: aaea6b8d-55eb-4427-8185-c050f855c257
ms.openlocfilehash: 935e427710d55120055be476a5cfb5fbcf73641b
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609187"
---
# <a name="install-cross-platform-mobile-development-with-c"></a>C++ によるクロスプラットフォーム モバイル開発をインストールする

Visual Studio で C++ を使用して、Windows デスクトップアプリ、ユニバーサル Windows プラットフォーム (UWP) アプリ、Linux アプリを構築できます。 これで、Android および iOS 用の C++ アプリを構築できます。 **C++ によるモバイル開発**ワークロードは、Visual Studio のインストール可能なコンポーネントのセットです。 これには、クロスプラットフォームの iOS、Android、UWP の Visual Studio テンプレートが含まれています。 このワークロードでは、すぐに使用を開始するために必要なクロスプラットフォームツールと Sdk がインストールされます。 自分で検索、ダウンロード、および構成を行う必要はありません。 これらのツールを Visual Studio で使用することで、クロスプラットフォーム プロジェクトを簡単に作成、編集、デバッグ、テストできます。

この記事では、Visual Studio を使って C++ でクロスプラットフォーム アプリを開発するために必要なツールとサード パーティのソフトウェアをインストールする方法について説明します。 概要については、「[Visual C++ クロスプラットフォーム モバイル](https://visualstudio.microsoft.com/vs/features/cplusplus-mdd/)」を参照してください。

## <a name="requirements"></a>必要条件

::: moniker range="vs-2017"

- インストール要件については、「[Visual Studio 2017 製品ファミリのシステム要件](/visualstudio/productinfo/vs2017-system-requirements-vs)」を参照してください。

   > [!IMPORTANT]
   > Windows 7 または Windows Server 2008 R2 を使用している場合は、Windows デスクトップ アプリケーション、Android Native Activity アプリおよびライブラリ、iOS 用のアプリとコード ライブラリのためのコードを開発できますが、Windows Store アプリまたは UWP アプリのコードは開発できません。

::: moniker-end
::: moniker range=">=vs-2019"

- インストール要件については、「[Visual Studio 2017 製品ファミリのシステム要件](/visualstudio/releases/2019/system-requirements)」を参照してください。

   > [!IMPORTANT]
   > Windows 7 または Windows Server 2008 R2 を使用している場合は、Windows デスクトップ アプリケーション、Android Native Activity アプリおよびライブラリ、iOS 用のアプリとコード ライブラリのためのコードを開発できますが、Windows Phone アプリまたは UWP アプリのコードは開発できません。

::: moniker-end

特定のデバイス プラットフォームのアプリをビルドするには、いくつかの追加要件があります。

- Android SDK に付属している x86 Android エミュレーターは、Intel Hardware Accelerated Execution Manager (HAXM) などのハードウェア アクセラレータを使用できるコンピューターで最適に動作します。 詳細については、「[エミュレーターのパフォーマンスのためのハードウェア高速化 (Hyper-V と HAXM)](/xamarin/android/get-started/installation/android-emulator/hardware-acceleration?tabs=vswin&pivots=windows)」を参照してください。

- iOS 用のコードをビルドするには、Apple ID、iOS Developer Program アカウント、[Xcode](https://developer.apple.com/xcode/) バージョン 10.2 以降を OS X Mavericks (バージョン 10.9) 以降のバージョンで実行できる Mac コンピューターが必要です。 インストール手順のリンクについては、「[iOS 用ツールのインストール](#install-tools-for-ios)」をご覧ください。

- Windows Phone エミュレーターには、Hyper-V を実行できるコンピューターが必要です。 エミュレーターをインストールして実行する前に、Windows の Hyper-V 機能を有効にする必要があります。 詳細については、エミュレーターの[システム要件](/visualstudio/cross-platform/system-requirements-for-the-visual-studio-emulator-for-android)をご覧ください。

## <a name="get-the-tools"></a>ツールの入手

C++ でのモバイル開発は、Visual Studio の Community、Professional、Enterprise エディションで利用できます。 Visual Studio を入手するには、 [Visual studio のダウンロード](https://visualstudio.microsoft.com/downloads/) ページに移動します。 クロスプラットフォーム モバイル開発ツールは、Visual Studio 2015 以降で利用できます。

## <a name="install-the-tools"></a>ツールのインストール

Visual Studio インストーラーには、**C++ によるモバイル開発**ワークロードが含まれます。 このワークロードでは、Visual Studio での Android および iOS の開発に必要な C++ 言語のツール、テンプレート、コンポーネントがインストールされます。 これには、Android のビルドとデバッグに必要な GCC および Clang ツールセットが含まれています。 このワークロードによって、Android SDK、およびコンポーネントがインストールされ、iOS 開発用の Mac と通信できるようになります。 また、iOS および Android アプリの開発をサポートするために必要なサードパーティ製のツールとソフトウェア開発キットもインストールされます。 これらのサードパーティ製ツールのほとんどは、Android プラットフォームのサポートに必要なオープン ソースのソフトウェアです。

- Android Native Development Kit (NDK)、Apache Ant、および C++ Android 開発ツールは、Android プラットフォームを対象にした C++ コードをビルドする場合に必要になります。

  > [!NOTE]
  > Android NDK の一部のツールでは、ファイルパスとファイル名の Unicode 文字がサポートされていません。 プロジェクトまたはソースファイルのパスまたはファイル名に Unicode 文字が含まれている場合、プロジェクトはビルドに失敗します。

- Google Android Emulator および Intel Hardware Accelerated Execution Manager (HAXM) は、オプションですがお勧めするコンポーネントです。 (Intel HAXM ドライバーは Intel プロセッサでのみ機能し、Hyper-v を含む一部の Vm とは互換性がありません)。Android デバイスで直接開発とデバッグを行うことができますが、多くの場合、デバッグのためにデスクトップでエミュレーターを使用する方が簡単です。

- iOS プラットフォームを対象とする C++ コードをビルドするには、C++ iOS 開発ツールが必要です。

> [!NOTE]
> Visual Studio 2015 を使用している場合は、「[Visual C++ for Cross-Platform Mobile Development のインストール (Visual Studio 2015)](install-visual-cpp-for-cross-platform-mobile-development.md?view=vs-2015)」をご覧ください

### <a name="install-the-mobile-development-with-c-workload"></a>C++ によるモバイル開発ワークロードをインストールする

1. **[スタート]** メニューから **Visual Studio インストーラー**を実行します。

1. Visual Studio が既にインストールされている場合は、インストールされている Visual Studio の中で変更するバージョンの **[変更]** ボタンをクリックします。 それ以外の場合は、**[インストール]** を選んで Visual Studio をインストールします。

1. **[ワークロード]** タブで、下にスクロールして、Visual Studio インストーラーの **[C++ によるモバイル開発]** ワークロードを選びます。 このワークロードを選ぶと、C++ による開発に必要な他のコンポーネントも選択されます。 他のワークロードを選び、個々のコンポーネントを同時にインストールすることもできます。 UWP もターゲットとするクロスプラットフォームのコードをビルドするには、**[ユニバーサル Windows プラットフォーム開発]** ワークロードを選びます。

1. **[インストールの詳細]** ウィンドウで、**[C++ によるモバイル開発]** を展開します。 **[オプション]** セクションでは、NDK の追加バージョン、Google Android Emulator、Intel Hardware Accelerated Execution Manager、IncrediBuild ビルド アクセラレーション ツールを選ぶことができます。

1. 既定では、1 つまたは複数の Android SDK セットアップ コンポーネントが、ワークロードによって組み込まれます。 Android SDK の追加バージョンを使用できます。 インストールに追加するには、**[個別のコンポーネント]** タブを選び、**[SDK、ライブラリ、およびフレームワーク]** セクションまで下にスクロールして選びます。

1. **[変更]** または **[インストール]** ボタンを選んで、**C++ によるモバイル開発**ワークロードと他の選択したワークロードおよびオプションのコンポーネントをインストールします。

   インストールが完了したら、インストーラーを閉じて、コンピューターを再起動します。 サード パーティ製コンポーネントの一部の設定操作は、コンピューターを再起動するまで有効になりません。

   > [!IMPORTANT]
   > 確実にすべてを正しくインストールするには、再起動する必要があります。

1. Visual Studio を開きます。

## <a name="install-tools-for-ios"></a>Install tools for iOS

Visual Studio を使用して、ios コードを編集、デバッグし、iOS シミュレーターにデプロイすることができます。 または、iOS デバイスに対して。 ライセンスの制限により、コードを Mac 上でリモートでビルドする必要があります。 Visual Studio を使用して iOS アプリをビルドして実行するには、まず、Mac でリモートエージェントをセットアップして構成します。 インストール方法、前提条件、構成オプションの詳細については、「[Install And Configure Tools to Build using iOS](../cross-platform/install-and-configure-tools-to-build-using-ios.md)」を参照してください。 iOS 用にビルドするのでない場合は、この手順を省略できます。

## <a name="install-or-update-dependencies-manually"></a>手動による依存関係のインストールまたは更新

**C++ によるモバイル開発**ワークロードをインストールするときに、サードパーティのすべての依存関係をインストールする必要はありません (または、Visual Studio 2015 の Visual C++ モバイル開発オプション)。 後でインストールするには、「 [ツールのインストール](#install-the-tools)」の手順に従ってください。 最新のサードパーティ製コンポーネントをインストールするため、Visual Studio インストーラーは定期的に更新されます。 更新された Sdk と NDKs をインストールするときに使用します。 また、Visual Studio とは別にインストールまたは更新することもできます。

Sdk Manager アプリを Android SDK ディレクトリでもう一度実行して、SDK を更新することができます。 オプションのツールと追加の API レベルをインストールします。 **[管理者として実行]** を使用して SDK Manager アプリを実行しなければ、更新のインストールが失敗する可能性があります。 Android アプリのビルドで問題が発生した場合は、SDK Manager を確認して、インストール済み SDK の更新プログラムの有無を調べてください。

一部の Android SDK エミュレーターを使用するには、ハードウェアアクセラレータの設定が必要になることがあります。 詳細については、「[エミュレーターのパフォーマンスのためのハードウェア高速化 (Hyper-V と HAXM)](/xamarin/android/get-started/installation/android-emulator/hardware-acceleration?tabs=vswin)」を参照してください。

ほとんどの場合、インストールしたサードパーティ製ソフトウェアの構成は Visual Studio によって検出されます。 内部環境変数にインストールパスを保持します。 これらのクロス プラットフォーム開発ツールの既定のパスは、Visual Studio IDE でオーバーライドできます。

### <a name="to-set-the-paths-for-third-party-tools"></a>サード パーティのツールのパスを設定するには

1. Visual Studio のメニューバーで、[**ツール**] [オプション] を選択し  >  **Options**ます。

1. **[オプション]** ダイアログ ボックスで、 **[クロス プラットフォーム]** > **[C++]** > **[Android]** の順に選びます。

   ![Android ツールのパスのオプション](../cross-platform/media/cppmdd-options-android.png "Android ツールのパスのオプション")

1. ツールが使用するパスを変更するには、パスの横にあるチェック ボックスをオンにして、テキスト ボックスでフォルダー パスを編集します。 参照ボタン (**...**) を使用して **[場所を選択]** ダイアログを開き、フォルダーを選ぶこともできます。

1. **[OK]** を選んで、カスタム ツール フォルダーの場所を保存します。

## <a name="see-also"></a>関連項目

[IOS を使用してビルドするためのツールのインストールと構成](install-and-configure-tools-to-build-using-ios.md)\
[Visual C++ クロスプラットフォーム モバイル](https://visualstudio.microsoft.com/vs/features/cplusplus-mdd/)
