---
title: C++ コンソール アプリケーション プロジェクト のビルドおよび実行 |Microsoft ドキュメント
description: Visual C での Hello World コンソール アプリをビルドおよび実行します。
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

C++ コンソール アプリケーション プロジェクトを作成しコードを入力すれば、Visual Studio 内でビルドできるし、実行もできます。そして、コマンドラインからスタンドアロンのアプリとしても実行できます。

## <a name="prerequisites"></a>前提の要件

- コンピュータにインストールされ、実行されているC ++ワークロードを備えたデスクトップ開発に、Visual Studioがあること。 まだインストールされていない場合は次の手順に従います [Visual Studio での C++ のインストール サポート](../build/vscpp-step-0-installation.md) 。

- 「Hello, World!」プロジェクトを作成し、そのソース コードを入力してあること。 まだ完了していない場合は次の手順に従います [C++ コンソール アプリケーション プロジェクトを作成](../build/vscpp-step-1-create.md)。

もし Visual Studio が次のような外観なら、アプリをビルドして実行する準備はできています。

   ![新しいプロジェクトをビルドする準備ができて](../build/media/vscpp-ready-to-build.png "新しいプロジェクトをビルドする準備完了")

## <a name="build-and-run-your-code-in-visual-studio"></a> Visual Studio でのコードのビルドおよびコードを実行

1. プロジェクトをビルドするには、**ビルド** メニューから **ソリューションのビルド** を選択します。 **出力** ウィンドウは、ビルド プロセスの結果を示しています。

   ![プロジェクトをビルド](../build/media/vscpp-build-solution.gif "プロジェクトをビルドします")

2. コードを実行するには、メニュー バー上にある **デバッグ** を選び、それから **デバッグなしで開始** を選んでください。

   ![プロジェクトの開始、](../build/media/vscpp-start-without-debugging.gif "プロジェクトの開始")

    Visual Studio 内でコンソール ウィンドウが開かれ、アプリが実行されます。 コードが実行された後に、「続行するには何かキーを押してください. . .」と表示されますので、出力の表示を見れる機会があります。

おめでとうございます! あなたは最初の「Hello, world!」コンソール アプリを Visual Studio で作成しました。 任意のキーを押せば、コンソール ウィンドウが閉じられ、Visual Studio に戻ります。

[問題が発生しました。](#build-and-run-your-code-in-visual-studio-issues)

## <a name="run-your-code-in-a-command-window"></a>コマンド ウィンドウで、コードを実行します。

通常、コンソール アプリを実行したい場合には、Visual Studio ではなくコマンド プロンプトで実行するのが大半です。 Visual Studio によってビルドされたアプリは、任意のコマンド ウィンドウから実行できます。コマンド プロンプト ウィンドウで検索して、新しいアプリを実行する方法を次に示します。

1. **ソリューション エクスプ ローラー** HelloWorld ソリューションを選択した状態で右クリックすると、コンテキスト メニューが開かれます。 その中から**ファイル エクスプローラーでフォルダーを開く**を選択すると、**ファイル エクスプローラー** ウィンドウによって HelloWorld ソリューション フォルダー内が開かれます。

1. **ファイル エクスプ ローラー**ウィンドウに現在いるので、デバッグ フォルダーを開きます。 これは、アプリ、HelloWorld.exe、およびその他のデバッグ ファイルのいくつか含まれています。 HelloWorld.exe を選択してある状態で、Shift キーと右クリックを押すと、コンテキスト メニューが開かれます。メニューにある**パスとしてコピー**を選択すれば、クリップボードにアプリのパスがコピーされます。

1. コマンド プロンプト ウィンドウを開くには、Windows キーを押しながら R キーを押せば、ダイアログが**開かれます**。 **開かれた** ダイアログ内のテキストボックスに*cmd.exe*と入力してから、**ok**ボタンを選択すれば、 コマンド プロンプト ウィンドウが起動します。

1. コマンド プロンプト ウィンドウで右クリックし、コマンド プロンプトに、アプリへのパスを貼り付けます。それから Enter キーを押せば、アプリが実行されます。

   ![コマンド プロンプトで、アプリを実行](../build/media/vscpp-run-in-cmd.gif "コマンド プロンプトで、アプリを実行")

おめでとう！ 以上で、Visual Studio にて、コンソール アプリケーションのビルドおよび実行をしました。

[問題が発生しました。](#run-your-code-in-a-command-window-issues)

## <a name="next-steps"></a>次の手順

この簡単なアプリをビルドおよび実行したなら、より複雑なプロジェクトの準備ができました。Visual Studio でのチュートリアル、Visual C の機能の詳細は次を参照してください[C++ デスクトップ開発用 Visual Studio IDE を使用して](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)。

## <a name="troubleshooting-guide"></a>トラブルシューティング ガイド

最初の C++ プロジェクトの作成での一般的な問題の発生時における解決策が必要なら、ここを参照してください。

### <a name="build-and-run-your-code-in-visual-studio-issues"></a>Visual Studio での問題のあるコードのビルドおよび実行

ソースコード エディターで赤い波線が下に表示される場合、ビルドにエラーまたは警告があります。 コードが、スペル、句読点、および大文字小文字の例と一致することを確認してください。

[戻る。](#build-and-run-your-code-in-visual-studio)

### <a name="run-your-code-in-a-command-window-issues"></a>コマンド ウィンドウで、コードを実行の問題

アプリを実行するコマンドラインで、ソリューションのデバッグ フォルダーに移動することもできます。 アプリへのパスを指定せず、他のディレクトリからアプリを実行することはできません。 ただし、アプリを別のディレクトリにコピーし、そこから実行します。

表示されない場合**パスとしてコピー**ショートカット メニューで、メニューを閉じるし、Shift キーを押しながら、もう一度開きます。 これは、便宜上だけです。 フォルダーに、ファイル エクスプ ローラーの検索バーからパスをコピーして貼り付けます、**実行**ダイアログ ボックスで、最後に実行可能ファイルの名前を入力します。 ほんの少しだけ多くの入力しますが、同じ結果があります。

[戻る。](#run-your-code-in-a-command-window)


<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
