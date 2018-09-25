---
title: Visual Studio 2017 で C++ サポートのインストール |Microsoft Docs
description: Visual Studio の Visual C サポートをインストールします。
ms.custom: mvc
ms.date: 09/17/2018
ms.topic: tutorial
ms.technology:
- cpp-tools
ms.devlang: C++
dev_langs:
- C++
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80e84bb7c81ccd9c3347989e68041125993ee73c
ms.sourcegitcommit: 92c568e9466ffd7346a4120c478c9bdea61c8756
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2018
ms.locfileid: "47029633"
---
# <a name="install-c-support-in-visual-studio"></a>Visual Studio での C++ のサポートをインストール

ダウンロードし、Visual Studio 2017 と Visual C ツールをまだインストールしていない場合、開始する方法を示します。

## <a name="prerequisites"></a>必須コンポーネント

- ブロードバンド インターネットの接続。 Visual Studio インストーラーでは数ギガバイトのデータをダウンロードします。

- Microsoft Windows 7 またはそれ以降のバージョンを実行するコンピューター。 開発のベスト エクスペリエンスを実現するには Windows 10 をお勧めします。 Visual Studio をインストールする前に、システムに最新の更新プログラムが適用されることを確認します。

- 十分な空きディスク領域。 Visual Studio では、7 GB 以上のディスク領域が必要ですし、多くの一般的なオプションがインストールされている場合、50 GB 以上かかることができます。 C: ドライブにインストールすることをお勧めします。

ディスク容量とオペレーティング システムの要件の詳細については、次を参照してください。 [Visual Studio 製品ファミリのシステム要件](/visualstudio/productinfo/vs2017-system-requirements-vs)します。 インストーラーにより、選択したオプションに必要なディスク領域の量が報告されます。

## <a name="visual-studio-2015-installation"></a>Visual Studio 2015 のインストール

Visual Studio 2015 をインストールするには、[以前のバージョンの Visual Studio のダウンロード](https://www.visualstudio.com/vs/older-downloads/) ページに移動してください。 セットアップ プログラムを実行し、**カスタム インストール**で C++ コンポーネントを選択します。 既存の Visual Studio 2015 インストールには、C++ のサポートを追加するには、種類と Windows のスタート ボタンをクリックして**プログラムの追加と削除**します。 結果の一覧からプログラムを開き、インストールされているプログラムの一覧で、Visual Studio 2015 のインストールを検索します。 選択し、それをダブルクリックして**変更**をインストールする Visual C コンポーネントを選択します。

一般に、Visual Studio 2015 のコンパイラを使用してコードをコンパイルする必要がある場合でも、Visual Studio 2017 を使用することを強くお勧めします。 詳細については、「[Visual Studio でネイティブ マルチ ターゲットを利用し、古いプロジェクトを作成する](../porting/use-native-multi-targeting.md)」を参照してください。

## <a name="visual-studio-2017-installation"></a>Visual Studio 2017 のインストール

1. Windows の最新の Visual Studio 2017 インストーラーをダウンロードします。

   > [!div class="nextstepaction"]
   > [Visual Studio 2017 のインストールに関するコミュニティ](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

   >[!Tip]
   > このコミュニティ版は、個人の開発者、クラス学習、学術研究、オープン ソース開発向けです。 その他の用途には、[Visual Studio 2017 Professional](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) または [Visual Studio 2017 Enterprise](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) を使用してください。

1. ダウンロードしたインストーラー ファイルを検索して実行します。 ブラウザーに表示されるか、ダウンロード フォルダーで見つかるでしょう。 インストーラーを実行するには、管理者特権が必要です。 インストーラーでシステムに変更を加えることを可能にするアクセス許可を付与するかどうかを求める **[ユーザーアカウント制御]** ダイアログが表示されます **。** 問題が発生した場合、エクスプローラーでダウンロードしたファイルを検索し、インストーラーのアイコンを右クリックし、コンテキスト メニューから **[管理者として実行]** を選択してください。

   ![Visual Studio 2017 インストーラーを実行](../build/media/vscpp-concierge-run-installer.gif "Visual Studio インストーラーを実行")

1. インストーラーによってワークロードの一覧が表示されます。これは、特定の開発分野の関連オプションのグループです。 C++ のサポートは、既定ではインストールされていないオプションのワークロードの一部です。

   ![C++ によるデスクトップ開発](../build/media/desktop-development-with-cpp.png "C++ によるデスクトップ開発")

   C++ の場合は、**[C++ ワークロードを使用したデスクトップ開発]** を選択し、それから **[インストール]** を選択してください。

   ![C++ のワークロードを使用したデスクトップ開発をインストール](../build/media/vscpp-concierge-choose-workload.gif "C++ ワークロードでのデスクトップ開発のインストール")

1. インストールが完了したら、**[起動]** ボタンを選択して Visual Studio を起動します。

   初めて Visual Studio を実行する時には、Microsoft アカウントでサインインするように求められます。 アカウントをお持ちでない場合は、新しいアカウントを無料で作成できます。 テーマを選択する必要もあります。 後で変更することもできるので、ご安心ください。

   Visual Studio をいくつかでかかる場合がありますを準備する分を使用して、初めて実行します。 どのようになるかを、短いコマ撮りで次に示します。


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
