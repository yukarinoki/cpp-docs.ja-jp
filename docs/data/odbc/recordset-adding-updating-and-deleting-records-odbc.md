---
title: 'レコード セット: 追加、更新、および削除 (Odbc) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- records [C++], updating
- record editing [C++], in recordsets
- recordsets [C++], adding records
- records [C++], adding
- ODBC recordsets [C++], adding records
- recordsets [C++], editing records
- recordsets [C++], updating
- records [C++], deleting
- AddNew method
- ODBC recordsets [C++], deleting records
- data in recordsets [C++]
- record editing [C++]
- recordsets [C++], deleting records
- ODBC recordsets [C++], editing records
- records [C++], editing
ms.assetid: 760c8889-bec4-482b-a8f2-319792a6af98
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: af3a3eb08ce5749c0cfe5ca2d1f59213826ff7ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-adding-updating-and-deleting-records-odbc"></a>レコードセット: レコードの追加、更新、削除 (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
> [!NOTE]
>  大量のレコードをより効率的に追加する方法もあります。 詳細については、次を参照してください。[レコード セット: レコードを追加する方法 (ODBC)](../../data/odbc/recordset-adding-records-in-bulk-odbc.md)です。  
  
> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチを使用している場合は、次を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。  
  
 更新できるスナップショットとダイナセットでは、レコードを追加、編集 (更新)、削除できます。 このトピックでは、次の内容について説明します。  
  
