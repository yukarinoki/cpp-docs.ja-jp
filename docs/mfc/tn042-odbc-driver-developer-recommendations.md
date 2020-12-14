---
description: '詳細については、次を参照してください: テクニカルノート 42: ODBC ドライバー開発者向けの推奨事項'
title: 'テクニカル ノート 42: ODBC ドライバーの開発に関する推奨事項'
ms.date: 11/04/2016
f1_keywords:
- vc.odbc
helpviewer_keywords:
- ODBC drivers [MFC], writing
- databases [MFC], ODBC
- TN042
ms.assetid: ecc6b5d9-f480-4582-9e22-8309fe561dad
ms.openlocfilehash: 896c99ffeba98f1ea38771676475c85abf13d983
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215301"
---
# <a name="tn042-odbc-driver-developer-recommendations"></a>テクニカル ノート 42: ODBC ドライバーの開発に関する推奨事項

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

このメモでは、ODBC ドライバーライターのガイドラインについて説明します。 この記事では、MFC データベースクラスによって実行される ODBC 機能の一般的な要件と仮定と、想定されるさまざまなセマンティックの詳細について説明します。 3つの `CRecordset` オープンモード (**forwardOnly**、 **snapshot** 、および **ダイナセット**) をサポートするために必要なドライバーの機能について説明します。

## <a name="odbcs-cursor-library"></a>ODBC のカーソルライブラリ

MFC データベースクラスは、多くの場合、ほとんどのレベル1の ODBC ドライバーによって提供される機能よりも多くの機能をユーザーに提供します。 さいわい、ODBC のカーソルライブラリは、データベースクラスとドライバーの間でレイヤーを設定し、この追加機能の多くを自動的に提供します。

たとえば、ほとんどの1.0 ドライバーは後方スクロールをサポートしていません。 カーソルライブラリはこれを検出し、ドライバーからの行をキャッシュし、の FETCH_PREV の呼び出しで要求されたとおりに表示し `SQLExtendedFetch` ます。

カーソルライブラリの依存関係のもう1つの重要な例は、更新を配置することです。 ほとんどの1.0 ドライバーでは、位置指定更新も行われませんが、カーソルライブラリでは、現在キャッシュされているデータ値に基づいてデータソース上のターゲット行を識別する update ステートメント、またはキャッシュされたタイムスタンプ値を生成します。

クラスライブラリでは、複数の行セットを使用しません。 そのため、行 `SQLSetPos` セットの行1には、常にいくつかのステートメントが適用されます。

## <a name="cdatabases"></a>CDatabases

それぞれ `CDatabase` が1つの **HDBC** を割り当てます。 ( `CDatabase` `ExecuteSQL` 関数が使用されている場合、 **HSTMT** は一時的に割り当てられます)。そのため `CDatabase` 、複数のが必要な場合は、 **henv** ごとに複数の **HDBC** s がサポートされている必要があります。

データベースクラスには、カーソルライブラリが必要です。 これは SQL_ODBC_CURSORS の呼び出し、SQL_CUR_USE_ODBC に反映され `SQLSetConnections` ます。  

`SQLDriverConnect`では、データソースへの接続を確立するためにによって **SQL_DRIVER_COMPLETE** が使用され `CDatabase::Open` ます。

ドライバーは `SQLGetInfo SQL_ODBC_API_CONFORMANCE`  >=  、 **SQL_OAC_LEVEL1**、SQL_OSC_MINIMUM をサポートしている必要があり `SQLGetInfo SQL_ODBC_SQL_CONFORMANCE`  >=  ます。

とその依存レコードセットに対してトランザクションがサポートされるようにするため、SQL_CURSOR_ROLLBACK_BEHAVIOR には `CDatabase` `SQLGetInfo SQL_CURSOR_COMMIT_BEHAVIOR` **SQL_CR_PRESERVE** が必要です。  そうしないと、トランザクション制御を実行しようとしても無視されます。

`SQLGetInfo SQL_DATA_SOURCE_READ_ONLY` サポートされている必要があります。 "Y" が返された場合、データソースに対する更新操作は実行されません。

`CDatabase`が読み取り専用で開かれている場合、データソースを読み取り専用に設定しようとすると `SQLSetConnectOption SQL_ACCESS_MODE` 、、 **SQL_MODE_READ_ONLY** が使用されます。

識別子を引用符で囲む必要がある場合、この情報はを呼び出してドライバーから返す必要があり `SQLGetInfo SQL_IDENTIFIER_QUOTE_CHAR` ます。

デバッグを目的 `SQLGetInfo SQL_DBMS_VER` として、と **SQL_DBMS_NAME** がドライバーから取得されます。

`SQLSetStmtOption SQL_QUERY_TIMEOUT`と **SQL_ASYNC_ENABLE** は、の HDBC で呼び出すことができ `CDatabase` ます。 

`SQLError` 任意またはすべての引数を NULL として呼び出すことができます。

