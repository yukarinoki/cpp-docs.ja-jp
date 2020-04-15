---
title: 'レコードセット: レコード更新のしくみ (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- records, updating
- ODBC recordsets, updating
- recordsets, editing records
- updating recordsets
- recordsets, updating
ms.assetid: 5ceecc06-7a86-43b1-93db-a54fb1e717c7
ms.openlocfilehash: 03fb696c1fadd834962d37c8e75b5f8910af819e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366977"
---
# <a name="recordset-how-recordsets-update-records-odbc"></a>レコードセット: レコード更新のしくみ (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

レコードセットでは、データ ソースからレコードを選択できるだけでなく、選択したレコードを (オプションで) 更新または削除したり、新しいレコードを追加したりできます。 レコードセットの更新可能性は、接続データ ソースが更新可能かどうか、レコードセット オブジェクトを作成するときに指定するオプション、および作成される SQL という 3 つの要素によって決まります。

> [!NOTE]
> `CRecordset`オブジェクトの基になる SQL は、レコードセットの更新可能性に影響を与える可能性があります。 たとえば、SQL に結合または**GROUP BY**句が含まれている場合、MFC は更新可能を FALSE に設定します。

> [!NOTE]
> このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチを使用している場合は、「[レコードセット: レコードの一括フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

このトピックでは、次の内容について説明します。

- [レコードセットの更新における役割](#_core_your_role_in_recordset_updating)と、フレームワークがあなたのために何をするのか。

- [エディット バッファとしてのレコードセット](#_core_the_edit_buffer)と[ダイナセットとスナップショットの違い](#_core_dynasets_and_snapshots):

[レコードセット: AddNew、編集、および削除作業 (ODBC) は、](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)レコードセットの観点からこれらの関数のアクションを記述します。

[レコードセット: 更新の詳細 (ODBC) は](../../data/odbc/recordset-more-about-updates-odbc.md)、トランザクションが更新に与える影響、レコードセットを閉じるかスクロールが進行中の更新に与える影響、および更新が他のユーザーの更新とどのように相互作用するかを説明することによって、レコードセット更新ストーリーを完了します。

## <a name="your-role-in-recordset-updating"></a><a name="_core_your_role_in_recordset_updating"></a>レコードセット更新におけるユーザーの役割

次の表は、レコードセットを使用してレコードを追加、編集、または削除する役割と、フレームワークが行う役割を示しています。

### <a name="recordset-updating-you-and-the-framework"></a>レコードセットの更新: あなたとフレームワーク

|あなたが|フレームワークの役割|
|---------|-------------------|
|データ ソースが更新可能 (または追加可能) かどうかを確認します。|データ ソースの更新可能性または追加可能性をテストするための[CDatabase](../../mfc/reference/cdatabase-class.md)メンバー関数を提供します。|
|任意の種類の更新可能なレコードセットを開きます。||
|または`CRecordset``CanAppend`などの`CanUpdate`更新関数を呼び出して、レコードセットが更新可能かどうかを判断します。||
|レコードセットのメンバー関数を呼び出して、レコードの追加、編集、および削除を行います。|レコードセット オブジェクトとデータ ソース間のデータ交換のしくみを管理します。|
|オプションで、トランザクションを使用して更新プロセスを制御します。|トランザクション`CDatabase`をサポートするメンバー関数を提供します。|

トランザクションの詳細については、「[トランザクション (ODBC) 」](../../data/odbc/transaction-odbc.md)を参照してください。

## <a name="the-edit-buffer"></a><a name="_core_the_edit_buffer"></a>エディット バッファ

レコードセットのフィールド データ メンバは、1 つのレコード (現在のレコード) を含む編集バッファとして機能します。 更新操作では、このバッファーを使用して現在のレコードを操作します。

- レコードを追加すると、編集バッファーを使用して新しいレコードが作成されます。 レコードの追加が完了すると、以前に現在のレコードが再び最新のレコードになります。

- レコードを更新 (編集) すると、編集バッファーを使用して、レコードセットのフィールド データ メンバーに新しい値が設定されます。 更新が完了すると、更新されたレコードは現在も最新の状態になります。

[AddNew](../../mfc/reference/crecordset-class.md#addnew)または[Edit](../../mfc/reference/crecordset-class.md#edit)を呼び出すと、現在のレコードが保存され、必要に応じて後で復元できます。 [Delete](../../mfc/reference/crecordset-class.md#delete)を呼び出すと、現在のレコードは保存されませんが、削除済みとしてマークされ、別のレコードまでスクロールする必要があります。

> [!NOTE]
> 編集バッファはレコードの削除には何の役割も果たしません。 カレント レコードを削除すると、レコードは削除済みとしてマークされ、別のレコードにスクロールするまでレコードセットは "レコードにありません" になります。

## <a name="dynasets-and-snapshots"></a><a name="_core_dynasets_and_snapshots"></a>ダイナセットとスナップショット

[Dynasets は](../../data/odbc/dynaset.md)、レコードにスクロールすると、レコードの内容を更新します。 [スナップショット](../../data/odbc/snapshot.md)はレコードの静的な表現であるため[、Requery](../../mfc/reference/crecordset-class.md#requery)を呼び出さない限りレコードの内容は更新されません。 ダイナセットのすべての機能を使用するには、ODBC API サポートの正しいレベルに準拠した ODBC ドライバーを使用する必要があります。 詳細については[、「ODBC](../../data/odbc/odbc-basics.md)と[ダイナセット](../../data/odbc/dynaset.md)」を参照してください。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: AddNew、Edit、Delete の動作のしくみ (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)
