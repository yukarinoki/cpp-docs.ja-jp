---
title: 再頒布可能パッケージ (C++) を使用してアプリを配置する
ms.date: 09/17/2018
helpviewer_keywords:
- walkthrough, deploying a Visual C++ application by using the redistributable package
ms.assetid: e59becbf-b8c6-4c8e-bab3-b69cc1ed3e5e
ms.openlocfilehash: ccf6b74096894c2e48258e6e0a60b807c7c6c5b4
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743798"
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-the-visual-c-redistributable-package"></a>チュートリアル: Visual C++ 再頒布可能パッケージを使用した Visual C++ アプリケーションの配置

この資料では、Visual C++ 再頒布可能パッケージを使用して、Visual C++ アプリケーションを配置する方法について説明します。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを完了するには、次のコンポーネントが必要です。

- Visual Studio がインストールされているコンピューター。

- Visual C++ ライブラリがない別のコンピューター。

### <a name="to-use-the-visual-c-redistributable-package-to-deploy-an-application"></a>Visual C++ 再頒布可能パッケージを使用してアプリケーションを配置するには

1.  「[チュートリアル: セットアップ プロジェクトを使用した Visual C++ アプリケーションの配置](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)」の手順に従って、MFC アプリケーションを作成してビルドします。

1. ファイルを作成して setup.bat という名前を付け、それに次のコマンドを追加します。 `MyMFCApplication` を自分のプロジェクトの名前に変更します。

    ```cmd
    @echo off
    vcredist_x86.exe
    mkdir "C:\Program Files\MyMFCApplication"
    copy MyMFCApplication.exe "C:\Program Files\MyMFCApplication"
    ```

1. 自己展開型のセットアップ ファイルを作成します。

   1. コマンド プロンプトまたは、**[実行]** ウィンドウで、iexpress.exe を実行します。

   1. **[新規の自己展開指示ファイルを作成する]** を選択し、**[次へ]** ボタンを選択します。

   1. **[Extract files and run an installation command]\(ファイルを抽出して、インストール コマンドを実行する)** を選択し、**[次へ]** を選択します。

   1. テキスト ボックスに自分の MFC アプリケーションの名前を入力し、**[次へ]** を選択します。

   1. **[確認プロンプト]** ページで、**[No prompt]\(プロンプトなし\)**、**[次へ]** の順に選択します。

   1. **[使用許諾契約書]** ページで、**[Do not display a license]\(ライセンスを表示しない\)**、**[次へ]** の順に選択します。

   1. **[パッケージしたファイル]** ページで、次のファイルを追加し、**[次へ]** を選択します。

      - 自分の MFC アプリケーション (.exe ファイル)。

      - vcredist_x86.exe。 このファイルは、\Program Files (x86)\Microsoft Visual Studio \<バージョン>\SDK\Bootstrapper\Packages\. にあります。 このファイルは [Microsoft](https://www.microsoft.com/download/confirmation.aspx?id=5555) からダウンロードすることもできます。

      - 前の手順で作成した、setup.bat ファイル。

   1. **[Install Program to Launch]\(起動するインストール プログラム\)** ページの **[インストール プログラム]** テキスト ボックスに、次のコマンドラインを入力し、**[次へ]** を選択します。

      **cmd.exe /c "setup.bat"**

   1. **[ウィンドウの表示]** ページで、**[既定]** を選択し、**[次へ]** を選択します。

   1. **[完了後のメッセージ]** ページで、**[メッセージなし]** を選択し、**[次へ]** を選択します。

   1. **[Package Name and Options]\(パッケージ名とオプション\)** ページで、自分の自己展開型のセットアップ ファイルの名前を入力し、**[パッケージ内に長いファイル名でファイルを保存する]** オプションを選択し、**[次へ]** を選択します。 ファイル名の末尾は Setup.exe にする必要があります (例: *MyMFCApplicationSetup.exe*)。

   1. **[再起動の構成]** ページで、**[No restart]\(再起動しない\)** を選択し、**[次へ]** を選択します。

   1. **[自己展開指示ファイルの保存]** ページで、**[自己展開指示 (SED) ファイルを保存する]** を選択し、**[次へ]** を選択します。

   1. **[パッケージの作成]** ページで、**[次へ]** を選択します。 **[完了]** を選択します。

1. Visual C++ ライブラリを持たない他のコンピューターで、自己展開型のセットアップ ファイルをテストします。

   1. 他のコンピューターで、セットアップ ファイルのコピーをダウンロードしてから、それを実行してインストールし、提供される手順に従います。 選択したオプションによっては、インストールに **[管理者として実行]** コマンドが必要になります。

   1. MFC アプリケーションを実行します。

      自己展開型のセットアップ ファイルにより、手順 2. で指定したフォルダーに格納されている MFC アプリケーションがインストールされます。 Visual C++ 再頒布可能パッケージのインストーラーは自己展開型のセットアップ ファイルに含まれているため、アプリケーションが正常に実行されます。

      > [!IMPORTANT]
      > どのバージョンのランタイムがインストールされているかを判断するため、インストーラーによってレジストリ キー \HKLM\SOFTWARE\Microsoft\VisualStudio\\\<バージョン>\VC\Runtimes\\<platform> がチェックされます。 インストーラーがインストールしようとしているバージョンよりも現在インストールされているバージョンが新しい場合、インストーラーは古いバージョンをインストールせずに成功を返し、追加のエントリをコントロール パネルのインストールされているプログラム ページに残したままにします。

## <a name="see-also"></a>関連項目

[配置例](deployment-examples.md)<br/>
