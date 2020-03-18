---
title: CDatabase クラス
ms.date: 11/04/2016
f1_keywords:
- CDatabase
- AFXDB/CDatabase
- AFXDB/CDatabase::CDatabase
- AFXDB/CDatabase::BeginTrans
- AFXDB/CDatabase::BindParameters
- AFXDB/CDatabase::Cancel
- AFXDB/CDatabase::CanTransact
- AFXDB/CDatabase::CanUpdate
- AFXDB/CDatabase::Close
- AFXDB/CDatabase::CommitTrans
- AFXDB/CDatabase::ExecuteSQL
- AFXDB/CDatabase::GetBookmarkPersistence
- AFXDB/CDatabase::GetConnect
- AFXDB/CDatabase::GetCursorCommitBehavior
- AFXDB/CDatabase::GetCursorRollbackBehavior
- AFXDB/CDatabase::GetDatabaseName
- AFXDB/CDatabase::IsOpen
- AFXDB/CDatabase::OnSetOptions
- AFXDB/CDatabase::Open
- AFXDB/CDatabase::OpenEx
- AFXDB/CDatabase::Rollback
- AFXDB/CDatabase::SetLoginTimeout
- AFXDB/CDatabase::SetQueryTimeout
- AFXDB/CDatabase::m_hdbc
helpviewer_keywords:
- CDatabase [MFC], CDatabase
- CDatabase [MFC], BeginTrans
- CDatabase [MFC], BindParameters
- CDatabase [MFC], Cancel
- CDatabase [MFC], CanTransact
- CDatabase [MFC], CanUpdate
- CDatabase [MFC], Close
- CDatabase [MFC], CommitTrans
- CDatabase [MFC], ExecuteSQL
- CDatabase [MFC], GetBookmarkPersistence
- CDatabase [MFC], GetConnect
- CDatabase [MFC], GetCursorCommitBehavior
- CDatabase [MFC], GetCursorRollbackBehavior
- CDatabase [MFC], GetDatabaseName
- CDatabase [MFC], IsOpen
- CDatabase [MFC], OnSetOptions
- CDatabase [MFC], Open
- CDatabase [MFC], OpenEx
- CDatabase [MFC], Rollback
- CDatabase [MFC], SetLoginTimeout
- CDatabase [MFC], SetQueryTimeout
- CDatabase [MFC], m_hdbc
ms.assetid: bd0de70a-e3c3-4441-bcaa-bbf434426ca8
ms.openlocfilehash: ebc36d82af9bfe12ab30a86214e58610b5eaab95
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424507"
---
# <a name="cdatabase-class"></a>CDatabase クラス

データ ソースへの接続を表します。これを通じてデータ ソース上で操作を行うことができます。

## <a name="syntax"></a>構文

