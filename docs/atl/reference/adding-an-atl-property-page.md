---
title: ATL プロパティ ページの追加
ms.date: 05/09/2019
helpviewer_keywords:
- property pages, adding
- ATL projects, adding property pages
- controls [ATL], property pages
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
ms.openlocfilehash: 4cd7444d18d26124f8c3c642bba55fb7592f5c8b
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91499325"
---
# <a name="adding-an-atl-property-page"></a>ATL プロパティ ページの追加

> [!NOTE]
> ATL プロパティ ページ ウィザードは、Visual Studio 2019 以降では使用できません。

Active Template Library (ATL) プロパティ ページをプロジェクトに追加するには、プロジェクトが ATL アプリケーションとして作成されているか、ATL サポートを含む MFC アプリケーションとして作成されている必要があります。 ATL アプリケーションを作成するか、[ATL オブジェクトを MFC アプリケーションに追加](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)して MFC アプリケーションの ATL サポートを実装するには、[ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)を利用できます。

コントロール用のプロパティ ページを追加する場合、コントロールで [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) インターフェイスをサポートする必要があります。 既定では、このインターフェイスは、[ATL コントロール ウィザード](../../atl/reference/atl-control-wizard.md)を使用して [ATL コントロールを作成](../../atl/reference/adding-an-atl-control.md)したときに、コントロール クラスの派生リストに含まれます。

> [!NOTE]
> コントロール クラスの派生リストに [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) がない場合は、手動で追加する必要があります。

## <a name="to-add-an-atl-property-page-to-your-project"></a>ATL プロパティ ページをプロジェクトに追加するには

1. **ソリューション エクスプローラー**または[クラス ビュー](/visualstudio/ide/viewing-the-structure-of-code)のいずれかで、ATL プロパティ ページを追加するプロジェクトの名前を右クリックします。

1. ショートカット メニューの **[追加]** をクリックし、**[クラスの追加]** をクリックします。

1. [[クラスの追加]](../../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) ダイアログ ボックスで、**[テンプレート]** ウィンドウの **[ATL プロパティ ページ]** をクリックし、次に **[開く]** をクリックして、[ATL プロパティ ページ ウィザード](../../atl/reference/atl-property-page-wizard.md)を表示します。

コントロール用のプロパティ ページを作成したら、コントロールのプロパティ マップに [PROP_PAGE](property-map-macros.md#prop_page) エントリを指定する必要があります。

## <a name="see-also"></a>関連項目

[[プロパティ ページ]](../../atl/atl-com-property-pages.md)<br/>
[ATL COM オブジェクトの基礎](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[例: プロパティページの実装](../../atl/example-implementing-a-property-page.md)
