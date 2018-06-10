---
title: 'チュートリアル: セットアップ プロジェクトを使用した Visual C++ アプリケーションの配置 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deployment for Visual C++
ms.assetid: 66735cda-8fe3-4211-a19a-2cf717a12a3f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 454507a3a3f33b43af0e50c25dab6703aa75a56b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "33332781"
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-a-setup-project"></a>チュートリアル: セットアップ プロジェクトを使用した Visual C++ アプリケーションの配置
セットアップ プロジェクトを使用して、Visual C++ アプリケーションを展開する方法について説明します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルを実行するには、次のコンポーネントが必要です。  
  
-   [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] がインストールされているコンピューター。  
  
-   Visual C++ ライブラリがない別のコンピューター。  
  
### <a name="to-deploy-an-application-by-using-a-setup-project"></a>セットアップ プロジェクトを使用してアプリケーションを配置するには  
  
1.  **MFC ApplicationWizard** を使用して新しい Visual Studio ソリューションを作成します。 ウィザードを見つけるには、**[新しいプロジェクト]** ダイアログ ボックスで、**Visual C++** ノードを展開し、**[MFC]**、**[MFC アプリケーション]** の順に選択して、プロジェクトの名前を入力し、**[OK]** をクリックします。  
  
2.  アクティブなソリューション構成を **[解放]** に変更します。 **[ビルド]** メニューの **[構成マネージャー]** を選択します。 **[構成マネージャー]** ダイアログ ボックスで、**[アクティブ ソリューション構成]** ドロップダウン ボックスの **[解放]** をクリックします。  
  
3.  F7 キーを押してアプリケーションをビルドします。 または、**[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。 これにより、セットアップ プロジェクトでこの MFC アプリケーション プロジェクトの出力を使用できます。  
  
4.  この操作が完了していない場合は、InstallShield Limited Edition (ISLE) をダウンロードします。これは Visual Studio の開発者向けの無料ツールで、セットアップと配置のための Visual Studio のプロジェクト テンプレートの機能に代わるものです。 インターネットに接続されているときには、メニュー バーの **[ファイル]**、**[新規]**、**[プロジェクト]** の順に選択するか、**ソリューション エクスプローラー**で **[追加]**、**[新しいプロジェクト]** の順に選択して **[新しいプロジェクト]** ダイアログ ボックスを開きます。 **[その他のプロジェクトの種類]** ノードを展開し、**[セットアップと配置]** ノードの **[InstallShield Limited Edition の有効化]** を選択し、表示される指示に従います。 InstallShield Limited Edition をダウンロード、インストール、有効化した後、Visual Studio を終了してから再び開きます。  
  
5.  開いている、**[新しいプロジェクト]** ダイアログ ボックスをもう一度開き、**[その他のプロジェクトの種類]** ノードを選択して、**[InstallShield Limited Edition]** ノードで **[InstallShield Limited Edition] プロジェクト**を選択します。  
  
6.  InstallShield Limited Edition テンプレートによって作成されたセットアップ プロジェクトの **[作業の開始]** ノードの指示に従って、Visual Studio MFC プロジェクトの出力参照を追加します。  
  
7.  インストーラー ファイル (setup.exe) を作成するセットアップ プロジェクトをビルドします。 これを行うには、**ソリューション エクスプローラー**でセットアップ プロジェクトを右クリックし、**[ビルド]** を選択します。  
  
     InstallShield Limited Edition によってセットアップ プロジェクト ツリー (既定では、セットアップ プロジェクトの Express\SingleImage\DiskImages\DISK1 サブフォルダーにあります) にセットアップ ファイルが作成されます。  
  
8.  Visual C ++ ライブラリがない 2 台目のコンピューターで、セットアップ プログラムを実行します。  
  
## <a name="see-also"></a>参照  
 [配置例](../ide/deployment-examples.md)