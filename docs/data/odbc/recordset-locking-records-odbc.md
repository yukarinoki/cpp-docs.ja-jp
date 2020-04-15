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
ms.openlocfilehash: abd5f817ad321241df2d8565bd6bf346c0792088
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366959"
---
# <a name="recordset-locking-records-odbc"></a>レコードセット: レコードのロック (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

このトピックでは、次の内容について説明します。

- [使用可能なレコード ロックの種類](#_core_record.2d.locking_modes)。

- [更新中にレコードセット内のレコードをロックする方法](#_core_locking_records_in_your_recordset)。

レコードセットを使用してデータ ソースのレコードを更新すると、アプリケーションはレコードをロックできるため、他のユーザーが同時にレコードを更新することはできません。 2 人のユーザーが同時に更新したレコードの状態は、2 人のユーザーが同時にレコードを更新できないことをシステムが保証できない限り、未定義です。

> [!NOTE]
> このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチを実装している場合、一部の情報は適用されません。 たとえば、 および`Edit``Update`メンバー関数を呼び出すことはできません。 バルク行フェッチの詳細については、「[レコードセット : レコードの一括フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

## <a name="record-locking-modes"></a><a name="_core_record.2d.locking_modes"></a>レコードロックモード

データベース・クラスは、2 つの[レコード・ロック・モードを](../../mfc/reference/crecordset-class.md#setlockingmode)提供します。

- オプティミスティック ロック (デフォルト)

- 悲観的なロック

レコードの更新は、次の 3 つのステップで実行されます。

1. 操作を開始するには[、Edit](../../mfc/reference/crecordset-class.md#edit)メンバー関数を呼び出します。

1. 現在のレコードの適切なフィールドを変更します。

1. [Update](../../mfc/reference/crecordset-class.md#update)メンバー関数を呼び出して、操作を終了し、通常は更新をコミットします。

オプティミスティック ロックは、呼び出し`Update`中にのみデータ ソースのレコードをロックします。 マルチユーザー環境でオプティミスティック・ロックを使用する場合、アプリケーション`Update`は障害条件を処理する必要があります。 悲観`Edit`的ロックは、呼び出し直後にレコードをロックし、呼び出`Update`すまで解放しません (失敗`CDBException`は、このメカニズムを通じて示されます`Update`。 同じレコードへの同時アクセスはアプリケーションの`Update`プロセスが完了するまで待機する必要があるため、ペシミスティック ロックは他のユーザーのパフォーマンスに影響を与える可能性があります。

## <a name="locking-records-in-your-recordset"></a><a name="_core_locking_records_in_your_recordset"></a>レコードセット内のレコードのロック

レコードセット オブジェクトの[ロック モード](#_core_record.2d.locking_modes)を既定から変更する場合は、 を呼び出す`Edit`前にモードを変更する必要があります。

#### <a name="to-change-the-current-locking-mode-for-your-recordset"></a>レコードセットの現在のロック モードを変更するには

1. またはを指定して[、SetLockingMode](../../mfc/reference/crecordset-class.md#setlockingmode)メンバー関数`CRecordset::pessimistic`を`CRecordset::optimistic`呼び出します。

新しいロック モードは、再度変更するかレコードセットが閉じられるまで有効です。

> [!NOTE]
> 現在、悲観的なロックをサポートしている ODBC ドライバは比較的少ない。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: 結合 (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)<br/>
[レコードセット: レコードの追加、更新、削除 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)
