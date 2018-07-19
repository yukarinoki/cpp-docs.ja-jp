---
title: レコード ビュー (MFC データ アクセス) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], record views
- ODBC recordsets [C++], record views
- databases [C++], record views
- record views [C++]
- forms [C++], data access tasks
ms.assetid: 562122d9-01d8-4284-acf6-ea109ab0408d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 742866b2b11811ee37365ee6cc5e4d3aa881db91
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111251"
---
# <a name="record-views--mfc-data-access"></a>レコード ビュー (MFC データ アクセス)
このセクションでは、MFC ODBC クラスにのみ適用されます。 OLE DB レコード ビューについては、次を参照してください。 [COleDBRecordView](../mfc/reference/coledbrecordview-class.md)と[を使用して OLE DB レコード ビュー](../data/oledb/using-ole-db-record-views.md)です。  
  
 クラスを提供するクラス ライブラリのフォーム ベースのデータ アクセス アプリケーションをサポートする[CRecordView](../mfc/reference/crecordview-class.md)です。 レコード ビューは、フォーム ビュー オブジェクトがそのコントロールが、フィールドのデータ メンバーに直接マップされます、 [recordset](../data/odbc/recordset-odbc.md)オブジェクト (およびクエリの結果またはデータ ソースのテーブル内の対応する列に間接的に)。 基底クラスと同様に[CFormView](../mfc/reference/cformview-class.md)、`CRecordView`ダイアログ テンプレート リソースに基づきます。  
  
## <a name="form-uses"></a>フォームの利用  
 フォームは、さまざまなデータ アクセス タスクに使用できます。  
  
-   データの入力  
  
-   データが読み取り専用かどうかの検証の実行  
  
-   データの更新  
  
## <a name="further-reading-about-record-views"></a>レコード ビューについての詳細情報  
 トピックの内容は、ODBC ベースのクラスおよび DAO ベースのクラスに共通して適用されます。 ODBC の場合は `CRecordView` を、DAO の場合は `CDaoRecordView` を使用します。  
  
 ここでは、次の内容について説明します。  
  
-   [レコード ビュー クラスの機能](../data/features-of-record-view-classes-mfc-data-access.md)  
  
-   [レコード ビューのデータ交換](../data/data-exchange-for-record-views-mfc-data-access.md)  
  
-   [レコード ビューの操作でのロール](../data/your-role-in-working-with-a-record-view-mfc-data-access.md)  
  
-   [デザインとレコード ビューの作成](../data/designing-and-creating-a-record-view-mfc-data-access.md)  
  
-   [レコード ビューを使用します。](../data/using-a-record-view-mfc-data-access.md)  
  
## <a name="see-also"></a>関連項目  
 [データ アクセス プログラミング (MFC/ATL)](../data/data-access-programming-mfc-atl.md)   
 [ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)