```
class CDatabase : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|Description|
|----------|-----------------|
|[CDatabase:: CDatabase](#cdatabase)|`CDatabase` オブジェクトを構築します。 `OpenEx` または `Open`を呼び出すことによって、オブジェクトを初期化する必要があります。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[CDatabase:: BeginTrans](#begintrans)|"トランザクション" を開始します。これは、接続されたデータソース上のクラス `CRecordset` の `AddNew`、`Edit`、`Delete`、および `Update` メンバー関数の一連の元に戻せる呼び出しです。 データソースは、`BeginTrans` が何らかの影響を与えるためのトランザクションをサポートしている必要があります。|
|[CDatabase:: BindParameters](#bindparameters)|`CDatabase::ExecuteSQL`を呼び出す前にパラメーターをバインドできます。|
|[CDatabase:: Cancel](#cancel)|2番目のスレッドから非同期操作またはプロセスをキャンセルします。|
|[CDatabase:: CanTransact](#cantransact)|データソースがトランザクションをサポートしている場合は0以外の値を返します。|
|[CDatabase:: CanUpdate](#canupdate)|`CDatabase` オブジェクトが更新可能な場合 (読み取り専用ではない場合) は0以外の値を返します。|
|[CDatabase:: Close](#close)|データソース接続を閉じます。|
|[CDatabase:: CommitTrans](#committrans)|`BeginTrans`によって開始されたトランザクションを完了します。 データソースを変更するトランザクションのコマンドが実行されます。|
|[CDatabase:: ExecuteSQL](#executesql)|SQL ステートメントを実行します。 データレコードは返されません。|
|[CDatabase:: GetBookmarkPersistence](#getbookmarkpersistence)|ブックマークをレコードセットオブジェクトで保持する操作を識別します。|
|[CDatabase:: GetConnect](#getconnect)|`CDatabase` オブジェクトをデータソースに接続するために使用される ODBC 接続文字列を返します。|
|[CDatabase:: Getカーソル Commitbehavior](#getcursorcommitbehavior)|開いているレコードセットオブジェクトでトランザクションをコミットした場合の影響を識別します。|
|[CDatabase:: GetCursorRollbackBehavior](#getcursorrollbackbehavior)|開いているレコードセットオブジェクトでトランザクションをロールバックした場合の効果を示します。|
|[CDatabase:: GetDatabaseName](#getdatabasename)|現在使用されているデータベースの名前を返します。|
|[CDatabase:: IsOpen](#isopen)|`CDatabase` オブジェクトが現在データソースに接続されている場合は0以外の値を返します。|
|[CDatabase:: OnSetOptions](#onsetoptions)|標準接続オプションを設定するためにフレームワークによって呼び出されます。 既定の実装では、クエリのタイムアウト値が設定されます。 これらのオプションは、`SetQueryTimeout`を呼び出すことで事前に設定できます。|
|[CDatabase:: Open](#open)|ODBC ドライバーを使用して、データソースへの接続を確立します。|
|[CDatabase:: OpenEx](#openex)|ODBC ドライバーを使用して、データソースへの接続を確立します。|
|[CDatabase:: Rollback](#rollback)|現在のトランザクション中に行われた変更を元に戻します。 データソースは、`BeginTrans` の呼び出しで定義されているように、変更されていない前の状態に戻ります。|
|[CDatabase:: SetLoginTimeout](#setlogintimeout)|データソース接続の試行がタイムアウトするまでの秒数を設定します。|
|[CDatabase:: SetQueryTimeout 解説](#setquerytimeout)|データベースクエリ操作がタイムアウトするまでの秒数を設定します。後続のすべてのレコードセット `Open`、`AddNew`、`Edit`、および `Delete` の呼び出しに影響します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|Name|Description|
|----------|-----------------|
|[CDatabase:: m_hdbc](#m_hdbc)|データソースへの Open Database Connectivity (ODBC) 接続ハンドル。 「 *HDBC*」と入力します。|

## <a name="remarks"></a>解説

データソースは、一部のデータベース管理システム (DBMS) によってホストされるデータの特定のインスタンスです。 例として、Microsoft SQL Server、Microsoft Access、Borland dBASE、xBASE などがあります。 アプリケーションで一度に1つ以上の `CDatabase` オブジェクトをアクティブにすることができます。

> [!NOTE]
>  Open Database Connectivity (ODBC) クラスではなく、データアクセスオブジェクト (DAO) クラスを使用している場合は、代わりにクラス[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)を使用します。 詳細については、記事「[概要: データベースプログラミング](../../data/data-access-programming-mfc-atl.md)」を参照してください。

`CDatabase`を使用するには、`CDatabase` オブジェクトを構築し、その `OpenEx` メンバー関数を呼び出します。 これにより、接続が開きます。 次に、接続されたデータソースを操作するために `CRecordset` オブジェクトを構築し、`CDatabase` オブジェクトへのポインターをレコードセットコンストラクターに渡します。 接続の使用が終了したら、`Close` メンバー関数を呼び出し、`CDatabase` オブジェクトを破棄します。 以前に閉じていないレコードセットは、`Close` によって閉じられます。

`CDatabase`の詳細については、「[データソース (ODBC)](../../data/odbc/data-source-odbc.md) 」および「[概要: データベースプログラミング](../../data/data-access-programming-mfc-atl.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CDatabase`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

##  <a name="begintrans"></a>CDatabase:: BeginTrans

接続されたデータソースとのトランザクションを開始するには、このメンバー関数を呼び出します。

```
BOOL BeginTrans();
```

### <a name="return-value"></a>戻り値

呼び出しが成功し、変更が手動でのみコミットされる場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

