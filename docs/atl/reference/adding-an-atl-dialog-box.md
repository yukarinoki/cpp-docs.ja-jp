---
description: 詳細については、「ATL ダイアログボックスの追加」を参照してください。
title: ATL ダイアログ ボックスの追加
ms.date: 11/04/2016
helpviewer_keywords:
- ATL projects, adding dialog resources
- MFC dialog boxes, ATL dialogs
- dialog boxes, ATL
ms.assetid: 152a378f-7b24-4f66-aeba-c740973f03a6
ms.openlocfilehash: 9d4abcafd5e12c6b8cffd636bf28a9e79f96e5ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165720"
---
# <a name="adding-an-atl-dialog-box"></a>ATL ダイアログ ボックスの追加

Atl ダイアログをプロジェクトに追加するには、atl プロジェクトか、ATL サポートを含む MFC プロジェクトである必要があります。 Atl [プロジェクトウィザード](../../atl/reference/atl-project-wizard.md) を使用して atl アプリケーションを作成するか、mfc アプリケーション [に atl オブジェクトを追加](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) して、mfc アプリケーションの atl サポートを実装することができます。

ATL ダイアログウィザードの既定では、 [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md)から派生したダイアログボックスが実装されます。 このクラスには、ActiveX および Windows コントロールをホストするためのサポートが含まれています。 ActiveX コントロールのサポートのオーバーヘッドを避けたい場合は、ウィザードによってコードが生成されたら、のすべてのインスタンスを、 `CAxDialogImpl` 基底クラスとして [CSimpleDialog](../../atl/reference/csimpledialog-class.md) または [CDialogImpl](../../atl/reference/cdialogimpl-class.md) に置き換えます。

> [!NOTE]
> `CSimpleDialog` Windows コモンコントロールのみをサポートするモーダルダイアログボックスを作成します。 `CDialogImpl` モーダルダイアログボックスまたはモードレスダイアログボックスを作成します。

## <a name="to-add-an-atl-dialog-resource-to-your-project"></a>ATL ダイアログリソースをプロジェクトに追加するには

1. Atl [プロジェクトウィザード](../../atl/reference/atl-project-wizard.md)を使用して atl プロジェクトを作成します。

1. [クラスビュー](/visualstudio/ide/viewing-the-structure-of-code)で、プロジェクト名を右クリックし、ショートカットメニューの [**追加**] をクリックします。 **[クラスの追加]** をクリックします。

1. [[クラスの追加](../../ide/adding-a-class-visual-cpp.md#add-class-dialog-box)] ダイアログボックスの [**テンプレート**] ペインで、[ **ATL ダイアログ**] をクリックします。 [ **開く** ] をクリックして、 [ATL ダイアログウィザード](../../atl/reference/atl-dialog-wizard.md)を表示します。

詳細については、「 [ダイアログボックスの実装](../../atl/implementing-a-dialog-box.md)」を参照してください。

## <a name="see-also"></a>関連項目

[クラスの追加](../../ide/adding-a-class-visual-cpp.md)<br/>
[ウィンドウクラス](../../atl/atl-window-classes.md)<br/>
[メッセージ マップ](../../atl/message-maps-atl.md)
