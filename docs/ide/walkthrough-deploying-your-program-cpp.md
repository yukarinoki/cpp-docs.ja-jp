---
title: 'チュートリアル: プログラムの配置 (C++) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++], walkthroughs
- setup projects [C++]
- program deployments [C++]
- projects [C++], setup
- projects [C++], deploying programs
- application deployment [C++], walkthroughs
ms.assetid: 79e6cc4e-dced-419d-aaf7-d62d1367603f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1753c63673b9dd083e2b690788801bd467938c3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-deploying-your-program-c"></a>チュートリアル: プログラムの配置 (C++)
これでチュートリアルを完了する前関連に記載されているアプリケーションを作成した[C++ デスクトップ開発用 Visual Studio IDE を使用して](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)、最後の手順は、他のユーザーが実行できるように、インストーラーを作成するのには自分のコンピューターにプログラムをインストールします。 そのためには、新しいプロジェクトを既存のソリューションに追加します。 この新しいプロジェクトの出力は、別のコンピューターにアプリをインストールする setup.exe ファイルです。  
  
 このチュートリアルでは、Windows インストーラーを使用してアプリケーションを配置する方法を示します。 アプリケーションの配置には ClickOnce を使用することもできます。 詳細については、「 [ClickOnce Deployment for Visual C++ Applications](../ide/clickonce-deployment-for-visual-cpp-applications.md)」を参照してください。 展開の詳細については一般を参照してください[アプリケーション、サービス、および配置コンポーネント](/visualstudio/deployment/deploying-applications-services-and-components)です。  
  
## <a name="prerequisites"></a>必須コンポーネント  
  
-   このチュートリアルは、C++ 言語の基本を理解していることを前提としています。  
  
-   以前関連チュートリアルに記載されているが完了したことも想定[C++ デスクトップ開発用 Visual Studio IDE を使用して](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)です。  
  
-   このチュートリアルは Visual Studio の Express Edition では完了できません。  
  
-   InstallShield Limited Edition (ISLE) をまだダウンロードしていない場合は、この記事の以降の手順に従ってダウンロードしてください。 ISLE は Visual Studio 開発者向けの無料版の InstallShield です。Visual Studio の以前のエディションのセットアップおよび配置プロジェクト テンプレートの機能に置き換わるものです。  
  
### <a name="to-install-the-isle-setup-and-deployment-project-template"></a>ISLE のセットアップおよび配置プロジェクト テンプレートをインストールするには  
  
1.  メニュー バーで、インターネットに接続しているときに選択**ファイル**、**新規**、**プロジェクト**を開くには、**新しいプロジェクト** ダイアログ ボックス。  
  
2.  ダイアログ ボックスの左側のウィンドウで展開、**インストール済み**、**テンプレート**、および**その他のプロジェクトの種類**ノード、および選択**セットアップと配置**. 中央のウィンドウで次のように選択します。 **InstallShield Limited Edition**を選択し、 **OK**ボタンをクリックします。  
  
3.  指示に従って InstallShield Limited Edition for Visual Studio をインストールします。  
  
4.  ISLE をダウンロード、インストール、有効化した後、Visual Studio を終了してから再び開きます。  
  
5.  メニュー バーで、次のように選択します。**ファイル**、**最近使ったプロジェクトおよびソリューション**、を選択し、**ゲーム**ソリューションを再度開きます。  
  
### <a name="to-create-a-setup-project-and-install-your-program"></a>セットアップ プロジェクトを作成してプログラムをインストールするには  
  
1.  アクティブなソリューション構成を [解放] に変更します。 メニュー バーで **[ビルド]**、 **[構成マネージャー]** の順に選択します。 **Configuration Manager**  ダイアログ ボックスで、**アクティブ ソリューション構成**ドロップダウン リストで、**リリース**です。 選択、**閉じる**構成を保存するボタンをクリックします。  
  
2.  メニュー バーで、次のように選択します。**ファイル**、**新規**、**プロジェクト**を開くには、**新しいプロジェクト** ダイアログ ボックス。  
  
