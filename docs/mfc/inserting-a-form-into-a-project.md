---
title: プロジェクトにフォームの挿入 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inserting forms [MFC]
- Insert New dialog box [MFC]
- forms, adding to projects
ms.assetid: f3bd2998-3ce2-496d-ac5c-57ca70eec7cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e62618301e09ad4c44fb91608976ecab972a59da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="inserting-a-form-into-a-project"></a>プロジェクトへのフォームの挿入
形式は、コントロールの便利なコンテナーを提供します。 簡単に、アプリケーションは、MFC ライブラリをサポートしている限り、MFC ベースのフォームをアプリケーションに挿入できます。  
  
### <a name="to-insert-a-form-into-your-project"></a>プロジェクトにフォームを挿入するには  
  
1.  クラス ビュー、フォームを追加するプロジェクトを選択し、マウスの右ボタンをクリックします。  
  
2.  ショートカット メニューから **[追加]** をクリックし、**クラスの追加**です。  
  
     場合、**新しいフォーム**コマンドではないプロジェクトは、アクティブ テンプレート ライブラリ (ATL) に基づく可能性があります場合、。 ATL プロジェクトにフォームを追加するにする必要があります[特定の設定を指定](../atl/reference/application-settings-atl-project-wizard.md)プロジェクトを作成しているとき。  
  
3.  **MFC**フォルダーで、をクリックして**MFC クラス**です。  
  
4.  MFC クラス ウィザードを使用すると、新しいクラスから派生[CFormView](../mfc/reference/cformview-class.md)です。  
  
 Visual C フォーム アプリケーションへの追加を開始することができるように、ダイアログ エディター内開くコントロールの追加とその全体的な設計に使用します。  
  
 (この機能は、ダイアログ ベースのアプリケーションでは該当しません)、次の手順を実行することがあります。  
  
1.  上書き、`OnUpdate`メンバー関数。  
  
2.  ビューからデータをドキュメントに移動するメンバー関数を実装します。  
  
3.  作成、`OnPrint`メンバー関数。  
  
## <a name="see-also"></a>関連項目  
 [フォーム ビュー](../mfc/form-views-mfc.md)