トランザクションは、`CRecordset` オブジェクトの `AddNew`、`Edit`、`Delete`、および `Update` メンバー関数の1つ以上の呼び出しで構成されます。 トランザクションを開始する前に、`CDatabase` オブジェクトが、`OpenEx` または `Open` メンバー関数を呼び出して、データソースに既に接続されている必要があります。 トランザクションを終了するには、 [CommitTrans](#committrans)を呼び出してデータソースへのすべての変更を受け入れるか、または[Rollback](#rollback)を呼び出してトランザクション全体を中止します。 トランザクションに関連するレコードセットを開いた後、実際の更新操作にできるだけ近い `BeginTrans` を呼び出します。

> [!CAUTION]
>  ODBC ドライバーによっては、`BeginTrans` を呼び出す前にレコードセットを開くと、`Rollback`の呼び出し時に問題が発生する可能性があります。 使用している特定のドライバーを確認する必要があります。 たとえば、microsoft ODBC Desktop Driver Pack 3.0 に含まれている Microsoft Access driver を使用する場合は、カーソルが開いているデータベースでトランザクションを開始しないように、Jet データベースエンジンの要件を考慮する必要があります。 MFC データベースクラスでは、開いているカーソルは、開いている `CRecordset` オブジェクトを意味します。 詳細については、「[テクニカルノート 68](../../mfc/tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver.md)」を参照してください。

また `BeginTrans` は、要求された同時実行とデータソースの機能に応じて、サーバー上のデータレコードをロックすることもあります。 データのロックの詳細については、「レコード[セット: レコードのロック (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)」を参照してください。

ユーザー定義のトランザクションについては、「[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)」で説明されています。

`BeginTrans` は、トランザクションのシーケンスをロールバック (反転) できる状態を確立します。 ロールバックの新しい状態を確立するには、現在のトランザクションをコミットし、`BeginTrans` を再度呼び出します。

> [!CAUTION]
>  `CommitTrans` または `Rollback` を呼び出さずに `BeginTrans` を再度呼び出すと、エラーになります。

[Cantransact](#cantransact)メンバー関数を呼び出して、ドライバーが特定のデータベースのトランザクションをサポートしているかどうかを確認します。 また、 [Getcursor Commitbehavior](#getcursorcommitbehavior)と[GetCursorRollbackBehavior](#getcursorrollbackbehavior)を呼び出して、カーソルの保持のサポートを確認する必要があります。

トランザクションの詳細については、「[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)」を参照してください。

### <a name="example"></a>例

  「[トランザクション: レコードセットでのトランザクションの実行 (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)」を参照してください。

##  <a name="bindparameters"></a>CDatabase:: BindParameters

[CDatabase:: ExecuteSQL](#executesql)を呼び出す前にパラメーターをバインドする必要がある場合は、`BindParameters` をオーバーライドします。

```
virtual void BindParameters(HSTMT hstmt);
```

### <a name="parameters"></a>パラメーター

*hstmt*<br/>
パラメーターをバインドする ODBC ステートメントハンドル。

### <a name="remarks"></a>解説

この方法は、ストアドプロシージャからの結果セットが不要な場合に便利です。

オーバーライドで、`SQLBindParameters` および関連する ODBC 関数を呼び出して、パラメーターをバインドします。 MFC は、`ExecuteSQL`の呼び出しの前にオーバーライドを呼び出します。 `SQLPrepare`を呼び出す必要はありません。`ExecuteSQL` は `SQLExecDirect` を呼び出し、 *hstmt*を破棄します。これは1回だけ使用されます。

##  <a name="cancel"></a>CDatabase:: Cancel

このメンバー関数を呼び出して、データソースが処理中の非同期操作または2番目のスレッドからのプロセスのいずれかをキャンセルするように要求します。

```
void Cancel();
```

### <a name="remarks"></a>解説

MFC ODBC クラスで非同期処理が使用されなくなったことに注意してください。非同期操作を実行するには、ODBC API 関数[SQLSetConnectOption](/sql/odbc/reference/syntax/sqlsetconnectoption-function)を直接呼び出す必要があります。 詳細については、「[非同期実行](/sql/odbc/reference/develop-app/asynchronous-execution)」を参照してください。

##  <a name="cantransact"></a>CDatabase:: CanTransact

データベースでトランザクションが許可されているかどうかを判断するには、このメンバー関数を呼び出します。

```
BOOL CanTransact() const;
```

### <a name="return-value"></a>戻り値

この `CDatabase` オブジェクトを使用しているレコードがトランザクションを許可する場合は0以外です。それ以外の場合は0です。

### <a name="remarks"></a>解説

トランザクションの詳細については、「[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)」を参照してください。

##  <a name="canupdate"></a>CDatabase:: CanUpdate

`CDatabase` オブジェクトで更新が許可されているかどうかを判断するには、このメンバー関数を呼び出します。

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>戻り値

`CDatabase` オブジェクトが更新を許可する場合は0以外の。それ以外の場合は0。 `CDatabase` オブジェクトを開いたときに*bReadOnly*で TRUE が渡されたか、データソース自体が読み取り専用であることを示します。 ODBC API 関数の呼び出しで `SQLGetInfo` SQL_DATASOURCE_READ_ONLY が "y" を返す場合、データソースは読み取り専用です。

### <a name="remarks"></a>解説

すべてのドライバーが更新をサポートするわけではありません。

##  <a name="cdatabase"></a>CDatabase:: CDatabase

`CDatabase` オブジェクトを構築します。

```
CDatabase();
```

### <a name="remarks"></a>解説

オブジェクトを構築した後は、その `OpenEx` または `Open` メンバー関数を呼び出して、指定されたデータソースへの接続を確立する必要があります。

`CDatabase` オブジェクトをドキュメントクラスに埋め込むと便利な場合があります。

### <a name="example"></a>例

この例では、`CDocument`派生クラスで `CDatabase` を使用する方法を示します。

[!code-cpp[NVC_MFCDatabase#9](../../mfc/codesnippet/cpp/cdatabase-class_1.h)]

[!code-cpp[NVC_MFCDatabase#10](../../mfc/codesnippet/cpp/cdatabase-class_2.cpp)]

##  <a name="close"></a>CDatabase:: Close

データソースから切断する場合は、このメンバー関数を呼び出します。

```
virtual void Close();
```

### <a name="remarks"></a>解説

このメンバー関数を呼び出す前に、`CDatabase` オブジェクトに関連付けられているすべてのレコードセットを閉じる必要があります。 `Close` によって `CDatabase` オブジェクトが破棄されないため、同じデータソースまたは別のデータソースへの新しい接続を開いてオブジェクトを再利用できます。

データベースを使用しているレコードセットの保留中の `AddNew` または `Edit` ステートメントはすべて取り消され、すべての保留中のトランザクションがロールバックされます。 `CDatabase` オブジェクトに依存するすべてのレコードセットは、未定義の状態のままになります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#12](../../mfc/codesnippet/cpp/cdatabase-class_3.cpp)]

##  <a name="committrans"></a>CDatabase:: CommitTrans

トランザクションの完了時にこのメンバー関数を呼び出します。

```
BOOL CommitTrans();
```

### <a name="return-value"></a>戻り値

更新が正常にコミットされた場合は0以外の。それ以外の場合は0です。 `CommitTrans` が失敗した場合、データソースの状態は未定義になります。 データを確認して、その状態を確認する必要があります。

### <a name="remarks"></a>解説

トランザクションは、 [BeginTrans](#begintrans)メンバー関数の呼び出しで開始された `CRecordset` オブジェクトの `AddNew`、`Edit`、`Delete`、および `Update` メンバー関数の一連の呼び出しで構成されます。 `CommitTrans` はトランザクションをコミットします。 既定では、更新プログラムは直ちにコミットされます。`BeginTrans` を呼び出すと、`CommitTrans` が呼び出されるまで更新のコミットメントが遅延されます。

`CommitTrans` を呼び出してトランザクションを終了するまでは、 [Rollback](#rollback)メンバー関数を呼び出してトランザクションを中止し、データソースを元の状態のままにすることができます。 新しいトランザクションを開始するには、`BeginTrans` を再度呼び出します。

トランザクションの詳細については、「[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)」を参照してください。

### <a name="example"></a>例

  「[トランザクション: レコードセットでのトランザクションの実行 (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)」を参照してください。

##  <a name="executesql"></a>CDatabase:: ExecuteSQL

SQL コマンドを直接実行する必要がある場合は、このメンバー関数を呼び出します。

```
void ExecuteSQL(LPCTSTR lpszSQL);
```

### <a name="parameters"></a>パラメーター

*lpszSQL*<br/>
実行する有効な SQL コマンドを含む null で終わる文字列へのポインター。 [CString](../../atl-mfc-shared/reference/cstringt-class.md)を渡すことができます。

### <a name="remarks"></a>解説

Null で終わる文字列としてコマンドを作成します。 `ExecuteSQL` はデータレコードを返しません。 レコードを操作する場合は、代わりにレコードセットオブジェクトを使用します。

データソース用のコマンドのほとんどは、データの選択、新しいレコードの挿入、レコードの削除、レコードの編集を行うためのコマンドをサポートする、レコードセットオブジェクトを介して発行されます。 ただし、すべての ODBC 機能がデータベースクラスによって直接サポートされるわけではないため、`ExecuteSQL`を使用して SQL の直接呼び出しを行う必要がある場合があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#13](../../mfc/codesnippet/cpp/cdatabase-class_4.cpp)]

##  <a name="getbookmarkpersistence"></a>CDatabase:: GetBookmarkPersistence

特定の操作の後で、レコードセット オブジェクトでのブックマークの永続性を判別するには、このメンバー関数を呼び出します。

```
DWORD GetBookmarkPersistence() const;
```

### <a name="return-value"></a>戻り値

レコードセット オブジェクトでブックマークが保持されている操作を識別するビットマスク。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

たとえば、`CRecordset::GetBookmark` を呼び出してから `CRecordset::Requery` を呼び出した場合、`GetBookmark` から取得されたブックマークは有効ではなくなっている場合があります。 `GetBookmarkPersistence` を呼び出してから `CRecordset::SetBookmark` を呼び出す必要があります。

`GetBookmarkPersistence` の戻り値として組み合わせることができるビットマスク値の一覧を次の表に示します。

|ビットマスク値|ブックマークの永続性|
|-------------------|--------------------------|
|SQL_BP_CLOSE|ブックマークは、`Requery` 操作の後に有効です。|
|SQL_BP_DELETE|行のブックマークは、その行の `Delete` 操作の後に有効です。|
|SQL_BP_DROP|ブックマークは、`Close` 操作の後に有効です。|
|SQL_BP_SCROLL|ブックマークは、任意の `Move` 操作の後に有効です。 これは、`CRecordset::CanBookmark` によって返されるのと同様に、レコードセットでブックマークがサポートされているかどうかだけを示します。|
|SQL_BP_TRANSACTION|トランザクションがコミットまたはロールバックされた後、ブックマークは有効です。|
|SQL_BP_UPDATE|行のブックマークは、その行の `Update` 操作の後に有効です。|
|SQL_BP_OTHER_HSTMT|1 つのレコードセット オブジェクトに関連付けられたブックマークは、別のレコードセットで有効です。|

この戻り値の詳細については、Windows SDK の ODBC API 関数 `SQLGetInfo` を参照してください。 ブックマークの詳細については、「[レコードセット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)」を参照してください。

##  <a name="getconnect"></a>CDatabase:: GetConnect

このメンバー関数を呼び出すことで、`OpenEx` オブジェクトをデータ ソースに接続した `Open` または `CDatabase` の呼び出し時に使用された接続文字列を取得します。

```
const CString GetConnect() const;
```

### <a name="return-value"></a>戻り値

`OpenEx` または `Open` が呼び出された場合は、接続文字列を含む**const**[CString](../../atl-mfc-shared/reference/cstringt-class.md) 。それ以外の場合は、空の文字列。

### <a name="remarks"></a>解説

接続文字列の作成方法の詳細については、「 [CDatabase:: Open](#open) 」を参照してください。

##  <a name="getcursorcommitbehavior"></a>CDatabase:: Getカーソル Commitbehavior

このメンバー関数を呼び出して、 [CommitTrans](#committrans)操作が、開いているレコードセットオブジェクトのカーソルにどのように影響するかを決定します。

```
int GetCursorCommitBehavior() const;
```

### <a name="return-value"></a>戻り値

開いているレコードセットオブジェクトに対するトランザクションの影響を示す値です。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

次の表に、`GetCursorCommitBehavior` に使用できる戻り値と、開いているレコードセットに対する対応結果を示します。

|戻り値|CRecordset オブジェクトへの影響|
|------------------|----------------------------------|
|SQL_CB_CLOSE|トランザクションのコミット直後に `CRecordset::Requery` を呼び出します。|
|SQL_CB_DELETE|トランザクションのコミット直後に `CRecordset::Close` を呼び出します。|
|SQL_CB_PRESERVE|`CRecordset` 操作で通常どおり続行します。|

この戻り値の詳細については、Windows SDK の ODBC API 関数 `SQLGetInfo` を参照してください。 トランザクションの詳細については、「[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)」を参照してください。

##  <a name="getcursorrollbackbehavior"></a>CDatabase:: GetCursorRollbackBehavior

このメンバー関数を呼び出して、[ロールバック](#rollback)操作が、開いているレコードセットオブジェクトのカーソルにどのように影響するかを決定します。

```
int GetCursorRollbackBehavior() const;
```

### <a name="return-value"></a>戻り値

開いているレコードセットオブジェクトに対するトランザクションの影響を示す値です。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

次の表に、`GetCursorRollbackBehavior` に使用できる戻り値と、開いているレコードセットに対する対応結果を示します。

|戻り値|CRecordset オブジェクトへの影響|
|------------------|----------------------------------|
|SQL_CB_CLOSE|トランザクションのロールバック直後に `CRecordset::Requery` を呼び出します。|
|SQL_CB_DELETE|トランザクションのロールバック直後に `CRecordset::Close` を呼び出します。|
|SQL_CB_PRESERVE|`CRecordset` 操作で通常どおり続行します。|

この戻り値の詳細については、Windows SDK の ODBC API 関数 `SQLGetInfo` を参照してください。 トランザクションの詳細については、「[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)」を参照してください。

##  <a name="getdatabasename"></a>CDatabase:: GetDatabaseName

このメンバー関数を呼び出して、現在接続されているデータベースの名前を取得します (データソースで "database" という名前のオブジェクトが定義されている場合)。

```
CString GetDatabaseName() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、データベース名を含む[CString](../../atl-mfc-shared/reference/cstringt-class.md) 。それ以外の場合は、空の `CString`。

### <a name="remarks"></a>解説

これは、`OpenEx` または `Open` 呼び出しで指定されたデータソース名 (DSN) と同じではありません。 によって返される `GetDatabaseName` は ODBC によって異なります。 一般に、データベースはテーブルのコレクションです。 このエンティティに名前がある場合は、`GetDatabaseName` によって返されます。

たとえば、この名前を見出しに表示することができます。 ODBC から名前を取得しているときにエラーが発生した場合、`GetDatabaseName` は空の `CString`を返します。

##  <a name="isopen"></a>CDatabase:: IsOpen

`CDatabase` オブジェクトが現在データソースに接続されているかどうかを判断するには、このメンバー関数を呼び出します。

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>戻り値

`CDatabase` オブジェクトが現在接続されている場合は0以外の。それ以外の場合は0です。

##  <a name="m_hdbc"></a>CDatabase:: m_hdbc

ODBC データソース接続 ("接続ハンドル") へのパブリックハンドルを格納します。

### <a name="remarks"></a>解説

通常、このメンバー変数に直接アクセスする必要はありません。 代わりに、`OpenEx` または `Open`を呼び出すときに、フレームワークによってハンドルが割り当てられます。 `CDatabase` オブジェクトで**delete**演算子を呼び出すと、フレームワークによってハンドルの割り当てが解除されます。 `Close` メンバー関数ではハンドルの割り当てが解除されないことに注意してください。

ただし、状況によっては、ハンドルを直接使用することが必要になる場合があります。 たとえば、クラス `CDatabase`を使用せずに ODBC API 関数を直接呼び出す必要がある場合は、パラメーターとして渡す接続ハンドルが必要になることがあります。 次のコード例を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#15](../../mfc/codesnippet/cpp/cdatabase-class_5.cpp)]

##  <a name="onsetoptions"></a>CDatabase:: OnSetOptions

このメンバー関数は、`ExecuteSQL` メンバー関数を使用して SQL ステートメントを直接実行するときに、フレームワークによって呼び出されます。

```
virtual void OnSetOptions(HSTMT hstmt);
```

### <a name="parameters"></a>パラメーター

*hstmt*<br/>
オプションを設定する ODBC ステートメントハンドル。

### <a name="remarks"></a>解説

`CRecordset::OnSetOptions` もこのメンバー関数を呼び出します。

ログインタイムアウト値を `OnSetOptions` 設定します。 `SetQueryTimeout` とメンバー関数を以前に呼び出した場合、`OnSetOptions` には現在の値が反映されます。それ以外の場合は、既定値が設定されます。

> [!NOTE]
>  MFC 4.2 より前の `OnSetOptions` も、処理モードを snychronous または非同期に設定しています。 MFC 4.2 以降では、すべての操作が同期されます。 非同期操作を実行するには、`SQLSetPos`ODBC API 関数への直接呼び出しを行う必要があります。

タイムアウト値を変更するには、`OnSetOptions` をオーバーライドする必要はありません。 代わりに、クエリのタイムアウト値をカスタマイズするには、レコードセットを作成する前に `SetQueryTimeout` を呼び出します。`OnSetOptions` は新しい値を使用します。 これらの値は、すべてのレコードセットまたは直接の SQL 呼び出しに対する後続の操作に適用されます。

追加のオプションを設定する場合は、`OnSetOptions` をオーバーライドします。 オーバーライドでは、ODBC API 関数 `SQLSetStmtOption`を呼び出す前または後に、基本クラス `OnSetOptions` を呼び出す必要があります。 `OnSetOptions`のフレームワークの既定の実装に示されているメソッドに従います。

##  <a name="open"></a>CDatabase:: Open

新しく構築された `CDatabase` オブジェクトを初期化するには、このメンバー関数を呼び出します。

```
virtual BOOL Open(
    LPCTSTR lpszDSN,
    BOOL bExclusive = FALSE,
    BOOL bReadOnly = FALSE,
    LPCTSTR lpszConnect = _T("ODBC;"),
    BOOL bUseCursorLib = TRUE);
```

### <a name="parameters"></a>パラメーター

*lpszDSN*<br/>
データソース名を指定します。 odbc 管理者プログラムを使用して ODBC に登録されている名前です。 DSN 値が*Lpszconnect* ("DSN =\<データソース >" の形式) で指定されている場合、 *lpszconnect*で再度指定することはできません。 この場合、 *Lpszdsn*は NULL である必要があります。 それ以外の場合、ユーザーがデータソースを選択できる [データソース] ダイアログボックスを表示する場合は、NULL を渡すことができます。 詳細については、「解説」を参照してください。

*bExclusive*<br/>
このバージョンのクラスライブラリではサポートされていません。 現在、このパラメーターが TRUE の場合、アサーションは失敗します。 データソースは常に共有 (非排他) として開かれます。

*bReadOnly*<br/>
接続を読み取り専用にし、データソースへの更新を禁止する場合は TRUE。 すべての依存レコードセットは、この属性を継承します。 既定値は FALSE です。

*lpszConnect*<br/>
接続文字列を指定します。 接続文字列は、データソース名、データソースで有効なユーザー ID、ユーザー認証文字列 (データソースが必要な場合はパスワード)、その他の情報など、情報を連結します。 接続文字列全体の先頭には、文字列 "ODBC;" を付ける必要があります。(大文字または小文字)。 ODBC データソースへの接続であることを示すには、"ODBC;" という文字列を使用します。これは、将来のバージョンのクラスライブラリが ODBC 以外のデータソースをサポートする場合の上位互換性のためのものです。

*bUseCursorLib*<br/>
ODBC カーソルライブラリの DLL を読み込む場合は TRUE を指定します。 カーソルライブラリによって、基になる ODBC ドライバーの一部の機能がマスクされ、ダイナセットの使用が実質的に妨げられます (ドライバーでサポートされている場合)。 カーソルライブラリが読み込まれる場合にサポートされるカーソルは、静的スナップショットと順方向専用カーソルだけです。 既定値は TRUE です。 `CRecordset` から派生せずにレコードセットオブジェクトを直接作成する場合は、カーソルライブラリを読み込まないようにしてください。

### <a name="return-value"></a>戻り値

接続が正常に確立された場合は0以外の。それ以外の場合は、接続情報を求めるダイアログボックスが表示されたときにユーザーが [キャンセル] を選択した場合は0になります。 それ以外の場合は、フレームワークによって例外がスローされます。

### <a name="remarks"></a>解説

データベースオブジェクトを使用してレコードセットオブジェクトを作成するには、事前にデータベースオブジェクトを初期化しておく必要があります。

> [!NOTE]
>  データソースに接続してデータベースオブジェクトを初期化するには、 [OpenEx](#openex)メンバー関数を呼び出すことをお勧めします。

`Open` 呼び出しのパラメーターに接続を確立するための十分な情報が含まれていない場合、ODBC ドライバーはダイアログボックスを開き、ユーザーから必要な情報を取得します。 `Open`を呼び出すと、接続文字列の*Lpszconnect*が `CDatabase` オブジェクトにプライベートに格納され、 [getconnect](#getconnect)メンバー関数を呼び出すことによって使用できるようになります。

必要に応じて、独自のダイアログボックスを開いて、ユーザーからの情報 (パスワードなど) を取得し、その情報を `Open`に渡す接続文字列に追加する前 `Open` に、独自のダイアログボックスを開くことができます。 または、次にアプリケーションが `CDatabase` オブジェクトで `Open` を呼び出すときに再利用できるように、渡す接続文字列を保存することもできます。

また、複数のレベルのログイン認証 (それぞれ別の `CDatabase` オブジェクト用) の接続文字列を使用したり、その他のデータソース固有の情報を伝達したりすることもできます。 接続文字列の詳細については、Windows SDK の第5章を参照してください。

たとえば、DBMS ホストが使用できない場合、接続のタイムアウトが発生する可能性があります。 接続試行が失敗した場合、`Open` によって `CDBException`がスローされます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#14](../../mfc/codesnippet/cpp/cdatabase-class_6.cpp)]

##  <a name="openex"></a>CDatabase:: OpenEx

新しく構築された `CDatabase` オブジェクトを初期化するには、このメンバー関数を呼び出します。

```
virtual BOOL OpenEx(
    LPCTSTR lpszConnectString,
    DWORD dwOptions = 0);
```

### <a name="parameters"></a>パラメーター

*lpszConnectString*<br/>
ODBC 接続文字列を指定します。 これには、データソース名とその他のオプションの情報 (ユーザー ID やパスワードなど) が含まれます。 たとえば、"DSN = SQLServer_Source;UID = SA;PWD = abc123 "は、使用可能な接続文字列です。 *Lpszconnectstring*に NULL を渡すと、データソースを選択するように求めるダイアログボックスが表示されます。

*dwOptions*<br/>
次の値の組み合わせを指定するビットマスク。 既定値は0です。これは、データベースが書き込みアクセスで共有として開かれ、ODBC カーソルライブラリ DLL が読み込まれないこと、および接続に必要な情報が不足している場合にのみ、[ODBC 接続] ダイアログボックスが表示されることを意味します。

- `CDatabase::openExclusive`、このバージョンのクラスライブラリではサポートされていません。 データソースは常に共有 (非排他) として開かれます。 現在、このオプションを指定した場合、アサーションは失敗します。

- `CDatabase::openReadOnly` データソースを読み取り専用として開きます。

- ODBC カーソルライブラリの DLL を `CDatabase::useCursorLib` 読み込みます。 カーソルライブラリによって、基になる ODBC ドライバーの一部の機能がマスクされ、ダイナセットの使用が実質的に妨げられます (ドライバーでサポートされている場合)。 カーソルライブラリが読み込まれる場合にサポートされるカーソルは、静的スナップショットと順方向専用カーソルだけです。 `CRecordset` から派生せずにレコードセットオブジェクトを直接作成する場合は、カーソルライブラリを読み込まないようにしてください。

- 十分な接続情報が指定されているかどうかに関係なく、[ODBC 接続] ダイアログボックスは表示されません `CDatabase::noOdbcDialog`。

- `CDatabase::forceOdbcDialog` 常に [ODBC 接続] ダイアログボックスが表示されます。

### <a name="return-value"></a>戻り値

接続が正常に確立された場合は0以外の。それ以外の場合は、接続情報を求めるダイアログボックスが表示されたときにユーザーが [キャンセル] を選択した場合は0になります。 それ以外の場合は、フレームワークによって例外がスローされます。

### <a name="remarks"></a>解説

データベースオブジェクトを使用してレコードセットオブジェクトを作成するには、事前にデータベースオブジェクトを初期化しておく必要があります。

`OpenEx` 呼び出しの*Lpszconnectstring*パラメーターに接続を確立するための十分な情報が含まれていない場合、ODBC ドライバーはダイアログボックスを開き、ユーザーから必要な情報を取得します。これは、 *dwOptions*パラメーターで `CDatabase::noOdbcDialog` または `CDatabase::forceOdbcDialog` が設定されていない場合に表示されます。 `OpenEx`を呼び出すと、接続文字列の*Lpszconnectstring*が `CDatabase` オブジェクトにプライベートに格納され、 [getconnect](#getconnect)メンバー関数を呼び出すことによって使用できるようになります。

必要に応じて、独自のダイアログボックスを開き、`OpenEx` を呼び出してユーザーからの情報 (パスワードなど) を取得し、`OpenEx`に渡す接続文字列にその情報を追加することができます。 または、次にアプリケーションが `CDatabase` オブジェクトで `OpenEx` を呼び出すときに再利用できるように、渡す接続文字列を保存することもできます。

また、複数のレベルのログイン認証 (それぞれ別の `CDatabase` オブジェクト用) の接続文字列を使用したり、その他のデータソース固有の情報を伝達したりすることもできます。 接続文字列の詳細については、 *ODBC プログラマーリファレンス*の第6章を参照してください。

たとえば、DBMS ホストが使用できない場合、接続のタイムアウトが発生する可能性があります。 接続試行が失敗した場合、`OpenEx` によって `CDBException`がスローされます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#11](../../mfc/codesnippet/cpp/cdatabase-class_7.cpp)]

##  <a name="rollback"></a>CDatabase:: Rollback

トランザクション中に行われた変更を元に戻すには、このメンバー関数を呼び出します。

```
BOOL Rollback();
```

### <a name="return-value"></a>戻り値

トランザクションが正常に元に戻された場合は0以外の。それ以外の場合は0です。 `Rollback` の呼び出しが失敗した場合、データソースとトランザクションの状態は定義されていません。 `Rollback` が0を返す場合は、データソースを確認してその状態を確認する必要があります。

### <a name="remarks"></a>解説

前回の[BeginTrans](#begintrans)以降に実行されたすべての `CRecordset` `AddNew`、`Edit`、`Delete`、および `Update` の呼び出しは、その呼び出しの時点で存在していた状態にロールバックされます。

`Rollback`の呼び出しの後にトランザクションが実行され、別のトランザクションに対して `BeginTrans` をもう一度呼び出す必要があります。 `BeginTrans` を呼び出す前の現在のレコードは、`Rollback`後に現在のレコードになります。

ロールバック後、ロールバックの前に最新だったレコードは最新のままになります。 ロールバック後のレコードセットとデータソースの状態の詳細については、「[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)」を参照してください。

### <a name="example"></a>例

  「[トランザクション: レコードセットでのトランザクションの実行 (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)」を参照してください。

##  <a name="setlogintimeout"></a>CDatabase:: SetLoginTimeout

`OpenEx` または `Open` を呼び出す前にこのメンバー関数を呼び出して、データソース接続の試行がタイムアウトするまでの既定の秒数をオーバーライドします。

```
void SetLoginTimeout(DWORD dwSeconds);
```

### <a name="parameters"></a>パラメーター

*dwSeconds*<br/>
接続試行がタイムアウトするまでに許容される秒数。

### <a name="remarks"></a>解説

たとえば、DBMS が使用できない場合は、接続試行がタイムアウトすることがあります。 初期化されていない `CDatabase` オブジェクトを構築した後、`OpenEx` または `Open`を呼び出す前に、`SetLoginTimeout` を呼び出します。

ログインタイムアウトの既定値は15秒です。 すべてのデータソースで、ログインタイムアウト値を指定する機能がサポートされているわけではありません。 データソースがタイムアウトをサポートしていない場合、トレース出力は取得されますが、例外は取得されません。 値0は "無限" を意味します。

##  <a name="setquerytimeout"></a>CDatabase:: SetQueryTimeout 解説

このメンバー関数を呼び出して、接続されたデータソースでの後続の操作がタイムアウトになるまでの既定の秒数をオーバーライドします。

```
void SetQueryTimeout(DWORD dwSeconds);
```

### <a name="parameters"></a>パラメーター

*dwSeconds*<br/>
クエリ試行がタイムアウトするまでに許容される秒数。

### <a name="remarks"></a>解説

操作は、ネットワークアクセスの問題、クエリ処理時間の超過などによってタイムアウトする場合があります。 クエリのタイムアウト値を変更する場合は、レコードセットを開く前、またはレコードセットの `AddNew`、`Update` または `Delete` のメンバー関数を呼び出す前に `SetQueryTimeout` を呼び出します。 この設定は、この `CDatabase` オブジェクトに関連付けられているすべてのレコードセットの後続の `Open`、`AddNew`、`Update`、および `Delete` の呼び出しすべてに影響します。 を開いた後でレコードセットのクエリタイムアウト値を変更しても、レコードセットの値は変更されません。 たとえば、後続の `Move` 操作では、新しい値は使用されません。

クエリタイムアウトの既定値は15秒です。 すべてのデータソースで、クエリのタイムアウト値を設定する機能がサポートされているわけではありません。 クエリのタイムアウト値を0に設定すると、タイムアウトは発生しません。データソースとの通信が応答しなくなる場合があります。 この動作は、開発時に便利な場合があります。 データソースがタイムアウトをサポートしていない場合、トレース出力は取得されますが、例外は取得されません。

## <a name="see-also"></a>参照

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CRecordset クラス](../../mfc/reference/crecordset-class.md)
