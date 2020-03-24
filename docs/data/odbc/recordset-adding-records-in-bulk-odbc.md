---
title: 'レコードセット: レコードを大量に追加する方法 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, adding records
- recordsets, adding records
- bulk record additions to recordsets
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
ms.openlocfilehash: f561cb0275933a973e97ef0518148e81e14a0234
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213019"
---
# <a name="recordset-adding-records-in-bulk-odbc"></a>レコードセット: レコードを大量に追加する方法 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

MFC [CRecordset](../../mfc/reference/crecordset-class.md)クラスには、新しいレコードをテーブルに一括して追加する際の効率を向上させる新しい最適化が用意されています。

> [!NOTE]
> このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチを使用している場合は、「レコード[セット: レコードを一括フェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

[CRecordset:: Open](../../mfc/reference/crecordset-class.md#open)メンバー関数の*dwOptions*パラメーターの新しいオプションである `optimizeBulkAdd`を使用すると、`Requery` または `Close`を呼び出さずに複数のレコードを連続して追加する場合のパフォーマンスが向上します。 最初の `Update` 呼び出しの前にダーティであるフィールドのみが、後続の `AddNew`/`Update` の呼び出しに対してダーティとしてマークされます。

データベースクラスを使用してレコードの追加、編集、および削除を行うために `::SQLSetPos` ODBC API 関数を利用している場合、この最適化は不要です。

ODBC カーソルライブラリが読み込まれた場合、または ODBC ドライバーが `::SQLSetPos`による追加、編集、および削除をサポートしていない場合は、この最適化によって一括追加のパフォーマンスが向上します。 この最適化を有効にするには、レコードセットの `Open` の呼び出しで、 *dwOptions*パラメーターを次のように設定します。

```
appendOnly | optimizeBulkAdd
```

## <a name="see-also"></a>参照

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: レコードの追加、更新、削除 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)<br/>
[レコードセット: レコードのロック (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)