-   [レコード セットが更新可能かどうかを確認する方法](#_core_determining_whether_your_recordset_is_updatable)です。  
  
-   [新しいレコードを追加する方法](#_core_adding_a_record_to_a_recordset)です。  
  
-   [既存のレコードを編集する方法](#_core_editing_a_record_in_a_recordset)です。  
  
-   [レコードを削除する方法](#_core_deleting_a_record_from_a_recordset)です。  
  
 更新プログラムを実行する方法の詳細については、ログアウトして、更新プログラムは、他のユーザーに表示、方法を参照してください。[レコード セット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)です。 通常は、レコードを追加、編集、または削除すると、すぐにレコードセットによってデータ ソースが更新されます。 また、一連の更新処理をトランザクションにまとめることもできます。 トランザクションを開始すると、そのトランザクションをコミットするまで、更新処理は終了しません。 したがって、更新をやり直すことができます。 トランザクションについては、次を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)です。  
  
 レコードセットの更新方法と更新設定の関係を次の表に示します。  
  
### <a name="recordset-readupdate-options"></a>レコードセットの読み出し/更新用の選択肢  
  
|型|読み取り|レコードの編集|レコードの削除|新規作成 (追加)|  
|----------|----------|-----------------|-------------------|------------------------|  
|読み取り専用|Y|N|N|N|  
|追加のみ可能 (Append-only)|Y|N|N|Y|  
|すべて更新可能|Y|Y|Y|Y|  
  
##  <a name="_core_determining_whether_your_recordset_is_updatable"></a> 確認するかどうかレコード セットの更新可能性  
 レコードセット オブジェクトは、データ ソースが更新可能であり、レコードセットが更新できるという設定で開かれている場合に更新できます。 また、使用する SQL ステートメント、ODBC ドライバーの機能、ODBC カーソル ライブラリがメモリ内にあるかどうかなどに応じて更新できるかどうかが決まります。 レコードセットかデータ ソースが読み取り専用のときは、更新できません。  
  
#### <a name="to-determine-whether-your-recordset-is-updatable"></a>レコードセットが更新可能かどうかを調べるには  
  
1.  レコード セット オブジェクトの[CanUpdate](../../mfc/reference/crecordset-class.md#canupdate)メンバー関数。  
  
     `CanUpdate` は、レコードセットが更新可能なときは 0 以外の値を返します。  
  
 既定では、レコード セットが完全に更新可能な (を実行できます`AddNew`、**編集**、および**削除**操作)。 使用することもできますが、 [appendOnly](../../mfc/reference/crecordset-class.md#open)更新可能なレコード セットを開くにはオプションです。 この方法で開いたレコードセットでは、`AddNew` を使用して新しいレコードを追加することだけができます。 既存のレコードを編集または削除することはできません。 レコード セットが呼び出すことによって追加のためだけに開かれているかどうかをテストすることができます、 [CanAppend](../../mfc/reference/crecordset-class.md#canappend)メンバー関数。 レコードセットがすべて更新できる場合、または追加のためだけに開かれている場合は、`CanAppend` が 0 以外の値を返します。  
  
 次の例では、レコードセット オブジェクト `CanUpdate` に対して `rsStudentSet` を使用しています。  
  
```  
if( !rsStudentSet.Open( ) )  
    return FALSE;  
if( !rsStudentSet.CanUpdate( ) )  
{  
    AfxMessageBox( "Unable to update the Student recordset." );  
    return;  
}  
```  
  
> [!CAUTION]
>  呼び出すことによって、レコード セットを更新する準備するときに**更新**、レコード セットが、テーブル (またはすべてのテーブルの一意のインデックスの列) の主キーを構成するすべての列が含まれているように注意します。 場合によっては、フレームワークは、レコードセット内で選択されている列だけに基づいてテーブル内の更新するレコードを特定します。 選択されている列数が不足していると、テーブル内の複数のレコードが更新されることがあり、場合によっては、テーブルの参照整合性が損なわれます。 呼び出すときにフレームワークが例外をスローするこの例では、**更新**です。  
  
##  <a name="_core_adding_a_record_to_a_recordset"></a> レコード セットにレコードを追加します。  
 場合、レコード セットに新しいレコードを追加することができます、 [CanAppend](../../mfc/reference/crecordset-class.md#canappend)メンバー関数は 0 以外の値を返します。  
  
#### <a name="to-add-a-new-record-to-a-recordset"></a>新しいレコードをレコードセットに追加するには  
  
1.  レコードセットがレコード追加可能レコードセットであることを確認します。  
  
2.  レコード セット オブジェクトの[AddNew](../../mfc/reference/crecordset-class.md#addnew)メンバー関数。  
  
     `AddNew` は、レコードセットをエディット バッファーとして利用できるようにします。 すべてのフィールド データ メンバーは特殊な値が Null に設定され、未変更の印を呼び出すときに、値が、データ ソースに書き込まれます (ダーティ) に変更されただけ[更新](../../mfc/reference/crecordset-class.md#update)です。  
  
3.  新しいレコードのフィールド データ メンバーの値を設定します。  
  
     フィールド データ メンバーに値を代入します。 代入しなかったフィールドはデータ ソースに書き出されません。  
  
4.  レコード セット オブジェクトの**更新**メンバー関数。  
  
     **更新**データ ソースに新しいレコードを書き込むことによって、追加を完了します。 呼び出しに失敗した場合に処理する方法について**更新**を参照してください[レコード セット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)です。  
  
 レコードの動作を追加して追加されたレコードが、レコード セットに表示される場合について、次を参照してください。[レコード セット: AddNew 方法、編集、および作業の削除 (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)です。  
  
 次に、新しいレコードを追加する例を示します。  
  
```  
if( !rsStudent.Open( ) )  
    return FALSE;  
if( !rsStudent.CanAppend( ) )  
    return FALSE;                      // no field values were set  
rsStudent.AddNew( );  
rsStudent.m_strName = strName;  
rsStudent.m_strCity = strCity;  
rsStudent.m_strStreet = strStreet;  
if( !rsStudent.Update( ) )  
{  
    AfxMessageBox( "Record not added; no field values were set." );  
    return FALSE;  
}  
```  
  
> [!TIP]
>  [キャンセル] を`AddNew`または**編集**ようにするだけで別の呼び出し、呼び出し`AddNew`または**編集**呼び出したり**移動**で、 **AFX_MOVE_REFRESH**パラメーター。 データ メンバーは前回の値にリセットされが継続**編集**または**追加**モード。  
  
##  <a name="_core_editing_a_record_in_a_recordset"></a> レコード セットのレコードの編集  
 既存のレコードを編集するには、場合、レコード セットの[CanUpdate](../../mfc/reference/crecordset-class.md#canupdate)メンバー関数は 0 以外の値を返します。  
  
#### <a name="to-edit-an-existing-record-in-a-recordset"></a>レコードセット内の既存のレコードを編集するには  
  
1.  レコードセットが更新可能であることを確認します。  
  
2.  更新するレコードに移動 (スクロール) します。  
  
3.  レコード セット オブジェクトの[編集](../../mfc/reference/crecordset-class.md#edit)メンバー関数。  
  
     **編集**レコード セットをエディット バッファーとして利用できるように準備します。 すべてのフィールド データ メンバーに未変更の印が付けられます。 呼び出すと、データ ソースに変更されたフィールド データ メンバーの新しい値が書き込まれる[更新](../../mfc/reference/crecordset-class.md#update)です。  
  
4.  新しいレコードのフィールド データ メンバーの値を設定します。  
  
     フィールド データ メンバーに値を代入します。 値を代入しなかったフィールドには変更前の値が残ります。  
  
5.  レコード セット オブジェクトの**更新**メンバー関数。  
  
     **更新**データ ソースに変更されたレコードを書き込むことによって、編集を完了します。 呼び出しに失敗した場合に処理する方法について**更新**を参照してください[レコード セット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)です。  
  
 編集終了後は、編集されたレコードが現在のレコードになります。  
  
 次の例は、**編集**操作します。 ここでは、編集するレコードに既に移動しているものと想定しています。  
  
```  
rsStudent.Edit( );  
rsStudent.m_strStreet = strNewStreet;  
rsStudent.m_strCity = strNewCity;  
rsStudent.m_strState = strNewState;  
rsStudent.m_strPostalCode = strNewPostalCode;  
if( !rsStudent.Update( ) )  
{  
    AfxMessageBox( "Record not updated; no field values were set." );  
    return FALSE;  
}  
```  
  
> [!TIP]
>  [キャンセル] を`AddNew`または**編集**ようにするだけで別の呼び出し、呼び出し`AddNew`または**編集**呼び出したり**移動**で、 **AFX_MOVE_REFRESH**パラメーター。 データ メンバーは前回の値にリセットされが継続**編集**または**追加**モード。  
  
##  <a name="_core_deleting_a_record_from_a_recordset"></a> レコード セットからレコードを削除します。  
 レコードを削除できる場合、レコード セットの[CanUpdate](../../mfc/reference/crecordset-class.md#canupdate)メンバー関数は 0 以外の値を返します。  
  
#### <a name="to-delete-a-record"></a>レコードを削除するには  
  
1.  レコードセットが更新可能であることを確認します。  
  
2.  更新するレコードに移動 (スクロール) します。  
  
3.  レコード セット オブジェクトの[削除](../../mfc/reference/crecordset-class.md#delete)メンバー関数。  
  
     **削除**すぐに削除されると、レコード セットと、データ ソースの両方で、レコードのマークを付けます。  
  
     異なり`AddNew`と**編集**、**削除**対応持たない**更新**を呼び出します。  
  
4.  別のレコードに移動 (スクロール) します。  
  
    > [!NOTE]
    >  レコードセット内を移動する場合、削除したレコードがスキップされないことがあります。 詳細については、次を参照してください。、 [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted)メンバー関数。  
  
 次の例は、**削除**操作します。 ここでは、削除するレコードに既に移動しているものと想定しています。 後に**削除**が呼び出されると、することが重要新しいレコードに移動します。  
  
```  
rsStudent.Delete( );  
rsStudent.MoveNext( );  
```  
  
 場合の影響の詳細については、 `AddNew`、**編集**、および**削除**メンバー関数を参照してください[レコード セット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)   
 [レコードセット: レコードのロック (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)