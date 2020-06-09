---
title: プロジェクトへのフォームの挿入
ms.date: 11/04/2016
helpviewer_keywords:
- inserting forms [MFC]
- Insert New dialog box [MFC]
- forms, adding to projects
ms.assetid: f3bd2998-3ce2-496d-ac5c-57ca70eec7cb
ms.openlocfilehash: 8e3162ac3917781920130bcbed23864eb90afa59
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618429"
---
# <a name="inserting-a-form-into-a-project"></a>プロジェクトへのフォームの挿入

フォームは、コントロールに便利なコンテナーを提供します。 アプリケーションが MFC ライブラリをサポートしている限り、MFC ベースのフォームをアプリケーションに簡単に挿入できます。

### <a name="to-insert-a-form-into-your-project"></a>プロジェクトにフォームを挿入するには

1. クラスビューから、フォームを追加するプロジェクトを選択し、マウスの右ボタンをクリックします。

1. ショートカット メニューの **[追加]** をクリックし、**[クラスの追加]** をクリックします。

   **新しいフォーム**コマンドが使用できない場合は、プロジェクトが ACTIVE TEMPLATE LIBRARY (ATL) に基づいている可能性があります。 ATL プロジェクトにフォームを追加するには、最初にプロジェクトを作成するときに[特定の設定を指定](../atl/reference/application-settings-atl-project-wizard.md)する必要があります。

1. **Mfc**フォルダーの [ **mfc クラス**] をクリックします。

1. MFC クラスウィザードを使用して、新しいクラスを[CFormView](reference/cformview-class.md)から派生させます。

Visual C++ によって、フォームがアプリケーションに追加され、ダイアログエディター内で開かれます。これにより、コントロールの追加とデザイン全体の作業を開始できます。

次の追加の手順を実行することもできます (ダイアログベースのアプリケーションには適用されません)。

1. `OnUpdate`メンバー関数をオーバーライドします。

1. メンバー関数を実装して、ビューからドキュメントにデータを移動します。

1. `OnPrint`メンバー関数を作成します。

## <a name="see-also"></a>関連項目

[フォーム ビュー](form-views-mfc.md)
