---
title: C++ コンソール アプリ プロジェクトのビルドと実行
description: Visual C++ で Hello World コンソール アプリをビルドして実行する
ms.custom: mvc
ms.date: 04/20/2020
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d71-719d-42dc-90d7-1d0ca31a2f55
ms.openlocfilehash: d1e92e598b370312730a7c4e208b935a264010bf
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749244"
---
# <a name="build-and-run-a-c-console-app-project"></a>C++ コンソール アプリ プロジェクトのビルドと実行

C++ コンソール アプリ プロジェクトを作成し、コードを入力しました。 これで、Visual Studio 内でビルドおよび実行できるようになりました。 次に、コマンド ラインからスタンドアロン アプリとして実行します。

## <a name="prerequisites"></a>必須コンポーネント

- Visual Studio 2019 と、C++ によるデスクトップ開発ワークロードがコンピューターにインストールおよび実行されている必要があります。 まだインストールされていない場合は、[Visual Studio での C++ サポートのインストール](vscpp-step-0-installation.md)に関するページを参照してください。

- "Hello, World!" プロジェクトを作成し、 そのソース コードを入力します。 まだこのステップを完了していない場合は、「[C++ コンソール アプリ プロジェクトを作成する](vscpp-step-1-create.md)」のステップに従ってください。

Visual Studio がこのような表示になったら、アプリをビルドして実行する準備ができています。

   ![新しいプロジェクトをビルドする準備が完了する](media/vscpp-ready-to-build.png "新しいプロジェクトをビルドする準備が完了する")

## <a name="build-and-run-your-code-in-visual-studio"></a>Visual Studio でコードをビルドして実行する

1. プロジェクトをビルドするには、 **[ビルド]** メニューの **[ソリューションのビルド]** を選択します。 **[出力]** ウィンドウに、ビルド プロセスの結果が表示されます。

   ![プロジェクトのビルド](media/vscpp-build-solution.gif "プロジェクトをビルドする")

1. コードを実行するには、メニュー バーで **[デバッグ]** 、 **[デバッグなしで開始]** の順に選択します。

   ![プロジェクトを開始する](media/vscpp-start-without-debugging.gif "プロジェクトを開始する")

   コンソール ウィンドウが開き、アプリが実行されます。 Visual Studio でコンソール アプリを起動すると、コードが実行され、"続行するには何かキーを押してください . " と表示されるので、出力を確認できます。

おめでとうございます! 最初の "Hello, world!" コンソール アプリを Visual Studio で作成しました。 キーを押してコンソール ウィンドウを閉じ、Visual Studio に戻ります。

[問題が発生した場合](#build-and-run-your-code-in-visual-studio-issues)。

## <a name="run-your-code-in-a-command-window"></a>コマンド ウィンドウでコードを実行する

通常は、Visual Studio ではなく、コマンド プロンプトでコンソール アプリを実行します。 アプリを Visual Studio でビルドしたら、任意のコマンド ウィンドウから実行できます。 コマンド プロンプト ウィンドウで新しいアプリを検索して実行する方法を次に示します。

1. **ソリューション エクスプローラー**で、HelloWorld ソリューション (HelloWorld プロジェクトではなく) を選択し、右クリックしてコンテキスト メニューを開きます。 **[エクスプローラーでフォルダーを開く]** をクリックして、HelloWorld ソリューションフォルダーで**エクスプローラー** ウィンドウを開きます。

1. **エクスプローラー** ウィンドウで、デバッグ フォルダーを開きます。 このフォルダーには、アプリ、*HelloWorld.exe*、および他のいくつかのデバッグ ファイルが含まれています。 **Shift** キーを押したまま *HelloWorld.exe* を右クリックして、コンテキスト メニューを開きます。 **[パスとしてコピー]** を選択して、アプリケーションへのパスをクリップボードにコピーします。

1. コマンド プロンプト ウィンドウを開くには **Windows + R** キーを押して、 **[実行]** ダイアログを開きます。 **[名前]** ボックスに「*cmd.exe*」と入力し、 **[OK]** を選択してコマンド プロンプト ウィンドウを実行します。

1. コマンド プロンプト ウィンドウで右クリックし、アプリケーションへのパスをコマンド プロンプトに貼り付けます。 Enter キーを押して、アプリを実行します。

   ![コマンド プロンプトでアプリを実行する](media/vscpp-run-in-cmd.gif "コマンド プロンプトでアプリを実行する")

これで、Visual Studio でコンソール アプリをビルドして実行できました。

[問題が発生した場合](#run-your-code-in-a-command-window-issues)。

## <a name="next-steps"></a>次の手順

このシンプルなアプリをビルドして実行したら、より複雑なプロジェクトの準備ができています。 詳細については、「[C++ デスクトップ開発のための Visual Studio IDE の使用](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)」を参照してください。 Visual Studio での Microsoft C++ の機能について説明する詳細なチュートリアルが用意されています。

## <a name="troubleshooting-guide"></a>トラブルシューティング ガイド

最初の C++ プロジェクトを作成するときの一般的な問題の解決策については、こちらを参照してください。

### <a name="build-and-run-your-code-in-visual-studio-issues"></a>Visual Studio でコードをビルドして実行する: 問題

ソース コード エディター内の任意の項目の下に赤の波線が表示される場合は、ビルドにエラーまたは警告がある可能性があります。 コードのスペル、句読点、および大文字小文字が例と一致していることを確認します。

[前に戻る。](#build-and-run-your-code-in-visual-studio)

### <a name="run-your-code-in-a-command-window-issues"></a>コマンド ウィンドウでコードを実行する: 問題

エクスプローラーに表示されたパスが *\\HelloWorld\\HelloWorld* で終わる場合は、HelloWorld *ソリューション*ではなく、HelloWorld *プロジェクト*を開いています。 アプリが含まれていないデバッグ フォルダーのせいで混乱する可能性があります。 エクスプローラーで上のレベルに移動し、ソリューション フォルダーであるパスで最初の *HelloWorld* に移動します。 このフォルダーにはデバッグ フォルダーも含まれていて、そこにアプリがあります。

コマンドラインでソリューション デバッグ フォルダーに移動して、アプリを実行することもできます。 アプリへのパスを指定せずに、他のディレクトリからアプリを実行することはできません。 ただし、アプリを別のディレクトリにコピーしてそこから実行することもできます。 また、PATH 環境変数で指定されたディレクトリにコピーしてから、任意の場所から実行することもできます。

ショートカット メニューの **[パスとしてコピー]** が表示されない場合は、メニューを閉じ、**Shift** キーを押しながらもう一度開いてください。 このコマンドは利便性を高めるためだけのものです。 また、エクスプローラーの検索バーからフォルダーへのパスをコピーし、 **[実行]** ダイアログに貼り付け、末尾に実行可能ファイルの名前を入力することもできます。 入力が少し多くなりますが、同じ結果が得られます。

[前に戻る。](#run-your-code-in-a-command-window)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
