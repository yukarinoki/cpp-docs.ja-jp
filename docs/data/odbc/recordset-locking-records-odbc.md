---
title: 'レコード セット: レコードのロック (ODBC) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- locks [C++], recordsets
- optimistic locking
- pessimistic locking in ODBC
- recordsets [C++], locking records
- optimistic locking, ODBC
- ODBC recordsets [C++], locking records
- data [C++], locking
ms.assetid: 8fe8fcfe-b55a-41a8-9136-94a7cd1e4806
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1fcef3233e4c2035cc481128d81723dad03fb18b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092142"
---
# <a name="recordset-locking-records-odbc"></a>レコードセット: レコードのロック (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 このトピックでは、次の内容について説明します。  
  
-   [レコードが使用可能なロックの種類](#_core_record.2d.locking_modes)です。  
  
-   [更新中に、レコード セット内のレコードをロックする方法](#_core_locking_records_in_your_recordset)です。  
  
 レコード セットを使用してデータ ソースのレコードを更新するときに、アプリケーションは、ため、他のユーザー レコードを更新できますなし、同時に、レコードをロックできます。 システムは 2 人のユーザーがレコードを同時に更新できないことを保証できる場合を除き、同時に 2 つのユーザーによって更新されたレコードの状態は定義されません。  
  
> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチを実装した場合、情報の一部は適用されません。 たとえばを呼び出すことはできません、**編集**と**更新**メンバー関数。 バルク行フェッチの詳細については、次を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。  
  
##  <a name="_core_record.2d.locking_modes"></a> レコードのロック モード  
 データベース クラスによって、2 つ[レコード ロックのモード](../../mfc/reference/crecordset-class.md#setlockingmode):  
  
-   共有ロック (既定)  
  
-   排他ロック  
  
 レコードを更新すると、3 つの手順で行われます。  
  
1.  呼び出して、操作を開始する、[編集](../../mfc/reference/crecordset-class.md#edit)メンバー関数。  
  
2.  現在のレコードの適切なフィールドを変更するとします。  
  
3.  操作を終了する — と更新プログラムを通常どおりコミット — を呼び出して、[更新](../../mfc/reference/crecordset-class.md#update)メンバー関数。  
  
 ロック中にのみ、データ ソースのレコード、**更新**呼び出します。 マルチ ユーザー環境で共有ロックを使用すると、アプリケーションを処理する必要があります、**更新**エラーが発生します。 呼び出すと、すぐにレコードがロック排他ロック**編集**によって解放されないにするまでの呼び出しと**更新**(によってエラーが指定されている、 `CDBException` の値ではなく、メカニズム**FALSE**によって返される**更新**)。 同じレコードへの同時アクセスは、アプリケーションの完了するまで待機する必要がありますので、他のユーザーの潜在的なパフォーマンスの低下が排他ロック**更新**プロセスです。  
  
##  <a name="_core_locking_records_in_your_recordset"></a> レコードをロック、レコード セット  
 レコード セット オブジェクトの変更したい場合[ロック モード](#_core_record.2d.locking_modes)を呼び出す前に、既定のモードを変更する必要があります**編集**です。  
  
#### <a name="to-change-the-current-locking-mode-for-your-recordset"></a>レコード セットの現在のロック モードを変更するには  
  
1.  呼び出す、 [SetLockingMode](../../mfc/reference/crecordset-class.md#setlockingmode)メンバー関数、いずれかを指定する**CRecordset::pessimistic**または**CRecordset::optimistic**です。  
  
 変更するか、レコード セットが閉じられるまで、新しいロック モードが有効になります。  
  
> [!NOTE]
>  比較的少数の ODBC ドライバーは、現在、排他ロックをサポートします。  
  
## <a name="see-also"></a>関連項目  
 [レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)   
 [レコード セット: 結合 (ODBC) を実行します。](../../data/odbc/recordset-performing-a-join-odbc.md)   
 [レコードセット: レコードの追加、更新、削除 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)