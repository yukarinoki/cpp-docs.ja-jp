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
ms.openlocfilehash: 8799ac36c443898f1e32b539f017e682bbf3e033
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212909"
---
# <a name="recordset-how-addnew-edit-and-delete-work-odbc"></a>レコードセット: AddNew、Edit、Delete の動作のしくみ (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

このトピックでは、クラス `CRecordset` の `AddNew`、`Edit`、および `Delete` メンバー関数のしくみについて説明します。 取り上げるトピックは次のとおりです。

- [レコードの追加のしくみ](#_core_adding_a_record)

- [追加されたレコードの表示](#_core_visibility_of_added_records)

- [レコードの編集のしくみ](#_core_editing_an_existing_record)

- [レコードの削除のしくみ](#_core_deleting_a_record)

> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチを使用している場合は、「レコード[セット: レコードを一括フェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

補足として、[レコードフィールドエクスチェンジ: rfx のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)について説明します。これは、更新操作における rfx の対応するロールを記述したものです。

##  <a name="adding-a-record"></a><a name="_core_adding_a_record"></a>レコードの追加

レコードセットに新しいレコードを追加するには、レコードセットの[AddNew](../../mfc/reference/crecordset-class.md#addnew)メンバー関数を呼び出し、新しいレコードのフィールドデータメンバーの値を設定し、 [Update](../../mfc/reference/crecordset-class.md#update)メンバー関数を呼び出してレコードをデータソースに書き込みます。

`AddNew`を呼び出すための前提条件として、レコードセットが読み取り専用として開かれていない必要があります。 `CanUpdate` および `CanAppend` のメンバー関数を使用すると、これらの条件を決定できます。

`AddNew`を呼び出すと、次のようになります。

- 編集バッファー内のレコードが格納されるため、操作が取り消された場合にその内容を復元できます。

- フィールドデータメンバーにフラグが設定され、後で変更を検出できるようになります。 フィールドデータメンバーも clean (変更なし) とマークされ、Null に設定されます。

`AddNew`を呼び出した後、エディットバッファーは新しい空のレコードを表し、値を入力する準備ができています。 これを行うには、値をに割り当てて手動で設定します。 フィールドに実際のデータ値を指定する代わりに `SetFieldNull` を呼び出して、Null 値を指定することもできます。

変更をコミットするには、`Update`を呼び出します。 新しいレコードに対して `Update` を呼び出すと、次のようになります。

- ODBC ドライバーが `::SQLSetPos` ODBC API 関数をサポートしている場合、MFC は関数を使用してデータソースにレコードを追加します。 `::SQLSetPos`を使用すると、SQL ステートメントを構築および処理する必要がないため、MFC でレコードをより効率的に追加できます。

- `::SQLSetPos` 使用できない場合、MFC は次のことを行います。

   1. 変更が検出されなかった場合、`Update` は何も行いません。0を返します。

   1. 変更がある場合は、`Update` によって SQL **INSERT**ステートメントが構築されます。 すべてのダーティフィールドデータメンバーによって表される列が、 **INSERT**ステートメントに一覧表示されます。 列を強制的に含めるには、 [SetFieldDirty](../../mfc/reference/crecordset-class.md#setfielddirty)メンバー関数を呼び出します。

        ```cpp
        SetFieldDirty( &m_dataMember, TRUE );
        ```

   1. `Update` は、新しいレコードをコミットします。 **INSERT**ステートメントが実行され、トランザクションが進行中でない限り、レコードがデータソースのテーブル (およびスナップショットでない場合はレコードセット) にコミットされます。

   1. 格納されているレコードは、エディットバッファーに復元されます。 **INSERT**ステートメントが正常に実行されたかどうかに関係なく、`AddNew` の呼び出し前の現在のレコードが最新のものになります。

   > [!TIP]
   > 新しいレコードを完全に制御するには、次の方法を使用します。値を持つフィールドの値を設定し、そのフィールドへのポインターを指定して `SetFieldNull` を呼び出して Null のままになるフィールドを明示的に設定し、パラメーター TRUE (既定値) を指定します。 フィールドがデータソースに書き込まれないようにするには、フィールドへのポインターを使用して `SetFieldDirty` を呼び出し、パラメーター FALSE を指定して、フィールドの値を変更しないようにします。 フィールドを Null にできるかどうかを判断するには、`IsFieldNullable`を呼び出します。

   > [!TIP]
   > レコードセットデータメンバーが値を変更したことを検出するために、MFC では、レコードセットに格納できる各データ型に適した PSEUDO_NULL 値が使用されます。 フィールドを PSEUDO_NULL 値に明示的に設定する必要があり、フィールドが既に Null とマークされている場合は、`SetFieldNull`を呼び出して、最初のパラメーターのフィールドのアドレスと2番目のパラメーターの FALSE を渡す必要もあります。

##  <a name="visibility-of-added-records"></a><a name="_core_visibility_of_added_records"></a>追加されたレコードの表示

レコードがレコードセットに表示されるのはいつですか。 追加されたレコードは、次の2つの点によって表示されることがあり、表示されないことがあります。

- ドライバーが対応していること。

- フレームワークで利用できること。

ODBC ドライバーが `::SQLSetPos` ODBC API 関数をサポートしている場合、MFC は関数を使用してレコードを追加します。 `::SQLSetPos`では、追加されたレコードは更新可能な MFC レコードセットから参照できます。 関数のサポートがない場合、追加されたレコードは表示されず、`Requery` を呼び出して表示する必要があります。 `::SQLSetPos` の使用も効率的です。

##  <a name="editing-an-existing-record"></a><a name="_core_editing_an_existing_record"></a>既存のレコードの編集

レコードセット内の既存のレコードを編集するには、レコードをスクロールし、レコードセットのメンバー関数[Edit](../../mfc/reference/crecordset-class.md#edit)を呼び出して、新しいレコードのフィールドデータメンバーの値を設定し、 [Update](../../mfc/reference/crecordset-class.md#update)メンバー関数を呼び出して変更されたレコードをデータソースに書き込みます。

`Edit`を呼び出すための前提条件として、レコードセットは更新可能である必要があります。 `CanUpdate` および `IsDeleted` のメンバー関数を使用すると、これらの条件を決定できます。 現在のレコードも削除されていない必要があります。レコードセットにレコードが存在している必要があります (`IsBOF` と `IsEOF` 返される値は0です)。

`Edit`を呼び出すと、エディットバッファー内のレコード (現在のレコード) が格納されます。 格納されているレコードの値は、フィールドが変更されたかどうかを検出するために後で使用されます。

`Edit`を呼び出した後も、エディットバッファーは現在のレコードを表しますが、フィールドデータメンバーへの変更を受け入れる準備ができました。 レコードを変更するには、編集するフィールドデータメンバーの値を手動で設定します。 フィールドに実際のデータ値を指定する代わりに `SetFieldNull` を呼び出して、Null 値を指定することもできます。 変更をコミットするには、`Update`を呼び出します。

> [!TIP]
> `AddNew` または `Edit` モードを終了するには、パラメーター *AFX_MOVE_REFRESH*を使用して `Move` を呼び出します。

`Update`を呼び出すための前提条件として、レコードセットを空にすることはできず、現在のレコードは削除されていない必要があります。 `IsBOF`、`IsEOF`、および `IsDeleted` はすべて0を返す必要があります。

編集されたレコードに対して `Update` を呼び出すと、次のようになります。

- ODBC ドライバーが `::SQLSetPos` ODBC API 関数をサポートしている場合、MFC は関数を使用してデータソースのレコードを更新します。 `::SQLSetPos`を使用すると、ドライバーは、サーバー上の対応するレコードと編集バッファーを比較し、2つのレコードが異なる場合は、サーバー上のレコードを更新します。 `::SQLSetPos`では、MFC では、SQL ステートメントを構築および処理する必要がないため、レコードをより効率的に更新できます。

   \- - または -

- `::SQLSetPos` 使用できない場合、MFC は次のことを行います。

   1. 変更がない場合、`Update` は何も行いません。0を返します。

   1. 変更がある場合、`Update` は SQL **UPDATE**ステートメントを構築します。 **UPDATE**ステートメントに示されている列は、変更されたフィールドデータメンバーに基づいています。

   1. `Update` は、変更をコミットし、 **update**ステートメントを実行します。また、レコードはデータソースで変更されますが、トランザクションが進行中の場合はコミットされません (トランザクションが更新に与える影響の詳細については、「[トランザクション: レコードセットでのトランザクションの実行 (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md) 」を参照してください)。 ODBC では、レコードのコピーも変更されます。

   1. `AddNew`のプロセスとは異なり、`Edit` プロセスでは、格納されているレコードは復元されません。 編集されたレコードは、現在のレコードとしてそのまま残ります。

   > [!CAUTION]
   > `Update`を呼び出してレコードセットを更新する準備ができたら、テーブルの主キーを構成するすべての列 (またはテーブルの一意のインデックスのすべての列、または行を一意に識別するのに十分な列) がレコードセットに含まれていることに注意してください。 場合によっては、フレームワークは、レコードセット内で選択されている列だけに基づいてテーブル内の更新するレコードを特定します。 必要なすべての列がないと、テーブル内の複数のレコードが更新される可能性があります。 この場合、`Update`を呼び出すと、フレームワークによって例外がスローされます。

   > [!TIP]
   > 以前のいずれかの関数を呼び出した後で、`Update`を呼び出す前に、`AddNew` または `Edit` を呼び出すと、保存されているレコードを使用して編集バッファーが更新され、進行中の新しいレコードまたは編集されたレコードが置き換えられます。 この動作により、`AddNew` または `Edit` を中止して新しいものを開始することができます。進行中のレコードが問題であると判断した場合は、`Edit` または `AddNew` をもう一度呼び出すだけです。

##  <a name="deleting-a-record"></a><a name="_core_deleting_a_record"></a>レコードの削除

レコードセットからレコードを削除するには、レコードをスクロールし、レコードセットの[Delete](../../mfc/reference/crecordset-class.md#delete)メンバー関数を呼び出します。 `AddNew` と `Edit`とは異なり、`Delete` では `Update`への一致する呼び出しは必要ありません。

`Delete`を呼び出すための前提条件として、レコードセットは更新可能である必要があり、レコードに記録されている必要があります。 `CanUpdate`、`IsBOF`、`IsEOF`、および `IsDeleted` の各メンバー関数を使用すると、これらの条件を決定できます。

`Delete`を呼び出すと、次のようになります。

- ODBC ドライバーが `::SQLSetPos` ODBC API 関数をサポートしている場合、MFC は関数を使用してデータソースのレコードを削除します。 `::SQLSetPos` の使用は、通常、SQL を使用するよりも効率的です。

   \- - または -

- `::SQLSetPos` 使用できない場合、MFC は次のことを行います。

   1. 編集バッファー内の現在のレコードは、`AddNew` と `Edit`としてバックアップされません。

   1. `Delete` は、レコードを削除する SQL **DELETE**ステートメントを構築します。

      編集バッファー内の現在のレコードは `AddNew` および `Edit`として格納されません。

   1. 削除をコミット `Delete` には、 **DELETE**ステートメントを実行します。 レコードは、データソースでは削除済みとしてマークされ、レコードがスナップショットの場合は ODBC でになります。

   1. 削除されたレコードの値は、レコードセットのフィールドデータメンバーに含まれていますが、フィールドデータメンバーは Null としてマークされ、レコードセットの `IsDeleted` メンバー関数は0以外の値を返します。

   > [!NOTE]
   > レコードを削除した後、別のレコードにスクロールして、新しいレコードのデータで編集バッファーを補充する必要があります。 `Delete` を再度呼び出すと、または `Edit`を呼び出すことができません。

更新操作で使用される SQL ステートメントの詳細については、「 [sql](../../data/odbc/sql.md)」を参照してください。

## <a name="see-also"></a>参照

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: 更新処理の詳細 (ODBC)](../../data/odbc/recordset-more-about-updates-odbc.md)<br/>
[レコード フィールド エクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)
