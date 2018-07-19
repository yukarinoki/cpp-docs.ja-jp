---
title: 'トランザクション: トランザクションに与える影響 (ODBC) の更新プログラム |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- transactions, updating recordsets
- ODBC recordsets, transactions
- transactions, rolling back
- CommitTrans method
- Rollback method, ODBC transactions
ms.assetid: 9e00bbf4-e9fb-4332-87fc-ec8ac61b3f68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 549f8495ca3a088ec4314cd26318d19f9a5a3176
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098005"
---
# <a name="transaction-how-transactions-affect-updates-odbc"></a>トランザクション: トランザクションが更新処理に与える影響 (ODBC)
更新、[データソース](../../data/odbc/data-source-odbc.md)エディット バッファー (トランザクションの外部で使用される同じメソッド) を使用してトランザクション中には、管理します。 レコード セットのフィールド データ メンバーは総称して、レコード セットのバックアップを取得中に一時的に現在のレコードを格納しているエディット バッファーとして機能する`AddNew`または**編集**です。 中に、**削除**操作、現在のレコードはトランザクション内でバックアップされません。 エディット バッファーおよび更新プログラムが現在のレコードを格納する方法の詳細については、次を参照してください。[レコード セット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)です。  
  
> [!NOTE]
>  バルク行フェッチを実装した場合を呼び出すことはできません`AddNew`、**編集**、または**削除**です。 代わりに、データ ソースへの更新を実行する、独自の関数を記述する必要があります。 バルク行フェッチの詳細については、次を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。  
  
 トランザクションを処理中に`AddNew`、**編集**、および**削除**操作をコミットまたはロールバックすることができます。 効果**CommitTrans**と**ロールバック**エディット バッファーには復元されませんを現在のレコードが発生する可能性があります。 現在のレコードが適切に復元することを確認するには、理解しておく必要がどのように**CommitTrans**と**ロールバック**のメンバー関数`CDatabase`の更新機能で機能`CRecordset`.  
  
##  <a name="_core_how_committrans_affects_updates"></a> CommitTrans が更新プログラムに与える影響  
 次の表の効果を説明する**CommitTrans**トランザクションにします。  
  
### <a name="how-committrans-affects-updates"></a>CommitTrans が更新プログラムに与える影響  
  
|操作|データ ソースの状態|  
|---------------|---------------------------|  
|`AddNew` および**更新**、し**CommitTrans**|新しいレコードは、データ ソースに追加されます。|  
|`AddNew` (なし**更新**)、し**CommitTrans**|新しいレコードが失われます。 レコードがデータ ソースに追加されません。|  
|**編集**と**更新**、し**CommitTrans**|データ ソースにコミットを編集します。|  
|**編集**(せず**更新**)、し**CommitTrans**|レコードの更新結果は失われます。 レコードは、データ ソースでは変更されません。|  
|**削除**し**CommitTrans**|レコードがデータ ソースから削除されました。|  
  
##  <a name="_core_how_rollback_affects_updates"></a> トランザクションのロールバックの影響  
 次の表の効果を説明する**ロールバック**トランザクションにします。  
  
### <a name="how-rollback-affects-transactions"></a>トランザクションのロールバックの影響  
  
|操作|現在のレコードの状態|する必要があります。|データ ソースの状態|  
|---------------|------------------------------|-------------------|---------------------------|  
|`AddNew` および**更新**、し**ロールバック**|現在のレコードのコンテンツは、新しいレコードを確保するために一時的に格納されます。 新しいレコードは、エディット バッファーに入力されます。 後に**更新**が呼び出されると、現在のレコードをエディット バッファーに復元します。||によるデータ ソースへの追記を**更新**を反転します。|  
|`AddNew` (なし**更新**)、し**ロールバック**|現在のレコードのコンテンツは、新しいレコードを確保するために一時的に格納されます。 編集バッファーに新しいレコードが含まれています。|呼び出す`AddNew`に空の新しいレコードをエディット バッファーを戻します。 呼び出すまたは**移動**をエディット バッファーに古い値を復元するには、(0) です。|**更新**呼び出されませんでした、データ ソースに加えられた変更はありませんでした。|  
|**編集**と**更新**、し**ロールバック**|現在のレコードの編集前のバージョンは一時的に格納されます。 エディット バッファーの内容には、編集が行われています。 後に**更新**が呼び出されたが、編集前のレコードのバージョンがまだ一時的に格納されています。|*ダイナセット*: 現在のレコードから外してをエディット バッファーに、レコードの編集前のバージョンを復元するバックアップをスクロールします。<br /><br /> *スナップショット*: 呼び出す**Requery**をデータ ソースからレコード セットを更新します。|データ ソースによって行われた変更**更新**が取り消されます。|  
|**編集**(せず**更新**)、し**ロールバック**|現在のレコードの編集前のバージョンは一時的に格納されます。 エディット バッファーの内容には、編集が行われています。|呼び出す**編集**もう一度をエディット バッファーにレコードの編集前のバージョンを復元します。|**更新**呼び出されませんでした、データ ソースに加えられた変更はありませんでした。|  
|**削除**し**ロールバック**|現在のレコードの内容が削除されます。|呼び出す**Requery**をデータ ソースから現在のレコードの内容を復元します。|データ ソースからデータの削除が取り消されます。|  
  
## <a name="see-also"></a>関連項目  
 [トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)   
 [トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)   
 [トランザクション: レコード セット (ODBC) からのトランザクションの実行](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)   
 [CDatabase クラス](../../mfc/reference/cdatabase-class.md)   
 [CRecordset クラス](../../mfc/reference/crecordset-class.md)