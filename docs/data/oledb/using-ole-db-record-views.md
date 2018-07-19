---
title: OLE DB レコード ビューの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB record views
- COleDBRecordView class, overview
- rowsets, record views
- record views, record view objects
- OLE DB, record views
- MFC, record views
ms.assetid: 1cd3e595-ce08-43d8-a0a9-d03b5d3e24ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6cebf8a1c1130a33ffd07e2d23d65c55a2a67b34
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111274"
---
# <a name="using-ole-db-record-views"></a>OLE DB レコード ビューの使用
MFC アプリケーションで OLE DB 行セットのデータを表示する場合は、MFC クラスを使用する必要があります[COleDBRecordView](../../mfc/reference/coledbrecordview-class.md)です。 レコード ビュー オブジェクトから作成`COleDBRecordView`MFC コントロールのデータベース レコードを表示することができます。 レコード ビューから作成された OLE DB 行セット オブジェクトに直接接続して、ダイアログ フォーム ビューとは、`CRowset`テンプレート クラス。 行セット オブジェクトへのハンドルを取得するは単純です。  
  
```  
COleDBRecordView myRecordView;  
...  
// CProductAccessor is a user record class  
CRowset<CAccessor<CProductAccessor>> myRowSet = myRecordView.OnGetRowset();  
```  
  
 ビューのフィールドの表示、 `CRowset`  ダイアログ ボックスのコントロール内のオブジェクト。 `COleDBRecordView`ダイアログ データ Exchange (DDX) を使用するオブジェクトとナビゲーション機能に組み込まれて`CRowset`(**MoveFirst**、 `MoveNext`、 `MovePrev`、および`MoveLast`) データの移動を自動化するにはフォームと行セットのフィールドのコントロール間です。 `COleDBRecordView` 追跡、行セット内のユーザーの位置、レコード ビューは、ユーザー インターフェイスと供給を更新できるように、 [OnMove](../../mfc/reference/coledbrecordview-class.md#onmove)別に移動する前に、現在のレコードを更新するためのメソッドです。  
  
 DDX 関数を使用することができます**COleDbRecordView**データベース レコード セットから直接データを取得し、ダイアログ コントロールで表示します。 使用する必要があります、 **ddx _\*** メソッド (など`DDX_Text`) ではなく、 **DDX_Field\*** 関数 (など`DDX_FieldText`) と**COleDbRecordView**.  
  
## <a name="see-also"></a>関連項目  
 [アクセサーの使用](../../data/oledb/using-accessors.md)   
 [COleDBRecordView クラス](../../mfc/reference/coledbrecordview-class.md)