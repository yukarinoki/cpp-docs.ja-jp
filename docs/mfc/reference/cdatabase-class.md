---
title: クラス
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
ms.openlocfilehash: bc920307e09179dc214710a3b6b19ff27a82749d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754640"
---
# <a name="cdatabase-class"></a>クラス

データ ソースへの接続を表します。これを通じてデータ ソース上で操作を行うことができます。

## <a name="syntax"></a>構文

```
class CDatabase : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[データベース::データベース](#cdatabase)|`CDatabase` オブジェクトを構築します。 オブジェクトを初期化するには、 または`OpenEx``Open`を呼び出す必要があります。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[データベース::ビギンストランス](#begintrans)|接続されたデータ ソース`AddNew`で、クラス、、、`Edit`および`Delete`クラス`Update``CRecordset`のメンバー関数に対する一連の呼び出しを元に戻せる "トランザクション" を開始します。 データ ソースは、何らかの効果`BeginTrans`を持つトランザクションをサポートする必要があります。|
|[を使用します。](#bindparameters)|を呼び出す`CDatabase::ExecuteSQL`前にパラメータをバインドできます。|
|[データベース::キャンセル](#cancel)|非同期操作または 2 番目のスレッドからのプロセスをキャンセルします。|
|[データベース::缶トランスアクト](#cantransact)|データ ソースがトランザクションをサポートする場合は、0 以外を返します。|
|[データベース::缶更新](#canupdate)|オブジェクトが`CDatabase`更新可能な場合は、0 以外を返します (読み取り専用ではありません)。|
|[データベース::閉じる](#close)|データ ソース接続を閉じます。|
|[データベース::コミットトランス](#committrans)|によって開始されたトランザクションを`BeginTrans`完了します。 トランザクション内でデータ ソースを変更するコマンドが実行されます。|
|[SQL を実行します。](#executesql)|SQL ステートメントを実行します。 データ レコードは返されません。|
|[を使用します。](#getbookmarkpersistence)|ブックマークがレコードセット オブジェクトに保持される操作を識別します。|
|[CDatabase::GetConnect](#getconnect)|オブジェクトをデータ ソースに接続するために使用`CDatabase`する ODBC 接続文字列を返します。|
|[を実行します。](#getcursorcommitbehavior)|開いているレコードセット オブジェクトに対してトランザクションをコミットした場合の影響を識別します。|
|[振る舞い](#getcursorrollbackbehavior)|開いているレコードセット オブジェクトに対してトランザクションをロールバックする効果を識別します。|
|[データベース名を取得します。](#getdatabasename)|現在使用中のデータベースの名前を返します。|
|[データベース::IsOpen](#isopen)|オブジェクトがデータ ソース`CDatabase`に現在接続されている場合は、0 以外を返します。|
|[::オンセットオプション](#onsetoptions)|標準接続オプションを設定するために、フレームワークによって呼び出されます。 既定の実装では、クエリのタイムアウト値を設定します。 これらのオプションは、 を呼び出`SetQueryTimeout`すことで事前に確立できます。|
|[データベース::オープン](#open)|ODBC ドライバを使用してデータ ソースへの接続を確立します。|
|[データベース::オープンエックス](#openex)|ODBC ドライバを使用してデータ ソースへの接続を確立します。|
|[データベース::ロールバック](#rollback)|現在のトランザクション中に行われた変更を取り消します。 データ ソースは、呼び出し時に定義された`BeginTrans`状態に変更されずに、以前の状態に戻ります。|
|[を設定します。](#setlogintimeout)|データ ソース接続の試行がタイムアウトするまでの秒数を設定します。|
|[を使用します。](#setquerytimeout)|データベース クエリ操作がタイムアウトするまでの秒数を設定します。後続のすべてのレコードセット`Open` `AddNew`、、、、`Edit`および呼び出し`Delete`に影響します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[データベース::m_hdbc](#m_hdbc)|データ ソースへのデータベース接続 (ODBC) 接続ハンドルを開きます。 *「HDBC」と*入力します。|

## <a name="remarks"></a>解説

データ ソースは、データベース管理システム (DBMS) によってホストされるデータの特定のインスタンスです。 例としては、SQL サーバー、アクセス、ボーランド dBASE、および xBASE が含まれます。 アプリケーションでは、一度に`CDatabase`1 つ以上のオブジェクトをアクティブにできます。

> [!NOTE]
> ODBC クラスではなく、データ アクセス オブジェクト (DAO) クラスを使用する場合は、代わりに[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)クラスを使用します。 詳細については、「[概要: データベース プログラミング](../../data/data-access-programming-mfc-atl.md)」を参照してください。

を使用`CDatabase`するには、オブジェクト`CDatabase`を構築し、`OpenEx`そのメンバー関数を呼び出します。 これにより、接続が開きます。 接続されたデータ`CRecordset`ソースを操作するためのオブジェクトを構築する場合は、オブジェクトへのポインターをレコードセット`CDatabase`コンストラクターに渡します。 接続の使用が終了したら、メンバー関数`Close`を呼び出して`CDatabase`オブジェクトを破棄します。 `Close`以前に閉じなかったレコードセットをすべて閉じます。

詳細については`CDatabase`、「[データ ソース (ODBC) 」](../../data/odbc/data-source-odbc.md)および「[概要 : データベース プログラミング](../../data/data-access-programming-mfc-atl.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CDatabase`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="cdatabasebegintrans"></a><a name="begintrans"></a>データベース::ビギンストランス

