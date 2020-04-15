---
title: 'テクニカル ノート 42: ODBC ドライバーの開発に関する推奨事項'
ms.date: 11/04/2016
f1_keywords:
- vc.odbc
helpviewer_keywords:
- ODBC drivers [MFC], writing
- databases [MFC], ODBC
- TN042
ms.assetid: ecc6b5d9-f480-4582-9e22-8309fe561dad
ms.openlocfilehash: 67f7a86a247b60be66dabb0a89f04d39ce76222b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372134"
---
# <a name="tn042-odbc-driver-developer-recommendations"></a>テクニカル ノート 42: ODBC ドライバーの開発に関する推奨事項

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

この注では、ODBC ドライバの作成者のガイドラインについて説明します。 MFC データベース クラスが作成する ODBC 機能の一般的な要件と前提事項、および予想されるセマンティックの詳細について説明します。 3`CRecordset`つのオープン モード **(forwardOnly**、**スナップショット**、**ダイナセット**) をサポートするために必要なドライバ機能について説明します。

## <a name="odbcs-cursor-library"></a>ODBC のカーソル ライブラリ

MFC Database クラスは、多くの場合、ほとんどのレベル 1 ODBC ドライバーで提供される機能を超える機能をユーザーに提供します。 さいわい、ODBC のカーソル ライブラリは、データベース クラスとドライバーの間に重なって、この追加機能の多くを自動的に提供します。

たとえば、ほとんどの 1.0 ドライバーは、後方スクロールをサポートしていません。 カーソル ライブラリはこれを検出し、ドライバーからの行をキャッシュし、FETCH_PREV呼び出しで`SQLExtendedFetch`要求どおりに表示します。

カーソル ライブラリ依存のもう 1 つの重要な例は、位置指定更新です。 ほとんどの 1.0 ドライバーも位置更新プログラムを持っていませんが、カーソル ライブラリは、現在のキャッシュされたデータ値、またはキャッシュされたタイムスタンプ値に基づいて、データ ソースのターゲット行を識別する update ステートメントを生成します。

クラス ライブラリは、複数の行セットを使用することはありません。 したがって、行セット`SQLSetPos`の行 1 には、常に少数のステートメントが適用されます。

## <a name="cdatabases"></a>データベース

