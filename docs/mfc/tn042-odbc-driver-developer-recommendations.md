---
title: 'TN042: ODBC ドライバーの開発に関する推奨事項 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.odbc
dev_langs:
- C++
helpviewer_keywords:
- ODBC drivers [MFC], writing
- databases [MFC], ODBC
- TN042
ms.assetid: ecc6b5d9-f480-4582-9e22-8309fe561dad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 35c75f5c5bae3a1b56abe91340de00f373663792
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="tn042-odbc-driver-developer-recommendations"></a>テクニカル ノート 42: ODBC ドライバーの開発に関する推奨事項
> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 このノートでは、ODBC ドライバーのライターのガイドラインについて説明します。 これは、一般的な要件と MFC データベース クラスを使用する、ODBC の機能と各種の予想されるセマンティック詳細の前提条件について説明します。 3 つをサポートするためにドライバーの機能に必要な`CRecordset`モードを開きます (**forwardOnly**、**スナップショット**と**ダイナセット**) については説明します。  
  
## <a name="odbcs-cursor-library"></a>ODBC のカーソル ライブラリ  
 MFC データベース クラスでは、ほとんどのレベル 1 の ODBC ドライバーによって提供される機能を上回っています。 多くの場合をユーザーに機能を表示します。 さいわい、ODBC のカーソル ライブラリがそれ自体のデータベース クラスと、ドライバーの間でレイヤーし、この追加機能の多くが自動的に提供します。  
  
 たとえば、ほとんどの 1.0 ドライバーでは、後方スクロールはできません。 カーソル ライブラリことができます、このことを検出しは、ドライバーからの行をキャッシュし、FETCH_PREV 呼び出し内で要求されるとおりに表示したり**SQLExtendedFetch**です。  
  
 カーソル ライブラリの他の重要な例では、位置指定更新です。 ほとんどの 1.0 ドライバーも位置指定更新ではありませんが、カーソル ライブラリの現在のキャッシュされたデータ値、またはキャッシュされたタイムスタンプ値に基づくデータ ソースを対象の行を特定する更新ステートメントが生成されます。  
  
 クラス ライブラリの複数の行セットを利用しません。 そのため、いくつか**SQLSetPos**ステートメントは常に行セットの最初の行に適用します。  
  
## <a name="cdatabases"></a>CDatabases  
 各`CDatabase`、1 つを割り当てます**HDBC**です。 (場合`CDatabase`の`ExecuteSQL`関数を使用すると、 **HSTMT**は一時的に割り当てられています)。複数の場合は`CDatabase`の必要な複数**HDBC**あたり秒**HENV**サポートする必要があります。  
  
 データベース クラスでは、カーソル ライブラリが必要です。 これに反映されて、 **SQLSetConnections**呼び出す**SQL_ODBC_CURSORS**、 **SQL_CUR_USE_ODBC**です。  
  
 **SQLDriverConnect**、 **SQL_DRIVER_COMPLETE**によって使用される`CDatabase::Open`データ ソースへの接続を確立するためにします。  
  
 ドライバーをサポートする必要があります**SQLGetInfo SQL_ODBC_API_CONFORMANCE** >= **SQL_OAC_LEVEL1**、 **SQLGetInfo SQL_ODBC_SQL_CONFORMANCE**  >= **以上でなければなりません**です。  
  
 トランザクションをサポートするために、`CDatabase`とその依存しているレコード セット**SQLGetInfo SQL_CURSOR_COMMIT_BEHAVIOR**と**SQL_CURSOR_ROLLBACK_BEHAVIOR** 必要があります**SQL_CR_PRESERVE**です。 それ以外の場合、トランザクションの管理を実行する試行は無視されます。  
  
 **SQLGetInfo SQL_DATA_SOURCE_READ_ONLY**サポートする必要があります。 "Y"が返された場合は、データ ソースで更新操作は実行されません。  
  
 場合、`CDatabase`が開かれている読み取り専用、読み取り、データ ソースを設定しようとすると、のみになりますで**SQLSetConnectOption SQL_ACCESS_MODE**、 **SQL_MODE_READ_ONLY**です。  
  
 この情報を使用してドライバーから返される必要があります識別子では、引用符で囲む必要がある場合、 **SQLGetInfo SQL_IDENTIFIER_QUOTE_CHAR**呼び出します。  
  
 デバッグの目的で、 **SQLGetInfo SQL_DBMS_VER**と**SQL_DBMS_NAME**ドライバーから取得されます。  
  
 **SQLSetStmtOption SQL_QUERY_TIMEOUT**と**SQL_ASYNC_ENABLE**で呼び出すことは、`CDatabase`の**HDBC**です。  
  
 **SQLError**任意またはすべての引数 NULL を指定して呼び出すことができます。  
  
 もちろん、 **SQLAllocEnv**、 **SQLAllocConnect**、 **SQLDisconnect**と**SQLFreeConnect**サポートする必要があります。  
  
