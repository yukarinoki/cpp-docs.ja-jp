---
description: '詳細については、「テクニカルノート 68: Microsoft Access 7 ODBC ドライバーでのトランザクションの実行」を参照してください。'
title: 'テクニカル ノート 68: Microsoft Access 7 ODBC ドライバーでのトランザクションの実行'
ms.date: 06/28/2018
f1_keywords:
- vc.data.odbc
helpviewer_keywords:
- TN068 [MFC]
- transactions [MFC], calling BeginTrans
- transactions [MFC], Microsoft Access
ms.assetid: d3f8f5d9-b118-4194-be36-a1aefb630c45
ms.openlocfilehash: ebc98a0fd2bea78c0159daa9a53a11a292482257
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214547"
---
# <a name="tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver"></a>テクニカル ノート 68: Microsoft Access 7 ODBC ドライバーでのトランザクションの実行

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

このメモでは、MFC ODBC データベースクラスおよび microsoft ODBC Desktop Driver Pack バージョン3.0 に含まれている Microsoft Access 7.0 ODBC ドライバーを使用する場合のトランザクションの実行方法について説明します。

## <a name="overview"></a>概要

データベースアプリケーションでトランザクションを実行する場合は、 `CDatabase::BeginTrans` `CRecordset::Open` アプリケーションで正しい順序でおよびを呼び出すように注意する必要があります。 Microsoft Access 7.0 ドライバーは Microsoft Jet データベースエンジンを使用します。 Jet では、開いているカーソルを持つデータベースでトランザクションを開始しないようにする必要があります。 MFC ODBC データベースクラスでは、開いているカーソルは開いているオブジェクトに相当し `CRecordset` ます。

を呼び出す前にレコードセットを開くと `BeginTrans` 、エラーメッセージが表示されない場合があります。 ただし、を呼び出した後、アプリケーションが更新された場合、そのレコードセットは永続的になり、 `CRecordset::Update` 更新プログラムはを呼び出すことによってロールバックされません `Rollback` 。 この問題を回避するには、まずを呼び出し、次にレコードセットを開く必要があり `BeginTrans` ます。

MFC は、カーソルのコミットとロールバックの動作についてドライバーの機能を確認します。 クラスに `CDatabase` は、との2つのメンバー関数が用意され `GetCursorCommitBehavior` ており、 `GetCursorRollbackBehavior` 開いているオブジェクトに対するトランザクションの影響を判断し `CRecordset` ます。 Microsoft Access 7.0 ODBC ドライバーでは、アクセスドライバーはカーソルの保持をサポートしていないため、これらのメンバー関数はを返し `SQL_CB_CLOSE` ます。 したがって、 `CRecordset::Requery` または操作の後にを呼び出す必要があり `CommitTrans` `Rollback` ます。

複数のトランザクションを1つずつ実行する必要がある場合、最初のトランザクションの後にを呼び出して、次のトランザクションを開始することはできません `Requery` 。 Jet の要件を満たすために、次のへの呼び出しの前にレコードセットを閉じる必要があり `BeginTrans` ます。 このテクニカルノートでは、この状況を処理する2つの方法について説明します。

- または操作の後でレコードセットを閉じ `CommitTrans` `Rollback` ます。

- ODBC API 関数を使用し `SQLFreeStmt` ます。

## <a name="closing-the-recordset-after-each-committrans-or-rollback-operation"></a>各 CommitTrans または Rollback 操作の後にレコードセットを閉じる

トランザクションを開始する前に、レコードセットオブジェクトが閉じていることを確認します。 を呼び出した後 `BeginTrans` 、レコードセットの `Open` メンバー関数を呼び出します。 またはを呼び出した直後に、レコードセットを閉じ `CommitTrans` `Rollback` ます。 レコードセットを繰り返し開いたり閉じたりすると、アプリケーションのパフォーマンスが低下することに注意してください。

## <a name="using-sqlfreestmt"></a>SQLFreeStmt の使用

また、ODBC API 関数を使用して、 `SQLFreeStmt` トランザクションの終了後にカーソルを明示的に閉じることもできます。 別のトランザクションを開始するには、を呼び出した `BeginTrans` 後にを呼び出し `CRecordset::Requery` ます。 を呼び出すときは `SQLFreeStmt` 、レコードセットの HSTMT を最初のパラメーターとして指定し、2番目のパラメーターとして *SQL_CLOSE* する必要があります。 このメソッドは、すべてのトランザクションの開始時にレコードセットを閉じて開くよりも高速です。 次のコードは、この手法を実装する方法を示しています。

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

この手法を実装するもう1つの方法は、新しい関数を記述することです。これを `RequeryWithBeginTrans` 呼び出すと、最初のトランザクションをコミットまたはロールバックした後に、次のトランザクションを開始できます。 このような関数を記述するには、次の手順を実行します。

1. のコードを `CRecordset::Requery( )` 新しい関数にコピーします。

2. の呼び出しの直後に、次の行を追加し `SQLFreeStmt` ます。

   `m_pDatabase->BeginTrans( );`

これで、この関数をトランザクションの各ペア間で呼び出すことができるようになりました。

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
> レコードセットメンバー変数を変更する必要がある場合は、この手法を使用しないでください。トランザクション間で *m_strFilter* または *m_strSort* します。 その場合は、または操作の後にレコードセットを閉じる必要があり `CommitTrans` `Rollback` ます。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
