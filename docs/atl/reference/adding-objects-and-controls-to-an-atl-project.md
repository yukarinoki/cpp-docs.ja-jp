---
title: ATL プロジェクトへのオブジェクトやコントロールの追加 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.controls
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding objects
- wizards [C++], ATL projects
- ATL projects, adding controls
- controls [ATL], adding to projects
- objects [C++], adding to ATL projects
- ATL Control Wizard
ms.assetid: c0adcbd0-07fe-4c55-a8fd-8c2c65ecdaad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a6f9102aeebd0cc60765c70cf74fb2329bc801f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357774"
---
# <a name="adding-objects-and-controls-to-an-atl-project"></a>ATL プロジェクトへのオブジェクトやコントロールの追加
ATL または MFC ベースでのプロジェクトにオブジェクトやコントロールを追加するのにには、ATL コード ウィザードのいずれかを使用します。 COM オブジェクトやコントロールを追加すると、.cpp、.h ファイルだけでなく .rgs ファイル スクリプト ベースのレジストリのサポートについては、ウィザードが生成されます。 Visual Studio で、次の ATL コード ウィザードを紹介します。  
  
||||  
|-|-|-|  
|[ATL シンプル オブジェクト](../../atl/reference/atl-simple-object-wizard.md)|[ATL ダイアログ](../../atl/reference/atl-dialog-wizard.md)|[ATL コントロール](../../atl/reference/atl-control-wizard.md)|  
|[ATL プロパティ ページ](../../atl/reference/atl-property-page-wizard.md)|[ATL Active Server Page コンポーネント](../../atl/reference/atl-active-server-page-component-wizard.md)|[ATL OLE DB コンシューマー](../../atl/reference/atl-ole-db-consumer-wizard.md)|  
|[MFC に ATL サポートを追加します。](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)|[ATL COM+ 1.0 コンポーネント ウィザード](../../atl/reference/atl-com-plus-1-0-component-wizard.md)|[ATL OLE DB プロバイダー](../../atl/reference/atl-ole-db-provider-wizard.md)|  
  
> [!NOTE]
>  ATL オブジェクトをプロジェクトに追加する前に、詳細とその関連するヘルプ トピック内のオブジェクトの要件を確認してください。  
  
### <a name="to-add-an-object-or-a-control-using-the-atl-control-wizard"></a>オブジェクトまたは ATL コントロール ウィザードを使用してコントロールを追加するには  
  
1.  ソリューション エクスプ ローラーでプロジェクト ノードを右クリックし、をクリックして**追加**ショートカット メニューからです。 をクリックして**クラスを追加**です。  
  
     [クラスの追加](../../ide/add-class-dialog-box.md) ダイアログ ボックスが表示されます。  
  
2.  [カテゴリ] ペインで選択した ATL フォルダーで、[テンプレート] ペインからを挿入するオブジェクトを選択します。 をクリックして**開く**です。 選択したオブジェクトのコード ウィザードが表示されます。  
  
    > [!NOTE]
    >  MFC プロジェクトに ATL オブジェクトを追加する場合は、既存のプロジェクトに ATL サポートを追加する必要があります。 次の手順でこれを行う[MFC プロジェクトへの ATL サポートの追加](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)です。  
  
     または、以前の ATL サポートを追加することがなく MFC プロジェクトに ATL オブジェクトを追加しようとすると、Visual Studio するように求められます ATL サポートをプロジェクトに追加するかどうかを指定します。 をクリックして**はい**をプロジェクトに ATL サポートを追加して、選択した ATL ウィザードを開きます。  
  
## <a name="see-also"></a>関連項目  
 [ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)   
 [Visual C プロジェクトの種類](../../ide/visual-cpp-project-types.md)   
 [アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL COM オブジェクトの基本事項](../../atl/fundamentals-of-atl-com-objects.md)   
 [ATL および C ランタイム コードによるプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)

