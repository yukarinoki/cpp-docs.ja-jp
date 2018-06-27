---
title: CDatabase クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8f250ba7c2265f0fb3766a1c4ad0b65a0022f00a
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955636"
---
# <a name="cdatabase-class"></a>CDatabase クラス
データ ソースへの接続を表します。これを通じてデータ ソース上で操作を行うことができます。  
  
## <a name="syntax"></a>構文  
  
```  
class CDatabase : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDatabase::CDatabase](#cdatabase)|`CDatabase` オブジェクトを構築します。 呼び出して、オブジェクトを初期化する必要があります`OpenEx`または`Open`です。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDatabase::BeginTrans](#begintrans)|「トランザクション」を開始-一連の呼び出し元に戻すこと、 `AddNew`、 `Edit`、`Delete`と`Update`クラスのメンバー関数`CRecordset`: 接続されているデータ ソースにします。 データ ソースのトランザクションをサポートする必要があります`BeginTrans`影響がないようにします。|  
|[CDatabase::BindParameters](#bindparameters)|呼び出す前にパラメーターをバインドできるように`CDatabase::ExecuteSQL`です。|  
|[CDatabase::Cancel](#cancel)|非同期操作または 2 番目のスレッドからのプロセスをキャンセルします。|  
|[CDatabase::CanTransact](#cantransact)|データ ソースには、トランザクションがサポートしている場合は 0 以外を返します。|  
|[CDatabase::CanUpdate](#canupdate)|場合は 0 以外を返します、`CDatabase`オブジェクトが更新可能な (いない読み取り専用)。|  
|[CDatabase::Close](#close)|データ ソース接続を閉じます。|  
|[CDatabase::CommitTrans](#committrans)|によって開始されたトランザクションが完了した`BeginTrans`です。 データ ソースを変更するトランザクションにコマンドが実行されます。|  
|[:Executesql](#executesql)|SQL ステートメントを実行します。 データ レコードは返されません。|  
|[CDatabase::GetBookmarkPersistence](#getbookmarkpersistence)|レコード セット オブジェクトで使用されるブックマークを永続化操作を識別します。|  
|[CDatabase::GetConnect](#getconnect)|接続に使用する ODBC 接続文字列を返します、`CDatabase`データ ソースへのオブジェクト。|  
|[CDatabase::GetCursorCommitBehavior](#getcursorcommitbehavior)|開いているレコード セット オブジェクトで、トランザクションのコミットの効果を識別します。|  
|[CDatabase::GetCursorRollbackBehavior](#getcursorrollbackbehavior)|開いているレコード セット オブジェクトのトランザクションのロールバックの効果を識別します。|  
|[CDatabase::GetDatabaseName](#getdatabasename)|現在使用中、データベースの名前を返します。|  
|[CDatabase::IsOpen](#isopen)|場合は 0 以外を返します、`CDatabase`オブジェクトが現在データ ソースに接続されています。|  
|[CDatabase::OnSetOptions](#onsetoptions)|標準的な接続オプションを設定するためにフレームワークによって呼び出されます。 既定の実装では、クエリのタイムアウト値を設定します。 これらのオプションを前もってを確立するには呼び出すことによって`SetQueryTimeout`です。|  
|[Cdatabase::open](#open)|(Odbc) を介してデータ ソースへの接続を確立します。|  
|[Cdatabase::openex](#openex)|(Odbc) を介してデータ ソースへの接続を確立します。|  
|[CDatabase::Rollback](#rollback)|現在のトランザクションで行われた変更を反転させます。 定義されている以前の状態、データ ソースを返します、`BeginTrans`変更されない呼び出しです。|  
|[CDatabase::SetLoginTimeout](#setlogintimeout)|その後データ ソース接続の試行はタイムアウトの秒数を設定します。|  
|[CDatabase::SetQueryTimeout](#setquerytimeout)|セットがどのデータベース後の秒数のクエリ操作はタイムアウトします。後続のすべてのレコード セットの影響を与える`Open`、 `AddNew`、 `Edit`、および`Delete`呼び出しです。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDatabase::m_hdbc](#m_hdbc)|データ ソースへの open Database Connectivity (ODBC) 接続ハンドルです。 型**HDBC**です。|  
  
## <a name="remarks"></a>Remarks  
 データ ソースとは、いくつかのデータベース管理システム (DBMS) によってホストされているデータの特定のインスタンスです。 例としては、Microsoft SQL Server、Microsoft Access、Borland dBASE xBASE です。 1 つ以上を持つことができます`CDatabase`アプリケーションで一度にアクティブなオブジェクトです。  
  
> [!NOTE]
>  オープン データベース コネクティビティ (ODBC) クラスではなく、データ アクセス オブジェクト (DAO) クラスで作業している場合は、クラスを使用して[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)代わりにします。 詳細については、記事を参照してください。[概要: データベース プログラミング](../../data/data-access-programming-mfc-atl.md)です。  
  
 使用する`CDatabase`、構築、`CDatabase`オブジェクトと呼び出しの`OpenEx`メンバー関数。 これは、接続を開きます。 構築する際に`CRecordset`接続されているデータ ソースに対する操作のためのオブジェクトは、レコード セット コンス トラクターへのポインターを渡す、`CDatabase`オブジェクト。 接続を使用して完了したらを呼び出す、`Close`メンバー関数し、破棄、`CDatabase`オブジェクト。 `Close` 閉じられていないすべてのレコード セットを閉じます。  
  
 詳細については`CDatabase`、記事を参照して[データ ソース (ODBC)](../../data/odbc/data-source-odbc.md)と[概要: データベース プログラミング](../../data/data-access-programming-mfc-atl.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDatabase`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdb.h  
  