それぞれが`CDatabase`単一の**HDBC**を割り当てます。 (関数`CDatabase`が`ExecuteSQL`使用されている場合は **、HSTMT**が一時的に割り振られます。したがって、複数`CDatabase`の'sが必要な場合は **、HENV**ごとに複数の**HDBC**sをサポートする必要があります。

データベース・クラスにはカーソル・ライブラリーが必要です。 これは、 SQL_ODBC_CURSORS`SQLSetConnections`呼**SQL_ODBC_CURSORS**び出し**に反映SQL_CUR_USE_ODBC。**

`SQLDriverConnect`SQL_DRIVER_COMPLETE**は**、データ`CDatabase::Open`ソースへの接続を確立するために 使用されます。

ドライバー**は、** `SQLGetInfo SQL_ODBC_API_CONFORMANCE`  >= SQL_OSC_MINIMUM `SQLGetInfo SQL_ODBC_SQL_CONFORMANCE`  >=  **SQL_OAC_LEVEL1**をサポートする必要があります。

トランザクションを、`CDatabase`およびその依存レコードセットでサポートするには`SQLGetInfo SQL_CURSOR_COMMIT_BEHAVIOR`**、SQL_CURSOR_ROLLBACK_BEHAVIOR** **SQL_CR_PRESERVE**が必要です。 それ以外の場合、トランザクション制御の実行試行は無視されます。

`SQLGetInfo SQL_DATA_SOURCE_READ_ONLY`がサポートされている必要があります。 "Y" が返された場合、データ ソースに対して更新操作は実行されません。

が`CDatabase`ReadOnly で開かれている場合は、 でデータ ソースを読み取`SQLSetConnectOption SQL_ACCESS_MODE`り専用に設定しようとしましたが、 **SQL_MODE_READ_ONLY。**

識別子がクォートを必要とする場合、この情報は`SQLGetInfo SQL_IDENTIFIER_QUOTE_CHAR`、呼び出しとドライバーから返される必要があります。

デバッグ目的で`SQLGetInfo SQL_DBMS_VER`**、SQL_DBMS_NAME**はドライバーから取得されます。

`SQLSetStmtOption SQL_QUERY_TIMEOUT`**SQL_ASYNC_ENABLE**は 's `CDatabase` **HDBC**で呼び出されるかもしれません。

`SQLError`は、任意の引数またはすべての引数 NULL で呼び出すことができます。

もちろん、 `SQLAllocEnv`、`SQLAllocConnect`および`SQLDisconnect``SQLFreeConnect`はサポートされている必要があります。

## <a name="executesql"></a>ExecuteSQL

一時的な**HSTMT**の割り当てと`ExecuteSQL`解放`SQLExecDirect`に`SQLFetch`加`SQLNumResultCol`えて`SQLMoreResults`、 、 、 を呼び出します。 `SQLCancel`**HSTMT**で呼び出される可能性があります。

## <a name="getdatabasename"></a>データベース名を取得します。

`SQLGetInfo SQL_DATABASE_NAME`が呼び出されます。

## <a name="begintrans-committrans-rollback"></a>トランスを開始, コミットトランス, ロールバック

`SQLSetConnectOption SQL_AUTOCOMMIT``SQLTransact SQL_COMMIT`SQL_ROLLBACK、**トランザクション**要求が行われる場合は**SQL_AUTOCOMMIT**が呼び出されます。

## <a name="crecordsets"></a>レコードセット

`SQLAllocStmt``SQLPrepare`、、(For `Open` `SQLExecute` `Requery`および`SQLExecDirect`)、更新操作`SQLFreeStmt`の場合は、サポートされている必要があります。 `SQLNumResultCols`さまざまな`SQLDescribeCol`時間に設定された結果に呼び出されます。

`SQLSetParam`は、パラメータ データのバインドや**DATA_AT_EXEC**機能に広く使用されています。

`SQLBindCol`出力列データ格納場所を ODBC に登録するために広く使用されます。

SQL_LONG_VARCHAR`SQLGetData`とSQL_LONG_VARBINARYデータ**を取得するために**、2 つの呼び出し**が**使用されます。 最初の呼び出しは、cbMaxValue 0 を呼`SQLGetData`び出して列の値の全長を検索しようとしますが、有効な pcbValue を使用します。 pcbValue が**SQL_NO_TOTAL**を保持している場合は、例外がスローされます。 それ以外の場合は **、HGLOBAL**が割`SQLGetData`り振られ、結果全体を取得するために別の呼び出しが行われます。

## <a name="updating"></a>更新中

悲観的なロックが要求された`SQLGetInfo SQL_LOCK_TYPES`場合は、照会されます。 **SQL_LCK_EXCLUSIVE**がサポートされていない場合は、例外がスローされます。

`CRecordset`**スナップショットまたは****ダイナセット**を更新しようとすると、2 番目の**HSTMT**が割り当てられます。 2 番目の**HSTMT**をサポートしていないドライバーの場合、カーソル ライブラリはこの機能をシミュレートします。 残念ながら、これは 2 番目の**HSTMT**要求を処理する前に、最初の**HSTMT**の現在のクエリを強制的に完了させる場合があります。

`SQLFreeStmt SQL_CLOSE`**SQL_RESET_PARAMS**され、`SQLGetCursorName`更新操作中に呼び出されます。

出力列**に CLongBinarys**がある場合は **、ODBC**の**DATA_AT_EXEC**機能がサポートされている必要があります。 これには、**SQL_NEED_DATA**および`SQLExecDirect`から`SQLParamData`SQL_NEED_DATA`SQLPutData`を返すことも含まれます。

`SQLRowCount`は、実行後に呼び出され、レコードが 1`SQLExecDirect`つだけ更新されたことを確認します。

## <a name="forwardonly-cursors"></a>転送専用カーソル

操作`SQLFetch`に必要な場合`Move`のみ。 **forwardOnly**カーソルは更新をサポートしません。

## <a name="snapshot-cursors"></a>スナップショット カーソル

スナップショット機能には`SQLExtendedFetch`サポートが必要です。 前述のように、ODBC カーソル ライブラリは、ドライバーが をサポート`SQLExtendedFetch`していない場合を検出し、必要なサポート自体を提供します。

`SQLGetInfo`**SQL_SCROLL_OPTIONS**は**SQL_SO_STATIC**をサポートする必要があります。

## <a name="dynaset-cursors"></a>ダイナセット カーソル

ダイナセットを開くために必要な最低限のサポートは次のとおりです。

`SQLGetInfo`を選択すると **、SQL_ODBC_VER**は "01" >返す必要があります。

`SQLGetInfo`SQL_SCROLL_OPTIONS**SQL_SCROLL_OPTIONS****は SQL_SO_KEYSET_DRIVEN**をサポートする必要があります。

`SQLGetInfo`SQL_ROW_UPDATES、"Y" を返す必要があります。 **SQL_ROW_UPDATES**

`SQLGetInfo`SQL_POSITIONED_UPDATES**SQL_POSITIONED_UPDATES****は、SQL_PS_POSITIONED_DELETE**と**SQL_PS_POSITIONED_UPDATE**をサポートする必要があります。

さらに、悲観的なロックが要求された場合、irow `SQLSetPos` 1、fRefresh FALSE、fLock **SQL_LCK_EXCLUSIVE**を使用した呼び出しが行われます。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
