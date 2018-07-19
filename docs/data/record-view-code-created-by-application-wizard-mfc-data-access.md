---
title: アプリケーション ウィザード (MFC データ アクセス) で作成したコードの表示を記録 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- application wizards [C++], record view code
- record views, refreshing controls
- record views, application wizard code
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 15355d156b3c85c8f99ba638b30f831da96686af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33107104"
---
# <a name="record-view-code-created-by-application-wizard--mfc-data-access"></a>アプリケーション ウィザードで作成されたレコード ビューのコード (MFC データ アクセス)
[MFC アプリケーション ウィザード](../mfc/reference/database-support-mfc-application-wizard.md)上書きの表示の`OnInitialUpdate`と`OnGetRecordset`メンバー関数。 このフレームワークによってフレーム ウィンドウ、ドキュメント、およびビューが作成された後、`OnInitialUpdate` が呼び出されてビューが初期化されます。 `OnInitialUpdate` は、レコードセットへのポインターをドキュメントから取得します。 基底クラスへの呼び出し[:oninitialupdate](../mfc/reference/cview-class.md#oninitialupdate)関数は、レコード セットを開きます。 次のコードは、このプロセスを示します、 `CRecordView`:  
  
```  
void CSectionForm::OnInitialUpdate()  
{  
   m_pSet = &GetDocument()->m_sectionSet;  
   CRecordView::OnInitialUpdate();  
}  
```  
  
 レコードセットが開くと、レコードが選択されます。 [:Open](../mfc/reference/crecordset-class.md#open)最初のレコードは、現在のレコードと DDX にデータを移動、レコード セットのフィールド データ メンバーから、対応するコントロールをフォーム ビューでします。 RFX の詳細については、次を参照してください。[レコード フィールド エクス チェンジ (RFX)](../data/odbc/record-field-exchange-rfx.md)です。 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../mfc/dialog-data-exchange-and-validation.md)です。 ドキュメント/ビューの作成手順については、次を参照してください。[クラスを Windows アプリケーションの作成に使用する](../mfc/using-the-classes-to-write-applications-for-windows.md)です。  
  
> [!NOTE]
>  エンド ユーザーには、レコードセットからレコード ビュー コントロールを更新するための機能を提供する必要があります。 この機能がないと、ユーザーがコントロールの値を無効な値に変更した場合に、現在のレコードを一切操作できなくなる可能性があります。 更新するには、コントロールを呼び出す、`CWnd`メンバー関数は、 [UpdateData](../mfc/reference/cwnd-class.md#updatedata)のパラメーターを持つ**FALSE**です。  
  
## <a name="see-also"></a>関連項目  
 [レコード ビューを使用します。](../data/using-a-record-view-mfc-data-access.md)