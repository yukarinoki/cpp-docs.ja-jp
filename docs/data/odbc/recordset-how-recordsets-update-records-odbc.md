---
description: '詳細情報: レコードセット: レコード更新のしくみ (ODBC)'
title: 'レコードセット: レコード更新のしくみ (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- records, updating
- ODBC recordsets, updating
- recordsets, editing records
- updating recordsets
- recordsets, updating
ms.assetid: 5ceecc06-7a86-43b1-93db-a54fb1e717c7
ms.openlocfilehash: c5304bd30093a203efbd9ee4d02d07b2d35b4b18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304507"
---
# <a name="recordset-how-recordsets-update-records-odbc"></a>レコードセット: レコード更新のしくみ (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

レコードセットでは、データソースからレコードを選択するだけでなく、必要に応じて、選択したレコードを更新または削除したり、新しいレコードを追加したりできます。 レコードセットの更新可能かどうかは、接続されたデータソースが更新可能かどうか、レコードセットオブジェクトを作成するときに指定するオプション、作成される SQL など、3つの要因によって決まります。

> [!NOTE]
> オブジェクトの基になる SQL は、 `CRecordset` レコードセットの変更可能性に影響を与えます。 たとえば、SQL に join 句または **GROUP by** 句が含まれている場合、MFC では、このようにして、の使用を FALSE に設定します。

> [!NOTE]
> このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチを使用している場合は、「レコード [セット: レコードを一括フェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

このトピックでは、次の内容について説明します。

- [レコードセットの更新におけるロール](#_core_your_role_in_recordset_updating) とフレームワークの機能。

- [エディットバッファーとしてのレコードセット](#_core_the_edit_buffer) と、 [ダイナセットとスナップショットの違い](#_core_dynasets_and_snapshots)。

[レコードセット: AddNew、Edit、Delete Work (ODBC) で](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md) は、レコードセットの観点からこれらの関数のアクションを記述します。

[レコードセット: 更新プログラム (ODBC) の詳細につい](../../data/odbc/recordset-more-about-updates-odbc.md) ては、トランザクションが更新に与える影響、レコードセットまたはスクロールを閉じることによって進行中の更新に影響を与える方法、および更新プログラムが他のユーザーの更新プログラムと対話する方法について説明します。

## <a name="your-role-in-recordset-updating"></a><a name="_core_your_role_in_recordset_updating"></a> レコードセットの更新でのロール

次の表に、レコードを追加、編集、または削除するためのレコードセットを使用する場合のロールと、フレームワークの機能を示します。

### <a name="recordset-updating-you-and-the-framework"></a>レコードセットの更新: ユーザーとフレームワーク

|自分|フレームワークの役割|
|---------|-------------------|
|データソースが更新可能である (または追加可能である) かどうかを判断します。|には、データソースの使用可能性をテストするための [CDatabase](../../mfc/reference/cdatabase-class.md) メンバー関数が用意されています。|
|更新可能なレコードセット (任意の型) を開きます。||
|やなどの update 関数を呼び出すことによって、レコードセットが更新可能かどうかを判断し `CRecordset` `CanUpdate` `CanAppend` ます。||
|レコードセットのメンバー関数を呼び出して、レコードを追加、編集、および削除します。|レコードセットオブジェクトとデータソースとの間でデータを交換するメカニズムを管理します。|
|必要に応じて、トランザクションを使用して更新プロセスを制御します。|`CDatabase`には、トランザクションをサポートするメンバー関数が用意されています。|

トランザクションの詳細については、「 [Transaction (ODBC)](../../data/odbc/transaction-odbc.md)」を参照してください。

## <a name="the-edit-buffer"></a><a name="_core_the_edit_buffer"></a> エディットバッファー

レコードセットのフィールドデータメンバーは、まとめて、1つのレコード (現在のレコード) を含む編集バッファーとして機能します。 更新操作では、このバッファーを使用して現在のレコードを操作します。

- レコードを追加すると、エディットバッファーを使用して新しいレコードが作成されます。 レコードの追加が完了すると、以前のレコードが再び最新の状態になります。

- レコードを更新 (編集) する場合、エディットバッファーを使用して、レコードセットのフィールドデータメンバーを新しい値に設定します。 更新が完了すると、更新されたレコードは最新の状態のままになります。

[AddNew](../../mfc/reference/crecordset-class.md#addnew)または[Edit](../../mfc/reference/crecordset-class.md#edit)を呼び出すと、現在のレコードが保存されるので、必要に応じて後で復元できます。 [Delete](../../mfc/reference/crecordset-class.md#delete)を呼び出すと、現在のレコードは格納されず、削除済みとしてマークされ、別のレコードにスクロールする必要があります。

> [!NOTE]
> 編集バッファーは、レコードの削除時にロールを持ちません。 現在のレコードを削除すると、レコードは削除済みとしてマークされます。レコードセットは、別のレコードにスクロールするまで "レコードではありません" と表示されます。

## <a name="dynasets-and-snapshots"></a><a name="_core_dynasets_and_snapshots"></a> ダイナセットとスナップショット

レコードにスクロールすると、レコードの内容[が更新さ](../../data/odbc/dynaset.md)れます。 [スナップショット](../../data/odbc/snapshot.md) はレコードの静的な表現であるため、 [Requery](../../mfc/reference/crecordset-class.md#requery)を呼び出さない限り、レコードの内容は更新されません。 ダイナセットのすべての機能を使用するには、適切なレベルの ODBC API サポートに準拠した ODBC ドライバーを操作する必要があります。 詳細については、「 [ODBC](../../data/odbc/odbc-basics.md) および [ダイナセット](../../data/odbc/dynaset.md)」を参照してください。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: AddNew、Edit、Delete のしくみ (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)
