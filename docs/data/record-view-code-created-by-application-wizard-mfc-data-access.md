---
description: 詳細については、「アプリケーションウィザードで作成されたレコードビューのコード (MFC データアクセス)」を参照してください。
title: アプリケーション ウィザードで作成されたレコード ビューのコード (MFC データ アクセス)
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [C++], record view code
- record views, refreshing controls
- record views, application wizard code
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
ms.openlocfilehash: b0fa7a4960096f11ab66194fa6e41be60b45d4c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332436"
---
# <a name="record-view-code-created-by-application-wizard--mfc-data-access"></a>アプリケーション ウィザードで作成されたレコード ビューのコード (MFC データ アクセス)

[MFC アプリケーションウィザード](../mfc/reference/database-support-mfc-application-wizard.md)では、ビューの `OnInitialUpdate` およびメンバー関数がオーバーライドされ `OnGetRecordset` ます。 このフレームワークによってフレーム ウィンドウ、ドキュメント、およびビューが作成された後、`OnInitialUpdate` が呼び出されてビューが初期化されます。 `OnInitialUpdate` は、レコードセットへのポインターをドキュメントから取得します。 基底クラスの [CView:: OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) 関数を呼び出すと、レコードセットが開かれます。 次のコードは、のこのプロセスを示してい `CRecordView` ます。

```cpp
void CSectionForm::OnInitialUpdate()
{
   m_pSet = &GetDocument()->m_sectionSet;
   CRecordView::OnInitialUpdate();
}
```

レコードセットが開くと、レコードが選択されます。 [CRecordset:: Open](../mfc/reference/crecordset-class.md#open) では最初のレコードが現在のレコードになり、DDX はレコードセットのフィールドデータメンバーからビュー内の対応するフォームコントロールにデータを移動します。 RFX の詳細については、「 [レコードフィールドエクスチェンジ (rfx)](../data/odbc/record-field-exchange-rfx.md)」を参照してください。 DDX の詳細については、「 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../mfc/dialog-data-exchange-and-validation.md)」を参照してください。 ドキュメント/ビューの作成プロセスの詳細については、「 [Windows 用のアプリケーションを記述するためのクラスの使用](../mfc/using-the-classes-to-write-applications-for-windows.md)」を参照してください。

> [!NOTE]
> エンド ユーザーには、レコードセットからレコード ビュー コントロールを更新するための機能を提供する必要があります。 この機能がないと、ユーザーがコントロールの値を無効な値に変更した場合に、現在のレコードを一切操作できなくなる可能性があります。 コントロールを更新するには、 `CWnd` パラメーターが FALSE のメンバー関数 [UpdateData](../mfc/reference/cwnd-class.md#updatedata) を呼び出します。

## <a name="see-also"></a>関連項目

[レコード ビューの使用法](../data/using-a-record-view-mfc-data-access.md)
