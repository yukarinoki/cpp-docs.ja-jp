---
title: セットアップ プロジェクトを使用して Visual C アプリケーションの配置 |Microsoft ドキュメント
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
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-a-setup-project"></a>チュートリアル: セットアップ プロジェクトを使用した Visual C++ アプリケーションの配置
セットアップ プロジェクトを使用して、Visual C アプリケーションを展開する方法について説明します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルを実行するには、次のコンポーネントが必要です。  
  
-   使用しているコンピューター[!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)]をインストールします。  
  
-   追加するコンピューターに Visual C ライブラリがないです。  
  
### <a name="to-deploy-an-application-by-using-a-setup-project"></a>セットアップ プロジェクトを使用してアプリケーションを配置するには  
  
1.  使用して、 **MFC ApplicationWizard**新しい Visual Studio ソリューションを作成します。 ウィザードを検索する、**新しいプロジェクト** ダイアログ ボックスで、展開、 **Visual C**ノード、 **MFC** **MFC アプリケーション**を入力してください、プロジェクトの名前を指定し、をクリックして**OK**です。  
  
2.  アクティブなソリューション構成を変更**リリース**です。 **ビルド**メニューの  **Configuration Manger**です。 **Configuration Manager**ダイアログ ボックスで、**リリース**から、**アクティブ ソリューション構成** ボックスの一覧です。  
  
3.  F7 キーを押してアプリケーションをビルドします。 か、または、**ビルド** メニューをクリックして**ソリューションのビルド**です。 これにより、セットアップ プロジェクトをこの MFC アプリケーション プロジェクトの出力を使用できます。  
  
4.  完了していない場合は、InstallShield Limited Edition (ISLE)、これは Visual Studio の開発者向けの無料で、セットアップと配置の Visual Studio でプロジェクト テンプレートの機能に代わるものをダウンロードします。 インターネットに接続しているときに開く、**新しいプロジェクト** ダイアログ ボックスを選択して**ファイル**、**新規**、**プロジェクト**横棒グラフ、またはメニューソリューションを右クリックして**ソリューション エクスプ ローラー**を選択して**追加**、**新しいプロジェクト**です。 展開、**その他のプロジェクトの種類**] ノードを選択 **[InstallShield Limited Edition**で、**セットアップと配置**ノード、し表示される指示に従います。 ダウンロードしてインストールされている、InstallShield Limited Edition をアクティブ化は、Visual Studio を閉じて再び開きます。  
  
5.  開いている、**新しいプロジェクト** ダイアログ ボックス、展開、**その他のプロジェクトの種類** ノードを選択**InstallShield Limited Edition プロジェクト**で、 **InstallShield Limited Edition**ノード。  
  
6.  指示に従って、**作業の開始**InstallShield Limited Edition のテンプレートを Visual Studio の MFC プロジェクト出力参照を追加で作成したセットアップ プロジェクトのノードです。  
  
7.  インストーラー ファイル (setup.exe) を作成するセットアップ プロジェクトをビルドします。 これを行うには、ノードを右クリックして、セットアップ プロジェクトで**ソリューション エクスプ ローラー**選択**ビルド**です。  
  
     InstallShield Limited Edition のセットアップ プロジェクト ツリーのセットアップ ファイルを作成する (既定では、可能性があります、セットアップ プロジェクトの Express\SingleImage\DiskImages\DISK1 サブフォルダーにあります)。  
  
8.  Visual C ライブラリがない 2 つ目のコンピューターでセットアップ プログラムを実行します。  
  
## <a name="see-also"></a>関連項目  
 [配置例](../ide/deployment-examples.md)