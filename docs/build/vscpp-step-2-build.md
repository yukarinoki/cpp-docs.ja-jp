---
title: ビルドおよび実行する C++ コンソール アプリケーション プロジェクト |Microsoft ドキュメント
description: ビルドおよび Visual C での Hello World コンソール アプリを実行します。
ms.custom: mvc
ms.date: 12/12/2017
ms.topic: tutorial
ms.technology:
- devlang-C++
ms.devlang: C++
dev_langs:
- C++
ms.assetid: 45138d71-719d-42dc-90d7-1d0ca31a2f55
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa63175e086fcb22552d0b7fd027b380d9766739
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="build-and-run-a-c-console-app-project"></a>ビルドおよび実行する C++ コンソール アプリケーション プロジェクト

C++ コンソール アプリケーション プロジェクトを作成し、コードを入力したら、ときにビルドし、Visual Studio 内で実行してコマンドラインからスタンドアロンのアプリとして実行します。

## <a name="prerequisites"></a>必須コンポーネント

- インストールされているし、コンピューターで実行されている C++ ワークロードでデスクトップの開発に Visual Studio があります。 これがまだインストールされていない場合の手順に従います[Visual Studio での C++ のインストール サポート](../build/vscpp-step-0-installation.md)です。

- 「こんにちは, World!」を作成します。 プロジェクトをそのソース コードを入力します。 これはまだ完了していない場合の手順に従います[C++ コンソール アプリケーション プロジェクトを作成](../build/vscpp-step-1-create.md)です。

Visual Studio は次のようなビルドして、アプリを実行する準備ができたら。

   ![新しいプロジェクトをビルドする準備ができて](../build/media/vscpp-ready-to-build.png "新しいプロジェクトをビルドする準備完了")

## <a name="build-and-run-your-code-in-visual-studio"></a>ビルドおよび Visual Studio でコードを実行します。

1. プロジェクトをビルドするには選択**ソリューションのビルド**から、**ビルド**メニュー。 **出力**ウィンドウは、ビルド プロセスの結果を示しています。

   ![プロジェクトをビルド](../build/media/vscpp-build-solution.gif "プロジェクトをビルドします")

1. メニュー バーで、コードを実行する**デバッグ**、**デバッグなしで開始**です。

   ![プロジェクトの開始、](../build/media/vscpp-start-without-debugging.gif "プロジェクトの開始")

    コンソール ウィンドウが開き、アプリを実行します。 Visual Studio で、コンソール アプリを起動すると、コードを実行し、出力"、キーを押して続行します。 である必要があります。 ." 出力を表示する機会を提供します。

おめでとうございます!  作成した最初の「こんにちは, world!」 Visual Studio でコンソール アプリです。 コンソール ウィンドウを閉じ、Visual Studio に戻るキーを押します。

[問題が発生しました。](#build-and-run-your-code-in-visual-studio-issues)

## <a name="run-your-code-in-a-command-window"></a>コマンド ウィンドウで、コードを実行します。

通常、Visual Studio ではなく、コマンド プロンプトでコンソール アプリを実行します。 Visual Studio によってアプリをビルドするは、任意のコマンド ウィンドウから実行できます。 検索して、コマンド プロンプト ウィンドウで、新しいアプリを実行する方法を次に示します。

1. **ソリューション エクスプ ローラー**HelloWorld ソリューションを選択して、右クリックして、コンテキスト メニューを開きます。 選択**ファイル エクスプ ローラーでフォルダーを開く**を開くには、**ファイル エクスプ ローラー** HelloWorld ソリューション フォルダー内のウィンドウ。

1. **ファイル エクスプ ローラー**ウィンドウがデバッグ フォルダーを開きます。 これは、アプリ、HelloWorld.exe、およびその他のデバッグ ファイルのいくつか含まれています。 HelloWorld.exe を選択し、Shift キーを押しながらを開くには、コンテキスト メニューを右クリックします。 選択**パスとしてコピー**をクリップボードにアプリのパスをコピーします。

1. コマンド プロンプト ウィンドウを開くには、Windows の R キーを押して、**実行**ダイアログ。 入力*cmd.exe*で、**開く** ボックスを選択し、 **ok**コマンド プロンプト ウィンドウを実行します。

1. コマンド プロンプト ウィンドウで右クリックし、コマンド プロンプトに、アプリへのパスを貼り付けます。 Enter キーを押して、アプリを実行します。

   ![コマンド プロンプトで、アプリを実行](../build/media/vscpp-run-in-cmd.gif "コマンド プロンプトで、アプリを実行")

以上で、ビルドを Visual Studio で、コンソール アプリケーションを実行しました。

[問題が発生しました。](#run-your-code-in-a-command-window-issues)

## <a name="next-steps"></a>次の手順

オブジェクトを構築し、この簡単なアプリを実行したら後、より複雑なプロジェクトの準備ができました。 参照してください[C++ デスクトップ開発用 Visual Studio IDE を使用して](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)に関するチュートリアルを Visual Studio での Visual C の機能の詳細。

## <a name="troubleshooting-guide"></a>トラブルシューティング ガイド

ここでソリューションの一般的な問題時になる最初の C++ プロジェクトを作成します。

### <a name="build-and-run-your-code-in-visual-studio-issues"></a>ビルドおよび Visual Studio の問題、コードを実行します。

ソース コード エディターでは何も下にある赤い波線が表示されない場合、エラーまたは警告に、ビルドがあります。 コードが、スペル、句読点、および大文字小文字の例と一致することを確認してください。

[戻ってください。](#build-and-run-your-code-in-visual-studio)

### <a name="run-your-code-in-a-command-window-issues"></a>コマンド ウィンドウで、コードを実行の問題

アプリを実行するコマンドラインで、ソリューションのデバッグ フォルダーに移動することもできます。 アプリへのパスを指定せず、他のディレクトリからアプリを実行することはできません。 ただし、アプリを別のディレクトリにコピーし、そこから実行します。

表示されない場合**パスとしてコピー**ショートカット メニューで、メニューを閉じるし、Shift キーを押しながら、もう一度開きます。 これは、便宜上だけです。 フォルダーに、ファイル エクスプ ローラーの検索バーからパスをコピーして貼り付けます、**実行**ダイアログ ボックスで、最後に実行可能ファイルの名前を入力します。 ほんの少しだけ多くの入力しますが、同じ結果があります。

[戻ってください。](#run-your-code-in-a-command-window)


<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
