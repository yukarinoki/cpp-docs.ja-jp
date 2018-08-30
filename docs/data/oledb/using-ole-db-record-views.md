---
title: OLE DB レコード ビューの使用 |Microsoft Docs
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
ms.openlocfilehash: b0b787686fc09d943de030645d56465cd259bc37
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215768"
---
# <a name="using-ole-db-record-views"></a>OLE DB レコード ビューの使用
MFC アプリケーションで OLE DB 行セットのデータを表示する場合は、MFC クラスを使用する必要があります[COleDBRecordView](../../mfc/reference/coledbrecordview-class.md)します。 レコード ビュー オブジェクトから作成`COleDBRecordView`MFC コントロールでのデータベース レコードを表示することができます。 レコード ビューが作成された OLE DB 行セット オブジェクトに直接接続ダイアログ フォーム ビュー、`CRowset`テンプレート クラス。 行セット オブジェクトを識別するハンドルを取得するは簡単です。  
  
```cpp  
COleDBRecordView myRecordView;  
...  
// CProductAccessor is a user record class  
CRowset<CAccessor<CProductAccessor>> myRowSet = myRecordView.OnGetRowset();  
```  
  
 ビューのフィールドの表示、 `CRowset`  ダイアログ ボックスのコントロール内のオブジェクト。 `COleDBRecordView`オブジェクトは、ダイアログ Data Exchange (DDX) を使用し、ナビゲーションの機能に組み込まれて`CRowset`(`MoveFirst`、 `MoveNext`、 `MovePrev`、および`MoveLast`)、フォーム上のコントロール間のデータの移動を自動化するには行セットのフィールド。 `COleDBRecordView` レコード ビューは、ユーザー インターフェイスと提供を更新できるようにに、行セット内のユーザーの位置はの追跡、 [OnMove](../../mfc/reference/coledbrecordview-class.md#onmove)間で移動する前に、現在のレコードを更新するためのメソッド。  
  
 DDX 関数を使用する`COleDbRecordView`をデータベースのレコード セットから直接データを取得し、ダイアログ コントロールに表示します。 使用する必要があります、 **DDX_** <strong>\*</strong>メソッド (など`DDX_Text`) ではなく、 **DDX_Field** <strong>\*</strong>関数 (など`DDX_FieldText`) と`COleDbRecordView`します。  
  
## <a name="see-also"></a>関連項目  
 [アクセサーの使用](../../data/oledb/using-accessors.md)   
 [COleDBRecordView クラス](../../mfc/reference/coledbrecordview-class.md)