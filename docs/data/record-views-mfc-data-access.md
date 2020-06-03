---
title: レコード ビュー (MFC データ アクセス)
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], record views
- ODBC recordsets [C++], record views
- databases [C++], record views
- record views [C++]
- forms [C++], data access tasks
ms.assetid: 562122d9-01d8-4284-acf6-ea109ab0408d
ms.openlocfilehash: 31dbd92219f263c625050524279b97ef38ba9ba1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209132"
---
# <a name="record-views--mfc-data-access"></a>レコード ビュー (MFC データ アクセス)

このセクションは、MFC ODBC クラスにのみ適用されます。 OLE DB レコードビューの詳細に[ついては、「](../mfc/reference/coledbrecordview-class.md) [OLE DB レコードビューの使用](../data/oledb/using-ole-db-record-views.md)」および「レコードビューの使用」を参照してください。

フォームベースのデータアクセスアプリケーションをサポートするために、クラスライブラリにはクラス[CRecordView](../mfc/reference/crecordview-class.md)が用意されています。 レコードビューは、コントロールが[レコードセット](../data/odbc/recordset-odbc.md)オブジェクトのフィールドデータメンバーに直接マップされるフォームビューオブジェクトです (また、データソースのクエリ結果またはテーブル内の対応する列に間接的にマップされます)。 基本クラス[CFormView](../mfc/reference/cformview-class.md)と同様に、`CRecordView` はダイアログテンプレートリソースに基づいています。

## <a name="form-uses"></a>フォームの利用

フォームは、さまざまなデータ アクセス タスクに使用できます。

- データの入力

- データが読み取り専用かどうかの検証の実行

- データを更新する

## <a name="further-reading-about-record-views"></a>レコード ビューについての詳細情報

トピックの内容は、ODBC ベースのクラスおよび DAO ベースのクラスに共通して適用されます。 ODBC の場合は `CRecordView` を、DAO の場合は `CDaoRecordView` を使用します。

取り上げるトピックは次のとおりです。

- [レコードビュークラスの機能](../data/features-of-record-view-classes-mfc-data-access.md)

- [レコードビューのデータ交換](../data/data-exchange-for-record-views-mfc-data-access.md)

- [レコードビューを操作するときのロール](../data/your-role-in-working-with-a-record-view-mfc-data-access.md)

- [レコードビューのデザインと作成](../data/designing-and-creating-a-record-view-mfc-data-access.md)

- [レコードビューの使用](../data/using-a-record-view-mfc-data-access.md)

## <a name="see-also"></a>参照

[データ アクセス プログラミング (MFC/ATL)](../data/data-access-programming-mfc-atl.md)<br/>
[ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)
