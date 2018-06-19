---
title: 'レコード セット: バルク (ODBC) レコードを追加する |Microsoft ドキュメント'
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
ms.openlocfilehash: 7bb39b910eae797f360513954ad0c32d5e99bb86
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089286"
---
# <a name="recordset-adding-records-in-bulk-odbc"></a>レコードセット: レコードを大量に追加する方法 (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 MFC [CRecordset](../../mfc/reference/crecordset-class.md)クラスにはテーブルに一括で新しいレコードを追加するときに、効率を向上させる新しい最適化します。  
  
> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチを使用している場合は、次を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。  
  
 新しいオプション、 **dwOptions**パラメーターを[:open](../../mfc/reference/crecordset-class.md#open)メンバー関数は、 **optimizeBulkAdd**、複数のレコードを追加するときにパフォーマンスが向上呼び出さずに連続して**Requery**または**閉じる**です。 1 つ目の前にダーティであるフィールドだけ**更新**呼び出しが後続のダーティとマークされて`AddNew` /**更新**呼び出しです。  
  
 データベース クラスを活用するために使用するかどうか、 **:: SQLSetPos** ODBC API 関数の追加、編集、およびレコードを削除するには、この最適化は必要ありません。  
  
 ODBC カーソル ライブラリが読み込まれる、または ODBC ドライバーでは、追加もサポートされていません、編集、および削除 **:: SQLSetPos**、この最適化のパフォーマンスを追加します。 この最適化を有効にするには設定、 **dwOptions**内のパラメーター、**開く**レコード セットには、次の呼び出し。  
  
```  
appendOnly | optimizeBulkAdd  
```  
  
## <a name="see-also"></a>関連項目  
 [レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)   
 [レコード セット: 追加、更新、および削除 (Odbc)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)   
 [レコードセット: レコードのロック (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)