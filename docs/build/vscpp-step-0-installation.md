---
title: Visual Studio に C および C++ サポートをインストールする
description: Microsoft C/C++ および関連ワークロードをサポートする Visual Studio をインストールする方法について説明します。
ms.custom: mvc
ms.date: 11/05/2020
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: 3f2d2ade54cb4db2cd692f044a5cd648600bc7f6
ms.sourcegitcommit: 12eb6a824dd7187a065d44fceca4c410f58e121e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2020
ms.locfileid: "94334183"
---
# <a name="install-c-and-c-support-in-visual-studio"></a>Visual Studio に C および C++ サポートをインストールする

まだ Visual Studio と Microsoft C/C++ ツールをダウンロードしてインストールしていない場合は、ここで説明する方法に従って始めることができます。

::: moniker range="msvc-160"

## <a name="visual-studio-2019-installation"></a>Visual Studio 2019 のインストール

Visual Studio 2019 へようこそ このバージョンでは、必要な機能だけを簡単に選択してインストールできます。 占有領域が最小限まで小さくなっているため、インストールが速く、システムにほとんど影響しません。

> [!NOTE]
> このトピックは、Windows への Visual Studio のインストールに適用されます。 [Visual Studio Code](https://code.visualstudio.com/) は、Windows、Mac、Linux システムで実行できる、軽量なクロスプラットフォームの開発環境です。 Microsoft [C/C++ for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools) 拡張機能では、IntelliSense、デバッグ、コードの書式設定、オートコンプリートがサポートされています。 Visual Studio for Mac では、Microsoft C++ はサポートされていませんが、.NET 言語とクロスプラットフォームの開発はサポートされています。 インストールの手順については、[Visual Studio for Mac をインストールする](/visualstudio/mac/installation/)」を参照してください。

このバージョンの他の新機能については、 Visual Studio の[リリース ノート](/visualstudio/releases/2019/release-notes/)を参照してください。

インストールの準備ができたら、 各ステップを順に実行していきます。

### <a name="step-1---make-sure-your-computer-is-ready-for-visual-studio"></a>手順 1 - コンピューターで Visual Studio の準備ができていることを確認する

Visual Studio のインストールを開始する前に

1. [システム要件](/visualstudio/releases/2019/system-requirements)を確認します。 これらの要件により、ご利用のコンピューターが Visual Studio 2019 に対応しているかどうかを確認できます。

1. 最新の Windows 更新プログラムを適用します。 これらの更新プログラムにより、Visual Studio の最新のセキュリティ更新プログラムと必要なシステム コンポーネントの両方がコンピューターにインストールされます。

1. 再起動します。 この再起動により、Visual Studio のインストールの際に妨げとなる、保留中のインストールや更新プログラムがないようにします。

1. 記憶域を解放します。 ディスク クリーンアップ アプリを実行するなどして、%SystemDrive% から不要なファイルとアプリケーションを削除します。

Visual Studio 2019 と以前のバージョンの Visual Studio を共存させて実行することについて疑問点がある場合は、「[Visual Studio 2019 の対象プラットフォームと互換性](/visualstudio/releases/2019/compatibility/)」ページをご覧ください。

### <a name="step-2---download-visual-studio"></a>手順 2 - Visual Studio をダウンロードする

次に、Visual Studio ブートストラップ ファイルをダウンロードします。 これを行うには、次のボタンをクリックして、Visual Studio のダウンロードページに移動します。 使用する Visual Studio のエディションを選択し、 **[無料試用版]** または **[無料ダウンロード]** ボタンを選択します。

 > [!div class="button"]
 > [Visual Studio のダウンロード](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019+rc)

### <a name="step-3---install-the-visual-studio-installer"></a>手順 3 - Visual Studio インストーラーをインストールする

ダウンロードしたブートストラップ ファイルを実行して、Visual Studio インストーラーをインストールします。 この新しい軽量インストーラーには、Visual Studio のインストールとカスタマイズの両方に必要なすべてのものが含まれています。

1. **[ダウンロード]** フォルダーで、次のいずれかのファイルと一致する、または似ているブートストラップをダブルクリックします。

   - Visual Studio Community の場合は **vs_community.exe**
   - Visual Studio Professional の場合は **vs_professional.exe**
   - Visual Studio Enterprise の場合は **vs_enterprise.exe**

   ユーザー アカウント制御の通知を受け取った場合は、 **[はい]** を選択して、ブートストラップの実行を許可します。

1. Microsoft の[ライセンス条項](https://visualstudio.microsoft.com/license-terms/)と[プライバシーに関する声明](https://privacy.microsoft.com/privacystatement)の確認を求められます。 **[続行]** を選択します。

### <a name="step-4---choose-workloads"></a>手順 4 - ワークロードを選択する

インストーラーのインストールが済んだら、それを使用して、必要な "*ワークロード*" (機能セット) を選択することにより、インストールをカスタマイズできます。 ここではその方法を説明します。

1. **[Visual Studio のインストール]** 画面で、必要なワークロードを見つけます。

   ![Visual Studio 2019:ワークロードをインストールする](../get-started/media/vs-installer-workloads.png)

   コア C および C++ のサポートの場合は、"C++ によるデスクトップ開発" ワークロードを選択します。 これには既定のコア エディターが用意されており、20 を超える言語の基本的なコード編集サポートが含まれ、プロジェクトなしで任意のフォルダーからコードを開いて編集することができます。また、統合ソース コード管理を利用できます。

   追加のワークロードでは、他の種類の開発がサポートされています。 たとえば、Microsoft Store 用の Windows ランタイムを使用するアプリを作成するには、"ユニバーサル Windows プラットフォーム開発" ワークロードを選択します。 DirectX、Unreal、Cocos2d を使用するゲームを作成するには、"C++ によるゲーム開発" を選択します。 IoT 開発など、Linux プラットフォームを対象とするには、"C++ による Linux 開発" を選択します。

   **[インストールの詳細]** ペインには、各ワークロードのインストールに含まれるオプションのコンポーネントの一覧が表示されます。 この一覧では、オプション コンポーネントを選択または選択解除できます。 たとえば、Visual Studio 2017 または 2015 のコンパイラ ツールセットを使用して開発をサポートするには、MSVC v141 または MSVC v140 のオプション コンポーネントを選択します。 MFC、実験的なモジュール言語拡張機能、IncrediBuild などのサポートを追加できます。

1. 必要なワークロード (複数可) とオプション コンポーネントを選択した後、 **[インストール]** を選択します。

   そうすると、ステータス画面が表示され、Visual Studio のインストールの進行状況が示されます。

> [!TIP]
> インストール後いつでも、最初にインストールしなかったワークロードまたはコンポーネントをインストールできます。 Visual Studio を開いている場合は、 **[ツール]**  >  **[ツールと機能を取得]** に移動すると、Visual Studio インストーラーが開きます。 または、スタート メニューから **Visual Studio インストーラー** を開きます。 そこから、インストールするワークロードまたはコンポーネントを選択できます。 次に、 **[変更]** を選択します。

### <a name="step-5---choose-individual-components-optional"></a>手順 5 - 個々のコンポーネントを選択する (省略可能)

ワークロード機能を使用して Visual Studio のインストールをカスタマイズしない場合、またはワークロードのインストール以外のコンポーネントを追加する場合は、 **[個別のコンポーネント]** タブから個々のコンポーネントをインストールまたは追加することによって行うことができます。必要なものを選択した後、画面の指示に従います。

  ![Visual Studio 2019 - 個々のコンポーネントのインストール](../get-started/media/vs-installer-individual-components.png "Visual Studio の個々のコンポーネントをインストールする")

### <a name="step-6---install-language-packs-optional"></a>手順 6 - 言語パックをインストールする (省略可能)

既定では、インストーラー プログラムが、最初の実行時にオペレーティング システムの言語の照合を試みます。 選択した言語で Visual Studio をインストールするには、Visual Studio インストーラーで **[言語パック]** タブをクリックした後、画面の指示に従います。

  ![Visual Studio 2019 - 言語パックのインストール](../get-started/media/vs-installer-language-packs.png "Visual Studio の言語パックをインストールする")

#### <a name="change-the-installer-language-from-the-command-line"></a>コマンド ラインかインストーラーの言語を変更する

コマンド ラインからインストーラーを実行して、既定の言語を変更することもできます。 たとえば、`vs_installer.exe --locale en-US` コマンドを実行して、インストーラーを英語で実行するように指定することができます。 この設定は、次回インストーラーを実行したときにも保持されています。 インストーラーでは次の言語トークンがサポートされます。zh-cn、zh-tw、cs-cz、en-us、es-es、fr-fr、de-de、it-it、ja-jp、ko-kr、pl-pl、pt-br、ru-ru、tr-tr。

### <a name="step-7---change-the-installation-location-optional"></a>手順 7 - インストール場所の変更 (省略可能)

システム ドライブ上の Visual Studio のインストール占有領域を小さくすることができます。 ダウンロード キャッシュ、共有コンポーネント、SDK、およびツールを別のドライブに移動して、Visual Studio を最速で実行できるドライブで維持できます。

  ![Visual Studio 2019 - インストール場所を変更する](../get-started/media/vs-installer-installation-locations.png "インストールの場所を変更する")

> [!IMPORTANT]
> Visual Studio を初めてインストールするときにのみ、別のドライブを選択できます。 既にインストールしてあるドライブを変更する場合は、Visual Studio をアンインストールした後、再インストールする必要があります。

### <a name="step-8---start-developing"></a>手順 8 - 開発を始める

1. Visual Studio のインストールが完了したら **[起動]** を選択して、Visual Studio を使用した開発を開始します。

1. スタート ウィンドウで、 **[新しいプロジェクトの作成]** を選択します。

1. 検索ボックスに作成するアプリの種類を入力し、使用可能なテンプレートの一覧を表示します。 テンプレートの一覧は、インストール時に選択したワークロードに依存します。 別のテンプレートを表示するには、異なるワークロードを選択します。

   **[言語]** ドロップダウン リストを使用して、特定のプログラミング言語に検索をフィルター処理することもできます。 **[プラットフォーム]** の一覧や **[プロジェクトの種類]** の一覧を使用して、フィルター処理することもできます。

1. Visual Studio で新しいプロジェクトが開き、コーディングできる状態になります。

::: moniker-end

::: moniker range="msvc-150"

## <a name="visual-studio-2017-installation"></a>Visual Studio 2017 のインストール

Visual Studio 2017 では、必要な機能だけを簡単に選択してインストールできます。 占有領域が最小限まで小さくなっているため、インストールが速く、システムにほとんど影響しません。

### <a name="prerequisites"></a>必須コンポーネント

- ブロードバンド インターネット接続。 Visual Studio インストーラーでは、数ギガバイトのデータをダウンロードできます。

- Microsoft Windows 7 またはそれ以降のバージョンを稼働しているコンピューター。 最適な開発作業のためには、Windows 10 をお勧めします。 Visual Studio をインストールする前に、お使いのシステムに最新の更新プログラムが適用されていることを確認してください。

- 十分な空きディスク領域。 Visual Studio では、少なくとも 7 GB のディスク領域が必要であり、よく使われる多くのオプションをインストールすると、50 GB 以上になることがあります。 C: ドライブにインストールすることをお勧めします。

ディスク領域とオペレーティング システムの要件の詳細については、「[Visual Studio 2017 製品ファミリのシステム要件](/visualstudio/productinfo/vs2017-system-requirements-vs)」を参照してください。 インストーラーでは、選択したオプションに必要なディスク領域の量が示されます。

### <a name="download-and-install"></a>ダウンロードしてインストールする

1. Windows 用の最新の Visual Studio 2017 インストーラーをダウンロードするには、Microsoft Visual Studio の[古いバージョンのダウンロード](https://www.visualstudio.com/vs/older-downloads/) ページに移動します。 **2017** のセクションを展開し、 **[ダウンロード]** ボタンを選択します。

   >[!Tip]
   > このコミュニティ版は、個人の開発者、クラス学習、学術研究、オープン ソース開発向けです。 その他の用途には、Visual Studio 2017 Professional または Visual Studio 2017 Enterprise を使用してください。

1. ダウンロードしたインストーラー ファイルを見つけて実行します。 ダウンロードされたファイルは、ブラウザーに表示される場合もあれば、ダウンロード フォルダーにある場合もあります。 インストーラーを実行するには管理者特権が必要です。 インストーラーがシステムを変更できるようにアクセス許可の付与を求める **[ユーザー アカウント制御]** ダイアログが表示される場合があります。 **[はい]** を選択します。 問題が発生する場合は、エクスプローラーでダウンロードしたファイルを見つけ、インストーラー アイコンを右クリックして、コンテキスト メニューから **[管理者として実行]** を選択します。

   ![Visual Studio インストーラーをダウンロードしてインストールする](media/vscpp-concierge-run-installer.gif "Visual Studio インストーラーをダウンロードしてインストールする")

1. インストーラーによって、ワークロード一覧が表示されます。これは、特定の開発分野の関連オプションのグループです。 C++ のサポートは、既定ではインストールされないオプションのワークロードの一部になっています。

   ![C++ によるデスクトップ開発ワークロード](media/desktop-development-with-cpp.png "C++ によるデスクトップ開発")

   C および C++ の場合は、 **[C++ によるデスクトップ開発]** ワークロードを選択して、 **[インストール]** を選択します。

   ![C++ によるデスクトップ開発ワークロードをインストールする](media/vscpp-concierge-choose-workload.gif "C++ によるデスクトップ開発ワークロードをインストールする")

1. インストールが終わったら、 **[起動]** ボタンを選択して Visual Studio を開始します。

   Visual Studio を初めて実行すると、Microsoft アカウントでサインインするように求められます。 それらのいずれのアカウントもない場合は、新しいアカウントを無料で作成できます。 テーマも選択する必要があります。 心配しないでください。後で必要に応じて変更できます。

   初めて実行したときは、Visual Studio が使用できるようになるまでに、数分かかる場合があります。 経過を短縮して見ると次のようになります。

   ![Visual Studio 2017 のサインイン](media/vscpp-quickstart-first-run.gif "Visual Studio 2017 のサインイン")

   2 回目以降の実行では、Visual Studio ははるかに速く起動するようになります。

1. Visual Studio が開いたら、タイトル バーのフラグ アイコンが強調表示されているかどうかを確認します。

   ![Visual Studio 2017 の通知フラグ](media/vscpp-first-start-page-flag.png "Visual Studio 2017 の通知フラグ")

   強調表示されている場合は、それを選択して **[通知]** ウィンドウを開きます。 Visual Studio に利用可能な更新プログラムがある場合は、すぐにインストールすることをお勧めします。 インストールが完了したら、Visual Studio を再起動します。

::: moniker-end

::: moniker range="<msvc-150"

## <a name="visual-studio-2015-installation"></a>Visual Studio 2015 のインストール

Visual Studio 2015 をインストールするには、Microsoft Visual Studio の[古いバージョンのダウンロード](https://www.visualstudio.com/vs/older-downloads/) ページに移動します。 **2015** のセクションを展開し、 **[ダウンロード]** ボタンを選択します。 ダウンロードされたセットアップ プログラムを実行し、 **[カスタム インストール]** を選択してから、C++ コンポーネントを選択します。 Visual Studio 2015 の既存のインストールに C および C++ のサポートを追加するには、Windows の [スタート] ボタンをクリックし、「**プログラムの追加と削除**」と入力します。 結果の一覧からプログラムを開き、インストールされているプログラムの一覧で、Visual Studio 2015 のインストールを見つけます。 それをダブルクリックし、 **[変更]** を選択して、インストールする Visual C++ コンポーネントを選択します。

一般に、Visual Studio 2015 コンパイラを使用してコードをコンパイルする必要がある場合でも、最新バージョンの Visual Studio を使用することを強くお勧めします。 詳細については、「[Visual Studio でネイティブ マルチ ターゲットを利用し、古いプロジェクトを作成する](../porting/use-native-multi-targeting.md)」を参照してください。

::: moniker-end

Visual Studio が実行されている場合は、次の手順に進むことができます。

## <a name="next-steps"></a>次の手順

> [!div class="nextstepaction"]
> [C++ プロジェクトを作成する](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
