<<<<<<< HEAD
---
title: Visual Studio で C++ サポートのインストール |Microsoft Docs
description: Visual Studio の Visual C サポートをインストールします。
ms.custom: mvc
ms.date: 06/21/2018
ms.topic: tutorial
ms.technology:
- devlang-C++
ms.devlang: C++
dev_langs:
- C++
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3cc9c124a5b3f2fea92f729d7d11df579cc25a39
ms.sourcegitcommit: bad2441d1930275ff506d44759d283d94cccd1c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2018
ms.locfileid: "39376060"
---
# <a name="install-c-support-in-visual-studio"></a>Visual Studio での C++ のサポートをインストール

まだ Visual Studio および Visual C++ ツールをダウンロードおよびインストールしていない場合は、次の方法で作業を開始できます。


## <a name="prerequisites"></a>必須コンポーネント

- ブロードバンド インターネットの接続。 Visual Studio インストーラーでは数ギガバイトのデータをダウンロードします。

- Microsoft Windows 7 またはそれ以降のバージョンを実行するコンピューター。 開発のベスト エクスペリエンスを実現するには Windows 10 をお勧めします。 Visual Studio をインストールする前に、システムに最新の更新プログラムが適用されることを確認します。

- 十分な空きディスク領域。 Visual Studio では、7 GB 以上のディスク領域が必要ですし、多くの一般的なオプションがインストールされている場合、50 GB 以上かかることができます。 C: ドライブにインストールすることをお勧めします。

ディスク容量とオペレーティング システムの要件の詳細については、次を参照してください。 [Visual Studio 製品ファミリのシステム要件](/visualstudio/productinfo/vs2017-system-requirements-vs)します。 インストーラーにより、選択したオプションに必要なディスク領域の量が報告されます。

## <a name="installation"></a>インストール

