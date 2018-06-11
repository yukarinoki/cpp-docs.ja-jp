---
title: 'チュートリアル: プログラムの配置 (C++) | Microsoft Docs'
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
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "33335537"
---
# <a name="walkthrough-deploying-your-program-c"></a>チュートリアル: プログラムの配置 (C++)
ここまでの関連チュートリアル (「[C++ デスクトップ開発のための Visual Studio IDE の使用](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)」を参照) を完了することで、アプリケーションの作成が完了しました。最後の手順は、他のユーザーが自分のコンピューターにプログラムをインストールできるようにインストーラーを作成することです。 そのためには、新しいプロジェクトを既存のソリューションに追加します。 この新しいプロジェクトの出力は、別のコンピューターにアプリをインストールする setup.exe ファイルです。  
  
 このチュートリアルでは、Windows インストーラーを使用してアプリケーションを配置する方法を示します。 アプリケーションの配置には ClickOnce を使用することもできます。 詳細については、「 [ClickOnce Deployment for Visual C++ Applications](../ide/clickonce-deployment-for-visual-cpp-applications.md)」を参照してください。 一般的な配置の詳細については、「[アプリケーション、サービス、およびコンポーネントの配置](/visualstudio/deployment/deploying-applications-services-and-components)」をご覧ください。  
  
## <a name="prerequisites"></a>必須コンポーネント  
  
-   このチュートリアルは、C++ 言語の基本を理解していることを前提としています。  
  
-   また、これまでの関連チュートリアル (「[C++ デスクトップ開発のための Visual Studio IDE の使用](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)」を参照) を完了していることも必要です。  
  
-   このチュートリアルは Visual Studio の Express Edition では完了できません。  
  
-   InstallShield Limited Edition (ISLE) をまだダウンロードしていない場合は、この記事の以降の手順に従ってダウンロードしてください。 ISLE は Visual Studio 開発者向けの無料版の InstallShield です。Visual Studio の以前のエディションのセットアップおよび配置プロジェクト テンプレートの機能に置き換わるものです。  
  
### <a name="to-install-the-isle-setup-and-deployment-project-template"></a>ISLE のセットアップおよび配置プロジェクト テンプレートをインストールするには  
  
1.  インターネットに接続されている状態で、メニュー バーで **[ファイル]**、**[新規作成]**、**[プロジェクト]** の順に選択して、**[新しいプロジェクト]** ダイアログ ボックスを開きます。  
  
2.  ダイアログ ボックスの左側のペインで、**[インストール済み]**、**[テンプレート]**、**[その他のプロジェクトの種類]** ノードを展開し、**[セットアップと配置]** を選択します。 中央のペインで、**[InstallShield Limited Edition の有効化]** を選択し、**[OK]** をクリックします。  
  
3.  指示に従って InstallShield Limited Edition for Visual Studio をインストールします。  
  
4.  ISLE をダウンロード、インストール、有効化した後、Visual Studio を終了してから再び開きます。  
  
5.  メニュー バーで **[ファイル]**、**[最近使ったプロジェクトとソリューション]** の順に選択し、**Game** ソリューションを選択して再び開きます。  
  
### <a name="to-create-a-setup-project-and-install-your-program"></a>セットアップ プロジェクトを作成してプログラムをインストールするには  
  
1.  アクティブなソリューション構成を [解放] に変更します。 メニュー バーで **[ビルド]**、 **[構成マネージャー]** の順に選択します。 **[構成マネージャー]** ダイアログ ボックスで、**[アクティブ ソリューション構成]** ドロップダウン リストの **[解放]** をクリックします。 **[閉じる]** をクリックして構成を保存します。  
  
2.  メニューバーで **[ファイル]**、**[新規作成]**、**[プロジェクト]** の順に選択して、**[新しいプロジェクト]** ダイアログ ボックスを開きます。  
  
