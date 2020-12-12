---
description: '詳細については、「レコードセット: レコードの追加、更新、および削除 (ODBC)」を参照してください。'
title: 'レコードセット: レコードの追加、更新、削除 (ODBC)'
ms.date: 11/04/2016
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
ms.openlocfilehash: 20af392182481cc786d65567b4db1547d703ba0e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186143"
---
# <a name="recordset-adding-updating-and-deleting-records-odbc"></a>レコードセット: レコードの追加、更新、削除 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

> [!NOTE]
> 大量のレコードをより効率的に追加する方法もあります。 詳細については、「レコード [セット: レコードを一括で追加する方法 (ODBC)](../../data/odbc/recordset-adding-records-in-bulk-odbc.md)」を参照してください。

> [!NOTE]
> このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチを使用している場合は、「レコード [セット: レコードを一括フェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

更新できるスナップショットとダイナセットでは、レコードを追加、編集 (更新)、削除できます。 このトピックでは、次の内容について説明します。

- [レコードセットが更新可能かどうかを確認する方法](#_core_determining_whether_your_recordset_is_updatable)。

- [新しいレコードを追加する方法](#_core_adding_a_record_to_a_recordset)。

- [既存のレコードを編集する方法](#_core_editing_a_record_in_a_recordset)。

- [レコードを削除する方法](#_core_deleting_a_record_from_a_recordset)。

更新プログラムの実行方法と、更新プログラムが他のユーザーにどのように表示されるかの詳細については、「レコード [セット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)」を参照してください。 通常は、レコードを追加、編集、または削除すると、すぐにレコードセットによってデータ ソースが更新されます。 また、一連の更新処理をトランザクションにまとめることもできます。 トランザクションを開始すると、そのトランザクションをコミットするまで、更新処理は終了しません。 したがって、更新をやり直すことができます。 トランザクションの詳細については、「 [Transaction (ODBC)](../../data/odbc/transaction-odbc.md)」を参照してください。

レコードセットの更新方法と更新設定の関係を次の表に示します。

### <a name="recordset-readupdate-options"></a>レコードセットの読み出し/更新用の選択肢

|Type|Read|レコードの編集|レコードの削除|新規作成 (追加)|
|----------|----------|-----------------|-------------------|------------------------|
|読み取り専用|Y|×|×|×|
|追加のみ可能 (Append-only)|Y|×|×|Y|
|すべて更新可能|Y|Y|Y|Y|

## <a name="determining-whether-your-recordset-is-updateable"></a><a name="_core_determining_whether_your_recordset_is_updatable"></a> レコードセットが更新可能かどうかを判断する

レコードセット オブジェクトは、データ ソースが更新可能であり、レコードセットが更新できるという設定で開かれている場合に更新できます。 また、使用する SQL ステートメント、ODBC ドライバーの機能、ODBC カーソル ライブラリがメモリ内にあるかどうかなどに応じて更新できるかどうかが決まります。 レコードセットかデータ ソースが読み取り専用のときは、更新できません。

#### <a name="to-determine-whether-your-recordset-is-updatable"></a>レコードセットが更新可能かどうかを調べるには

1. レコードセットオブジェクトの [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) メンバー関数を呼び出します。

   `CanUpdate` は、レコードセットが更新可能なときは 0 以外の値を返します。

既定では、レコードセットは完全に更新でき `AddNew` ます (、 `Edit` 、および操作を実行でき `Delete` ます)。 ただし、 [appendOnly](../../mfc/reference/crecordset-class.md#open) オプションを使用して、更新可能なレコードセットを開くこともできます。 この方法で開いたレコードセットでは、`AddNew` を使用して新しいレコードを追加することだけができます。 既存のレコードを編集または削除することはできません。 [CanAppend](../../mfc/reference/crecordset-class.md#canappend)メンバー関数を呼び出すことで、レコードセットが追加のためだけに開かれているかどうかをテストできます。 レコードセットがすべて更新できる場合、または追加のためだけに開かれている場合は、`CanAppend` が 0 以外の値を返します。

次の例では、レコードセット オブジェクト `CanUpdate` に対して `rsStudentSet` を使用しています。

```cpp
if( !rsStudentSet.Open( ) )
    return FALSE;
if( !rsStudentSet.CanUpdate( ) )
{
    AfxMessageBox( "Unable to update the Student recordset." );
    return;
}
```

> [!CAUTION]
> を呼び出してレコードセットを更新する準備ができたら `Update` 、テーブルの主キーを構成するすべての列 (またはテーブルの一意のインデックスのすべての列) がレコードセットに含まれていることに注意してください。 場合によっては、フレームワークは、レコードセット内で選択されている列だけに基づいてテーブル内の更新するレコードを特定します。 選択されている列数が不足していると、テーブル内の複数のレコードが更新されることがあり、場合によっては、テーブルの参照整合性が損なわれます。 この場合、を呼び出すと、フレームワークは例外をスローし `Update` ます。

## <a name="adding-a-record-to-a-recordset"></a><a name="_core_adding_a_record_to_a_recordset"></a> レコードセットへのレコードの追加

[CanAppend](../../mfc/reference/crecordset-class.md#canappend)メンバー関数が0以外の値を返す場合は、レコードセットに新しいレコードを追加できます。

#### <a name="to-add-a-new-record-to-a-recordset"></a>新しいレコードをレコードセットに追加するには

1. レコードセットがレコード追加可能レコードセットであることを確認します。

1. レコードセットオブジェクトの [AddNew](../../mfc/reference/crecordset-class.md#addnew) メンバー関数を呼び出します。

   `AddNew` は、レコードセットをエディット バッファーとして利用できるようにします。 すべてのフィールドデータメンバーは特殊な値 Null に設定され、変更なしとしてマークされます。そのため、 [Update](../../mfc/reference/crecordset-class.md#update)を呼び出すと、変更された (ダーティ) 値のみがデータソースに書き込まれます。

1. 新しいレコードのフィールド データ メンバーの値を設定します。

   フィールド データ メンバーに値を代入します。 代入しなかったフィールドはデータ ソースに書き出されません。

1. レコードセットオブジェクトの `Update` メンバー関数を呼び出します。

   `Update` 新しいレコードをデータソースに書き込むことにより、追加を完了します。 の呼び出しに失敗した場合の結果については `Update` 、「レコード [セット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)」を参照してください。

レコードの追加のしくみ、および追加したレコードがレコードセットに表示されるタイミングについては、「 [レコードセット: 操作方法: AddNew、編集、および削除 (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)」を参照してください。

次に、新しいレコードを追加する例を示します。

```cpp
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
> またはをキャンセルするには `AddNew` `Edit` 、単にまたはを呼び出すか、 `AddNew` `Edit` AFX_MOVE_REFRESH パラメーターを指定してを呼び出し `Move` ます。  データメンバーは以前の値にリセットされ、まだ `Edit` または `Add` モードになります。

## <a name="editing-a-record-in-a-recordset"></a><a name="_core_editing_a_record_in_a_recordset"></a> レコードセット内のレコードの編集

レコードセットの [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) メンバー関数が0以外の値を返す場合は、既存のレコードを編集できます。

#### <a name="to-edit-an-existing-record-in-a-recordset"></a>レコードセット内の既存のレコードを編集するには

1. レコードセットが更新可能であることを確認します。

1. 更新するレコードに移動 (スクロール) します。

1. レコードセットオブジェクトの [Edit](../../mfc/reference/crecordset-class.md#edit) メンバー関数を呼び出します。

   `Edit` は、レコードセットをエディット バッファーとして利用できるようにします。 すべてのフィールド データ メンバーに未変更の印が付けられます。 [更新](../../mfc/reference/crecordset-class.md#update)を呼び出すと、変更されたフィールドデータメンバーの新しい値がデータソースに書き込まれます。

1. 新しいレコードのフィールド データ メンバーの値を設定します。

   フィールド データ メンバーに値を代入します。 値を代入しなかったフィールドには変更前の値が残ります。

1. レコードセットオブジェクトの `Update` メンバー関数を呼び出します。

   `Update` 変更されたレコードをデータソースに書き込むことによって、編集を完了します。 の呼び出しに失敗した場合の結果については `Update` 、「レコード [セット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)」を参照してください。

編集終了後は、編集されたレコードが現在のレコードになります。

操作の例を次に示し `Edit` ます。 ここでは、編集するレコードに既に移動しているものと想定しています。

```cpp
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
> またはをキャンセルするには `AddNew` `Edit` 、単にまたはを呼び出すか、 `AddNew` `Edit` AFX_MOVE_REFRESH パラメーターを指定してを呼び出し `Move` ます。  データメンバーは以前の値にリセットされ、まだ `Edit` または `Add` モードになります。

## <a name="deleting-a-record-from-a-recordset"></a><a name="_core_deleting_a_record_from_a_recordset"></a> レコードセットからレコードを削除する

レコードセットの [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) メンバー関数から0以外の値が返された場合は、レコードを削除できます。

#### <a name="to-delete-a-record"></a>レコードを削除するには

1. レコードセットが更新可能であることを確認します。

1. 更新するレコードに移動 (スクロール) します。

1. レコードセットオブジェクトの [Delete](../../mfc/reference/crecordset-class.md#delete) メンバー関数を呼び出します。

   `Delete` レコードをレコードセットとデータソースの両方で削除済みとして直ちにマークします。

   `AddNew`やとは異なり `Edit` 、に `Delete` は対応する呼び出しがありません `Update` 。

1. 別のレコードに移動 (スクロール) します。

   > [!NOTE]
   >  レコードセット内を移動する場合、削除したレコードがスキップされないことがあります。 詳細については、「 [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) メンバー関数」を参照してください。

操作の例を次に示し `Delete` ます。 ここでは、削除するレコードに既に移動しているものと想定しています。 を `Delete` 呼び出すと、新しいレコードに移動することが重要になります。

```
rsStudent.Delete( );
rsStudent.MoveNext( );
```

、、およびメンバー関数の効果の詳細については `AddNew` `Edit` `Delete` 、「 [レコードセット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: レコードのロック (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)
