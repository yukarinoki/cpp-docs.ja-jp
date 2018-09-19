---
title: 'レコード セット: レコードを追加する方法 (ODBC) の |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, adding records
- recordsets, adding records
- bulk record additions to recordsets
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c870861d11a27b5343888e62259a585720274190
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068586"
---
# <a name="recordset-adding-records-in-bulk-odbc"></a>レコードセット: レコードを大量に追加する方法 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。  
  
MFC [CRecordset](../../mfc/reference/crecordset-class.md)クラスには、新しい最適化を一括でテーブルに新しいレコードを追加するときに、効率を向上させます。  
  
> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチを使用している場合は、次を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
新しいオプション、 *dwOptions*パラメーターを[:open](../../mfc/reference/crecordset-class.md#open)メンバー関数は、 `optimizeBulkAdd`を呼び出さずに連続して複数のレコードを追加するときにパフォーマンスが向上`Requery`または`Close`します。 1 つ目の前にダーティであるフィールドのみ`Update`呼び出しが後続のダーティとマークされて`AddNew` / `Update`呼び出し。  
  
活用するために、データベース クラスを使用しているかどうか、 `::SQLSetPos` ODBC API 関数を追加すると、編集、およびレコードを削除するには、この最適化は必要ありません。  
  
編集、および削除の場合は、ODBC カーソル ライブラリが読み込まれるか、ODBC ドライバーでは、追加もサポートされていません、 `::SQLSetPos`、この最適化のパフォーマンスを追加します。 この最適化を有効にするには設定、 *dwOptions*パラメーター、`Open`レコード セットを次の呼び出し。  
  
```  
appendOnly | optimizeBulkAdd  
```  
  
## <a name="see-also"></a>関連項目  

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: レコードの追加、更新、削除 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)<br/>
[レコードセット: レコードのロック (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)