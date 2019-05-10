---
title: ATL プロジェクトへのオブジェクトやコントロールの追加
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.controls
helpviewer_keywords:
- ATL projects, adding objects
- wizards [C++], ATL projects
- ATL projects, adding controls
- controls [ATL], adding to projects
- objects [C++], adding to ATL projects
- ATL Control Wizard
ms.assetid: c0adcbd0-07fe-4c55-a8fd-8c2c65ecdaad
ms.openlocfilehash: d16e9a9e7b92d2a98f8994227c5641994677fdda
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221211"
---
# <a name="adding-objects-and-controls-to-an-atl-project"></a>ATL プロジェクトへのオブジェクトやコントロールの追加

ATL または MFC ベースのプロジェクトにオブジェクトまたはコントロールを追加するのにには、ATL コード ウィザードのいずれかを使用します。 追加する COM オブジェクトまたはコントロールごとに、.cpp、.h ファイルとともにに .rgs ファイル スクリプト ベースのレジストリのサポートをウィザードが生成されます。 次の ATL コード ウィザードは、Visual Studio で使用できます。

||||
|-|-|-|
|[ATL シンプル オブジェクト](../../atl/reference/atl-simple-object-wizard.md)|[ATL ダイアログ](../../atl/reference/atl-dialog-wizard.md)|[ATL コントロール](../../atl/reference/atl-control-wizard.md)|
|[ATL プロパティ ページ](../../atl/reference/atl-property-page-wizard.md)|[ATL Active Server Page コンポーネント](../../atl/reference/atl-active-server-page-component-wizard.md)|[ATL OLE DB コンシューマー](../../atl/reference/atl-ole-db-consumer-wizard.md)|
|[MFC に ATL サポートを追加します。](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)|[ATL COM+ 1.0 コンポーネント ウィザード](../../atl/reference/atl-com-plus-1-0-component-wizard.md)|[ATL OLE DB プロバイダー](../../atl/reference/atl-ole-db-provider-wizard.md)|

> [!NOTE]
> ATL オブジェクトをプロジェクトに追加する前に、詳細とその関連するヘルプ トピック内のオブジェクトの要件を確認してください。

## <a name="to-add-an-object-or-a-control-using-the-atl-control-wizard"></a>オブジェクトまたは ATL コントロール ウィザードを使用してコントロールを追加するには

1. **ソリューション エクスプ ローラー**プロジェクト ノードを右クリックし、クリックして、**追加**ショートカット メニューから。 クリックして**クラスを追加**します。

   [クラスの追加](../../ide/add-class-dialog-box.md) ダイアログ ボックスが表示されます。

1. **ATL**で選択したフォルダー、**カテゴリ**ウィンドウからを挿入するオブジェクトを選択、**テンプレート**ウィンドウ。 **[開く]** をクリックします。 選択したオブジェクトのコード ウィザードが表示されます。

   > [!NOTE]
   > MFC プロジェクトへの ATL オブジェクトを追加する場合は、既存のプロジェクトに ATL サポートを追加する必要があります。 次の手順でこれを行う[MFC プロジェクトへの ATL サポートの追加](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)します。

   代わりに、以前の ATL サポートを追加せず、MFC プロジェクトに ATL オブジェクトを追加しようとした場合は、Visual Studio するように求められますをプロジェクトに追加した ATL サポートをするかどうかを指定します。 クリックして**はい**をプロジェクトに ATL サポートを追加し、選択した ATL ウィザードを開きます。

## <a name="see-also"></a>関連項目

[ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)<br/>
[C++Visual Studio でプロジェクトの種類](../../build/reference/visual-cpp-project-types.md)<br/>
[ATL COM オブジェクトの基礎](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[ATL および C ランタイム コードによるプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)
