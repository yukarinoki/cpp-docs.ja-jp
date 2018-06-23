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

もし、まだダウンロードしておらず、Visual Studio および Visual C++ ツールをまだインストールしていない場合には、次の方法で作業を開始できます。

## <a name="prerequisites"></a>必須コンポーネント

- ブロードバンド インターネットの接続。 Visual Studio インストーラーでは数ギガバイトのデータをダウンロードします。

- Microsoft Windows 7 またはそれ以降のバージョンを実行するコンピューター。 Windows 10 を、最適な開発の体感のため、お勧めします。 Visual Studio をインストールする前に、システムに最新の更新プログラムが適用されていることを確認してください。

- 十分な空きディスク領域。 Visual Studio では、7 GB 以上のディスク領域が必要ですし、多くの一般的なオプションがインストールされている場合、50 GB 以上かかることができます。 C: ドライブにインストールすることをお勧めします。

ディスク容量とオペレーティング システムの要件の詳細については、「 [Visual Studio 2017 のシステム要件](https://www.visualstudio.com/productinfo/vs2017-system-requirements-vs)です。 インストーラーにより、選択したオプションに必要なディスク領域の量が報告されます。

## <a name="installation"></a>インストール

1. Windows の最新の Visual Studio 2017 インストーラーをダウンロードします。

   > [!div class="nextstepaction"]
   > <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Community&rel=15&utm_source=docs&utm_medium=clickbutton">Visual Studio 2017 のインストールに関するコミュニティ</a>

   >[!Tip]
   > このコミュニティ版は、個人の開発者、クラス学習、学術研究、オープン ソース開発向けです。 その他の用途には、<a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Professional&rel=15&utm_source=docs&utm_medium=clickbutton">Visual Studio 2017 Professional</a> または <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Enterprise&rel=15&utm_source=docs&utm_medium=clickbutton">Visual Studio 2017 Enterprise</a> を使用してください。

1. インストーラー ファイルをダウンロードして実行します。 ブラウザーに表示される可能性や、ダウンロード フォルダーで見つかるでしょう。 インストーラーでは、管理者特権を実行する必要があります。 表示される、**ユーザーアカウント制御**ダイアログが、インストーラーがシステムに変更を加えるアクセス許可を付与するように求めてくるので、**はい**を選択してください。; 問題が発生した場合、ファイル エクスプローラーでダウンロードしたファイルを検索して、インストーラーのアイコンを右クリックし、コンテキスト メニューから**管理者として実行**を選択してください。

   ![Visual Studio 2017 インストーラーを実行して](../build/media/vscpp-concierge-run-installer.gif "Visual Studio のインストーラーを実行")

1. インストーラーがワークロード一覧を表示します。これは、特定の開発分野の関連オプションのグループです。 C++ のサポートでは、オプションのワークロードの一部が、既定ではインストールされていません。

   ![C++ を使用したデスクトップ開発](../build/media/desktop-development-with-cpp.png "C++ を使用したデスクトップの開発")

    C++ のために、 **C++ ワークロードを使用したデスクトップ開発**を選択し、それから**インストール**してください。

   ![C++ のワークロードでデスクトップの開発をインストール](../build/media/vscpp-concierge-choose-workload.gif "C++ ワークロードでデスクトップ開発のインストール")

1. インストールが完了したら、**起動**ボタンを選択すれば、Visual Studio が起動されます。

   初めて Visual Studio を実行する時には、 Microsoft アカウントでサインインするように求められます。 それらのいずれのアカウントもない場合は、新しいアカウントを無料で作成できます。 また、テーマを選択する必要があります。 ご安心ください、後でも変更できます。 

   最初の実行では、Visual Studio の準備に数分かかる場合があります。 どのようになるかを、簡単なコマで次に示します。

   ![Visual Studio 2017 がサインイン](../build/media/vscpp-quickstart-first-run.gif "Visual Studio 2017 のサインイン")

   Visual Studio は、二回目の起動からは、とても高速に起動します。

1. Visual Studio が開いたら、タイトル バーのフラグ アイコンを強調表示するかを確認します。

   ![Visual Studio 2017 通知フラグ](../build/media/vscpp-first-start-page-flag.png "Visual Studio 2017 通知フラグ")

   強調表示されているものがあれば、それを選択すると**通知**ウィンドウが開かれます。  Visual Studio のための利用可能な更新プログラムがある場合には、今すぐインストールすることをお勧めします。 インストールが完了したら、Visual Studio を再起動してください。

Visual Studio が実行されている時は、次の手順を続行する準備ができています。

## <a name="next-steps"></a>次の手順

> [!div class="nextstepaction"]
> [C++ プロジェクトの作成](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
