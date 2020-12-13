---
description: '詳細については、「レコードセット: レコードを一括で追加する (ODBC)」を参照してください。'
title: 'レコードセット: レコードを大量に追加する方法 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, adding records
- recordsets, adding records
- bulk record additions to recordsets
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
ms.openlocfilehash: 5cb47fc8e96a38b2e5cc6c83cf464f28f2a85aaf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340399"
---
# <a name="recordset-adding-records-in-bulk-odbc"></a>レコードセット: レコードを大量に追加する方法 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

MFC [CRecordset](../../mfc/reference/crecordset-class.md) クラスには、新しいレコードをテーブルに一括して追加する際の効率を向上させる新しい最適化が用意されています。

> [!NOTE]
> このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチを使用している場合は、「レコード [セット: レコードを一括フェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

[CRecordset:: Open](../../mfc/reference/crecordset-class.md#open)メンバー関数の *dwOptions* パラメーターの新しいオプションで `optimizeBulkAdd` は、またはを呼び出さずに複数のレコードを連続して追加すると、パフォーマンスが向上し `Requery` `Close` ます。 最初の呼び出しの前にダーティであるフィールドのみ `Update` が、後続の呼び出しに対してダーティとしてマークされ `AddNew` / `Update` ます。

データベースクラスを使用して、 `::SQLSetPos` レコードの追加、編集、および削除のために ODBC API 関数を利用している場合、この最適化は不要です。

ODBC カーソルライブラリが読み込まれた場合、または ODBC ドライバーがの追加、編集、および削除をサポートしていない場合は `::SQLSetPos` 、この最適化によって一括追加のパフォーマンスが向上します。 この最適化を有効にするには 、 `Open` レコードセットの呼び出しで dwOptions パラメーターを次のように設定します。

```
appendOnly | optimizeBulkAdd
```

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: レコードの追加、更新、および削除 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)<br/>
[レコードセット: レコードのロック (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)
