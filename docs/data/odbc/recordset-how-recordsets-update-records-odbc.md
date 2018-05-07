---
title: ': レコード更新レコードのしくみ (ODBC) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- records, updating
- ODBC recordsets, updating
- recordsets, editing records
- updating recordsets
- recordsets, updating
ms.assetid: 5ceecc06-7a86-43b1-93db-a54fb1e717c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b16faf4c5ef0208c946cff123ecbe62b513e65ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-how-recordsets-update-records-odbc"></a>レコードセット: レコード更新のしくみ (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 ほか、データ ソースからレコードを選択して、レコード セット (必要に応じて) を更新または選択したレコードを削除したり新しいレコードを追加できます。 次の 3 つの要因によって決まりますレコード セットの updateability: 接続されているデータ ソースが更新可能かどうか、レコード セット オブジェクト、および作成される SQL を作成するときに指定するオプションです。  
  
> [!NOTE]
>  これで、SQL、`CRecordset`オブジェクトが基レコード セットの更新に影響を与えることができます。 たとえば、SQL に結合が含まれている場合または**GROUP BY**句、MFC の設定、updateability **FALSE**です。  
  
> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチを使用している場合は、次を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。  
  
 このトピックでは、次の内容について説明します。  
  
-   [レコード セットを更新中に、ロール](#_core_your_role_in_recordset_updating)フレームワークの動作をするとします。  
  
-   [レコード セットをエディット バッファーとして](#_core_the_edit_buffer)と[ダイナセットを使う場合とスナップショットの相違点](#_core_dynasets_and_snapshots)です。  
  
 [レコード セット: どの AddNew、Edit、および作業の削除 (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)レコード セットの観点からこれらの関数の動作について説明します。  
  
 [レコード セット: 詳細の更新 (ODBC)](../../data/odbc/recordset-more-about-updates-odbc.md)トランザクションが更新プログラムに与える影響、レコード セットを閉じるか、またはスクロールへの影響、進行中の更新、および更新内容が他の更新プログラムと対話する方法について説明して、レコード セットの更新プログラムのストーリーを完了しますユーザー。  
  
##  <a name="_core_your_role_in_recordset_updating"></a> レコード セットを更新中に、ロール  
 次の表は、レコード セットを使用して、追加、編集、またはフレームワークの動作をすると、レコードを削除するロールを示します。  
  
### <a name="recordset-updating-you-and-the-framework"></a>レコード セットの更新: プログラマとフレームワーク  
  
|プログラマの役割|フレームワークの役割|  
|---------|-------------------|  
|データ ソースが更新可能な (または追加可能) かどうかを確認します。|装置[CDatabase](../../mfc/reference/cdatabase-class.md)データ ソースの更新または追加をテストするためのメンバー関数。|  
|(任意の型の)、更新可能なレコード セットを開きます。||  
|呼び出すことによって、レコード セットが更新可能かどうかを調べる`CRecordset`などの機能を更新`CanUpdate`または`CanAppend`です。||  
|レコード セットを追加、編集、およびレコードを削除するメンバー関数を呼び出します。|レコード セット オブジェクトとデータ ソース間でデータを交換するための機構を管理します。|  
|必要に応じて、トランザクションを使用して、更新処理を制御します。|装置`CDatabase`トランザクションをサポートするメンバー関数。|  
  
 トランザクションの詳細については、次を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)です。  
  
##  <a name="_core_the_edit_buffer"></a> エディット バッファー  
 集合的に実行されるように、レコード セットのフィールド データ メンバーを 1 つのレコードを格納しているエディット バッファーとして機能-現在のレコードです。 更新操作では、このバッファーを使用して、現在のレコードを操作します。  
  
-   レコードを追加する時に、エディット バッファーを使用して、新しいレコードを作成します。 レコードの追加が完了したら、以前の現在のレコードが再び現在します。  
  
-   更新するときに、レコード セットのフィールド データ メンバーを新しい値に設定する (編集)、編集、レコードのバッファーが使用されます。 更新が完了したら、更新されたレコードはまだ最新です。  
  
 呼び出すと[AddNew](../../mfc/reference/crecordset-class.md#addnew)または[編集](../../mfc/reference/crecordset-class.md#edit)、必要に応じて後で復元できるように、現在のレコードが格納されます。 呼び出すと[削除](../../mfc/reference/crecordset-class.md#delete)別のレコードをスクロールする必要があります、および現在のレコードが保存されず、削除済みとしてマークされます。  
  
> [!NOTE]
>  エディット バッファーは、レコードの削除で役割を果たすありません。 現在のレコードを削除してレコードは、削除済みとしてマークされているレコード セットは、別のレコードをスクロールするまで"レコード"ではなく、します。  
  
##  <a name="_core_dynasets_and_snapshots"></a> ダイナセットを使う場合とスナップショット  
 [ダイナセットを使う場合](../../data/odbc/dynaset.md)レコードをスクロールすると、レコードの内容を更新します。 [スナップショット](../../data/odbc/snapshot.md)ない限り、レコードの内容が更新されないため、レコードの静的な表現は、 [Requery](../../mfc/reference/crecordset-class.md#requery)です。 ダイナセットを使う場合のすべての機能を使用するには、ODBC API のサポートの適切なレベルに準拠している ODBC ドライバーで作業する必要があります。 詳細については、次を参照してください。 [ODBC](../../data/odbc/odbc-basics.md)と[ダイナセット](../../data/odbc/dynaset.md)です。  
  
## <a name="see-also"></a>関連項目  
 [レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)   
 [レコードセット: AddNew、Edit、Delete の動作のしくみ (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)