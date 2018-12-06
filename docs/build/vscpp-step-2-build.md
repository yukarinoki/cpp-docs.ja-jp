---
title: ビルドおよび C++ コンソール アプリ プロジェクトの実行
description: Visual C での Hello World コンソール アプリをビルドおよび実行します。
ms.custom: mvc
ms.date: 12/12/2017
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d71-719d-42dc-90d7-1d0ca31a2f55
ms.openlocfilehash: 09780d5823190eb4cb3b4ad13bb60e33808e4987
ms.sourcegitcommit: beeb77b2976e997debc55b1af35024cc62e62799
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2018
ms.locfileid: "52977733"
---
# <a name="build-and-run-a-c-console-app-project"></a>ビルドおよび C++ コンソール アプリ プロジェクトの実行

C++ コンソール アプリケーション プロジェクトを作成しコードを入力すれば、Visual Studio 内でビルドおよび実行できます。そして、コマンドラインからスタンドアロンのアプリとしても実行できます。

## <a name="prerequisites"></a>前提条件

- コンピューターに C ++ によるデスクトップ開発のワークロードを備えた Visual Studio をインストールして実行します。 まだインストールされていない場合は、「[Visual Studio での C++ のインストール サポート](../build/vscpp-step-0-installation.md)」の手順に従います。

- 「Hello, World!」プロジェクトを作成し、 そのソース コードを入力します。 まだ行っていない場合は、「[C++ コンソール アプリケーション プロジェクトを作成](../build/vscpp-step-1-create.md)」の手順に従います。

もし Visual Studio が次のような外観なら、アプリをビルドして実行する準備はできています。

   ![新しいプロジェクトをビルドする準備ができて](../build/media/vscpp-ready-to-build.png "新しいプロジェクトを構築する準備")

## <a name="build-and-run-your-code-in-visual-studio"></a>Visual Studio でのビルドおよびコードの実行

1. プロジェクトをビルドするには、**ビルド** メニューから **ソリューションのビルド** を選択します。 **出力** ウィンドウは、ビルド プロセスの結果を示しています。

   ![プロジェクトをビルド](../build/media/vscpp-build-solution.gif "プロジェクトをビルドします")

1. コードを実行するには、メニュー バー上にある **デバッグ** を選び、それから **デバッグなしで開始** を選んでください。

   ![プロジェクトを開始する](../build/media/vscpp-start-without-debugging.gif "プロジェクトを開始します")

   Visual Studio 内でコンソール ウィンドウが開かれ、アプリが実行されます。 コードが実行された後に、「続行するには何かキーを押してください. . .」 . ." と表示されますので、出力の表示を見れる機会があります。

おめでとうございます! 初めての「Hello, world!」 コンソール アプリが Visual Studio で作成されました。 任意のキーを押せば、コンソール ウィンドウが閉じられ、Visual Studio に戻ります。

[問題が発生しました](#build-and-run-your-code-in-visual-studio-issues)

## <a name="run-your-code-in-a-command-window"></a>コマンド ウィンドウで、コードを実行します。

通常、コンソール アプリは Visual Studio ではなく、コマンド プロンプトで実行します。 一度 Visual Studio でアプリがビルドされたら、任意のコマンド ウィンドウから実行できます。 コマンド プロンプト ウィンドウで新しいアプリを検索し実行する方法を次に示します。

1. **[ソリューション エクスプ ローラー]** で、HelloWorld ソリューションを選択し、右クリックしてコンテキスト メニューを開きます。 **[エクスプローラーでフォルダーを開く]** を選択し、HelloWorld ソリューション フォルダーで **[エクスプローラー]** ウィンドウを開きます。

1. **[ファイル エクスプ ローラー]** ウィンドウで [デバッグ] フォルダーを開きます。 これには、アプリ、HelloWorld.exe、および他のいくつかのデバッグ ファイルが含まれています。 HelloWorld.exe を選択し、Shift キーを押しながら右クリックしてコンテキスト メニューを開きます。 **[パスとしてコピー]** を選択し、アプリへのパスをクリップボードにコピーします。

1. コマンド プロンプト ウィンドウを開くには、Windows-R キーを押して、**実行**ダイアログ。 入力*cmd.exe*で、**オープン** ボックスに、選択し、 **ok**コマンド プロンプト ウィンドウを実行します。

1. コマンド プロンプト ウィンドウで右クリックし、コマンド プロンプトに、アプリへのパスを貼り付けます。 アプリを実行するには、enter キーを押します。

   ![コマンド プロンプトで、アプリを実行](../build/media/vscpp-run-in-cmd.gif "コマンド プロンプトで、アプリの実行")

これで、ビルドし、Visual Studio でコンソール アプリを実行しました。

[問題が発生しました](#run-your-code-in-a-command-window-issues)

## <a name="next-steps"></a>次の手順

オブジェクトを構築し、この簡単なアプリを実行したら後、より複雑なプロジェクトの準備ができました。 Visual Studio でのチュートリアル、Visual C の機能の詳細は次を参照してください[C++ デスクトップ開発用 Visual Studio IDE を使用して](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)。

## <a name="troubleshooting-guide"></a>トラブルシューティング ガイド

最初の C++ プロジェクトの作成での一般的な問題の発生時のソリューションは、ここを参照してください。

### <a name="build-and-run-your-code-in-visual-studio-issues"></a>ビルドし、Visual Studio の問題でコードを実行

ソース コード エディターで赤い波線が下に表示される場合、ビルドにエラーまたは警告があります。 コードが、スペル、句読点、および大文字小文字の例と一致することを確認してください。

[戻る。](#build-and-run-your-code-in-visual-studio)

### <a name="run-your-code-in-a-command-window-issues"></a>コマンド ウィンドウで、コードを実行の問題

アプリを実行するコマンドラインでソリューションのデバッグ フォルダーに移動することもできます。 アプリへのパスを指定せず、その他のディレクトリからアプリを実行することはできません。 ただし、アプリを別のディレクトリにコピーでき、そこから実行できます。

表示されない場合**パスとしてコピー**ショートカット メニューで、メニューを閉じるし、Shift キーを押しながら、もう一度開きます。 これは、利便性。 ファイル エクスプ ローラーの検索バーから、フォルダーにパスをコピーしてに貼り付けることができます、**実行**ダイアログ ボックスで、最後に、実行可能ファイルの名前を入力します。 ほんの少し詳細入力ですが、同じ結果があります。

[戻る。](#run-your-code-in-a-command-window)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
