---
title: 再頒布可能パッケージ (C++) を使用してアプリを配置 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- walkthrough, deploying a Visual C++ application by using the redistributable package
ms.assetid: e59becbf-b8c6-4c8e-bab3-b69cc1ed3e5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 37bba00efdf0368973fa4ffbac1cbc6bb6298ce1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-the-visual-c-redistributable-package"></a>チュートリアル: Visual C++ 再頒布可能パッケージを使用した Visual C++ アプリケーションの配置
この資料では、Visual C 再頒布可能パッケージを使用して、Visual C アプリケーションを展開する方法について説明します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルを完了するこれらのコンポーネントが必要です。  
  
-   Visual Studio がインストールされているコンピューター。  
  
-   追加するコンピューターに Visual C ライブラリがないです。  
  
### <a name="to-use-the-visual-c-redistributable-package-to-deploy-an-application"></a>Visual C 再頒布可能パッケージを使用してアプリケーションを展開するには  
  
1.  作成し、最初の 3 つの手順に従って、MFC アプリケーションをビルド[チュートリアル: プロジェクトを配置する、Visual C++ を使ったアプリケーション セットアップ](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md)です。  
  
2.  ファイルを作成し、setup.bat という名前を次のコマンドを追加します。 変更`MyMFCApplication`プロジェクトの名前にします。  
  
    ```cmd
    @echo off  
    vcredist_x86.exe  
    mkdir "C:\Program Files\MyMFCApplication"  
    copy MyMFCApplication.exe "C:\Program Files\MyMFCApplication"  
    ```  
  
3.  自己解凍形式のセットアップ ファイルを作成します。  
  
    1.  コマンド プロンプトまたは、**実行**ウィンドウ、iexpress.exe を実行します。  
  
    2.  選択**新しい自己抽出ディレクティブ ファイルの作成**を選択し、**次**ボタンをクリックします。  
  
    3.  選択**ファイルを抽出して、インストール コマンドを実行**を選択し**次**です。  
  
    4.  テキスト ボックスに、MFC アプリケーションの名前を入力し、**次**です。  
  
    5.  **確認プロンプト**] ページで、[**いいえプロンプト**を選択し**次**です。  
  
    6.  **使用許諾契約書**] ページで、[**ライセンスを表示しない**を選択し**次**です。  
  
    7.  **ファイルをパッケージ化** ページで、次のファイルを追加して、選択**次**です。  
  
        -   MFC アプリケーション (.exe ファイル)。  
  
        -   vcredist_x86.exe です。 このファイルは \Program Files\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\vcredist_x86 にあります\\です。  
  
        -   前の手順で作成した、setup.bat ファイル。  
  
    8.  **起動するプログラムをインストール** ページの 、**プログラムをインストール**テキスト ボックスは、次のコマンドラインを入力し、**次**です。  
  
         **cmd.exe/c"setup.bat"**  
  
    9. **表示ウィンドウ**] ページで、[**既定**を選択し**次**です。  
  
    10. **完了メッセージ**] ページで、[**メッセージはありません**を選択し**次**です。  
  
    11. **パッケージ名とオプション**] ページで、select、自己解凍形式のセットアップ ファイルの名前を入力、**パッケージ内に長いファイル名を使用してファイルを格納**オプションをクリックして **[次へ**. ファイル名の末尾には、Setup.exe—for 例では、MyMFCApplicationSetup.exe をする必要があります。  
  
    12. **再起動を構成する**] ページで、[**再起動しない**を選択し**次**です。  
  
    13. **自己抽出ディレクティブの保存**] ページで、[**自己抽出ディレクティブ (SED) ファイルを保存**を選択し**次**です。  
  
    14. **パッケージを作成する**ページで、選択**次**です。  
  
4.  Visual C ライブラリがないその他のコンピューターで自己解凍形式のセットアップ ファイルをテストします。  
  
    1.  他のコンピューターで、セットアップ ファイルのコピーをダウンロードし、それを実行してで提供される手順を実行してインストールします。  
  
    2.  MFC アプリケーションを実行します。  
  
         自己解凍形式のセットアップ ファイルは、手順 2. で指定したフォルダーには、MFC アプリケーションをインストールします。 Visual C 再頒布可能パッケージのインストーラーが、自己解凍形式のセットアップ ファイルに含まれているため、アプリケーションが正常に実行します。  
  
        > [!IMPORTANT]
        >  インストーラーを調べるには、ランタイムのバージョンがインストールされているには、レジストリ キー \HKLM\SOFTWARE\Microsoft\VisualStudio\11.0\VC\Runtimes を確認\\[platform] です。 現在インストールされているバージョンをインストールしようとして、インストーラーのバージョンよりも新しい場合は、インストーラーは、古いバージョンをインストールしなくても成功を返し、コントロール パネルの インストールされているプログラム ページの追加のエントリのままにします。  
  
## <a name="see-also"></a>関連項目  
 [配置例](../ide/deployment-examples.md)