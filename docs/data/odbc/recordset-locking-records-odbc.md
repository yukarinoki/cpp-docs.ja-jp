---
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
ms.openlocfilehash: d4e80816a131c997e9f5bfaa34f025394b05a358
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212863"
---
# <a name="recordset-locking-records-odbc"></a>レコードセット: レコードのロック (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

このトピックでは、次の内容について説明します。

- [使用できるレコードロックの種類](#_core_record.2d.locking_modes)。

- [更新中にレコードセットのレコードをロックする方法](#_core_locking_records_in_your_recordset)。

レコードセットを使用してデータソースのレコードを更新する場合、アプリケーションはレコードをロックして、他のユーザーが同時にレコードを更新できないようにすることができます。 2人のユーザーによって同時に更新されたレコードの状態は、2人のユーザーがレコードを同時に更新できない場合を除いて、定義されていません。

> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチを実装している場合は、一部の情報が適用されません。 たとえば、`Edit` および `Update` メンバー関数を呼び出すことはできません。 バルク行フェッチの詳細については、「レコード[セット: バルクデータフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

##  <a name="record-locking-modes"></a><a name="_core_record.2d.locking_modes"></a>レコードロックモード

データベースクラスには、次の2つの[レコードロックモード](../../mfc/reference/crecordset-class.md#setlockingmode)が用意されています。

- オプティミスティックロック (既定値)

- ペシミスティックロック

レコードの更新は、次の3つの手順で行われます。

1. 操作を開始するには、 [Edit](../../mfc/reference/crecordset-class.md#edit)メンバー関数を呼び出します。

1. 現在のレコードの適切なフィールドを変更します。

1. [更新](../../mfc/reference/crecordset-class.md#update)メンバー関数を呼び出して、操作を終了し、通常は更新をコミットします。

オプティミスティックロックは、`Update` の呼び出し中にのみ、データソースのレコードをロックします。 マルチユーザー環境でオプティミスティックロックを使用する場合、アプリケーションは `Update` のエラー状態を処理する必要があります。 ペシミスティックロックは、`Edit` を呼び出した直後にレコードをロックし、`Update` を呼び出すまでそのレコードを解放しません (エラーは `Update`によって返される FALSE 値ではなく、`CDBException` メカニズムによって示されます)。 ペシミスティックロックは、他のユーザーにとってパフォーマンスが低下する可能性があります。これは、同じレコードへの同時アクセスが、アプリケーションの `Update` プロセスが完了するまで待機する必要があるためです。

##  <a name="locking-records-in-your-recordset"></a><a name="_core_locking_records_in_your_recordset"></a>レコードセット内のレコードのロック

レコードセットオブジェクトの[ロックモード](#_core_record.2d.locking_modes)を既定値から変更する場合は、`Edit`を呼び出す前にモードを変更する必要があります。

#### <a name="to-change-the-current-locking-mode-for-your-recordset"></a>レコードセットの現在のロックモードを変更するには

1. `CRecordset::pessimistic` または `CRecordset::optimistic`のいずれかを指定して、 [Setロックモード](../../mfc/reference/crecordset-class.md#setlockingmode)メンバー関数を呼び出します。

新しいロックモードは、再度変更するか、レコードセットが閉じられるまで有効なままです。

> [!NOTE]
>  現在、排他的ロックをサポートしている ODBC ドライバーはほとんどありません。

## <a name="see-also"></a>参照

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: 結合 (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)<br/>
[レコードセット: レコードの追加、更新、削除 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)
