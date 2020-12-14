---
description: '詳細情報: レコードセット: レコードのロック (ODBC)'
title: 'レコードセット: レコードのロック (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- locks [C++], recordsets
- optimistic locking
- pessimistic locking in ODBC
- recordsets [C++], locking records
- optimistic locking, ODBC
- ODBC recordsets [C++], locking records
- data [C++], locking
ms.assetid: 8fe8fcfe-b55a-41a8-9136-94a7cd1e4806
ms.openlocfilehash: 1833aff2a1a68affe02cdcf5294007802452bbf9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304481"
---
# <a name="recordset-locking-records-odbc"></a>レコードセット: レコードのロック (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

このトピックでは、次の内容について説明します。

- [使用できるレコードロックの種類](#_core_record.2d.locking_modes)。

- [更新中にレコードセットのレコードをロックする方法](#_core_locking_records_in_your_recordset)。

レコードセットを使用してデータソースのレコードを更新する場合、アプリケーションはレコードをロックして、他のユーザーが同時にレコードを更新できないようにすることができます。 2人のユーザーによって同時に更新されたレコードの状態は、2人のユーザーがレコードを同時に更新できない場合を除いて、定義されていません。

> [!NOTE]
> このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチを実装している場合は、一部の情報が適用されません。 たとえば、 `Edit` メンバー関数とメンバー関数を呼び出すことはできません `Update` 。 バルク行フェッチの詳細については、「レコード [セット: バルクデータフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

## <a name="record-locking-modes"></a><a name="_core_record.2d.locking_modes"></a> Record-Locking モード

データベースクラスには、次の2つの [レコードロックモード](../../mfc/reference/crecordset-class.md#setlockingmode)が用意されています。

- オプティミスティックロック (既定値)

- ペシミスティックロック

レコードの更新は、次の3つの手順で行われます。

1. 操作を開始するには、 [Edit](../../mfc/reference/crecordset-class.md#edit) メンバー関数を呼び出します。

1. 現在のレコードの適切なフィールドを変更します。

1. [更新](../../mfc/reference/crecordset-class.md#update)メンバー関数を呼び出して、操作を終了し、通常は更新をコミットします。

オプティミスティックロックは、呼び出し中にのみ、データソースのレコードをロックし `Update` ます。 マルチユーザー環境でオプティミスティックロックを使用する場合は、アプリケーションでエラー条件を処理する必要があり `Update` ます。 ペシミスティックロックは、を呼び出した直後にレコードをロックし `Edit` `Update` ます。を呼び出すまで (エラーは、 `CDBException` によって返される FALSE 値ではなく、機構によって示され `Update` ます。 ペシミスティックロックは、他のユーザーにとってパフォーマンスが低下する可能性があります。これは、同じレコードへの同時アクセスが、アプリケーションのプロセスが完了するまで待機する必要があるため `Update` です。

## <a name="locking-records-in-your-recordset"></a><a name="_core_locking_records_in_your_recordset"></a> レコードセット内のレコードのロック

レコードセットオブジェクトの [ロックモード](#_core_record.2d.locking_modes) を既定値から変更する場合は、を呼び出す前にモードを変更する必要があり `Edit` ます。

#### <a name="to-change-the-current-locking-mode-for-your-recordset"></a>レコードセットの現在のロックモードを変更するには

1. またはを指定して、 [Setロックモード](../../mfc/reference/crecordset-class.md#setlockingmode) メンバー関数を呼び出し `CRecordset::pessimistic` `CRecordset::optimistic` ます。

新しいロックモードは、再度変更するか、レコードセットが閉じられるまで有効なままです。

> [!NOTE]
> 現在、排他的ロックをサポートしている ODBC ドライバーはほとんどありません。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: 結合の実行 (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)<br/>
[レコードセット: レコードの追加、更新、および削除 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)
