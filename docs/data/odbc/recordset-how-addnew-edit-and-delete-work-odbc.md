---
title: 'レコードセット: AddNew、Edit、Delete の動作のしくみ (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- records [C++], updating
- record editing [C++], in recordsets
- recordsets [C++], adding records
- records [C++], adding
- ODBC recordsets [C++], adding records
- recordsets [C++], editing records
- recordsets [C++], updating
- AddNew method
- ODBC recordsets [C++], deleting records
- records [C++], deleting in recordsets
- data in recordsets [C++]
- recordsets [C++], deleting records
- ODBC recordsets [C++], editing records
- records [C++], editing
ms.assetid: cab43d43-235a-4bed-ac05-67d10e94f34e
ms.openlocfilehash: 63718a6be3a9ce19ddbce923a84def21448c42a0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367000"
---
# <a name="recordset-how-addnew-edit-and-delete-work-odbc"></a>レコードセット: AddNew、Edit、Delete の動作のしくみ (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

このトピックでは、クラス`AddNew``CRecordset`の`Edit`、 `Delete` 、 、 および メンバー関数がどのように機能するかを説明します。 取り上げるトピックは次のとおりです。

- [レコードの追加のしくみ](#_core_adding_a_record)

- [追加されたレコードの表示](#_core_visibility_of_added_records)

- [レコードの編集のしくみ](#_core_editing_an_existing_record)

- [レコードの削除のしくみ](#_core_deleting_a_record)

> [!NOTE]
> このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチを使用している場合は、「[レコードセット: レコードの一括フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

補足として、更新操作における RFX の対応する役割を説明する[「レコード フィールド エクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。

## <a name="adding-a-record"></a><a name="_core_adding_a_record"></a>レコードの追加

レコードセットに新しいレコードを追加するには、レコードセットの[AddNew](../../mfc/reference/crecordset-class.md#addnew)メンバー関数を呼び出し、新しいレコードのフィールド データ メンバーの値を設定し[、Update](../../mfc/reference/crecordset-class.md#update)メンバー関数を呼び出してレコードをデータ ソースに書き込みます。

呼び出し`AddNew`の前提条件として、レコードセットが読み取り専用で開かれていない必要があります。 および`CanUpdate``CanAppend`メンバー関数を使用して、これらの条件を決定できます。

あなたが呼び`AddNew`出すとき:

- 編集バッファー内のレコードは保管されるため、操作が取り消されるとその内容を復元できます。

- フィールド データ メンバーにはフラグが設定されるため、後で変更を検出できます。 フィールド データ メンバーも、クリーン (変更なし) としてマークされ、Null に設定されます。

を呼び`AddNew`出した後、エディット バッファーは、値を入力する準備ができた新しい空のレコードを表します。 これを行うには、値を割り当てることによって手動で値を設定します。 フィールドに実際のデータ値を指定する代わりに、呼び出`SetFieldNull`して値 Null を指定できます。

変更をコミットするには、 を`Update`呼び出します。 新しいレコード`Update`を呼び出すとき:

- ODBC ドライバーが ODBC `::SQLSetPos` API 関数をサポートしている場合、MFC は、データ ソースにレコードを追加する関数を使用します。 では`::SQLSetPos`、SQL ステートメントを構築して処理する必要がないため、MFC はレコードをより効率的に追加できます。

- 使用`::SQLSetPos`できない場合、MFC は次の処理を行います。

   1. 変更が検出されない場合は`Update`、何も行われず 0 を返します。

   1. 変更がある場合は、SQL `Update` **INSERT**ステートメントを作成します。 すべてのダーティ フィールド データ メンバーによって表される列は **、INSERT**ステートメントに一覧表示されます。 列を強制的に含めるには[、SetFieldDirty](../../mfc/reference/crecordset-class.md#setfielddirty)メンバー関数を呼び出します。

        ```cpp
        SetFieldDirty( &m_dataMember, TRUE );
        ```

   1. `Update`新しいレコードをコミットする - **INSERT**ステートメントが実行され、トランザクションが進行中でない限り、データ ソース (およびスナップショットではない場合はレコードセット) のテーブルにレコードがコミットされます。

   1. 格納されたレコードは、編集バッファーに復元されます。 `AddNew` **INSERT**ステートメントが正常に実行されたかどうかに関係なく、呼び出しの前に最新であったレコードが再び最新の状態になります。

   > [!TIP]
   > 新しいレコードを完全に制御するには、値を持つフィールドの値を設定し、フィールドへのポインターと TRUE (既定値) を呼び出`SetFieldNull`して Null のままのフィールドを明示的に設定する方法を使用します。 フィールドがデータ ソースに書き込まれないようにするには、フィールドへのポインターと`SetFieldDirty`FALSE パラメーターを使用して呼び出し、フィールドの値を変更しないでください。 フィールドを Null にできるかどうかを調べるには、`IsFieldNullable`を呼び出します。

   > [!TIP]
   > レコードセット データ メンバーの値が変更されたことを検出するために、MFC では、レコードセットに格納できる各データ型に適したPSEUDO_NULL値が使用されます。 フィールドを明示的にPSEUDO_NULL値に設定する必要があり、そのフィールドが既に Null としてマークされている場合は、`SetFieldNull`を呼び出す必要があります。

## <a name="visibility-of-added-records"></a><a name="_core_visibility_of_added_records"></a>追加されたレコードの表示

追加したレコードがレコードセットに表示されるのはいつですか? 追加されたレコードが表示されることがあり、次の 2 つの状況に応じて表示されないことがあります。

- あなたのドライバーができること。

- フレームワークが利用できる内容。

ODBC ドライバーが ODBC `::SQLSetPos` API 関数をサポートしている場合、MFC は、レコードを追加する関数を使用します。 を`::SQLSetPos`使用すると、更新可能な MFC レコードセットからレコードが追加されます。 関数をサポートしない場合、追加されたレコードは表示されず、呼び`Requery`出して表示する必要があります。 また`::SQLSetPos`、使用の方が効率的です。

## <a name="editing-an-existing-record"></a><a name="_core_editing_an_existing_record"></a>既存のレコードの編集

レコードセット内の既存のレコードを編集するには、レコードにスクロールし、レコードセットの[Edit](../../mfc/reference/crecordset-class.md#edit)メンバー関数を呼び出し、新しいレコードのフィールド データ メンバーの値を設定し、変更されたレコードをデータ ソースに書き込む[更新](../../mfc/reference/crecordset-class.md#update)メンバー関数を呼び出します。

呼び出し`Edit`の前提条件として、レコードセットは更新可能でレコード上になければなりません。 および`CanUpdate``IsDeleted`メンバー関数を使用して、これらの条件を決定できます。 現在のレコードも削除されていない必要があり、レコードセットにレコード (両方とも`IsBOF``IsEOF`0 を返す) が存在する必要があります。

を呼び`Edit`出すと、エディット バッファー (現在のレコード) のレコードが格納されます。 保存されたレコードの値は、後でフィールドが変更されたかどうかを検出するために使用されます。

を呼び`Edit`出した後も、エディット バッファーは現在のレコードを表しますが、フィールド データ メンバーへの変更を受け入れる準備が整いました。 レコードを変更するには、編集するフィールド データ メンバーの値を手動で設定します。 フィールドに実際のデータ値を指定する代わりに、呼び出`SetFieldNull`して値 Null を指定できます。 変更をコミットするには、`Update`に電話します。

> [!TIP]
> `AddNew`モードから抜け出`Edit`すには、`Move`パラメータ*AFX_MOVE_REFRESH*を呼び出します。

呼び出し`Update`の前提条件として、レコードセットは空で、現在のレコードは削除されていない必要があります。 `IsBOF`、、`IsEOF`および`IsDeleted`、すべて 0 を返す必要があります。

編集したレコード`Update`を呼び出すと、次のようになります。

- ODBC ドライバーが ODBC `::SQLSetPos` API 関数をサポートしている場合、MFC は、データ ソースのレコードを更新する関数を使用します。 を`::SQLSetPos`使用すると、ドライバは、サーバー上の対応するレコードと編集バッファを比較し、2 つのレコードが異なる場合はサーバー上のレコードを更新します。 では`::SQLSetPos`、MFC は SQL ステートメントを構築および処理する必要がないため、より効率的にレコードを更新できます。

   \- または

- 使用`::SQLSetPos`できない場合、MFC は次の処理を行います。

   1. 変更がない場合は、何も`Update`行わないし、0を返します。

   1. 変更がある場合は、SQL `Update` **UPDATE**ステートメントを作成します。 **UPDATE**ステートメントにリストされている列は、変更されたフィールド・データ・メンバーに基づいています。

   1. `Update`**UPDATE**ステートメントをコミットし、データ ソースでレコードが変更されますが、トランザクションが進行中の場合はコミットされません ([トランザクション: レコードセットでのトランザクションの実行 (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)で、トランザクションが更新に与える影響の詳細を参照してください。 ODBC はレコードのコピーを保持しますが、そのコピーも変更されます。

   1. `AddNew`のプロセスとは異なり`Edit`、保存されたレコードは復元されません。 編集したレコードは、現在のレコードとして残ります。

   > [!CAUTION]
   > を呼び出`Update`してレコードセットを更新する準備をするときは、テーブルの主キーを構成するすべての列 (テーブル上の一意のインデックスのすべての列、または行を一意に識別するための十分な列) がレコードセットに含まれるのを考慮します。 場合によっては、フレームワークは、レコードセット内で選択されている列だけに基づいてテーブル内の更新するレコードを特定します。 必要な列がすべて存在しない場合、テーブル内の複数のレコードが更新される可能性があります。 この場合、フレームワークは を呼び出`Update`すと例外をスローします。

   > [!TIP]
   > いずれかの関数を`AddNew`呼`Edit`び出した後、以前に呼び出`Update`した後で、 を呼び出した後で、保存されているレコードでエディット バッファーが更新され、進行中の新規レコードまたは編集済みのレコードが置き換えられます。 この動作により、新しいレコードを中止`AddNew`したり`Edit`、新しいレコードを開始したりする方法が提供されます`Edit``AddNew`。

## <a name="deleting-a-record"></a><a name="_core_deleting_a_record"></a>レコードの削除

レコードセットからレコードを削除するには、レコードにスクロールしてレコードセットの[Delete](../../mfc/reference/crecordset-class.md#delete)メンバー関数を呼び出します。 と`AddNew``Edit`は`Delete`異なり、 に一致`Update`する呼び出しは必要ありません。

呼び出し`Delete`の前提条件として、レコードセットは更新可能で、レコード上にある必要があります。 `CanUpdate`、、`IsBOF`および`IsEOF``IsDeleted`メンバー関数を使用して、これらの条件を決定できます。

あなたが呼び`Delete`出すとき:

- ODBC ドライバーが ODBC `::SQLSetPos` API 関数をサポートしている場合、MFC は、データ ソースのレコードを削除する関数を使用します。 通常`::SQLSetPos`、SQL を使用するよりも、使用の方が効率的です。

   \- または

- 使用`::SQLSetPos`できない場合、MFC は次の処理を行います。

   1. エディット バッファの現在のレコードは、`AddNew`および`Edit`のようにバックアップされません。

   1. `Delete`レコードを削除する SQL **DELETE**ステートメントを作成します。

      エディット バッファーの現在のレコードは、`AddNew`および`Edit`のように格納されません。

   1. `Delete`削除をコミットする — **DELETE**ステートメントを実行します。 レコードは、データ ソースで削除済みとマークされ、レコードがスナップショットの場合は ODBC で削除されます。

   1. 削除されたレコードの値はレコードセットのフィールド データ メンバーに残りますが、フィールド データ メンバーは Null とマークされ`IsDeleted`、レコードセットのメンバー関数は 0 以外の値を返します。

   > [!NOTE]
   > レコードを削除した後、別のレコードにスクロールして、編集バッファーに新しいレコードのデータを再入力する必要があります。 もう一度呼び出`Delete`すか、呼び`Edit`出すとエラーになります。

更新操作で使用される SQL ステートメントについては[、SQL](../../data/odbc/sql.md)を参照してください。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: 更新処理の詳細 (ODBC)](../../data/odbc/recordset-more-about-updates-odbc.md)<br/>
[レコード フィールド エクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)
