---
title: 'TN068: Microsoft Access 7 ODBC ドライバーでのトランザクションを実行する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.data.odbc
dev_langs:
- C++
helpviewer_keywords:
- TN068 [MFC]
- transactions [MFC], calling BeginTrans
- transactions [MFC], Microsoft Access
ms.assetid: d3f8f5d9-b118-4194-be36-a1aefb630c45
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b3db4c30eceb47d0f9169195fd131b4334d25cd
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122347"
---
# <a name="tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver"></a>テクニカル ノート 68: Microsoft Access 7 ODBC ドライバーでのトランザクションの実行

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

ここでは、MFC ODBC データベース クラスと Microsoft ODBC Driver パックでデスクトップ バージョン 3.0 に含まれる Microsoft Access 7.0 の ODBC ドライバーを使用する場合は、トランザクションを実行する方法について説明します。

## <a name="overview"></a>概要

データベース アプリケーションでは、トランザクションを実行する場合がありますを呼び出す`CDatabase::BeginTrans`と`CRecordset::Open`アプリケーションで、正しい順序で。 Microsoft Access 7.0 ドライバーは、Microsoft Jet データベース エンジンを使用し、Jet は、アプリケーションでは、開いているカーソルのある任意のデータベースでトランザクションを開始できないことが必要です。 開いているカーソルが開いているようになります、MFC ODBC データベース クラスの`CRecordset`オブジェクト。

呼び出しの前にレコード セットを開く場合`BeginTrans`、すべてのエラー メッセージが表示されない場合があります。 ただし、すべてのレコード セットが更新呼び出した後に永続的に、アプリケーションが`CRecordset::Update`、更新プログラムはロールバックされませんを呼び出して、`Rollback`です。 この問題を避けるためには、呼び出す必要があります`BeginTrans`最初し、レコード セットを開きます。

MFC では、commit および rollback のカーソルの動作のドライバーの機能を確認します。 クラス`CDatabase`2 つのメンバー関数を提供`GetCursorCommitBehavior`と`GetCursorRollbackBehavior`に、開いているすべてのトランザクションの効果を判断`CRecordset`オブジェクト。 これらのメンバー関数が返す、Microsoft Access 7.0 の ODBC ドライバーの`SQL_CB_CLOSE`Access ドライバーがカーソル位置の保存をサポートしていないためです。 そのため、呼び出す必要があります`CRecordset::Requery`次、`CommitTrans`または`Rollback`操作します。

複数のトランザクションを 1 つずつ実行する必要がある場合を呼び出せません`Requery`最初のトランザクション次のいずれかから開始からします。 [次へ] 呼び出しの前に、レコード セットを閉じる必要があります`BeginTrans`Jet の要件を満たすためにします。 このテクニカル ノートでは、このような状況を処理する 2 つの方法について説明します。

- それぞれの後に、レコード セットを閉じる`CommitTrans`または`Rollback`操作します。

- ODBC API 関数を使用して`SQLFreeStmt`です。

## <a name="closing-the-recordset-after-each-committrans-or-rollback-operation"></a>各 CommitTrans またはロールバック操作の後に、レコード セットを閉じる

トランザクションを開始する前に、レコード セット オブジェクトが閉じられていることを確認します。 呼び出した後`BeginTrans`、レコード セットを呼び出す`Open`メンバー関数。 レコード セットを呼び出した後すぐに閉じる`CommitTrans`または`Rollback`です。 繰り返しレコード セットの開閉によってアプリケーションのパフォーマンスが低下することに注意してください。

## <a name="using-sqlfreestmt"></a>SQLFreeStmt を使用します。

ODBC API 関数を使用することもできます。`SQLFreeStmt`を明示的にトランザクションの終了後にカーソルを閉じます。 別のトランザクションを開始するには、呼び出す`BeginTrans`続く`CRecordset::Requery`です。 呼び出すときに`SQLFreeStmt`、レコード セットの HSTMT を最初のパラメーターとして指定する必要がありますと*SQL_CLOSE* 2 番目のパラメーターです。 このメソッドが終了し、すべてのトランザクションの先頭のレコード セットを開くよりも高速です。 次のコードでは、この手法を実装する方法を示します。

```cpp
CMyDatabase db;
db.Open("MYDATASOURCE");
CMyRecordset rs(&db);

// start transaction 1 and
// open the recordset
db.BeginTrans();
rs.Open();

// manipulate data

// end transaction 1
db.CommitTrans(); // or Rollback()

// close the cursor
::SQLFreeStmt(rs.m_hstmt, SQL_CLOSE);

// start transaction 2
db.BeginTrans();
// now get the result set
rs.Requery();

// manipulate data

// end transaction 2
db.CommitTrans();

rs.Close();
db.Close();
```

この手法を実装する別の方法は、新しい関数を記述する`RequeryWithBeginTrans`、1 つ目のロールバックまたはコミットした後、次のトランザクションを開始するに呼び出せるです。 このような関数を記述するには、次の手順を行います。

1. コードをコピー`CRecordset::Requery( )`新しい関数にします。

2. 呼び出しの直後に次の行を追加`SQLFreeStmt`:

   `m_pDatabase->BeginTrans( );`

これでトランザクションの各ペアの間には、この関数を呼び出すことができます。

```cpp
// start transaction 1 and
// open the recordset
db.BeginTrans();

rs.Open();

// manipulate data

// end transaction 1
db.CommitTrans();   // or Rollback()

// close the cursor, start new transaction,
// and get the result set
rs.RequeryWithBeginTrans();

// manipulate data

// end transaction 2
db.CommitTrans();   // or Rollback()
```

> [!NOTE]
> レコード セットのメンバー変数を変更する必要がある場合は、この手法を使用しないでください*か*または*レコード*トランザクション間でします。 その場合は、それぞれの後に、レコード セットを閉じる必要があります`CommitTrans`または`Rollback`操作します。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)  
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)  