1. Windows の最新の Visual Studio 2017 インストーラーをダウンロードします。

   > [!div class="nextstepaction"]
   > [Visual Studio 2017 のインストールに関するコミュニティ](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

   >[!Tip]
   > このコミュニティ版は、個人の開発者、クラス学習、学術研究、オープン ソース開発向けです。 その他の用途には、<a target="frameTarget" href="https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017">Visual Studio 2017 Professional</a> または <a target="frameTarget" href="https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017">Visual Studio 2017 Enterprise</a> を使用してください。

1. ダウンロードしたインストーラー ファイルを検索して実行します。 ブラウザーに表示されるか、ダウンロード フォルダーで見つかるでしょう。 インストーラーを実行するには、管理者特権が必要です。 インストーラーでシステムに変更を加えることを可能にするアクセス許可を付与するかどうかを求める **[ユーザーアカウント制御]** ダイアログが表示されます **。** 問題が発生した場合、エクスプローラーでダウンロードしたファイルを検索し、インストーラーのアイコンを右クリックし、コンテキスト メニューから **[管理者として実行]** を選択してください。

   ![Visual Studio 2017 インストーラーを実行](../build/media/vscpp-concierge-run-installer.gif "Visual Studio インストーラーを実行")

1. インストーラーによってワークロードの一覧が表示されます。これは、特定の開発分野の関連オプションのグループです。 C++ のサポートは、既定ではインストールされていないオプションのワークロードの一部です。

   ![C++ によるデスクトップ開発](../build/media/desktop-development-with-cpp.png "C++ によるデスクトップ開発")

    C++ の場合は、**[C++ ワークロードを使用したデスクトップ開発]** を選択し、それから **[インストール]** を選択してください。

   ![C++ のワークロードを使用したデスクトップ開発をインストール](../build/media/vscpp-concierge-choose-workload.gif "C++ ワークロードでのデスクトップ開発のインストール")

1. インストールが完了したら、**[起動]** ボタンを選択して Visual Studio を起動します。

   初めて Visual Studio を実行する時には、Microsoft アカウントでサインインするように求められます。 アカウントをお持ちでない場合は、新しいアカウントを無料で作成できます。 テーマを選択する必要もあります。 後で変更することもできるので、ご安心ください。 

   初めて実行する場合、Visual Studio の準備に数分かかる場合があります。 どのようになるかを、短いコマ撮りで次に示します。


   ![Visual Studio 2017 のサインイン](../build/media/vscpp-quickstart-first-run.gif "Visual Studio 2017 のサインイン")

   Visual Studio は、二回目の起動からは、とても高速に起動します。

1. Visual Studio が開いたらは、タイトル バーでフラグ アイコンが強調表示されているかどうかを確認します。

   ![Visual Studio 2017 の通知フラグ](../build/media/vscpp-first-start-page-flag.png "Visual Studio 2017 の通知フラグ")

   強調表示されて選択を開くには、**通知**ウィンドウです。 Visual Studio に利用可能な更新プログラムがある場合には、今すぐインストールすることをお勧めします。 インストールが完了したら、Visual Studio を再起動してください。

Visual Studio が実行されている場合は、次の手順に進む準備ができています。

## <a name="next-steps"></a>次の手順

> [!div class="nextstepaction"]
> [C++ プロジェクトの作成](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
||||||| merged common ancestors
---
title: Visual Studio での C++ のサポートのインストール |Microsoft ドキュメント
description: Visual Studio の Visual C サポートをインストールします。
ms.custom: mvc
ms.date: 12/12/2017
ms.topic: tutorial
ms.technology:
- devlang-C++
ms.devlang: C++
dev_langs:
- C++
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69092cdd6d79197fb7a2cbdc60b783174b70950b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="install-c-support-in-visual-studio"></a>Visual Studio での C++ のサポートをインストールします。

ダウンロードし、Visual Studio および Visual C ツールをまだインストールしていない場合は、作業を開始する方法を次に示します。

## <a name="prerequisites"></a>必須コンポーネント

- ブロード バンド インターネット接続を使用します。 Visual Studio インストーラーには数ギガバイトのデータをダウンロードできます。

- Microsoft Windows 7 またはそれ以降のバージョンを実行するコンピューター。 Windows 10 は、最適な開発エクスペリエンスをお勧めします。 Visual Studio をインストールする前に、システムに最新の更新プログラムが適用されていることを確認してください。

- 十分な空きディスク領域。 Visual Studio では、7 GB 以上のディスク領域が必要ですし、多くの一般的なオプションがインストールされている場合、50 GB 以上かかることができます。 C: ドライブにインストールすることをお勧めします。

ディスク容量とオペレーティング システムの要件の詳細については、「 [Visual Studio 2017 のシステム要件](https://www.visualstudio.com/productinfo/vs2017-system-requirements-vs)です。 インストーラーにより、選択したオプションに必要なディスク領域の量が報告されます。

## <a name="installation"></a>インストール

1. Windows の最新の Visual Studio 2017 インストーラーをダウンロードします。

   > [!div class="nextstepaction"]
   > <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Community&rel=15&utm_source=docs&utm_medium=clickbutton">Visual Studio 2017 のインストールに関するコミュニティ</a>

   >[!Tip]
   > このコミュニティ版は、個人の開発者、クラス学習、学術研究、オープン ソース開発向けです。 その他の用途には、<a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Professional&rel=15&utm_source=docs&utm_medium=clickbutton">Visual Studio 2017 Professional</a> または <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Enterprise&rel=15&utm_source=docs&utm_medium=clickbutton">Visual Studio 2017 Enterprise</a> を使用してください。

1. インストーラー ファイルをダウンロードして実行を検索します。 ブラウザーに表示される可能性や、ダウンロード フォルダーで検索することがあります。 インストーラーでは、管理者特権を実行する必要があります。 表示される、**ユーザー アカウント制御**インストーラーは、システムに変更を加える; を選択できるようにするアクセス許可を付与するように求めるダイアログ**はい**です。 ファイル エクスプ ローラーで、ダウンロードしたファイルを検索に問題が発生した場合、インストーラーのアイコンを右クリックし、選択**管理者として実行**コンテキスト メニュー。

   ![Visual Studio 2017 インストーラーを実行して](../build/media/vscpp-concierge-run-installer.gif "Visual Studio のインストーラーを実行")

1. インストーラーによって、ワークロード一覧が表示されます。これは、特定の開発分野の関連オプションのグループです。 C++ のサポートは、既定でインストールされていないオプションのワークロードの一部ではようになりました。

   ![C++ を使用したデスクトップ開発](../build/media/desktop-development-with-cpp.png "C++ を使用したデスクトップの開発")

    C++ では、選択、 **C++ を使用したデスクトップ開発**ワークロードを選択し**インストール**です。

   ![C++ のワークロードでデスクトップの開発をインストール](../build/media/vscpp-concierge-choose-workload.gif "C++ ワークロードでデスクトップ開発のインストール")

1. インストールが完了したら、選択、**起動**Visual Studio を起動するボタンをクリックします。

   初めて Visual Studio を実行する Microsoft アカウントでサインインするように求められます。 それらのいずれのアカウントもない場合は、新しいアカウントを無料で作成できます。 また、テーマを選択する必要があります。 ご安心くださいする場合は後で変更することができます。 

   Visual Studio をいくつかでかかる場合がありますの準備を整えるを使用して最初に実行する (分) です。 どのように、簡単なコマで次に示します。

   ![Visual Studio 2017 がサインイン](../build/media/vscpp-quickstart-first-run.gif "Visual Studio 2017 のサインイン")

   Visual Studio は、もう一度実行すると非常に高速起動します。

1. Visual Studio が開いたら、タイトル バーのフラグ アイコンを強調表示するかを確認します。

   ![Visual Studio 2017 通知フラグ](../build/media/vscpp-first-start-page-flag.png "Visual Studio 2017 通知フラグ")

   強調表示されて選択を開くには、**通知**ウィンドウです。 更新プログラムを Visual Studio の使用可能な場合は、今すぐインストールするをお勧めします。 インストールが完了したら、Visual Studio を再起動します。

Visual Studio が実行されている場合は、次の手順を続行する準備ができたらです。

## <a name="next-steps"></a>次の手順

> [!div class="nextstepaction"]
> [C++ プロジェクトを作成します。](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
=======
---
title: Visual Studio での C++ のサポートのインストール |Microsoft ドキュメント
description: Visual Studio の Visual C サポートをインストールします。
ms.custom: mvc
ms.date: 12/12/2017
ms.topic: tutorial
ms.technology:
- devlang-C++
ms.devlang: C++
dev_langs:
- C++
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69092cdd6d79197fb7a2cbdc60b783174b70950b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="install-c-support-in-visual-studio"></a>Visual Studio での C++ のサポートをインストール

まだ Visual Studio および Visual C++ ツールをダウンロードおよびインストールしていない場合は、次の方法で作業を開始できます。

## <a name="prerequisites"></a>必須コンポーネント

- ブロードバンド インターネットの接続。 Visual Studio インストーラーでは数ギガバイトのデータをダウンロードします。

- Microsoft Windows 7 またはそれ以降のバージョンを実行するコンピューター。開発のベスト エクスペリエンスを実現するには Windows 10 をお勧めします。Visual Studio をインストールする前に、システムに最新の更新プログラムが適用されていることを確認してください。

- 十分な空きディスク領域。 Visual Studio では、7 GB 以上のディスク領域が必要ですし、多くの一般的なオプションがインストールされている場合、50 GB 以上かかることができます。 C: ドライブにインストールすることをお勧めします。

ディスク容量とオペレーティング システムの要件の詳細については、「 [Visual Studio 2017 のシステム要件](https://www.visualstudio.com/productinfo/vs2017-system-requirements-vs)です。 インストーラーにより、選択したオプションに必要なディスク領域の量が報告されます。

## <a name="installation"></a>インストール

1. Windows の最新の Visual Studio 2017 インストーラーをダウンロードします。

   > [!div class="nextstepaction"]
   > <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Community&rel=15&utm_source=docs&utm_medium=clickbutton">Visual Studio 2017 のインストールに関するコミュニティ</a>

   >[!Tip]
   > このコミュニティ版は、個人の開発者、クラス学習、学術研究、オープン ソース開発向けです。 その他の用途には、<a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Professional&rel=15&utm_source=docs&utm_medium=clickbutton">Visual Studio 2017 Professional</a> または <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Enterprise&rel=15&utm_source=docs&utm_medium=clickbutton">Visual Studio 2017 Enterprise</a> を使用してください。

2. ダウンロードしたインストーラー ファイルを検索して実行します。ブラウザーに表示されるか、ダウンロード フォルダーで見つかるでしょう。インストーラーを実行するには、管理者特権が必要です。インストーラーでシステムに変更を加えることを可能にするアクセス許可を付与するかどうかを求める **[ユーザーアカウント制御]** ダイアログが表示されます。**[はい]**を選択してください。問題が発生した場合、エクスプローラーでダウンロードしたファイルを検索し、インストーラーのアイコンを右クリックし、コンテキスト メニューから **[管理者として実行]** を選択してください。

   ![Visual Studio 2017 インストーラーを実行して](../build/media/vscpp-concierge-run-installer.gif "Visual Studio のインストーラーを実行")

3. インストーラーによってワークロードの一覧が表示されます。これは、特定の開発分野の関連オプションのグループです。C++ のサポートは、既定ではインストールされていないオプションのワークロードの一部です。

   ![C++ を使用したデスクトップ開発](../build/media/desktop-development-with-cpp.png "C++ を使用したデスクトップの開発")

    C++ の場合は、**[C++ ワークロードを使用したデスクトップ開発]** を選択し、それから **[インストール]** を選択してください。

   ![C++ のワークロードでデスクトップの開発をインストール](../build/media/vscpp-concierge-choose-workload.gif "C++ ワークロードでデスクトップ開発のインストール")

4. インストールが完了したら、**[起動]** ボタンを選択して Visual Studio を起動します。

   初めて Visual Studio を実行する時には、Microsoft アカウントでサインインするように求められます。アカウントをお持ちでない場合は、新しいアカウントを無料で作成できます。テーマを選択する必要もあります。後で変更することもできるので、ご安心ください。 

   初めて実行する場合、Visual Studio の準備に数分かかる場合があります。どのようになるかを、短いコマ撮りで次に示します。

   ![Visual Studio 2017 がサインイン](../build/media/vscpp-quickstart-first-run.gif "Visual Studio 2017 のサインイン")

   Visual Studio は、二回目の起動からは、とても高速に起動します。

1. Visual Studio が開いたら、タイトル バーのフラグ アイコンを強調表示するかを確認します。

   ![Visual Studio 2017 通知フラグ](../build/media/vscpp-first-start-page-flag.png "Visual Studio 2017 通知フラグ")

   強調表示されている場合、それを選択して **[通知]** ウィンドウを開きます。Visual Studio に利用可能な更新プログラムがある場合には、今すぐインストールすることをお勧めします。インストールが完了したら、Visual Studio を再起動してください。

Visual Studio が実行されている場合は、次の手順に進む準備ができています。

## <a name="next-steps"></a>次の手順

> [!div class="nextstepaction"]
> [C++ プロジェクトの作成](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
>>>>>>> live
