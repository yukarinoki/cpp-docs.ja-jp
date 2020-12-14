---
description: 詳細については、「レコードビューを使用したロールの操作 (MFC データアクセス)」を参照してください。
title: レコード ビューを利用するために必要な作業 (MFC データ アクセス)
ms.date: 11/04/2016
helpviewer_keywords:
- record views, customizing default code
- MFC, record views
ms.assetid: 691e89a5-ff21-4ca3-9278-69d4678288bb
ms.openlocfilehash: f1eff5db930859ca1956286a9364c72b02f2b473
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302609"
---
# <a name="your-role-in-working-with-a-record-view--mfc-data-access"></a>レコード ビューを利用するために必要な作業 (MFC データ アクセス)

次の表は、レコード ビューを使用するために通常必要となる作業と、フレームワークの役割を示しています。

### <a name="working-with-a-record-view-you-and-the-framework"></a>レコード ビューの使用: プログラマとフレームワーク

|自分|フレームワークの役割|
|---------|-------------------|
|Visual C++ ダイアログ エディターを使用して、フォームをデザインします。|コントロール付きのダイアログ テンプレート リソースを作成します。|
|[MFC アプリケーションウィザード](../mfc/reference/database-support-mfc-application-wizard.md)を使用して、 [CRecordView](../mfc/reference/crecordview-class.md)および[CRecordset](../mfc/reference/crecordset-class.md)から派生したクラスを作成します。|派生クラスを作成します。|
|レコード ビューのコントロールをレコードセットのフィールド データ メンバーに対応付けます。|コントロールとレコードセット フィールド間で DDX を行います。|
||メニューまたはツールバーのボタンから、[ **最初** に移動]、[ **最後** に移動]、[ **次** に移動]、および [ **前** に移動] コマンドの既定のコマンドハンドラーを提供します。|
||データ ソースへの変更を反映します。|
|(省略可能) リスト ボックス、コンボ ボックスなどのコントロールにセカンド レコードセットのデータを設定するためのコードを記述します。||
|(省略可能) 特別な検証用のコードを記述します。||
|(省略可能) レコードを追加または削除するためのコードを記述します。||

フォーム ベースのプログラミングは、データベース操作の単なる 1 つの手法です。 他のユーザーインターフェイスを使用するアプリケーション、またはユーザーインターフェイスを使用しないアプリケーションの詳細については、「Mfc: ドキュメントとビューを使用し [たデータベースクラスの使用](../data/mfc-using-database-classes-with-documents-and-views.md) 」および「 [mfc: ドキュメントとビューを使用しないデータベースクラスの使用](../data/mfc-using-database-classes-without-documents-and-views.md)」を参照してください。 データベースレコードを表示する別の方法については、「 [CListView](../mfc/reference/clistview-class.md) and [CTreeView](../mfc/reference/ctreeview-class.md)classes」を参照してください。

## <a name="see-also"></a>関連項目

[レコードビュー (MFC データアクセス)](../data/record-views-mfc-data-access.md)<br/>
[ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)