3.  ダイアログ ボックスの左側のペインで、**[インストール済み]**、**[テンプレート]**、**[その他のプロジェクトの種類]** ノードを展開し、**[セットアップと配置]** を選択します。 中央のペインで **[InstallShield Limited Edition プロジェクト]** を選択します。  
  
4.  **[名前]** ボックスにセットアップ プロジェクトの名前を入力します。 この例では「**Game Installer**」と入力します。 **[ソリューション]** ドロップダウン リストで **[ソリューションに追加]** をクリックします。 **[OK]** をクリックすると、セットアップ プロジェクトが作成されます。 **[プロジェクト アシスタント (Game Installer)]** タブがエディター ウィンドウで開きます。  
  
5.  **[プロジェクト アシスタント (Game Installer)]** タブの下部で、**[アプリケーション情報]** リンクを選択します。  
  
6.  **[アプリケーション情報]** ページで、インストーラーに表示する会社名を指定します。 自分の会社の名前を使用できます。この例では「**Contoso**」を使用します。 アプリケーション名を指定します。この例では「**Game**」と指定します。 自分の会社の Web アドレスを指定します。この例では「**http://www.contoso.com**」を使用します。  
  
7.  **[プロジェクト アシスタント (Game Installer)]** タブの下部で、**[インストール要件]** リンクを選択します。  
  
8.  **[インストール要件]** ページの **[Do you want to display a License Agreement Dialog]** (使用許諾契約ダイアログ ボックスを表示しますか) で、**[いいえ]** をクリックします。 **[Do you want to prompt users to enter their Company Name and User Name]** (ユーザーに自分の会社名とユーザー名の入力を求めますか) で、**[いいえ]** をクリックします。  
  
9. **ソリューション エクスプローラー**で、**Game Installer** プロジェクト、**[セットアップの編成]** ノードの順に展開し、**[一般情報]** ページを開きます。  
  
10. エディター ウィンドウの **[一般情報 (Game Installer)]** タブで、**[タグ作成者 ID]** にたとえば「**regid.2012-12.com.Contoso**」と指定します。  
  
11. **ソリューション エクスプローラー**で、**Game Installer** プロジェクトの下の **[アプリケーション データの指定]** ノードを展開し、**[ファイル]** ページを開きます。  
  
12. エディター ウィンドウの **[ファイル (Game Installer)]** タブで、**[ソース コンピューターのファイル]** の下の **[Game のプライマリ出力]** のショートカット メニューを開き、**[コピー]** を選択します。  
  
13. **[インストール先コンピューターのファイル]** で、**[名前]** 列の下の空白部分でショートカット メニューを開き、**[貼り付け]** を選択します。 "**Game.Primary Output**" という新しい項目が表示されます。  
  
14. **ソリューション エクスプローラー**で、**[アプリケーション データの指定]** ノードの下の **[再配布可能ファイル]** ページを開きます。  
  
15. エディター ウィンドウの **[再配布可能ファイル (Game Installer)]** タブで、**[Visual C++ 11.0 CRT (x86)]** チェック ボックスをオンにします。  
  
16. メニューバーで **[ビルド]**、**[ソリューションのビルド]** の順に選択して、Game プロジェクトと Game Installer プロジェクトをビルドします。  
  
17. ソリューション フォルダーで、Game Installer プロジェクトからビルドされた setup.exe プログラムを見つけて実行し、Game アプリケーションをコンピューターにインストールします。 このファイルをコピーして、アプリケーションとその必要なライブラリ ファイルを別のコンピューターにインストールできます。  
  
18. セットアップ プロジェクトの多くのオプションは独自の要件に合わせて設定できます。 詳細については、**ソリューション エクスプローラー**で、**Game Installer** プロジェクトの下の **[作業の開始]** ページを開いてから、F1 キーを押して ISLE ヘルプ ライブラリを開いてください。  
  
## <a name="next-steps"></a>次の手順  
 **前へ:** [チュートリアル: プロジェクトのデバッグ (C++)](../ide/walkthrough-debugging-a-project-cpp.md)  
  
## <a name="see-also"></a>参照  
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)  
 [デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)