3.  ダイアログ ボックスの左側のウィンドウで展開、**インストール済み**、**テンプレート**、および**その他のプロジェクトの種類**ノード、および選択**セットアップと配置**. 中央のウィンドウで次のように選択します。 **InstallShield Limited Edition プロジェクト**です。  
  
4.  セットアップ プロジェクトの名前を入力、**名前**ボックス。 この例では、入力**Game Installer**です。 **ソリューション**ドロップダウン リストで、**ソリューションに追加**です。 選択、 **OK**セットアップ プロジェクトを作成するボタンをクリックします。 A**プロジェクト アシスタント (Game Installer)** エディター ウィンドウでタブが表示されます。  
  
5.  下部にある、**プロジェクト アシスタント (Game Installer)**  タブで、選択、**アプリケーション情報**リンクします。  
  
6.  **アプリケーション情報** ページで、インストーラーに表示するように、会社名を指定します。 会社名を使用したり、この例では、使用**Contoso**です。 アプリケーション名を指定します。この例で指定して**ゲーム**です。 会社の web アドレスを指定するか、この例では、使用 **http://www.contoso.com**です。  
  
7.  下部にある、**プロジェクト アシスタント (Game Installer)**  タブで、選択、**インストール面接**リンクします。  
  
8.  **インストール面接**] ページの [**使用許諾契約ダイアログを表示する**を選択、**いいえ**オプション ボタンをクリックします。 **、会社名を入力するユーザーとユーザー名を確認する**を選択、**いいえ**オプション ボタンをクリックします。  
  
9. **ソリューション エクスプ ローラー**、展開、 **Game Installer**プロジェクトで、展開、 **Organize Your Setup**ノードを開き、 **一般情報**ページ。  
  
10. **一般的な情報 (Game Installer)** エディター ウィンドウでタブで、指定、**タグ作成者 ID**など、 **regid.2012-12.com.contoso」と**です。  
  
11. **ソリューション エクスプ ローラー**、 **Game Installer**プロジェクトで、展開、 **Specify Application Data**ノードを開き、**ファイル**ページです。  
  
12. **ファイル (Game Installer)** エディター ウィンドウで、タブの下にある**ソース コンピューターのファイル**、ショートカット メニューを開き、 **Game のプライマリ出力**を選択して**コピー**です。  
  
13. 下の空白部分でショートカット メニューを開き、**名前**内の列**先のコンピューターのファイル**を選択し、**貼り付け**です。 新しい項目の名前付き**Game.Primary 出力**が表示されます。  
  
14. **ソリューション エクスプ ローラー**、 **Specify Application Data**ノードを開いて、**再頒布可能パッケージ**ページ。  
  
15. **再頒布可能ファイル (Game Installer)** エディター ウィンドウでタブ、 **Visual C 11.0 CRT (x86)** チェック ボックスをオンします。  
  
16. メニュー バーで、次のように選択します。**ビルド**、**ソリューションのビルド**、Game プロジェクトと Game Installer プロジェクトをビルドします。  
  
17. ソリューション フォルダーで、Game Installer プロジェクトからビルドされた setup.exe プログラムを見つけて実行し、Game アプリケーションをコンピューターにインストールします。 このファイルをコピーして、アプリケーションとその必要なライブラリ ファイルを別のコンピューターにインストールできます。  
  
18. セットアップ プロジェクトの多くのオプションは独自の要件に合わせて設定できます。 詳細についてで**ソリューション エクスプ ローラー**下で、 **Game Installer**プロジェクトを開き、**作業の開始**ページし、F1 キーを押して ISLE ヘルプ ライブラリを開きます。  
  
## <a name="next-steps"></a>次の手順  
 **前:** [チュートリアル: プロジェクトのデバッグ (C++)](../ide/walkthrough-debugging-a-project-cpp.md)  
  
## <a name="see-also"></a>関連項目  
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)  
 [デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)