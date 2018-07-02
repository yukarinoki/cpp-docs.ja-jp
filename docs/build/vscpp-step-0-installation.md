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
