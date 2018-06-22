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

C++ コンソール アプリケーション プロジェクトを作成し、コードを入力すれば、Visual Studio 内で実行することによりビルドできます。コマンドラインからスタンドアロンのアプリとして実行します。

## <a name="prerequisites"></a>必須コンポーネント

- コンピュータにインストールされ、実行されているC ++ワークロードを備えたデスクトップ開発には、Visual Studioがあります。 まだインストールされていない場合は次の手順に従います [Visual Studio での C++ のインストール サポート](../build/vscpp-step-0-installation.md) 。

- 「Hello, World!」プロジェクトを作成し、そのソース コードを入力します。 まだ完了していない場合は次の手順に従います [C++ コンソール アプリケーション プロジェクトを作成](../build/vscpp-step-1-create.md)。

もし Visual Studio が次のような外観なら、アプリをビルドして実行する準備はできています。

   ![新しいプロジェクトをビルドする準備ができて](../build/media/vscpp-ready-to-build.png "新しいプロジェクトをビルドする準備完了")

## <a name="build-and-run-your-code-in-visual-studio"></a>ビルドおよび Visual Studio でコードを実行します。

1. プロジェクトをビルドするには、**ビルド** メニューから **ソリューションのビルド** を選択します。 **出力** ウィンドウは、ビルド プロセスの結果を示しています。

   ![プロジェクトをビルド](../build/media/vscpp-build-solution.gif "プロジェクトをビルドします")

2. コードを実行するには、メニュー バー上にある **デバッグ** を選び、それから **デバッグなしで開始** を選んでください。

   ![プロジェクトの開始、](../build/media/vscpp-start-without-debugging.gif "プロジェクトの開始")

    Visual Studio 内でコンソール ウィンドウが開かれ、アプリが実行されます。 コードが実行された後に、「続行するには何かキーを押してください. . .」と表示されますので、出力の表示を見れる機会があります。

おめでとうございます! あなたは最初の「Hello, world!」コンソール アプリをVisual Studio で作成しました。 任意のキーを押せば、コンソール ウィンドウが閉じられ、Visual Studio に戻ります。

[問題が発生しました。](#build-and-run-your-code-in-visual-studio-issues)

## <a name="run-your-code-in-a-command-window"></a>コマンド ウィンドウで、コードを実行します。

通常、コンソール アプリを実行したい場合には、Visual Studio ではなくコマンド プロンプトで実行するのが大半です。 Visual Studio によってアプリをビルドする場合は、任意のコマンド ウィンドウから実行できます。コマンド プロンプト ウィンドウで検索して、新しいアプリを実行する方法を次に示します。

1. **ソリューション エクスプ ローラー**HelloWorld ソリューションを選択して、右クリックして、コンテキスト メニューを開きます。 選択**ファイル エクスプ ローラーでフォルダーを開く**を開くには、**ファイル エクスプ ローラー** HelloWorld ソリューション フォルダー内のウィンドウ。

1. **ファイル エクスプ ローラー**ウィンドウがデバッグ フォルダーを開きます。 これは、アプリ、HelloWorld.exe、およびその他のデバッグ ファイルのいくつか含まれています。 HelloWorld.exe を選択し、Shift キーを押しながらを開くには、コンテキスト メニューを右クリックします。 選択**パスとしてコピー**をクリップボードにアプリのパスをコピーします。

1. コマンド プロンプト ウィンドウを開くには、Windows の R キーを押して、**実行**ダイアログ。 入力*cmd.exe*で、**開く** ボックスを選択し、 **ok**コマンド プロンプト ウィンドウを実行します。

1. コマンド プロンプト ウィンドウで右クリックし、コマンド プロンプトに、アプリへのパスを貼り付けます。 Enter キーを押して、アプリを実行します。

   ![コマンド プロンプトで、アプリを実行](../build/media/vscpp-run-in-cmd.gif "コマンド プロンプトで、アプリを実行")

以上で、ビルドを Visual Studio で、コンソール アプリケーションを実行しました。

[問題が発生しました。](#run-your-code-in-a-command-window-issues)

## <a name="next-steps"></a>次の手順

オブジェクトを構築し、この簡単なアプリを実行したら後、より複雑なプロジェクトの準備ができました。Visual Studio でのチュートリアル、Visual C の機能の詳細は次を参照してください[C++ デスクトップ開発用 Visual Studio IDE を使用して](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)。

## <a name="troubleshooting-guide"></a>トラブルシューティング ガイド

最初の C++ プロジェクトの作成での一般的な問題の発生時のソリューションは、ここを参照してください。

### <a name="build-and-run-your-code-in-visual-studio-issues"></a>ビルドおよび Visual Studio の問題、コードを実行します。

ソース コード エディターで赤い波線が下に表示される場合、ビルドにエラーまたは警告があります。 コードが、スペル、句読点、および大文字小文字の例と一致することを確認してください。

[戻る。](#build-and-run-your-code-in-visual-studio)

### <a name="run-your-code-in-a-command-window-issues"></a>コマンド ウィンドウで、コードを実行の問題

アプリを実行するコマンドラインで、ソリューションのデバッグ フォルダーに移動することもできます。 アプリへのパスを指定せず、他のディレクトリからアプリを実行することはできません。 ただし、アプリを別のディレクトリにコピーし、そこから実行します。

表示されない場合**パスとしてコピー**ショートカット メニューで、メニューを閉じるし、Shift キーを押しながら、もう一度開きます。 これは、便宜上だけです。 フォルダーに、ファイル エクスプ ローラーの検索バーからパスをコピーして貼り付けます、**実行**ダイアログ ボックスで、最後に実行可能ファイルの名前を入力します。 ほんの少しだけ多くの入力しますが、同じ結果があります。

[戻る。](#run-your-code-in-a-command-window)


<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
