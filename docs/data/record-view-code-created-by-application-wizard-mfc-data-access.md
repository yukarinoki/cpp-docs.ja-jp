---
title: アプリケーション ウィザードで作成されたレコード ビューのコード (MFC データ アクセス)
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [C++], record view code
- record views, refreshing controls
- record views, application wizard code
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
ms.openlocfilehash: 69481299980329b98e378f02e090670fa3d7ece2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376017"
---
# <a name="record-view-code-created-by-application-wizard--mfc-data-access"></a>アプリケーション ウィザードで作成されたレコード ビューのコード (MFC データ アクセス)

[MFC アプリケーション ウィザード](../mfc/reference/database-support-mfc-application-wizard.md)は、ビュー`OnInitialUpdate`と`OnGetRecordset`メンバー関数をオーバーライドします。 このフレームワークによってフレーム ウィンドウ、ドキュメント、およびビューが作成された後、`OnInitialUpdate` が呼び出されてビューが初期化されます。 `OnInitialUpdate` は、レコードセットへのポインターをドキュメントから取得します。 基本クラス[CView::OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate)関数を呼び出すと、レコードセットが開かれます。 次のコードは、 のこの`CRecordView`プロセスを示しています。

```cpp
void CSectionForm::OnInitialUpdate()
{
   m_pSet = &GetDocument()->m_sectionSet;
   CRecordView::OnInitialUpdate();
}
```

レコードセットが開くと、レコードが選択されます。 [CRecordset::Open](../mfc/reference/crecordset-class.md#open)は最初のレコードをカレント レコードにし、DDX はレコードセットのフィールド データ メンバからビュー内の対応するフォーム コントロールにデータを移動します。 RFX の詳細については、「[レコード フィールド エクスチェンジ (RFX)」](../data/odbc/record-field-exchange-rfx.md)を参照してください。 DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 ドキュメント/ビューの作成プロセスの詳細については、「 [Windows 用アプリケーションを記述するためのクラスの使用](../mfc/using-the-classes-to-write-applications-for-windows.md)」を参照してください。

> [!NOTE]
> エンド ユーザーには、レコードセットからレコード ビュー コントロールを更新するための機能を提供する必要があります。 この機能がないと、ユーザーがコントロールの値を無効な値に変更した場合に、現在のレコードを一切操作できなくなる可能性があります。 コントロールを更新するには、メンバー関数`CWnd`[UpdateData](../mfc/reference/cwnd-class.md#updatedata)を FALSE のパラメーターで呼び出します。

## <a name="see-also"></a>関連項目

[レコード ビューの使用法](../data/using-a-record-view-mfc-data-access.md)
