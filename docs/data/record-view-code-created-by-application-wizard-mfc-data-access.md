---
title: アプリケーション ウィザード (MFC データ アクセス) で作成したコードの表示を記録 |Microsoft Docs
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
ms.openlocfilehash: f2b98e66b6aac51f0ac6685943af75f14d631c21
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117713"
---
# <a name="record-view-code-created-by-application-wizard--mfc-data-access"></a>アプリケーション ウィザードで作成されたレコード ビューのコード (MFC データ アクセス)

[MFC アプリケーション ウィザード](../mfc/reference/database-support-mfc-application-wizard.md)上書きビューの`OnInitialUpdate`と`OnGetRecordset`メンバー関数。 このフレームワークによってフレーム ウィンドウ、ドキュメント、およびビューが作成された後、`OnInitialUpdate` が呼び出されてビューが初期化されます。 `OnInitialUpdate` は、レコードセットへのポインターをドキュメントから取得します。 基底クラスへの呼び出し[:oninitialupdate](../mfc/reference/cview-class.md#oninitialupdate)関数は、レコード セットを開きます。 次のコードに対して、このプロセスを示しています、 `CRecordView`:  
  
```cpp  
void CSectionForm::OnInitialUpdate()  
{  
   m_pSet = &GetDocument()->m_sectionSet;  
   CRecordView::OnInitialUpdate();  
}  
```  
  
レコードセットが開くと、レコードが選択されます。 [:Open](../mfc/reference/crecordset-class.md#open) DDX にデータを移動、レコード セットのフィールド データ メンバーから、対応するコントロールをフォーム ビューで、現在のレコードは、最初のレコードを使用します。 RFX の詳細については、次を参照してください。[レコード フィールド エクス チェンジ (RFX)](../data/odbc/record-field-exchange-rfx.md)します。 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../mfc/dialog-data-exchange-and-validation.md)です。 ドキュメント/ビューの作成手順については、次を参照してください。 [Windows のアプリケーションを記述するクラスを使用して](../mfc/using-the-classes-to-write-applications-for-windows.md)します。  
  
> [!NOTE]
>  エンド ユーザーには、レコードセットからレコード ビュー コントロールを更新するための機能を提供する必要があります。 この機能がないと、ユーザーがコントロールの値を無効な値に変更した場合に、現在のレコードを一切操作できなくなる可能性があります。 呼び出すコントロールを更新する、`CWnd`メンバー関数は[UpdateData](../mfc/reference/cwnd-class.md#updatedata) FALSE のパラメーターを持つ。  
  
## <a name="see-also"></a>関連項目  

[レコード ビューの使用](../data/using-a-record-view-mfc-data-access.md)