もちろん、、 `SQLAllocEnv` 、 `SQLAllocConnect` `SQLDisconnect` および `SQLFreeConnect` がサポートされている必要があります。

## <a name="executesql"></a>ExecuteSQL

一時的な **HSTMT** の割り当てと解放に加えて、、、 `ExecuteSQL` およびを呼び出し `SQLExecDirect` `SQLFetch` `SQLNumResultCol` `SQLMoreResults` ます。 `SQLCancel` は、 **HSTMT** で呼び出すことができます。

## <a name="getdatabasename"></a>GetDatabaseName

`SQLGetInfo SQL_DATABASE_NAME` が呼び出されます。

## <a name="begintrans-committrans-rollback"></a>BeginTrans、CommitTrans、Rollback

`SQLSetConnectOption SQL_AUTOCOMMIT` また `SQLTransact SQL_COMMIT` 、トランザクション要求が行われると、 **SQL_ROLLBACK** および **SQL_AUTOCOMMIT** が呼び出されます。

## <a name="crecordsets"></a>CRecordsets

`SQLAllocStmt`、 `SQLPrepare` 、 `SQLExecute` (およびの場合 `Open` `Requery` `SQLExecDirect` )、(更新操作の場合) は `SQLFreeStmt` サポートされている必要があります。 `SQLNumResultCols` と `SQLDescribeCol` は、さまざまなタイミングで結果セットに対して呼び出されます。

`SQLSetParam` は、パラメーターデータのバインドと機能の **DATA_AT_EXEC** に広く使用されています。

`SQLBindCol` は、出力列のデータストレージの場所を ODBC で登録するために広く使用されています。

2つ `SQLGetData` の呼び出しを使用して、データの **SQL_LONG_VARCHAR** と **SQL_LONG_VARBINARY** を取得します。 最初の呼び出しでは、 `SQLGetData` cbMaxValue が0で、有効な pcbValue を指定してを呼び出すことによって、列の値の合計長を検索しようとします。 PcbValue が **SQL_NO_TOTAL** を保持している場合は、例外がスローされます。 それ以外の場合は、 **HGLOBAL** が割り当てられ、 `SQLGetData` 結果全体を取得するために別の呼び出しが行われます。

## <a name="updating"></a>更新中

ペシミスティックロックが要求されると、 `SQLGetInfo SQL_LOCK_TYPES` クエリが実行されます。 **SQL_LCK_EXCLUSIVE** がサポートされていない場合は、例外がスローされます。

(スナップショットまたはダイナセット) を更新しようとすると、 `CRecordset` 2 番目の **HSTMT** が割り当てられます。  2番目の **HSTMT** をサポートしていないドライバーの場合、この機能はカーソルライブラリによってシミュレートされます。 残念ながら、2番目の **hstmt** の要求を処理する前に、最初の **hstmt** に対する現在のクエリを強制的に完了することがあります。

`SQLFreeStmt SQL_CLOSE` および **SQL_RESET_PARAMS** `SQLGetCursorName` は、更新操作中に呼び出されます。

**Outputcolumns** に **CLongBinarys** がある場合は、ODBC の **DATA_AT_EXEC** 機能がサポートされている必要があります。 これには、、、およびから **SQL_NEED_DATA** を返すことが含まれ `SQLExecDirect` `SQLParamData` `SQLPutData` ます。

`SQLRowCount` は、の実行後に呼び出され、によって1つのレコードのみが更新されたことを確認し `SQLExecDirect` ます。

## <a name="forwardonly-cursors"></a>ForwardOnly カーソル

`SQLFetch`操作にはのみが必要です `Move` 。 **ForwardOnly** カーソルは更新をサポートしていないことに注意してください。

## <a name="snapshot-cursors"></a>スナップショットカーソル

スナップショット機能にはサポートが必要です `SQLExtendedFetch` 。 前述のように、ODBC カーソルライブラリは、ドライバーがサポートしていないことを検出 `SQLExtendedFetch` し、必要なサポート自体を提供します。

`SQLGetInfo`、 **SQL_SCROLL_OPTIONS** **SQL_SO_STATIC** をサポートする必要があります。

## <a name="dynaset-cursors"></a>ダイナセットカーソル

次に、ダイナセットを開くために必要な最小のサポートを示します。

`SQLGetInfo`, **SQL_ODBC_VER** > "01" を返す必要があります。

`SQLGetInfo`、 **SQL_SCROLL_OPTIONS** **SQL_SO_KEYSET_DRIVEN** をサポートする必要があります。

`SQLGetInfo`, **SQL_ROW_UPDATES** は "Y" を返す必要があります。

`SQLGetInfo`、 **SQL_POSITIONED_UPDATES** **SQL_PS_POSITIONED_DELETE** と **SQL_PS_POSITIONED_UPDATE** をサポートする必要があります。

また、ペシミスティックロックが要求された場合は、 `SQLSetPos` irow 1、fRefresh FALSE、および fLock **SQL_LCK_EXCLUSIVE** を指定したへの呼び出しが行われます。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