接続されたデータ ソースでトランザクションを開始するには、このメンバー関数を呼び出します。

```
BOOL BeginTrans();
```

### <a name="return-value"></a>戻り値

呼び出しが成功し、変更が手動でのみコミットされた場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

トランザクションは`AddNew`、オブジェクトの 、 、 、 `Edit` `Delete`、 `Update` 、 、`CRecordset`のメンバー関数に対する 1 つ以上の呼び出しで構成されます。 トランザクションを開始する前に`CDatabase`、オブジェクトまたは`Open`メンバー関数を呼び出して、オブジェクトが`OpenEx`データ ソースに接続されている必要があります。 トランザクションを終了するには[、CommitTrans](#committrans)を呼び出してデータ ソースに対するすべての変更を受け入れる (および実行する) か[、Rollback](#rollback)を呼び出してトランザクション全体を中止します。 トランザクション`BeginTrans`に関連するレコードセットを開き、可能な限り実際の更新操作に近づいた後に呼び出します。

> [!CAUTION]
> ODBC ドライバによっては、呼び出し`BeginTrans`前にレコードセットを開くと`Rollback`、 を呼び出す際に問題が発生する場合があります。 使用している特定のドライバを確認してください。 たとえば、Microsoft ODBC デスクトップ ドライバ パック 3.0 に含まれている Microsoft Access ドライバを使用する場合、オープン カーソルを持つデータベースでトランザクションを開始しないように Jet データベース エンジンの要件を考慮する必要があります。 MFC データベース クラスでは、開いているカーソルは開`CRecordset`いているオブジェクトを意味します。 詳細については、テクニカル[ノート 68](../../mfc/tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver.md)を参照してください。

`BeginTrans`また、要求された同時実行性とデータ ソースの機能に応じて、サーバー上のデータ レコードをロックすることもできます。 データのロックについては、「[レコードセット: レコードのロック (ODBC) 」](../../data/odbc/recordset-locking-records-odbc.md)を参照してください。

ユーザー定義のトランザクションについては、「[トランザクション (ODBC) 」](../../data/odbc/transaction-odbc.md)を参照してください。

`BeginTrans`は、一連のトランザクションをロールバック (逆) できる状態を確立します。 ロールバックの新しい状態を確立するには、現在のトランザクションをコミットしてから、`BeginTrans`もう一度呼び出します。

> [!CAUTION]
> 呼`BeginTrans`び出し`CommitTrans`を`Rollback`行わずに再度呼び出すか、またはエラーです。

[CanTransact](#cantransact)メンバー関数を呼び出して、ドライバーが特定のデータベースのトランザクションをサポートしているかどうかを確認します。 また、カーソル保持のサポートを決定するために[、GetCursorCommitBehavior](#getcursorcommitbehavior)と[GetCursorRollbackBehavior](#getcursorrollbackbehavior)を呼び出す必要があります。

トランザクションの詳細については、「[トランザクション (ODBC) 」](../../data/odbc/transaction-odbc.md)を参照してください。

### <a name="example"></a>例

  「[トランザクション: レコードセットでのトランザクションの実行 (ODBC)」](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)を参照してください。

## <a name="cdatabasebindparameters"></a><a name="bindparameters"></a>を使用します。

`BindParameters` [CDatabase::ExecuteSQL](#executesql)を呼び出す前にパラメータをバインドする必要があるときにオーバーライドします。

```
virtual void BindParameters(HSTMT hstmt);
```

### <a name="parameters"></a>パラメーター

*hstmt*<br/>
パラメーターをバインドする ODBC ステートメント ハンドル。

### <a name="remarks"></a>解説

この方法は、ストアド プロシージャの結果セットが不要な場合に便利です。

オーバーライドで、パラメーターを`SQLBindParameters`バインドするために、ODBC 関数と関連する ODBC 関数を呼び出します。 MFC は、呼び出し`ExecuteSQL`の前にオーバーライドを呼び出します。 呼び出す`SQLPrepare`必要はありません。`ExecuteSQL` `SQLExecDirect` *hstmt*を呼び出して破棄します。

## <a name="cdatabasecancel"></a><a name="cancel"></a>データベース::キャンセル

データ ソースが、進行中の非同期操作または 2 番目のスレッドからのプロセスのいずれかを取り消すように要求するには、このメンバー関数を呼び出します。

```cpp
void Cancel();
```

### <a name="remarks"></a>解説

MFC ODBC クラスは非同期処理を使用しなくなります。非同期操作を実行するには、ODBC API 関数[SQLSetConnect オプション](/sql/odbc/reference/syntax/sqlsetconnectoption-function)を直接呼び出す必要があります。 詳細については、「[非同期実行](/sql/odbc/reference/develop-app/asynchronous-execution)」を参照してください。

## <a name="cdatabasecantransact"></a><a name="cantransact"></a>データベース::缶トランスアクト

データベースでトランザクションが許可されているかどうかを確認します。

```
BOOL CanTransact() const;
```

### <a name="return-value"></a>戻り値

この`CDatabase`オブジェクトを使用するレコードセットでトランザクションを許可する場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

トランザクションの詳細については、「[トランザクション (ODBC) 」](../../data/odbc/transaction-odbc.md)を参照してください。

## <a name="cdatabasecanupdate"></a><a name="canupdate"></a>データベース::缶更新

`CDatabase`オブジェクトが更新を許可するかどうかを確認します。

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>戻り値

オブジェクトが更新を`CDatabase`許可する場合は 0 以外。それ以外の場合は 0 を指定し、`CDatabase`オブジェクトを開いたときに true を*bReadOnly*で渡したか、データ ソース自体が読み取り専用であることを示します。 odbc API 関数`SQLGetInfo`の SQL_DATASOURCE_READ_ONLY呼び出しが "y" を返す場合、データ ソースは読み取り専用です。

### <a name="remarks"></a>解説

すべてのドライバが更新をサポートしているわけではありません。

## <a name="cdatabasecdatabase"></a><a name="cdatabase"></a>データベース::データベース

`CDatabase` オブジェクトを構築します。

```
CDatabase();
```

### <a name="remarks"></a>解説

オブジェクトを構築した後、指定したデータ`OpenEx`ソース`Open`への接続を確立するには、そのオブジェクトまたはメンバー関数を呼び出す必要があります。

ドキュメント クラスにオブジェクトを`CDatabase`埋め込むと便利な場合があります。

### <a name="example"></a>例

この例では、派生`CDatabase`クラスで`CDocument`の使用を示します。

[!code-cpp[NVC_MFCDatabase#9](../../mfc/codesnippet/cpp/cdatabase-class_1.h)]

[!code-cpp[NVC_MFCDatabase#10](../../mfc/codesnippet/cpp/cdatabase-class_2.cpp)]

## <a name="cdatabaseclose"></a><a name="close"></a>データベース::閉じる

データ ソースから切断する場合は、このメンバー関数を呼び出します。

```
virtual void Close();
```

### <a name="remarks"></a>解説

このメンバー関数を呼び出す前`CDatabase`に、オブジェクトに関連付けられているレコードセットをすべて閉じる必要があります。 オブジェクト`Close`は`CDatabase`破棄されないため、同じデータ ソースまたは別のデータ ソースへの新しい接続を開いてオブジェクトを再利用できます。

データベースを`AddNew`使用`Edit`しているレコードセットの保留中またはステートメントはすべて取り消され、保留中のすべてのトランザクションがロールバックされます。 `CDatabase`オブジェクトに依存するレコードセットは未定義の状態のままになります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#12](../../mfc/codesnippet/cpp/cdatabase-class_3.cpp)]

## <a name="cdatabasecommittrans"></a><a name="committrans"></a>データベース::コミットトランス

トランザクションの完了時にこのメンバー関数を呼び出します。

```
BOOL CommitTrans();
```

### <a name="return-value"></a>戻り値

更新が正常にコミットされた場合は 0 以外の値を返します。それ以外の場合は 0。 失敗`CommitTrans`した場合、データ ソースの状態は未定義です。 データをチェックして、その状態を確認する必要があります。

### <a name="remarks"></a>解説

トランザクションは`AddNew`[、BeginTrans](#begintrans)メンバー関数の呼び`Edit`出`Delete`し`Update`で始まる`CRecordset`オブジェクトの 、 、 、 、 のメンバー関数に対する一連の呼び出しで構成されます。 `CommitTrans`トランザクションをコミットします。 既定では、更新は直ちにコミットされます。呼`BeginTrans`び出しは、更新のコミットメント`CommitTrans`が呼び出されるまで遅延します。

トランザクションを終了`CommitTrans`するために呼び出すまで[、Rollback](#rollback)メンバー関数を呼び出してトランザクションを中止し、データ ソースを元の状態のままにすることができます。 新しいトランザクションを開始するには、`BeginTrans`もう一度呼び出します。

トランザクションの詳細については、「[トランザクション (ODBC) 」](../../data/odbc/transaction-odbc.md)を参照してください。

### <a name="example"></a>例

  「[トランザクション: レコードセットでのトランザクションの実行 (ODBC)」](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)を参照してください。

## <a name="cdatabaseexecutesql"></a><a name="executesql"></a>SQL を実行します。

SQL コマンドを直接実行する必要がある場合に、このメンバー関数を呼び出します。

```cpp
void ExecuteSQL(LPCTSTR lpszSQL);
```

### <a name="parameters"></a>パラメーター

*Lpszsql*<br/>
実行する有効な SQL コマンドを含む NULL で終わる文字列へのポインター。 [CString](../../atl-mfc-shared/reference/cstringt-class.md)を渡すことができます。

### <a name="remarks"></a>解説

コマンドを NULL で終わる文字列として作成します。 `ExecuteSQL`データ レコードを返しません。 レコードを操作する場合は、代わりにレコードセット オブジェクトを使用します。

データ ソースのコマンドのほとんどは、レコードセット オブジェクトを通じて発行され、データの選択、新しいレコードの挿入、レコードの削除、およびレコードの編集を行うためのコマンドをサポートします。 ただし、すべての ODBC 機能がデータベース クラスで直接サポートされているわけではないため、 を使用`ExecuteSQL`して SQL を直接呼び出す必要がある場合があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#13](../../mfc/codesnippet/cpp/cdatabase-class_4.cpp)]

## <a name="cdatabasegetbookmarkpersistence"></a><a name="getbookmarkpersistence"></a>を使用します。

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
|SQL_BP_CLOSE|ブックマークは操作後に`Requery`有効です。|
|SQL_BP_DELETE|行のブックマークは、その行に対`Delete`する操作の後で有効です。|
|SQL_BP_DROP|ブックマークは操作後に`Close`有効です。|
|SQL_BP_SCROLL|ブックマークは、操作の後`Move`に有効です。 これは、`CRecordset::CanBookmark` によって返されるのと同様に、レコードセットでブックマークがサポートされているかどうかだけを示します。|
|SQL_BP_TRANSACTION|トランザクションがコミットまたはロールバックされた後、ブックマークは有効です。|
|SQL_BP_UPDATE|行のブックマークは、その行に対`Update`する操作の後で有効です。|
|SQL_BP_OTHER_HSTMT|1 つのレコードセット オブジェクトに関連付けられたブックマークは、別のレコードセットで有効です。|

この戻り値の詳細については、Windows SDK の`SQLGetInfo`ODBC API 関数を参照してください。 ブックマークの詳細については、「[レコードセット: ブックマークと絶対位置 (ODBC)」](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)を参照してください。

## <a name="cdatabasegetconnect"></a><a name="getconnect"></a>データベース::ゲットコネクト

このメンバー関数を呼び出すことで、`OpenEx` オブジェクトをデータ ソースに接続した `Open` または `CDatabase` の呼び出し時に使用された接続文字列を取得します。

```
const CString GetConnect() const;
```

### <a name="return-value"></a>戻り値

呼び出`OpenEx`された場合`Open`は、接続文字列を含む**const**[CString。](../../atl-mfc-shared/reference/cstringt-class.md)それ以外の場合は空の文字列。

### <a name="remarks"></a>解説

接続文字列の作成方法については[、「CDatabase::Open」](#open)を参照してください。

## <a name="cdatabasegetcursorcommitbehavior"></a><a name="getcursorcommitbehavior"></a>を実行します。

このメンバー関数を呼び出して、開いているレコードセット オブジェクトのカーソルに対する[CommitTrans](#committrans)操作の影響を調べます。

```
int GetCursorCommitBehavior() const;
```

### <a name="return-value"></a>戻り値

開いているレコードセット オブジェクトに対するトランザクションの影響を示す値。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

次の表は、使用可能な戻り`GetCursorCommitBehavior`値と、開いているレコードセットに対する影響を示しています。

|戻り値|CRecordset オブジェクトに対する影響|
|------------------|----------------------------------|
|SQL_CB_CLOSE|トランザクション`CRecordset::Requery`のコミット直後に呼び出します。|
|SQL_CB_DELETE|トランザクション`CRecordset::Close`のコミット直後に呼び出します。|
|SQL_CB_PRESERVE|操作を通常どおり`CRecordset`行います。|

この戻り値の詳細については、Windows SDK の`SQLGetInfo`ODBC API 関数を参照してください。 トランザクションの詳細については、「[トランザクション (ODBC) 」](../../data/odbc/transaction-odbc.md)を参照してください。

## <a name="cdatabasegetcursorrollbackbehavior"></a><a name="getcursorrollbackbehavior"></a>振る舞い

このメンバー関数を呼び出して、開いているレコードセット オブジェクトのカーソルに[対するロールバック](#rollback)操作の影響を調べます。

```
int GetCursorRollbackBehavior() const;
```

### <a name="return-value"></a>戻り値

開いているレコードセット オブジェクトに対するトランザクションの影響を示す値。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

次の表は、使用可能な戻り`GetCursorRollbackBehavior`値と、開いているレコードセットに対する影響を示しています。

|戻り値|CRecordset オブジェクトに対する影響|
|------------------|----------------------------------|
|SQL_CB_CLOSE|トランザクション`CRecordset::Requery`のロールバック直後に呼び出します。|
|SQL_CB_DELETE|トランザクション`CRecordset::Close`のロールバック直後に呼び出します。|
|SQL_CB_PRESERVE|操作を通常どおり`CRecordset`行います。|

この戻り値の詳細については、Windows SDK の`SQLGetInfo`ODBC API 関数を参照してください。 トランザクションの詳細については、「[トランザクション (ODBC) 」](../../data/odbc/transaction-odbc.md)を参照してください。

## <a name="cdatabasegetdatabasename"></a><a name="getdatabasename"></a>データベース名を取得します。

現在接続されているデータベースの名前を取得します 。(データ ソースが "database" という名前のオブジェクトを定義している場合)。

```
CString GetDatabaseName() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、データベース名を含む[CString。](../../atl-mfc-shared/reference/cstringt-class.md)それ以外の場合`CString`は、空の .

### <a name="remarks"></a>解説

これは、`OpenEx`または`Open`呼び出しで指定されたデータ・ソース名 (DSN) とは同じではありません。 返`GetDatabaseName`される値は ODBC によって異なります。 一般に、データベースはテーブルの集合です。 このエンティティに名前がある場合は`GetDatabaseName`、それを返します。

たとえば、この名前を見出しに表示する場合があります。 ODBC から名前を取得中にエラーが発生した場合`GetDatabaseName`は、空`CString`の値を返します。

## <a name="cdatabaseisopen"></a><a name="isopen"></a>データベース::IsOpen

`CDatabase`オブジェクトが現在データ ソースに接続されているかどうかを調べます。

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>戻り値

オブジェクトが`CDatabase`現在接続されている場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="cdatabasem_hdbc"></a><a name="m_hdbc"></a>データベース::m_hdbc

ODBC データ ソース接続へのパブリック ハンドルを含みます。

### <a name="remarks"></a>解説

通常、このメンバー変数に直接アクセスする必要はありません。 代わりに、フレームワークは、 または`OpenEx``Open`を呼び出したときにハンドルを割り当てます。 オブジェクトの delete 演算子を呼び出すと、フレームワークはハンドルの割り当てを解除します。 **delete** `CDatabase` メンバー関数は`Close`ハンドルの割り当てを解除しません。

ただし、状況によっては、ハンドルを直接使用する必要があります。 たとえば、クラス`CDatabase`を介してではなく ODBC API 関数を直接呼び出す必要がある場合は、接続ハンドルをパラメーターとして渡す必要があります。 以下のコード例を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#15](../../mfc/codesnippet/cpp/cdatabase-class_5.cpp)]

## <a name="cdatabaseonsetoptions"></a><a name="onsetoptions"></a>::オンセットオプション

フレームワークは、メンバー関数を使用して SQL ステートメントを直接実行`ExecuteSQL`するときに、このメンバー関数を呼び出します。

```
virtual void OnSetOptions(HSTMT hstmt);
```

### <a name="parameters"></a>パラメーター

*hstmt*<br/>
オプションが設定されている ODBC ステートメント ハンドル。

### <a name="remarks"></a>解説

`CRecordset::OnSetOptions`また、このメンバー関数も呼び出します。

`OnSetOptions`ログイン タイムアウト値を設定します。 `SetQueryTimeout`以前に、 メンバー関数を呼び出した場合`OnSetOptions`は、現在の値を反映します。それ以外の場合は、既定値を設定します。

> [!NOTE]
> MFC 4.2 より`OnSetOptions`前のバージョンでは、処理モードを snychronous または非同期に設定します。 MFC 4.2 以降では、すべての操作は同期的です。 非同期操作を実行するには、ODBC API 関数`SQLSetPos`を直接呼び出す必要があります。

タイムアウト値を変更するためにオーバーライド`OnSetOptions`する必要はありません。 代わりに、クエリのタイムアウト値をカスタマイズするには`SetQueryTimeout`、レコードセットを作成する前に呼び出します。`OnSetOptions`新しい値を使用します。 設定された値は、すべてのレコードセットまたは直接 SQL 呼び出しに対する後続の演算に適用されます。

追加`OnSetOptions`オプションを設定する場合は、オーバーライドします。 オーバーライドは、ODBC API`OnSetOptions`関数`SQLSetStmtOption`を呼び出す前または後に基本クラスを呼び出す必要があります。 フレームワークの既定の実装で示されているメソッドに従ってください`OnSetOptions`。

## <a name="cdatabaseopen"></a><a name="open"></a>データベース::オープン

新しく構築`CDatabase`されたオブジェクトを初期化するには、このメンバー関数を呼び出します。

```
virtual BOOL Open(
    LPCTSTR lpszDSN,
    BOOL bExclusive = FALSE,
    BOOL bReadOnly = FALSE,
    LPCTSTR lpszConnect = _T("ODBC;"),
    BOOL bUseCursorLib = TRUE);
```

### <a name="parameters"></a>パラメーター

*を指定します。*<br/>
ODBC 管理ツールを使用して ODBC に登録されたデータ ソース名を指定します。 DSN 値が*lpszConnect*で指定されている場合 ("DSN=\<データ・ソース・>" という形式で) は *、lpszDSN*で再度指定してはなりません。 この場合 *、lpszDSN*は NULL にする必要があります。 それ以外の場合は、ユーザーがデータ ソースを選択できる [データ ソース] ダイアログ ボックスをユーザーに表示する場合は、NULL を渡すことができます。 詳細については、「解説」を参照してください。

*bエクスクルーシブ*<br/>
このバージョンのクラス ライブラリではサポートされていません。 現在、このパラメータが TRUE の場合、アサーションは失敗します。 データ ソースは常に共有として開かれます (排他的ではありません)。

*読み取り専用*<br/>
接続を読み取り専用にし、データ ソースへの更新を禁止する場合は TRUE。 すべての依存レコードセットはこの属性を継承します。 既定値は FALSE です。

*lpszConnect*<br/>
接続文字列を指定します。 接続文字列は、データ ソース名、データ ソースで有効なユーザー ID、ユーザー認証文字列 (データ ソースが必要な場合はパスワード) などの情報を連結します。 接続文字列全体の先頭には、"ODBC;" という文字列を付ける必要があります。(大文字または小文字)。 "ODBC;" 文字列は、ODBC データ ソースへの接続を示すために使用されます。これは、クラス ライブラリの将来のバージョンが ODBC 以外のデータ ソースをサポートする可能性がある場合の上位互換性を確保するためです。

*カーソルリブ*<br/>
ODBC カーソル ライブラリ DLL を読み込む場合は TRUE。 カーソル ライブラリは、基になる ODBC ドライバーの一部の機能をマスクし、ダイナセットの使用を効果的に防止します (ドライバーがサポートしている場合)。 カーソル ライブラリがロードされた場合にサポートされる唯一のカーソルは、静的スナップショットと前方専用カーソルです。 既定値は TRUE です。 レコードセット オブジェクトから派生`CRecordset`せずに直接からレコードセット オブジェクトを作成する場合は、カーソル ライブラリを読み込まないようにしてください。

### <a name="return-value"></a>戻り値

接続が正常に確立された場合は 0 以外の値を返します。それ以外の場合は、ユーザーが接続情報を要求するダイアログ ボックスが表示されたときに [キャンセル] を選択した場合は 0。 それ以外の場合は、フレームワークが例外をスローします。

### <a name="remarks"></a>解説

データベース オブジェクトを使用してレコードセット オブジェクトを構築する前に、データベース オブジェクトを初期化する必要があります。

> [!NOTE]
> [OpenEx](#openex)メンバー関数を呼び出すことは、データ ソースに接続してデータベース オブジェクトを初期化する場合に推奨される方法です。

`Open`呼び出しのパラメーターに接続を行うための十分な情報が含まれていない場合、ODBC ドライバーはダイアログ ボックスを開き、ユーザーから必要な情報を取得します。 を呼び`Open`出すと、接続文字列*lpszConnect*は`CDatabase`オブジェクト内にプライベートに格納され[、GetConnect](#getconnect)メンバー関数を呼び出して使用できます。

必要に応じて、ユーザーからパスワードなどの情報を取得するために呼`Open`び出す前に独自のダイアログ ボックスを開き、その情報を渡す接続文字列に`Open`追加できます。 また、渡した接続文字列を保存して、次回アプリケーションが`Open``CDatabase`オブジェクトを呼び出す際に再利用できるようにすることもできます。

また、接続文字列を使用して、複数レベルのログイン許可 (それぞれ別`CDatabase`のオブジェクト) を使用したり、他のデータ ソース固有の情報を伝達したりできます。 接続文字列の詳細については、Windows SDK の第 5 章を参照してください。

たとえば、DBMS ホストが使用できない場合などに、接続試行がタイムアウトになる可能性があります。 接続の試行が失敗した`Open`場合は、`CDBException`をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#14](../../mfc/codesnippet/cpp/cdatabase-class_6.cpp)]

## <a name="cdatabaseopenex"></a><a name="openex"></a>データベース::オープンエックス

新しく構築`CDatabase`されたオブジェクトを初期化するには、このメンバー関数を呼び出します。

```
virtual BOOL OpenEx(
    LPCTSTR lpszConnectString,
    DWORD dwOptions = 0);
```

### <a name="parameters"></a>パラメーター

*文字列*<br/>
ODBC 接続文字列を指定します。 これには、データ ソース名のほか、ユーザー ID やパスワードなどのオプション情報も含まれます。 たとえば、"DSN=SQLServer_Source;UID=SA;PWD=abc123" は、可能な接続文字列です。 *lpszConnectString*に NULL を渡すと、データ ソースを選択するように求めるダイアログ ボックスが表示されます。

*dw オプション*<br/>
次の値の組み合わせを指定するビットマスク。 既定値は 0 で、データベースは書き込みアクセスで共有として開かれ、ODBC カーソル ライブラリ DLL は読み込まれず、ODBC 接続ダイアログ ボックスは接続を行うだけの情報がない場合にのみ表示されます。

- `CDatabase::openExclusive`このバージョンのクラス ライブラリではサポートされていません。 データ ソースは常に共有として開かれます (排他的ではありません)。 現在、このオプションを指定するとアサーションは失敗します。

- `CDatabase::openReadOnly`データ ソースを読み取り専用で開きます。

- `CDatabase::useCursorLib`ODBC カーソル ライブラリ DLL を読み込みます。 カーソル ライブラリは、基になる ODBC ドライバーの一部の機能をマスクし、ダイナセットの使用を効果的に防止します (ドライバーがサポートしている場合)。 カーソル ライブラリがロードされた場合にサポートされる唯一のカーソルは、静的スナップショットと前方専用カーソルです。 レコードセット オブジェクトから派生`CRecordset`せずに直接からレコードセット オブジェクトを作成する場合は、カーソル ライブラリを読み込まないようにしてください。

- `CDatabase::noOdbcDialog`十分な接続情報が提供されているかどうかに関係なく、ODBC 接続ダイアログ ボックスを表示しません。

- `CDatabase::forceOdbcDialog`常に ODBC 接続ダイアログ ボックスを表示します。

### <a name="return-value"></a>戻り値

接続が正常に確立された場合は 0 以外の値を返します。それ以外の場合は、ユーザーが接続情報を要求するダイアログ ボックスが表示されたときに [キャンセル] を選択した場合は 0。 それ以外の場合は、フレームワークが例外をスローします。

### <a name="remarks"></a>解説

データベース オブジェクトを使用してレコードセット オブジェクトを構築する前に、データベース オブジェクトを初期化する必要があります。

`OpenEx`呼び出しの*lpszConnectString*パラメーターに接続を行うのに必要な情報が含まれていない場合は、odbc ドライバーがダイアログ ボックスを開き、dwOptions`CDatabase::noOdbcDialog`パラメーター`CDatabase::forceOdbcDialog`を設定*dwOptions*していない場合、ユーザーから必要な情報を取得します。 を呼び`OpenEx`出すと、接続文字列*lpszConnectString*は`CDatabase`オブジェクト内にプライベートに格納され[、GetConnect](#getconnect)メンバー関数を呼び出して使用できます。

必要に応じて、ユーザーからパスワードなどの情報を取得する前`OpenEx`に独自のダイアログ ボックスを開き、 に渡す接続文字列にその情報を`OpenEx`追加できます。 また、渡した接続文字列を保存して、次回アプリケーションが`OpenEx``CDatabase`オブジェクトを呼び出す際に再利用できるようにすることもできます。

また、接続文字列を使用して、複数レベルのログイン許可 (それぞれ別`CDatabase`のオブジェクト) を使用したり、他のデータ ソース固有の情報を伝達したりできます。 接続文字列の詳細については *、『ODBC プログラマ リファレンス*』の第 6 章を参照してください。

たとえば、DBMS ホストが使用できない場合などに、接続試行がタイムアウトになる可能性があります。 接続の試行が失敗した`OpenEx`場合は、`CDBException`をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#11](../../mfc/codesnippet/cpp/cdatabase-class_7.cpp)]

## <a name="cdatabaserollback"></a><a name="rollback"></a>データベース::ロールバック

トランザクション中に行われた変更を元に戻すには、このメンバー関数を呼び出します。

```
BOOL Rollback();
```

### <a name="return-value"></a>戻り値

トランザクションが正常に取り消された場合は 0 以外の値を返します。それ以外の場合は 0。 呼び`Rollback`出しが失敗した場合、データ ソースとトランザクションの状態は未定義になります。 0`Rollback`を返す場合は、データ ソースをチェックして、その状態を確認する必要があります。

### <a name="remarks"></a>解説

最後`CRecordset``AddNew`の`Edit` `Delete` `Update` [BeginTrans](#begintrans)以降に実行された呼び出し、、、および呼び出しは、その呼び出しの時点で存在した状態にロールバックされます。

に対する`Rollback`呼び出しが終了した後、もう一`BeginTrans`度別のトランザクションを呼び出す必要があります。 呼び出す`BeginTrans`前に現在のレコードが、 の後`Rollback`に再びカレント レコードになります。

ロールバック後、ロールバック前のカレントレコードは最新の状態を保つ。 ロールバック後のレコードセットとデータ ソースの状態の詳細については、「[トランザクション (ODBC) 」](../../data/odbc/transaction-odbc.md)を参照してください。

### <a name="example"></a>例

  「[トランザクション: レコードセットでのトランザクションの実行 (ODBC)」](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)を参照してください。

## <a name="cdatabasesetlogintimeout"></a><a name="setlogintimeout"></a>を設定します。

このメンバー関数を呼び出す`OpenEx` `Open` ( または ) を呼び出す前に、データ ソース接続がタイムアウトするまでの既定の秒数を上書きします。

```cpp
void SetLoginTimeout(DWORD dwSeconds);
```

### <a name="parameters"></a>パラメーター

*ドワー秒*<br/>
接続試行がタイムアウトするまでの秒数。

### <a name="remarks"></a>解説

たとえば、DBMS が使用できない場合、接続試行がタイムアウトになることがあります。 初期化`SetLoginTimeout``CDatabase`されていないオブジェクトを構築した後、または`OpenEx``Open`を呼び出す前に呼び出します。

ログイン タイムアウトのデフォルト値は 15 秒です。 すべてのデータ ソースが、ログイン タイムアウト値を指定する機能をサポートしているわけではありません。 データ ソースがタイムアウトをサポートしていない場合は、トレース出力を取得しますが、例外は取得しません。 値 0 は"無限" を意味します。

## <a name="cdatabasesetquerytimeout"></a><a name="setquerytimeout"></a>を使用します。

接続されているデータ ソースでの後続の操作がタイムアウトするまでに許容される既定の秒数をオーバーライドします。

```cpp
void SetQueryTimeout(DWORD dwSeconds);
```

### <a name="parameters"></a>パラメーター

*ドワー秒*<br/>
クエリがタイムアウトするまでの秒数。

### <a name="remarks"></a>解説

ネットワーク アクセスの問題、クエリ処理時間の過剰などにより、操作がタイムアウトすることがあります。 クエリ`SetQueryTimeout`のタイムアウト値を変更する場合は、レコードセットを開`AddNew`く`Update`前`Delete`、またはレコードセットの の 、またはメンバー関数を呼び出す前に呼び出します。 この設定は、この`Open`オブジェクト`AddNew`に`Update`関連付`Delete`けられているレコードセットに対する後続の`CDatabase`、、、、、、およびすべての呼び出しに影響します。 開いた後にレコードセットのクエリ タイムアウト値を変更しても、レコードセットの値は変更されません。 たとえば、後続`Move`の操作では新しい値は使用されません。

クエリ タイムアウトの既定値は 15 秒です。 すべてのデータ ソースが、クエリ のタイムアウト値を設定する機能をサポートしているわけではありません。 クエリのタイムアウト値を 0 に設定した場合、タイムアウトは発生しません。データ ソースとの通信が応答を停止する可能性があります。 この動作は、開発中に役立つ場合があります。 データ ソースがタイムアウトをサポートしていない場合は、トレース出力を取得しますが、例外は取得しません。

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/crecordset-class.md)