## <a name="executesql"></a>ExecuteSQL  
 割り当てと解放、一時的なだけでなく**HSTMT**、`ExecuteSQL`呼び出し**SQLExecDirect**、 **SQLFetch**、 **SQLNumResultCol**と`SQLMoreResults`です。 **SQLCancel**で呼び出すことは、 **HSTMT**です。  
  
## <a name="getdatabasename"></a>GetDatabaseName  
 **SQLGetInfo SQL_DATABASE_NAME**が呼び出されます。  
  
## <a name="begintrans-committrans-rollback"></a>BeginTrans、CommitTrans、ロールバック  
 **SQLSetConnectOption SQL_AUTOCOMMIT**と**SQLTransact 指定して**、 **SQL_ROLLBACK**と**SQL_AUTOCOMMIT**がトランザクションを要求する場合に呼び出されます行われます。  
  
## <a name="crecordsets"></a>CRecordsets  
 **SQLAllocStmt**、 **SQLPrepare**、 **SQLExecute** (の**開く**と**Requery**)、 **SQLExecDirect** (の update 操作の場合)、 **SQLFreeStmt**サポートする必要があります。 **SQLNumResultCols**と**SQLDescribeCol**はさまざまなタイミングで設定の結果で呼び出されます。  
  
 **SQLSetParam**パラメーターのデータをバインドするためによく使用されますと**DATA_AT_EXEC**機能します。  
  
 **SQLBindCol**広範囲に登録するための odbc 列のデータ記憶域の場所を出力します。  
  
 2 つ**SQLGetData**呼び出しを使用して取得**SQL_LONG_VARCHAR**と**SQL_LONG_VARBINARY**データ。 最初の呼び出しが、呼び出すことによって、列の値の長さの合計を検索しようとしています。 **SQLGetData** cbMaxValue 0 ではなく、有効な pcbValue します。 PcbValue 保持している場合**SQL_NO_TOTAL**例外がスローされます。 それ以外の場合、`HGLOBAL`が割り当てられる別および**SQLGetData**呼び出しの結果全体を取得しようとしています。  
  
## <a name="updating"></a>Updating  
 排他ロックが要求された場合**SQLGetInfo SQL_LOCK_TYPES**は照会されます。 場合**SQL_LCK_EXCLUSIVE**はサポートされていない例外がスローされます。  
  
 更新しようとする、 `CRecordset` (**スナップショット**または**ダイナセット**)、2 番目になります**HSTMT**を割り当てます。 サポートしていないドライバーの 2 番目の**HSTMT**、カーソル ライブラリでは、この機能をシミュレートします。 残念ながら、場合によって場合があります最初に、現在のクエリを強制**HSTMT** 、2 つ目を処理する前に完了するまで**HSTMT**からの要求。  
  
 **SQLFreeStmt SQL_CLOSE**と**SQL_RESET_PARAMS**と**SQLGetCursorName**更新操作中に呼び出されます。  
  
 ある場合**CLongBinarys**で、 **outputColumns**、ODBC の**DATA_AT_EXEC**機能をサポートする必要があります。 これは、返すことが含まれています。 **SQL_NEED_DATA**から**SQLExecDirect**、 **SQLParamData**と**SQLPutData**です。  
  
 **SQLRowCount**によって 1 つだけのレコードが更新されたことを確認する実行後に呼び出されます、 **SQLExecDirect**です。  
  
## <a name="forwardonly-cursors"></a>ForwardOnly カーソル  
 のみ**SQLFetch**に必要な**移動**操作します。 なお**forwardOnly**カーソルは更新プログラムをサポートしていません。  
  
## <a name="snapshot-cursors"></a>スナップショット カーソル  
 スナップショット機能が必要です**SQLExtendedFetch**をサポートします。 前述のように、ドライバーがサポートしていない場合に ODBC カーソル ライブラリが検出**SQLExtendedFetch**、およびそれ自体に必要なサポートを提供します。  
  
 **SQLGetInfo**、 **SQL_SCROLL_OPTIONS**をサポートする必要があります**SQL_SO_STATIC**です。  
  
## <a name="dynaset-cursors"></a>ダイナセット カーソル  
 ダイナセットを開くために必要な最小のサポートを次に示します。  
  
 **SQLGetInfo**、 **SQL_ODBC_VER**返す必要があります >「01」。  
  
 **SQLGetInfo**、 **SQL_SCROLL_OPTIONS**をサポートする必要があります**SQL_SO_KEYSET_DRIVEN**です。  
  
 **SQLGetInfo**、 **SQL_ROW_UPDATES** "Y"を返す必要があります。  
  
 **SQLGetInfo**、 **SQL_POSITIONED_UPDATES**をサポートする必要があります**SQL_PS_POSITIONED_DELETE**と**SQL_PS_POSITIONED_UPDATE**です。  
  
 さらに、排他ロックが要求された場合に呼び出し**SQLSetPos** irow 1、fRefresh FALSE fLock と**SQL_LCK_EXCLUSIVE**になります。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

