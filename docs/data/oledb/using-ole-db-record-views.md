---
description: '詳細情報: OLE DB レコードビューの使用'
title: OLE DB レコード ビューの使用
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB record views
- COleDBRecordView class, overview
- rowsets, record views
- record views, record view objects
- OLE DB, record views
- MFC, record views
ms.assetid: 1cd3e595-ce08-43d8-a0a9-d03b5d3e24ce
ms.openlocfilehash: 8230ba118038852f81159d21a51165b7448a26aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332456"
---
# <a name="using-ole-db-record-views"></a>OLE DB レコード ビューの使用

MFC アプリケーションで OLE DB 行セットデータを表示する場合は、MFC クラスの [Cobf Brecordview](../../mfc/reference/coledbrecordview-class.md)を使用します。 から作成されたレコードビューオブジェクトを `COleDBRecordView` 使用すると、MFC コントロールにデータベースレコードを表示できます。 レコードビューは、テンプレートクラスから作成された OLE DB 行セットオブジェクトに直接接続されたダイアログフォームビューです `CRowset` 。 行セットオブジェクトへのハンドルの取得は簡単です。

```cpp
COleDBRecordView myRecordView;
...
// CProductAccessor is a user record class
CRowset<CAccessor<CProductAccessor>> myRowSet = myRecordView.OnGetRowset();
```

ビューには、ダイアログのコントロール内のオブジェクトのフィールドが表示され `CRowset` ます。 オブジェクトは、 `COleDBRecordView` ダイアログデータエクスチェンジ (DDX) と、(、、、および) に組み込まれているナビゲーション機能を使用して、 `CRowset` `MoveFirst` `MoveNext` `MovePrev` `MoveLast` フォーム上のコントロールと行セットのフィールドの間でのデータの移動を自動化します。 `COleDBRecordView` レコードビューがユーザーインターフェイスを更新し、別のレコードに移動する前に現在のレコードを更新するための [OnMove](../../mfc/reference/coledbrecordview-class.md#onmove) メソッドを提供できるように、行セット内のユーザーの位置を追跡します。

と共に DDX 関数を使用すると `COleDbRecordView` 、データベースレコードセットから直接データを取得し、ダイアログコントロールに表示できます。  <strong>\*</strong> DDX_Field 関数 (など) ではなく、DDX_ メソッド (など) を使用 `DDX_Text`  <strong>\*</strong> `DDX_FieldText` `COleDbRecordView` します。

## <a name="see-also"></a>関連項目

[アクセサーの使用](../../data/oledb/using-accessors.md)<br/>
[Cobf Brecordview クラス](../../mfc/reference/coledbrecordview-class.md)<br/>