##  <a name="begintrans"></a>  CDatabase::BeginTrans  
 接続されたデータ ソースでトランザクションを開始するには、このメンバー関数を呼び出します。  
  
```  
BOOL BeginTrans();
```  
  
### <a name="return-value"></a>戻り値  
 変更をコミットするだけです。 手動で呼び出しが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 1 つまたは複数の呼び出しのトランザクションでは、 `AddNew`、 `Edit`、 `Delete`、および`Update`のメンバー関数、`CRecordset`オブジェクト。 トランザクションを開始する前に、`CDatabase`オブジェクト必要があります既にが接続されたデータ ソースへの呼び出しによってその`OpenEx`または`Open`メンバー関数。 トランザクションを終了するには、呼び出し[CommitTrans](#committrans)しを受け入れてデータ ソースに対するすべての変更 (実行して) を呼び出したり[ロールバック](#rollback)全体のトランザクションを中止します。 呼び出す`BeginTrans`後、トランザクションに関係するすべてのレコード セットを開くし、として、実際の更新操作。  
  
> [!CAUTION]
>  ODBC ドライバーによって呼び出す前にレコード セットを開く`BeginTrans`を呼び出すときに問題が発生する可能性があります`Rollback`です。 使用している特定のドライバーを確認する必要があります。 たとえば、Microsoft ODBC デスクトップ ドライバー パック 3.0 に含まれる Microsoft Access ドライバーを使用する場合は、開いているカーソルのある任意のデータベースでトランザクションを開始する必要がありますいない Jet データベース エンジンの要件を考慮する必要があります。 MFC データベース クラスで開いているカーソルは開いていることを意味`CRecordset`オブジェクト。 詳細については、次を参照してください。[テクニカル ノート 68](../../mfc/tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver.md)です。  
  
 `BeginTrans` 要求された同時実行とデータ ソースの機能によって、サーバーでデータ レコードをロックも可能性があります。 データのロックに関する情報を記事を参照してください。[レコード セット: レコードのロック (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)です。  
  
 ユーザー定義のトランザクションが、記事で説明した[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)です。  
  
 `BeginTrans` 一連のトランザクションをロールバックできる状態を確立する (反転)。 ロールバックの新しい状態を確立するために、現在のトランザクションをコミットし、呼び出す`BeginTrans`もう一度です。  
  
> [!CAUTION]
>  呼び出す`BeginTrans`呼び出さずにもう一度`CommitTrans`または`Rollback`エラーが発生します。  
  
 呼び出す、 [CanTransact](#cantransact)ドライバーが特定のデータベースのトランザクションをサポートしているかどうかを調べます。 呼び出す必要もあります[GetCursorCommitBehavior](#getcursorcommitbehavior)と[GetCursorRollbackBehavior](#getcursorrollbackbehavior)カーソル位置の保持のサポートの決定をします。  
  
 トランザクションの詳細については、記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)です。  
  
### <a name="example"></a>例  
  記事を参照して[トランザクション: レコード セット (ODBC) でのトランザクションを実行する](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)です。  
  
##  <a name="bindparameters"></a>  CDatabase::BindParameters  
 オーバーライド`BindParameters`を呼び出す前にパラメーターをバインドする必要がある場合[:executesql](#executesql)です。  
  
```  
virtual void BindParameters(HSTMT hstmt);
```  
  
### <a name="parameters"></a>パラメーター  
 `hstmt`  
 パラメーターをバインドする ODBC ステートメント ハンドルです。  
  
### <a name="remarks"></a>Remarks  
 この方法は、結果を必要としない場合に役立ちますストアド プロシージャから設定します。  
  
 オーバーライドの中で呼び出して`SQLBindParameters`および関連するパラメーターをバインドする ODBC 関数。 MFC は、呼び出しの前に上書きを呼び出して`ExecuteSQL`です。 呼び出す必要はありません`SQLPrepare`です。`ExecuteSQL`呼び出し`SQLExecDirect`を破棄し、 **hstmt**、これが一度だけ使用します。  
  
##  <a name="cancel"></a>  CDatabase::Cancel  
 データ ソースが実行中の非同期操作または 2 番目のスレッドからのプロセスのいずれかを取り消すことを要求するには、このメンバー関数を呼び出します。  
  
```  
void Cancel();
```  
  
### <a name="remarks"></a>Remarks  
 MFC ODBC クラスに非同期処理が使用できなくに注意してください。非同期操作を実行する ODBC API 関数を直接に呼び出す必要があります[SQLSetConnectOption](https://msdn.microsoft.com/library/ms713564.aspx)です。 詳細については、次を参照してください。[非同期実行](https://msdn.microsoft.com/library/ms713563.aspx)Windows SDK に含まれています。  
  
##  <a name="cantransact"></a>  CDatabase::CanTransact  
 データベースがトランザクションを許可するかどうかを決定するには、このメンバー関数を呼び出します。  
  
```  
BOOL CanTransact() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値を使用してこのレコード セット`CDatabase`オブジェクトは、トランザクションを許可する。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>Remarks  
 トランザクションの詳細については、記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)です。  
  
##  <a name="canupdate"></a>  CDatabase::CanUpdate  
 決定するには、このメンバー関数を呼び出すかどうか、`CDatabase`オブジェクトの更新が許可されます。  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、`CDatabase`オブジェクトにより、更新は、渡される 0 それ以外の場合、いずれかがあるかを示す**TRUE**で*bReadOnly*開いたときに、`CDatabase`オブジェクトまたはデータ ソース自体のことが読み取り専用です。 データ ソースは、ODBC API 関数への呼び出しは読み取り専用`SQLGetInfo`の**SQL_DATASOURCE_READ_ONLY** "y"を返します。  
  
### <a name="remarks"></a>Remarks  
 すべてのドライバーは、更新をサポートします。  
  
##  <a name="cdatabase"></a>  CDatabase::CDatabase  
 `CDatabase` オブジェクトを構築します。  
  
```  
CDatabase();
```  
  
### <a name="remarks"></a>Remarks  
 オブジェクトを構築するには、後に呼び出す必要があります、`OpenEx`または`Open`メンバー関数を指定したデータ ソースへの接続を確立します。  
  
 埋め込みにできると便利な場合があります、`CDatabase`ドキュメント クラスのオブジェクト。  
  
### <a name="example"></a>例  
 この例を使用して`CDatabase`で、 `CDocument`-クラスを派生します。  
  
 [!code-cpp[NVC_MFCDatabase#9](../../mfc/codesnippet/cpp/cdatabase-class_1.h)]  
  
 [!code-cpp[NVC_MFCDatabase#10](../../mfc/codesnippet/cpp/cdatabase-class_2.cpp)]  
  
##  <a name="close"></a>  CDatabase::Close  
 データ ソースから切断する場合は、このメンバー関数を呼び出します。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Remarks  
 関連付けられているすべてのレコード セットを閉じる必要があります、`CDatabase`オブジェクトのこのメンバー関数を呼び出す前にします。 `Close`を破棄しません、`CDatabase`オブジェクト、同じデータ ソースまたは別のデータ ソースへの新しい接続を開くことによって、オブジェクトを再利用できます。  
  
 保留中のすべて`AddNew`または`Edit`データベースを使用してレコード セットのステートメントはキャンセルされ、すべて保留中のトランザクションはロールバックされます。 すべてのレコード セットに依存する、`CDatabase`オブジェクトは、未定義の状態のままにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase#12](../../mfc/codesnippet/cpp/cdatabase-class_3.cpp)]  
  
##  <a name="committrans"></a>  CDatabase::CommitTrans  
 トランザクションを完了すると、このメンバー関数を呼び出します。  
  
```  
BOOL CommitTrans();
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、更新プログラムが正常にコミットされます。それ以外の場合 0 を返します。 場合`CommitTrans`失敗した場合、データ ソースの状態が定義されていません。 状態を決定するデータを確認する必要があります。  
  
### <a name="remarks"></a>Remarks  
 呼び出しの一連のトランザクションでは、 `AddNew`、 `Edit`、`Delete`と`Update`のメンバー関数、`CRecordset`への呼び出しで始まっているオブジェクト、 [BeginTrans](#begintrans)メンバー関数。 `CommitTrans` トランザクションをコミットします。 既定では、更新プログラムすぐにコミットされます。呼び出す`BeginTrans`時まで遅延する更新プログラムのコミットメントをにより`CommitTrans`と呼びます。  
  
 呼び出されるまで`CommitTrans`、トランザクションを終了するには、呼び出すことができます、[ロールバック](#rollback)メンバー関数、トランザクションを中止し、元の状態で、データ ソースのままにします。 新しいトランザクションを開始するには、呼び出す`BeginTrans`もう一度です。  
  
 トランザクションの詳細については、記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)です。  
  
### <a name="example"></a>例  
  記事を参照して[トランザクション: レコード セット (ODBC) でのトランザクションを実行する](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)です。  
  
##  <a name="executesql"></a>  :Executesql  
 SQL コマンドを直接実行する必要がある場合は、このメンバー関数を呼び出します。  
  
```  
void ExecuteSQL(LPCTSTR lpszSQL);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszSQL*  
 実行する有効な SQL コマンドを含む null で終わる文字列へのポインター。 渡すことができます、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)です。  
  
### <a name="remarks"></a>Remarks  
 Null で終わる文字列として、コマンドを作成します。 `ExecuteSQL` データ レコードは返しません。 レコードを操作する場合は、レコード セット オブジェクトを使用します。  
  
 ほとんどのデータ ソースのコマンドは、データを選択すると、新しいレコードの挿入、レコードを削除、およびレコードの編集のコマンドをサポートしているレコード セット オブジェクトを介して発行されます。 ただし、すべての ODBC の機能が直接サポート データベース クラスでため直接 SQL を使用して通話する必要がありますも`ExecuteSQL`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase#13](../../mfc/codesnippet/cpp/cdatabase-class_4.cpp)]  
  
##  <a name="getbookmarkpersistence"></a>  CDatabase::GetBookmarkPersistence  
 特定の操作の後で、レコードセット オブジェクトでのブックマークの永続性を判別するには、このメンバー関数を呼び出します。  
  
```  
DWORD GetBookmarkPersistence() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコードセット オブジェクトでブックマークが保持されている操作を識別するビットマスク。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>Remarks  
 たとえば、`CRecordset::GetBookmark` を呼び出してから `CRecordset::Requery` を呼び出した場合、`GetBookmark` から取得されたブックマークは有効ではなくなっている場合があります。 `GetBookmarkPersistence` を呼び出してから `CRecordset::SetBookmark` を呼び出す必要があります。  
  
 `GetBookmarkPersistence` の戻り値として組み合わせることができるビットマスク値の一覧を次の表に示します。  
  
|ビットマスク値|ブックマークの永続性|  
|-------------------|--------------------------|  
|`SQL_BP_CLOSE`|ブックマークが後に有効な`Requery`操作します。|  
|`SQL_BP_DELETE`|行のブックマークが後に有効では、`Delete`行に対して操作します。|  
|`SQL_BP_DROP`|ブックマークが後に有効な`Close`操作します。|  
|`SQL_BP_SCROLL`|いずれかの後、ブックマークは有効な`Move`操作します。 これは、`CRecordset::CanBookmark` によって返されるのと同様に、レコードセットでブックマークがサポートされているかどうかだけを示します。|  
|`SQL_BP_TRANSACTION`|トランザクションがコミットまたはロールバックされた後、ブックマークは有効です。|  
|`SQL_BP_UPDATE`|行のブックマークが後に有効では、`Update`行に対して操作します。|  
|`SQL_BP_OTHER_HSTMT`|1 つのレコードセット オブジェクトに関連付けられたブックマークは、別のレコードセットで有効です。|  
  
 この戻り値の詳細については、ODBC API 関数を参照してください。 `SQLGetInfo` Windows SDK に含まれています。 ブックマークの詳細については、記事を参照してください。[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)です。  
  
##  <a name="getconnect"></a>  CDatabase::GetConnect  
 このメンバー関数を呼び出すことで、`OpenEx` オブジェクトをデータ ソースに接続した `Open` または `CDatabase` の呼び出し時に使用された接続文字列を取得します。  
  
```  
const CString GetConnect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A **const**[CString](../../atl-mfc-shared/reference/cstringt-class.md)場合、接続文字列を含む`OpenEx`または`Open`と呼ばれる、それ以外のされましたが、空の文字列。  
  
### <a name="remarks"></a>Remarks  
 参照してください[cdatabase::open](#open)接続文字列を作成する方法の詳細についてはします。  
  
##  <a name="getcursorcommitbehavior"></a>  CDatabase::GetCursorCommitBehavior  
 決定するには、このメンバー関数を呼び出す方法、 [CommitTrans](#committrans)操作は、開いているレコード セット オブジェクトのカーソルに影響します。  
  
```  
int GetCursorCommitBehavior() const;  
```  
  
### <a name="return-value"></a>戻り値  
 開いているレコード セット オブジェクトでのトランザクションの効果を示す値。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>Remarks  
 次の表に、戻り値の`GetCursorCommitBehavior`と開いているレコード セットへの対応する影響します。  
  
|戻り値|CRecordset オブジェクトへの影響|  
|------------------|----------------------------------|  
|`SQL_CB_CLOSE`|呼び出す`CRecordset::Requery`トランザクションのコミットの直後です。|  
|`SQL_CB_DELETE`|呼び出す`CRecordset::Close`トランザクションのコミットの直後です。|  
|`SQL_CB_PRESERVE`|通常どおり続行`CRecordset`操作します。|  
  
 この戻り値の詳細については、ODBC API 関数を参照してください。 `SQLGetInfo` Windows SDK に含まれています。 トランザクションの詳細については、記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)です。  
  
##  <a name="getcursorrollbackbehavior"></a>  CDatabase::GetCursorRollbackBehavior  
 決定するには、このメンバー関数を呼び出す方法、[ロールバック](#rollback)操作は、開いているレコード セット オブジェクトのカーソルに影響します。  
  
```  
int GetCursorRollbackBehavior() const;  
```  
  
### <a name="return-value"></a>戻り値  
 開いているレコード セット オブジェクトでのトランザクションの効果を示す値。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>Remarks  
 次の表に、戻り値の`GetCursorRollbackBehavior`と開いているレコード セットへの対応する影響します。  
  
|戻り値|CRecordset オブジェクトへの影響|  
|------------------|----------------------------------|  
|`SQL_CB_CLOSE`|呼び出す`CRecordset::Requery`直後、トランザクションをロールバックします。|  
|`SQL_CB_DELETE`|呼び出す`CRecordset::Close`直後、トランザクションをロールバックします。|  
|`SQL_CB_PRESERVE`|通常どおり続行`CRecordset`操作します。|  
  
 この戻り値の詳細については、ODBC API 関数を参照してください。 `SQLGetInfo` Windows SDK に含まれています。 トランザクションの詳細については、記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)です。  
  
##  <a name="getdatabasename"></a>  CDatabase::GetDatabaseName  
 指定します (データ ソースには、「データベース」と呼ばれる名前付きオブジェクトを定義します)、現在接続しているデータベースの名前を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetDatabaseName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)それ以外の成功した場合は、データベース名を含む、空`CString`です。  
  
### <a name="remarks"></a>Remarks  
 これは、同じデータ ソース名 (DSN) で指定された、`OpenEx`または`Open`呼び出します。 どのような`GetDatabaseName`返しますは ODBC によって異なります。 一般に、データベースは、テーブルのコレクションです。 このエンティティの名前が`GetDatabaseName`オブジェクトを返します。  
  
 たとえば、見出しにこの名前を表示する可能性があります、します。 ODBC から名前を取得中にエラーが発生した場合`GetDatabaseName`空白を返します`CString`です。  
  
##  <a name="isopen"></a>  CDatabase::IsOpen  
 決定するには、このメンバー関数を呼び出すかどうか、`CDatabase`オブジェクトが現在データ ソースに接続されています。  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、`CDatabase`オブジェクトが現在接続されている場合は 0 です。  
  
##  <a name="m_hdbc"></a>  CDatabase::m_hdbc  
 ODBC データ ソース接続へのパブリック ハンドルが含まれています:「接続ハンドル」  
  
### <a name="remarks"></a>Remarks  
 通常ができなくなりますこのメンバー変数に直接アクセスする必要があります。 呼び出すときにフレームワークがハンドルを割り当てる代わりに、`OpenEx`または`Open`です。 呼び出すときにフレームワークがハンドルを解放、**削除**演算子で、`CDatabase`オブジェクト。 なお、`Close`メンバー関数は、ハンドルを解放できません。  
  
 状況によっては、ただし、する必要があります、ハンドルを直接使用します。 クラスではなく、直接、ODBC API 関数を呼び出す必要がある場合など、 `CDatabase`、接続ハンドルをパラメーターとして渡す必要がある可能性があります。 次のコード例を参照してください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase#15](../../mfc/codesnippet/cpp/cdatabase-class_5.cpp)]  
  
##  <a name="onsetoptions"></a>  CDatabase::OnSetOptions  
 直接 SQL ステートメントを実行するときに、フレームワークがこのメンバー関数を呼び出す、`ExecuteSQL`メンバー関数。  
  
```  
virtual void OnSetOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>パラメーター  
 *hstmt*  
 オプションが設定される ODBC ステートメント ハンドルです。  
  
### <a name="remarks"></a>Remarks  
 `CRecordset::OnSetOptions` このメンバー関数も呼び出します。  
  
 `OnSetOptions` ログイン タイムアウト値を設定します。 以前の呼び出しがあった場合、`SetQueryTimeout`とメンバー関数、 `OnSetOptions` ; の現在の値を反映してそれ以外の場合、既定値を設定します。  
  
> [!NOTE]
>  MFC 4.2 の前に`OnSetOptions`もどちら snychronous または非同期処理モードを設定します。 MFC 4.2 以降では、すべての操作は同期的です。 非同期操作を実行する ODBC API 関数への直接呼び出しを行う必要があります`SQLSetPos`です。  
  
 オーバーライドする必要はありません`OnSetOptions`タイムアウト値を変更します。 クエリのタイムアウト値をカスタマイズする代わりに、 `SetQueryTimeout` ; のレコード セットを作成する前に`OnSetOptions`新しい値が使用されます。 値の設定は、すべてのレコード セットまたは SQL の直接の呼び出しの後続の処理に適用されます。  
  
 オーバーライド`OnSetOptions`追加オプションを設定する場合。 上書きは基本クラスを呼び出す必要があります`OnSetOptions`前に、または後に、ODBC API 関数を呼び出す`SQLSetStmtOption`です。 フレームワークの既定の実装で示されているメソッドに従う`OnSetOptions`です。  
  
##  <a name="open"></a>  Cdatabase::open  
 新しく構築された初期化するためにこのメンバー関数を呼び出す`CDatabase`オブジェクト。  
  
```  
virtual BOOL Open(
    LPCTSTR lpszDSN,  
    BOOL bExclusive = FALSE,  
    BOOL bReadOnly = FALSE,  
    LPCTSTR lpszConnect = _T("ODBC;"),  
    BOOL bUseCursorLib = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszDSN*  
 データ ソース名を指定します: ODBC 管理者プログラムを通じて ODBC で名前が登録されています。 DSN の値がで指定されている場合*lpszConnect* (フォームに"DSN =\<データ ソース >") で再度指定してはなりませんが*lpszDSN*です。 この場合、 *lpszDSN*する必要があります**NULL**です。 それ以外の場合に渡すことができます**NULL**ユーザーがデータ ソースを選択できるデータ ソース ダイアログ ボックスをユーザーに表示するかどうか。 詳細については、「解説」を参照してください。  
  
 *bExclusive*  
 クラス ライブラリのこのバージョンではサポートされていません。 このパラメーターは場合、アサーションは現時点では、失敗**TRUE**です。 共有 (排他的ではない) で、データ ソースが常に開かれます。  
  
 *bReadOnly*  
 **TRUE**読み取り専用にして、データ ソースへの更新を禁止する、接続する場合。 依存するすべてのレコード セットは、この属性を継承します。 既定値は**FALSE**です。  
  
 *lpszConnect*  
 接続文字列を指定します。 接続文字列では、データ ソース名、データ ソース、ユーザー認証の文字列 (パスワード、データ ソースでは、いずれかが必要な場合)、およびその他の情報に有効なユーザー ID を含む可能性のある情報を連結します。 接続文字列全体を文字列"ODBC"です。 によってプレフィックス指定する必要があります。(大文字または小文字)。 "ODBC"です文字列を使用して、接続が、ODBC データ ソースにすることを示します。これは、非 ODBC データ ソースをサポートするクラス ライブラリの将来のバージョンと上位互換性のためです。  
  
 *データ*  
 **TRUE**する場合は、ODBC カーソル ライブラリ DLL に読み込む。 カーソル ライブラリでは、基になる、ODBC ドライバー (ドライバーには、それらがサポートされている) 場合は、ダイナセットを使う場合の使用を効果的に回避の一部の機能をマスクします。 カーソル ライブラリが読み込まれている場合はサポートされてのみカーソルは、静的スナップショットと順方向専用カーソルです。 既定値は**TRUE**です。 直接からレコード セット オブジェクトを作成する予定のかどうか`CRecordset`から派生するがない場合は、カーソル ライブラリいない読み込ま必要があります。  
  
### <a name="return-value"></a>戻り値  
 接続が正常に行われた; 場合は 0 以外。それ以外の場合の詳細な接続情報を求めるダイアログ ボックスが表示されたら、ユーザーが選択した場合は 0 を取り消します。 その他のすべてのケースでは、フレームワークは、例外をスローします。  
  
### <a name="remarks"></a>Remarks  
 レコード セット オブジェクトを構築するために使用する前に、データベース オブジェクトを初期化する必要があります。  
  
> [!NOTE]
>  呼び出す、 [OpenEx](#openex)メンバー関数は、データ ソースに接続し、データベース オブジェクトを初期化することをお勧めします。  
  
 場合のパラメーター、`Open`呼び出しは、接続を作成するための十分な情報を含まない、ODBC ドライバーは、ユーザーから、必要な情報を取得するダイアログ ボックスを開きます。 呼び出すと`Open`、接続文字列*lpszConnect*、非公開で格納されている、`CDatabase`オブジェクトを呼び出すことによって利用可能なは、 [GetConnect](#getconnect)メンバー関数。  
  
 呼び出す前に、独自のダイアログ ボックスを開くことができる場合は、`Open`パスワードなど、ユーザーから情報を取得し、その情報、接続文字列を追加に渡す`Open`です。 アプリケーションの呼び出しと時間を節約できます再利用できるように、次を指定した接続文字列にすることがありますまたは`Open`上、`CDatabase`オブジェクト。  
  
 複数レベルのログインの権限の接続文字列を使用することもできます (それぞれ異なるを`CDatabase`オブジェクト) またはその他のデータ ソースに固有の情報を伝達します。 接続文字列の詳細については、Windows SDK の第 5 章を参照してください。  
  
 たとえば、DBMS ホストが使用できない場合は、接続試行がタイムアウトする可能性はします。 接続の試行が失敗した場合、`Open`スロー、`CDBException`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase#14](../../mfc/codesnippet/cpp/cdatabase-class_6.cpp)]  
  
##  <a name="openex"></a>  Cdatabase::openex  
 新しく構築された初期化するためにこのメンバー関数を呼び出す`CDatabase`オブジェクト。  
  
```  
virtual BOOL OpenEx(
    LPCTSTR lpszConnectString,  
    DWORD dwOptions = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszConnectString*  
 ODBC 接続文字列を指定します。 これには、データ ソース名だけでなく、ユーザー ID やパスワードなどの省略可能なその他の情報が含まれます。 たとえば、"DSN = SQLServer_Source です。UID = SA;PWD = abc123"有効な接続文字列です。 渡す場合**NULL**の*lpszConnectString*、データ ソース ダイアログ ボックスは、ユーザーがデータ ソースを選択を求められます。  
  
 *dwOptions*  
 次の値の組み合わせを指定するビットマスク。 既定値は 0、書き込みアクセス権と共有するには、ODBC カーソル ライブラリ DLL は読み込まれず、として、データベースをオープンするはことを意味、接続を確立するための十分な情報がない場合にのみ、ODBC の接続 ダイアログ ボックスが表示されます。  
  
- **CDatabase::openExclusive**クラス ライブラリのこのバージョンでサポートされていません。 共有 (排他的ではない) で、データ ソースが常に開かれます。 現時点では、このオプションを指定する場合、アサーションが失敗します。  
  
- **CDatabase::openReadOnly**読み取り専用とデータ ソースを開きます。  
  
- **読み込む**ODBC カーソル ライブラリ DLL を読み込めません。 カーソル ライブラリでは、基になる、ODBC ドライバー (ドライバーには、それらがサポートされている) 場合は、ダイナセットを使う場合の使用を効果的に回避の一部の機能をマスクします。 カーソル ライブラリが読み込まれている場合はサポートされてのみカーソルは、静的スナップショットと順方向専用カーソルです。 直接からレコード セット オブジェクトを作成する予定のかどうか`CRecordset`から派生するがない場合は、カーソル ライブラリいない読み込ま必要があります。  
  
- **CDatabase::noOdbcDialog**十分な接続情報が提供されるかどうかに関係なく、ODBC の接続 ダイアログ ボックスは表示されません。  
  
- **CDatabase::forceOdbcDialog**常に、ODBC 接続 ダイアログ ボックスを表示します。  
  
### <a name="return-value"></a>戻り値  
 接続が正常に行われた; 場合は 0 以外。それ以外の場合の詳細な接続情報を求めるダイアログ ボックスが表示されたら、ユーザーが選択した場合は 0 を取り消します。 その他のすべてのケースでは、フレームワークは、例外をスローします。  
  
### <a name="remarks"></a>Remarks  
 レコード セット オブジェクトを構築するために使用する前に、データベース オブジェクトを初期化する必要があります。  
  
 場合、 *lpszConnectString*内のパラメーター、`OpenEx`呼び出しに接続するために十分な情報が含まれていない場合、されませんが、ODBC ドライバーは、ユーザーから、必要な情報を取得するダイアログ ボックスを開きます設定**CDatabase::noOdbcDialog**または**CDatabase::forceOdbcDialog**で、 *dwOptions*パラメーター。 呼び出すと`OpenEx`、接続文字列*lpszConnectString*、非公開で格納されている、`CDatabase`オブジェクトを呼び出すことによって利用可能なは、 [GetConnect](#getconnect)メンバー関数。  
  
 呼び出す前に、独自のダイアログ ボックスを開くことができる場合は、`OpenEx`パスワードなど、ユーザーから情報を取得しに渡す接続文字列にその情報を追加する`OpenEx`です。 アプリケーションの呼び出しと時間を節約できます再利用できるように、次を指定した接続文字列にすることがありますまたは`OpenEx`上、`CDatabase`オブジェクト。  
  
 複数レベルのログインの権限の接続文字列を使用することもできます (それぞれ異なるを`CDatabase`オブジェクト) またはその他のデータ ソースに固有の情報を伝達します。 接続文字列の詳細についてで第 6 章を参照してください、 *ODBC プログラマ リファレンス*です。  
  
 たとえば、DBMS ホストが使用できない場合は、接続試行がタイムアウトする可能性はします。 接続の試行が失敗した場合、`OpenEx`スロー、`CDBException`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase#11](../../mfc/codesnippet/cpp/cdatabase-class_7.cpp)]  
  
##  <a name="rollback"></a>  CDatabase::Rollback  
 このメンバー関数をトランザクション中に行われた変更を逆に呼び出します。  
  
```  
BOOL Rollback();
```  
  
### <a name="return-value"></a>戻り値  
 トランザクションが正常に取り消された; 場合は 0 以外。それ以外の場合 0 を返します。 場合、`Rollback`呼び出しが失敗した、データ ソースとトランザクションの状態が定義されていません。 場合`Rollback`0 を返しますの状態を決定するデータ ソースを確認する必要があります。  
  
### <a name="remarks"></a>Remarks  
 すべて`CRecordset` `AddNew`、 `Edit`、 `Delete`、および`Update`、最後に実行されるコール[BeginTrans](#begintrans)呼び出しの時点に存在していた状態にロールバックされます。  
  
 呼び出しの後に`Rollback`、トランザクションと、呼び出す必要があります`BeginTrans`別のトランザクション用にもう一度です。 呼び出した前に、の現在のレコード`BeginTrans`レコードになり、現在もう一度後`Rollback`です。  
  
 ロールバック後、ロールバック前に、の現在のレコードのままです。 レコード セットとロールバック後、データ ソースの状態に関する詳細については、記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)です。  
  
### <a name="example"></a>例  
  記事を参照して[トランザクション: レコード セット (ODBC) でのトランザクションを実行する](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)です。  
  
##  <a name="setlogintimeout"></a>  CDatabase::SetLoginTimeout  
 このメンバー関数を呼び出す — を呼び出す前に`OpenEx`または`Open`— ソース接続がタイムアウトを実行しようとしたデータまでに許容される秒数の既定をオーバーライドします。  
  
```  
void SetLoginTimeout(DWORD dwSeconds);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwSeconds*  
 接続を試行するまでに許可する秒数がタイムアウトになりました。  
  
### <a name="remarks"></a>Remarks  
 接続の試行には、たとえば、DBMS が利用できない場合は、タイムアウトが可能性があります。 呼び出す`SetLoginTimeout`、初期化されていない構成した後`CDatabase`オブジェクトが、前に呼び出す`OpenEx`または`Open`です。  
  
 ログイン タイムアウトの既定値は、15 秒です。 すべてのデータ ソースは、ログイン タイムアウト値を指定する機能をサポートします。 データ ソースがタイムアウトをサポートしていない場合は、トレース出力でもない例外を取得します。 値が 0 の場合「無期限」です。  
  
##  <a name="setquerytimeout"></a>  CDatabase::SetQueryTimeout  
 既定の接続されているデータ ソースのタイムアウトの後続の処理になるまでの秒数をオーバーライドする場合は、このメンバー関数を呼び出します。  
  
```  
void SetQueryTimeout(DWORD dwSeconds);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwSeconds*  
 クエリ試行するまでに許可する秒数がタイムアウトになりました。  
  
### <a name="remarks"></a>Remarks  
 操作は、ネットワーク アクセスの問題、過剰なクエリ処理時間などによりタイムアウト可能性があります。 呼び出す`SetQueryTimeout`またはレコード セットの前に、レコード セットを開く前に`AddNew`、`Update`または`Delete`メンバー関数をクエリのタイムアウト値を変更する場合。 この設定は後続のすべての適用`Open`、 `AddNew`、 `Update`、および`Delete`これに関連付けられているすべてのレコード セットへの呼び出し`CDatabase`オブジェクト。 かっこの後、レコード セットのクエリ タイムアウト値を変更しても、レコード セットの値は変わりません。 例については、後続`Move`操作は、新しい値を使用しないでください。  
  
 クエリのタイムアウトの既定値は、15 秒です。 すべてのデータ ソースは、クエリのタイムアウト値を設定する機能をサポートします。 0 の場合のクエリ タイムアウト値を設定すると、タイムアウトが発生しなかった場合データ ソースとの通信が応答を停止します。 この動作は、開発時に役立ちます。 データ ソースがタイムアウトをサポートしていない場合は、トレース出力でもない例外を取得します。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRecordset クラス](../../mfc/reference/crecordset-class.md)
