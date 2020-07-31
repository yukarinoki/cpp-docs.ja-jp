---
title: CRecordset クラス
ms.date: 11/04/2016
f1_keywords:
- CRecordset
- AFXDB/CRecordset
- AFXDB/CRecordset::CRecordset
- AFXDB/CRecordset::AddNew
- AFXDB/CRecordset::CanAppend
- AFXDB/CRecordset::CanBookmark
- AFXDB/CRecordset::Cancel
- AFXDB/CRecordset::CancelUpdate
- AFXDB/CRecordset::CanRestart
- AFXDB/CRecordset::CanScroll
- AFXDB/CRecordset::CanTransact
- AFXDB/CRecordset::CanUpdate
- AFXDB/CRecordset::CheckRowsetError
- AFXDB/CRecordset::Close
- AFXDB/CRecordset::Delete
- AFXDB/CRecordset::DoBulkFieldExchange
- AFXDB/CRecordset::DoFieldExchange
- AFXDB/CRecordset::Edit
- AFXDB/CRecordset::FlushResultSet
- AFXDB/CRecordset::GetBookmark
- AFXDB/CRecordset::GetDefaultConnect
- AFXDB/CRecordset::GetDefaultSQL
- AFXDB/CRecordset::GetFieldValue
- AFXDB/CRecordset::GetODBCFieldCount
- AFXDB/CRecordset::GetODBCFieldInfo
- AFXDB/CRecordset::GetRecordCount
- AFXDB/CRecordset::GetRowsetSize
- AFXDB/CRecordset::GetRowsFetched
- AFXDB/CRecordset::GetRowStatus
- AFXDB/CRecordset::GetSQL
- AFXDB/CRecordset::GetStatus
- AFXDB/CRecordset::GetTableName
- AFXDB/CRecordset::IsBOF
- AFXDB/CRecordset::IsDeleted
- AFXDB/CRecordset::IsEOF
- AFXDB/CRecordset::IsFieldDirty
- AFXDB/CRecordset::IsFieldNull
- AFXDB/CRecordset::IsFieldNullable
- AFXDB/CRecordset::IsOpen
- AFXDB/CRecordset::Move
- AFXDB/CRecordset::MoveFirst
- AFXDB/CRecordset::MoveLast
- AFXDB/CRecordset::MoveNext
- AFXDB/CRecordset::MovePrev
- AFXDB/CRecordset::OnSetOptions
- AFXDB/CRecordset::OnSetUpdateOptions
- AFXDB/CRecordset::Open
- AFXDB/CRecordset::RefreshRowset
- AFXDB/CRecordset::Requery
- AFXDB/CRecordset::SetAbsolutePosition
- AFXDB/CRecordset::SetBookmark
- AFXDB/CRecordset::SetFieldDirty
- AFXDB/CRecordset::SetFieldNull
- AFXDB/CRecordset::SetLockingMode
- AFXDB/CRecordset::SetParamNull
- AFXDB/CRecordset::SetRowsetCursorPosition
- AFXDB/CRecordset::SetRowsetSize
- AFXDB/CRecordset::Update
- AFXDB/CRecordset::m_hstmt
- AFXDB/CRecordset::m_nFields
- AFXDB/CRecordset::m_nParams
- AFXDB/CRecordset::m_pDatabase
- AFXDB/CRecordset::m_strFilter
- AFXDB/CRecordset::m_strSort
helpviewer_keywords:
- CRecordset [MFC], CRecordset
- CRecordset [MFC], AddNew
- CRecordset [MFC], CanAppend
- CRecordset [MFC], CanBookmark
- CRecordset [MFC], Cancel
- CRecordset [MFC], CancelUpdate
- CRecordset [MFC], CanRestart
- CRecordset [MFC], CanScroll
- CRecordset [MFC], CanTransact
- CRecordset [MFC], CanUpdate
- CRecordset [MFC], CheckRowsetError
- CRecordset [MFC], Close
- CRecordset [MFC], Delete
- CRecordset [MFC], DoBulkFieldExchange
- CRecordset [MFC], DoFieldExchange
- CRecordset [MFC], Edit
- CRecordset [MFC], FlushResultSet
- CRecordset [MFC], GetBookmark
- CRecordset [MFC], GetDefaultConnect
- CRecordset [MFC], GetDefaultSQL
- CRecordset [MFC], GetFieldValue
- CRecordset [MFC], GetODBCFieldCount
- CRecordset [MFC], GetODBCFieldInfo
- CRecordset [MFC], GetRecordCount
- CRecordset [MFC], GetRowsetSize
- CRecordset [MFC], GetRowsFetched
- CRecordset [MFC], GetRowStatus
- CRecordset [MFC], GetSQL
- CRecordset [MFC], GetStatus
- CRecordset [MFC], GetTableName
- CRecordset [MFC], IsBOF
- CRecordset [MFC], IsDeleted
- CRecordset [MFC], IsEOF
- CRecordset [MFC], IsFieldDirty
- CRecordset [MFC], IsFieldNull
- CRecordset [MFC], IsFieldNullable
- CRecordset [MFC], IsOpen
- CRecordset [MFC], Move
- CRecordset [MFC], MoveFirst
- CRecordset [MFC], MoveLast
- CRecordset [MFC], MoveNext
- CRecordset [MFC], MovePrev
- CRecordset [MFC], OnSetOptions
- CRecordset [MFC], OnSetUpdateOptions
- CRecordset [MFC], Open
- CRecordset [MFC], RefreshRowset
- CRecordset [MFC], Requery
- CRecordset [MFC], SetAbsolutePosition
- CRecordset [MFC], SetBookmark
- CRecordset [MFC], SetFieldDirty
- CRecordset [MFC], SetFieldNull
- CRecordset [MFC], SetLockingMode
- CRecordset [MFC], SetParamNull
- CRecordset [MFC], SetRowsetCursorPosition
- CRecordset [MFC], SetRowsetSize
- CRecordset [MFC], Update
- CRecordset [MFC], m_hstmt
- CRecordset [MFC], m_nFields
- CRecordset [MFC], m_nParams
- CRecordset [MFC], m_pDatabase
- CRecordset [MFC], m_strFilter
- CRecordset [MFC], m_strSort
ms.assetid: dd89a21d-ef39-4aab-891b-1e373d67c855
ms.openlocfilehash: d00764205b3b81e9f01dbe53d0c67372ebb2532e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219626"
---
# <a name="crecordset-class"></a>CRecordset クラス

データ ソースから選択された 1 組のレコードセットを表現します。

## <a name="syntax"></a>構文

```
class CRecordset : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CRecordset:: CRecordset](#crecordset)|`CRecordset` オブジェクトを構築します。 派生クラスは、このクラスを呼び出すコンストラクターを提供する必要があります。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CRecordset:: AddNew](#addnew)|新しいレコードを追加するための準備をします。 `Update`を呼び出して、追加を完了します。|
|[CRecordset:: CanAppend](#canappend)|メンバー関数を使用してレコードセットに新しいレコードを追加できる場合は、0以外の値を返し `AddNew` ます。|
|[CRecordset:: CanBookmark](#canbookmark)|レコードセットがブックマークをサポートしている場合は0以外の値を返します。|
|[CRecordset:: Cancel](#cancel)|2番目のスレッドから非同期操作またはプロセスをキャンセルします。|
|[CRecordset:: CancelUpdate](#cancelupdate)|または操作によって保留中の更新をキャンセル `AddNew` `Edit` します。|
|[CRecordset:: CanRestart](#canrestart)|`Requery`レコードセットのクエリを再実行するためにを呼び出すことができる場合は、0以外の値を返します。|
|[CRecordset:: CanScroll](#canscroll)|レコードをスクロールできる場合は0以外の値を返します。|
|[CRecordset:: CanTransact](#cantransact)|データソースがトランザクションをサポートしている場合は0以外の値を返します。|
|[CRecordset:: CanUpdate](#canupdate)|レコードセットを更新できる場合は0以外の値を返します (レコードを追加、更新、または削除できます)。|
|[CRecordset:: CheckRowsetError](#checkrowseterror)|レコードのフェッチ中に生成されたエラーを処理するために呼び出されます。|
|[CRecordset:: Close](#close)|レコードセットと、それに関連付けられている ODBC HSTMT を閉じます。|
|[CRecordset::D e)](#delete)|レコードセットから現在のレコードを削除します。 削除後は、明示的に別のレコードにスクロールする必要があります。|
|[CRecordset::D oBulkFieldExchange](#dobulkfieldexchange)|データソースからレコードセットにデータの一括行を交換するために呼び出されます。 バルクレコードフィールドエクスチェンジ (Bulk RFX) を実装します。|
|[CRecordset::D oFieldExchange](#dofieldexchange)|レコードセットのフィールドデータメンバーとデータソースの対応するレコードとの間で、双方向のデータ交換を行うために呼び出されます。 レコードフィールドエクスチェンジ (RFX) を実装します。|
|[CRecordset:: Edit](#edit)|現在のレコードへの変更を準備します。 `Update`を呼び出して、編集を完了します。|
|[CRecordset:: FlushResultSet](#flushresultset)|定義済みのクエリを使用する場合、別の結果セットが取得されると、0以外の値を返します。|
|[CRecordset:: GetBookmark](#getbookmark)|レコードのブックマーク値をパラメーターオブジェクトに割り当てます。|
|[CRecordset:: GetDefaultConnect](#getdefaultconnect)|既定の接続文字列を取得するために呼び出されます。|
|[CRecordset:: GetDefaultSQL](#getdefaultsql)|実行する既定の SQL 文字列を取得するために呼び出されます。|
|[CRecordset:: GetFieldValue](#getfieldvalue)|レコードセット内のフィールドの値を返します。|
|[CRecordset:: GetODBCFieldCount](#getodbcfieldcount)|レコードセット内のフィールドの数を返します。|
|[CRecordset:: GetODBCFieldInfo](#getodbcfieldinfo)|レコードセット内のフィールドに関する特定の種類の情報を返します。|
|[CRecordset:: GetRecordCount](#getrecordcount)|レコードセット内のレコードの数を返します。|
|[CRecordset:: GetRowsetSize](#getrowsetsize)|1回のフェッチ中に取得するレコードの数を返します。|
|[CRecordset:: GetRowsFetched](#getrowsfetched)|フェッチ中に取得された実際の行数を返します。|
|[CRecordset:: GetRowStatus](#getrowstatus)|フェッチ後の行の状態を返します。|
|[CRecordset:: GetSQL](#getsql)|レコードセットのレコードを選択するために使用する SQL 文字列を取得します。|
|[CRecordset:: GetStatus](#getstatus)|レコードセットの状態を取得します。現在のレコードのインデックスと、レコードの最終カウントが取得されたかどうかを取得します。|
|[CRecordset:: GetTableName](#gettablename)|レコードセットの基になるテーブルの名前を取得します。|
|[CRecordset:: IsBOF](#isbof)|レコードセットが最初のレコードの前に配置されている場合は、0以外の値を返します。 現在のレコードが存在しません。|
|[CRecordset:: IsDeleted](#isdeleted)|レコードセットが削除されたレコードに配置されている場合は、0以外の値を返します。|
|[CRecordset:: IsEOF](#iseof)|レコードセットが最後のレコードの後に配置されている場合は0以外の値を返します。 現在のレコードが存在しません。|
|[CRecordset:: IsFieldDirty](#isfielddirty)|現在のレコード内の指定されたフィールドが変更されている場合は、0以外の値を返します。|
|[CRecordset:: IsFieldNull](#isfieldnull)|現在のレコード内の指定されたフィールドが null (値がない) の場合は、0以外の値を返します。|
|[CRecordset:: IsFieldNullable](#isfieldnullable)|現在のレコード内の指定されたフィールドを null に設定できる場合 (値がない場合) は0以外の値を返します。|
|[CRecordset:: IsOpen](#isopen)|`Open`が以前に呼び出されている場合は、0以外の値を返します。|
|[CRecordset:: Move](#move)|現在のレコードから指定された数のレコードに、いずれかの方向でレコードセットを配置します。|
|[CRecordset:: MoveFirst](#movefirst)|レコードセット内の最初のレコードに現在のレコードを配置します。 最初にテスト `IsBOF` します。|
|[CRecordset:: MoveLast](#movelast)|最後のレコードまたは最後の行セットの現在のレコードを配置します。 最初にテスト `IsEOF` します。|
|[CRecordset:: MoveNext](#movenext)|現在のレコードを次のレコードまたは次の行セットに配置します。 最初にテスト `IsEOF` します。|
|[CRecordset:: MovePrev](#moveprev)|前のレコードまたは前の行セットの現在のレコードを配置します。 最初にテスト `IsBOF` します。|
|[CRecordset:: OnSetOptions](#onsetoptions)|指定された ODBC ステートメントのオプション (選択時に使用される) を設定するために呼び出されます。|
|[CRecordset:: OnSetUpdateOptions](#onsetupdateoptions)|指定された ODBC ステートメントに対してオプション (update で使用) を設定するために呼び出されます。|
|[CRecordset:: Open](#open)|テーブルを取得するか、レコードセットが表すクエリを実行して、レコードセットを開きます。|
|[CRecordset:: RefreshRowset](#refreshrowset)|指定された行のデータと状態を更新します。|
|[CRecordset:: Requery](#requery)|レコードセットのクエリを再実行して、選択したレコードを更新します。|
|[CRecordset:: SetAbsolutePosition](#setabsoluteposition)|指定されたレコード番号に対応するレコードにレコードセットを配置します。|
|[CRecordset:: SetBookmark](#setbookmark)|ブックマークで指定されたレコードにレコードセットを配置します。|
|[CRecordset:: SetFieldDirty](#setfielddirty)|現在のレコード内の指定されたフィールドを変更済みとしてマークします。|
|[CRecordset:: SetFieldNull](#setfieldnull)|現在のレコード内の指定されたフィールドの値を null に設定します (値はありません)。|
|[CRecordset:: Setロックモード](#setlockingmode)|ロックモードを "オプティミスティック" ロック (既定値) または "ペシミスティック" ロックに設定します。 更新のためにレコードをロックする方法を指定します。|
|[CRecordset:: SetParamNull](#setparamnull)|指定されたパラメーターを null に設定します (値はありません)。|
|[CRecordset:: SetRowsetCursorPosition](#setrowsetcursorposition)|行セット内の指定された行にカーソルを移動します。|
|[CRecordset:: SetRowsetSize](#setrowsetsize)|フェッチ中に取得するレコードの数を指定します。|
|[CRecordset:: Update](#update)|`AddNew` `Edit` 新しいデータまたは編集されたデータをデータソースに保存することによって、操作または操作を完了します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CRecordset:: m_hstmt](#m_hstmt)|レコードセットの ODBC ステートメントハンドルを格納します。 「`HSTMT`」と入力します。|
|[CRecordset:: m_nFields](#m_nfields)|レコードセットのフィールドデータメンバーの数を格納します。 「`UINT`」と入力します。|
|[CRecordset:: m_nParams](#m_nparams)|レコードセット内のパラメーターデータメンバーの数を格納します。 「`UINT`」と入力します。|
|[CRecordset:: m_pDatabase](#m_pdatabase)|`CDatabase`レコードセットをデータソースに接続するために使用するオブジェクトへのポインターを格納します。|
|[CRecordset:: m_strFilter](#m_strfilter)|`CString`構造化照会言語 (SQL) 句を指定するを格納し `WHERE` ます。 特定の条件を満たすレコードのみを選択するためのフィルターとして使用されます。|
|[CRecordset:: m_strSort](#m_strsort)|`CString`SQL 句を指定するを格納し `ORDER BY` ます。 レコードの並べ替え方法を制御するために使用します。|

## <a name="remarks"></a><a name="remarks"></a> 解説

"レコードセット" と呼ば `CRecordset` れるオブジェクトは、通常、ダイナセットとスナップショットの2つの形式で使用されます。 ダイナセットは、他のユーザーが行ったデータの更新と同期したままになります。 スナップショットは、データの静的なビューです。 各フォームは、レコードセットを開いたときに固定されたレコードのセットを表しますが、ダイナセット内のレコードにスクロールすると、他のユーザーまたはアプリケーション内の他のレコードセットによってレコードに加えられた変更が反映されます。

> [!NOTE]
> Open Database Connectivity (ODBC) クラスではなく、データアクセスオブジェクト (DAO) クラスを使用している場合は、代わりにクラス[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)を使用します。 詳細については、記事「[概要: データベースプログラミング](../../data/data-access-programming-mfc-atl.md)」を参照してください。

いずれかの種類のレコードセットを操作するには、通常、からアプリケーション固有のレコードセットクラスを派生し `CRecordset` ます。 レコードセットデータソースからレコードを選択すると、次のことができます。

- レコードをスクロールします。

- レコードを更新し、ロックモードを指定します。

- レコードセットをフィルター処理して、データソースで使用できるレコードのうち、どれを選択するかを制限します。

- レコードセットを並べ替えます。

- レコードセットをパラメーター化して、実行時まで知られていない情報で選択をカスタマイズします。

クラスを使用するには、データベースを開き、オブジェクトへのポインターをコンストラクターに渡して、レコードセットオブジェクトを構築し `CDatabase` ます。 次に、レコードセットの `Open` メンバー関数を呼び出します。この関数では、オブジェクトがダイナセットであるかスナップショットであるかを指定できます。 を呼び出す `Open` と、データソースからデータが選択されます。 レコードセットオブジェクトを開いた後、そのメンバー関数とデータメンバーを使用して、レコードをスクロールして操作します。 使用できる操作は、オブジェクトがダイナセットまたはスナップショットのどちらであるか、更新可能か読み取り専用か (これは、Open Database Connectivity (ODBC) データソースの機能によって異なります)、および一括行フェッチを実装したかどうかによって異なります。 呼び出し以降に変更または追加された可能性があるレコードを更新するには `Open` 、オブジェクトの `Requery` メンバー関数を呼び出します。 オブジェクトのメンバー関数を呼び出して、 `Close` 終了時にオブジェクトを破棄します。

派生クラスでは、レコードフィールド `CRecordset` の読み取りと更新をサポートするために、レコードフィールドエクスチェンジ (RFX) またはバルクレコードフィールドエクスチェンジ (BULK RFX) が使用されます。

レコードセットとレコードフィールドエクスチェンジの詳細については、「[データベースプログラミング](../../data/data-access-programming-mfc-atl.md)、[レコードセット (odbc)](../../data/odbc/recordset-odbc.md)」、「レコード[セット: バルクデータフェッチ (odbc)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」、および「[レコードフィールドエクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)」を参照してください。 ダイナセットとスナップショットについては、「[ダイナセット](../../data/odbc/dynaset.md)と[スナップショット](../../data/odbc/snapshot.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CRecordset`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="crecordsetaddnew"></a><a name="addnew"></a>CRecordset:: AddNew

テーブルに新しいレコードを追加する準備をします。

```
virtual void AddNew();
```

### <a name="remarks"></a>解説

新しく追加されたレコードを表示するには、 [Requery](#requery)メンバー関数を呼び出す必要があります。 レコードのフィールドは、最初は Null になります。 (データベース用語では、Null は "値がない" ことを意味し、C++ では NULL とは異なります)。操作を完了するには、 [Update](#update)メンバー関数を呼び出す必要があります。 `Update`データソースへの変更を保存します。

> [!NOTE]
> バルク行フェッチを実装している場合は、を呼び出すことはできません `AddNew` 。 これにより、アサーションは失敗します。 クラスに `CRecordset` は、データの一括行を更新するためのメカニズムが用意されていませんが、ODBC API 関数を使用して独自の関数を記述することができ `SQLSetPos` ます。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

`AddNew`レコードセットのフィールドデータメンバーを使用して、新しい空のレコードを準備します。 を呼び出した後 `AddNew` 、レコードセットのフィールドデータメンバーに必要な値を設定します。 (この目的で[Edit](#edit)メンバー関数を呼び出す必要はありません。 `Edit` 既存のレコードに対してのみ使用してください。)後でを呼び出すと `Update` 、フィールドデータメンバーの変更された値がデータソースに保存されます。

> [!CAUTION]
> を呼び出す前に新しいレコードにスクロールする `Update` と、新しいレコードは失われ、警告は表示されません。

データソースでトランザクションがサポートされている場合は、 `AddNew` トランザクションの呼び出し部分を作成できます。 トランザクションの詳細については、「クラス[CDatabase](../../mfc/reference/cdatabase-class.md)」を参照してください。 を呼び出す前に、 [CDatabase:: BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans)を呼び出す必要があることに注意してください `AddNew` 。

> [!NOTE]
> ダイナセットの場合、最後のレコードとしてレコードセットに新しいレコードが追加されます。 追加されたレコードはスナップショットには追加されません。`Requery`レコードセットを更新するには、を呼び出す必要があります。

`AddNew`メンバー関数が呼び出されていないレコードセットに対してを呼び出すことはでき `Open` ません。 `CDBException` `AddNew` に追加できないレコードセットに対してを呼び出すと、がスローされます。 [CanAppend](#canappend)を呼び出すことで、レコードセットが更新可能かどうかを判断できます。

詳細については、「[レコードセット: レコード更新のしくみ (odbc)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)」、「レコード[セット: レコードの追加、更新、削除](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)(odbc)」、および「[トランザクション (odbc](../../data/odbc/transaction-odbc.md))」を参照してください。

### <a name="example"></a>例

「[トランザクション: レコードセットでのトランザクションの実行 (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)」を参照してください。

## <a name="crecordsetcanappend"></a><a name="canappend"></a>CRecordset:: CanAppend

以前に開いたレコードセットで、新しいレコードを追加できるかどうかを判断します。

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>戻り値

レコードセットで新しいレコードの追加が許可されている場合は0以外の。それ以外の場合は0です。 `CanAppend`レコードセットを読み取り専用として開いた場合、は0を返します。

## <a name="crecordsetcanbookmark"></a><a name="canbookmark"></a>CRecordset:: CanBookmark

レコードセットでブックマークを使用してレコードをマークできるかどうかを決定します。

```
BOOL CanBookmark() const;
```

### <a name="return-value"></a>戻り値

レコードセットがブックマークをサポートしている場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

この関数は、 `CRecordset::useBookmarks` [Open](#open)メンバー関数の*dwOptions*パラメーターのオプションに依存しません。 `CanBookmark`指定された ODBC ドライバーおよびカーソルの種類がブックマークをサポートするかどうかを示します。 `CRecordset::useBookmarks`サポートされている場合、ブックマークを使用できるようにするかどうかを示します。

> [!NOTE]
> ブックマークは、順方向専用のレコードセットではサポートされていません。

ブックマークとレコードセットナビゲーションの詳細については、「[レコードセット: ブックマークと絶対位置 (odbc)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) 」および「[レコードセット: スクロール (odbc)](../../data/odbc/recordset-scrolling-odbc.md)」を参照してください。

## <a name="crecordsetcancel"></a><a name="cancel"></a>CRecordset:: Cancel

データソースが処理中の非同期操作または2番目のスレッドからのプロセスのいずれかをキャンセルすることを要求します。

```cpp
void Cancel();
```

### <a name="remarks"></a>解説

MFC ODBC クラスで非同期処理が使用されなくなったことに注意してください。非同期操作を実行するには、ODBC API 関数を直接呼び出す必要があり `SQLSetConnectOption` ます。 詳細については、『 *ODBC SDK プログラマーズガイド』* の「非同期関数の実行」を参照してください。

## <a name="crecordsetcancelupdate"></a><a name="cancelupdate"></a>CRecordset:: CancelUpdate

[Update](#update)が呼び出される前に、[編集](#edit)または[AddNew](#addnew)操作によって発生した保留中の更新をキャンセルします。

```cpp
void CancelUpdate();
```

### <a name="remarks"></a>解説

> [!NOTE]
> このメンバー関数は、バルク行フェッチを使用しているレコードセットには適用されません。このようなレコードセットは、、、またはを呼び出すことができないため `Edit` `AddNew` `Update` です。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

自動ダーティフィールドチェックが有効になっている場合、で `CancelUpdate` は、メンバー変数が以前に存在していた値または呼び出された値に復元されます `Edit` `AddNew` 。それ以外の場合は、値の変更は保持されます。 既定では、レコードセットが開かれると、自動フィールドチェックが有効になります。 無効にするには、 `CRecordset::noDirtyFieldCheck` [Open](#open)メンバー関数の*dwOptions*パラメーターでを指定する必要があります。

データの更新の詳細については、「レコード[セット: レコードの追加、更新、および削除 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)」を参照してください。

## <a name="crecordsetcanrestart"></a><a name="canrestart"></a>CRecordset:: CanRestart

レコードセットで、メンバー関数を呼び出すことによってクエリを再起動できるかどうかを決定します (レコードを更新するため) `Requery` 。

```
BOOL CanRestart() const;
```

### <a name="return-value"></a>戻り値

Requery が許可される場合は0以外の。それ以外の場合は0です。

## <a name="crecordsetcanscroll"></a><a name="canscroll"></a>CRecordset:: CanScroll

レコードセットでスクロールが許可されているかどうかを判断します。

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>戻り値

レコードセットでスクロールが許可されている場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

スクロールの詳細については、「[レコードセット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)」を参照してください。

## <a name="crecordsetcantransact"></a><a name="cantransact"></a>CRecordset:: CanTransact

レコードセットでトランザクションが許可されるかどうかを判断します。

```
BOOL CanTransact() const;
```

### <a name="return-value"></a>戻り値

レコードセットでトランザクションが許可されている場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

詳細については、「[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)」を参照してください。

## <a name="crecordsetcanupdate"></a><a name="canupdate"></a>CRecordset:: CanUpdate

レコードセットを更新できるかどうかを決定します。

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>戻り値

レコードセットを更新できる場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

基になるデータソースが読み取り専用の場合、または `CRecordset::readOnly` レコードセットを開いたときに*dwOptions*パラメーターでを指定した場合は、レコードセットが読み取り専用になることがあります。

## <a name="crecordsetcheckrowseterror"></a><a name="checkrowseterror"></a>CRecordset:: CheckRowsetError

レコードのフェッチ中に生成されたエラーを処理するために呼び出されます。

```
virtual void CheckRowsetError(RETCODE nRetCode);
```

### <a name="parameters"></a>パラメーター

*nRetCode*<br/>
ODBC API 関数のリターンコード。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

この仮想メンバー関数は、レコードがフェッチされるときに発生するエラーを処理します。これは、バルク行フェッチ時に役立ちます。 をオーバーライドして `CheckRowsetError` 、独自のエラー処理を実装することもできます。

`CheckRowsetError`は `Open` 、、 `Requery` 、または任意の操作など、カーソルナビゲーション操作で自動的に呼び出され `Move` ます。 ODBC API 関数の戻り値が渡され `SQLExtendedFetch` ます。 次の表に、 *nRetCode*パラメーターの有効な値を示します。

|nRetCode|説明|
|--------------|-----------------|
|SQL_SUCCESS|関数は正常に完了しました。追加情報はありません。|
|SQL_SUCCESS_WITH_INFO|関数は正常に完了しました。致命的でないエラーが発生した可能性があります。 を呼び出すことによって、追加情報を取得でき `SQLError` ます。|
|SQL_NO_DATA_FOUND|結果セットのすべての行がフェッチされました。|
|SQL_ERROR|関数が失敗しました。 を呼び出すことによって、追加情報を取得でき `SQLError` ます。|
|SQL_INVALID_HANDLE|無効な環境ハンドル、接続ハンドル、またはステートメントハンドルが原因で関数が失敗しました。 これは、プログラミングエラーを示します。 から追加情報を入手することはできません `SQLError` 。|
|SQL_STILL_EXECUTING|非同期的に開始された関数はまだ実行されています。 既定では、MFC はこの値をに渡さないことに注意して `CheckRowsetError` ください。MFC は SQL_STILL_EXECUTING が `SQLExtendedFetch` 返されなくなるまで、を呼び出し続けます。|

の詳細については `SQLError` 、Windows SDK を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

## <a name="crecordsetclose"></a><a name="close"></a>CRecordset:: Close

レコードセットを閉じます。

```
virtual void Close();
```

### <a name="remarks"></a>解説

レコードセットに割り当てられたフレームワークの ODBC HSTMT とすべてのメモリの割り当てが解除されます。 通常、を呼び出した後 `Close` 、C++ レコードセットオブジェクトがで割り当てられている場合は、そのオブジェクトを削除し **`new`** ます。

を呼び出した後で、をもう一度呼び出すことができ `Open` `Close` ます。 これにより、レコードセットオブジェクトを再利用できます。 別の方法として、を呼び出すことも `Requery` できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#17](../../mfc/codesnippet/cpp/crecordset-class_1.cpp)]

## <a name="crecordsetcrecordset"></a><a name="crecordset"></a>CRecordset:: CRecordset

`CRecordset` オブジェクトを構築します。

```
CRecordset(CDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>パラメーター

*pDatabase*<br/>
オブジェクトへのポインター、 `CDatabase` または NULL 値が含まれています。 NULL ではなく、 `CDatabase` オブジェクトのメンバー関数が呼び出されていない場合は、それを `Open` データソースに接続するために、レコードセットは自身の呼び出し中にそのオブジェクトを開こうとし `Open` ます。 NULL を渡した場合、 `CDatabase` オブジェクトが構築され、ClassWizard でレコードセットクラスを派生させるときに指定したデータソース情報を使用して接続されます。

### <a name="remarks"></a>解説

を直接使用することも、 `CRecordset` からアプリケーション固有のクラスを派生させることもでき `CRecordset` ます。 ClassWizard を使用して、レコードセットクラスを派生させることができます。

> [!NOTE]
> 派生クラスは、独自のコンストラクターを提供*する必要があり*ます。 派生クラスのコンストラクターで、コンストラクターを呼び出し `CRecordset::CRecordset` 、適切なパラメーターを渡します。

`CDatabase`オブジェクトを自動的に作成して接続するには、レコードセットコンストラクターに NULL を渡します。 これは、 `CDatabase` レコードセットを構築する前にオブジェクトを構築して接続する必要のない短縮形です。

### <a name="example"></a>例

詳細については、「[レコードセット: テーブルのクラスの宣言 (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)」を参照してください。

## <a name="crecordsetdelete"></a><a name="delete"></a>CRecordset::D e)

現在のレコードを削除します。

```
virtual void Delete();
```

### <a name="remarks"></a>解説

削除が正常に完了すると、レコードセットのフィールドデータメンバーが Null 値に設定され、削除されたレコードから移動するために、関数のいずれかを明示的に呼び出す必要があり `Move` ます。 削除されたレコードから移動すると、それに戻ることはできません。 データソースでトランザクションがサポートされている場合は、 `Delete` トランザクションの呼び出し部分を作成できます。 詳細については、「[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)」を参照してください。

> [!NOTE]
> バルク行フェッチを実装している場合は、を呼び出すことはできません `Delete` 。 これにより、アサーションは失敗します。 クラスに `CRecordset` は、データの一括行を更新するためのメカニズムが用意されていませんが、ODBC API 関数を使用して独自の関数を記述することができ `SQLSetPos` ます。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

> [!CAUTION]
> レコードセットは更新可能である必要があり、を呼び出すときにレコードセットの現在の有効なレコードが存在する必要があります。 `Delete` それ以外の場合は、エラーが発生します。 たとえば、を再度呼び出す前にレコードを削除しても、によって新しいレコードにスクロールしていない場合 `Delete` 、は `Delete` [CDBException](../../mfc/reference/cdbexception-class.md)をスローします。

[AddNew](#addnew)や[Edit](#edit)とは異なり、への呼び出しの `Delete` 後に[Update](#update)を呼び出すことはできません。 `Delete`呼び出しが失敗した場合、フィールドのデータメンバーは変更されません。

### <a name="example"></a>例

次の例では、関数のフレームに作成されたレコードセットを示します。 この例では `m_dbCust` 、型のメンバー変数が `CDatabase` 既にデータソースに接続されていることを前提としています。

[!code-cpp[NVC_MFCDatabase#18](../../mfc/codesnippet/cpp/crecordset-class_2.cpp)]

## <a name="crecordsetdobulkfieldexchange"></a><a name="dobulkfieldexchange"></a>CRecordset::D oBulkFieldExchange

データソースからレコードセットにデータの一括行を交換するために呼び出されます。 バルクレコードフィールドエクスチェンジ (Bulk RFX) を実装します。

```
virtual void DoBulkFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CFieldExchange](../../mfc/reference/cfieldexchange-class.md)オブジェクトへのポインター。 フレームワークでは、フィールド交換操作のコンテキストを指定するために、このオブジェクトが既に設定されています。

### <a name="remarks"></a>解説

バルク行フェッチが実装されている場合、フレームワークはこのメンバー関数を呼び出して、データソースからレコードセットオブジェクトにデータを自動的に転送します。 `DoBulkFieldExchange`また、パラメーターのデータメンバー (存在する場合) を、レコードセットの選択に使用する SQL ステートメント文字列のパラメータープレースホルダーにバインドします。

バルク行フェッチが実装されていない場合、フレームワークは[DoFieldExchange](#dofieldexchange)を呼び出します。 バルク行フェッチを実装するには、 `CRecordset::useMultiRowFetch` [Open](#open)メンバー関数で*dwOptions*パラメーターのオプションを指定する必要があります。

> [!NOTE]
> `DoBulkFieldExchange`は、から派生したクラスを使用している場合にのみ使用でき `CRecordset` ます。 から直接レコードセットオブジェクトを作成した場合は `CRecordset` 、 [GetFieldValue](#getfieldvalue)メンバー関数を呼び出してデータを取得する必要があります。

バルクレコードフィールドエクスチェンジ (Bulk RFX) は、レコードフィールドエクスチェンジ (RFX) に似ています。 データは、データソースからレコードセットオブジェクトに自動的に転送されます。 ただし、、、 `AddNew` `Edit` `Delete` 、またはを呼び出し `Update` て、変更をデータソースに戻すことはできません。 クラスに `CRecordset` は、現在、データの一括行を更新する機構が用意されていませんが、ODBC API 関数を使用して独自の関数を記述することはでき `SQLSetPos` ます。

ClassWizard では、一括レコードフィールドの交換がサポートされていないことに注意してください。そのため、 `DoBulkFieldExchange` BULK RFX 関数の呼び出しを作成して手動でオーバーライドする必要があります。 これらの関数の詳細については、「[レコードフィールドエクスチェンジ関数](../../mfc/reference/record-field-exchange-functions.md)」を参照してください。

バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。 関連情報については、「[レコードフィールドエクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)」を参照してください。

## <a name="crecordsetdofieldexchange"></a><a name="dofieldexchange"></a>CRecordset::D oFieldExchange

レコードセットのフィールドデータメンバーとデータソースの対応するレコードとの間で、双方向のデータ交換を行うために呼び出されます。 レコードフィールドエクスチェンジ (RFX) を実装します。

```
virtual void DoFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
[CFieldExchange](../../mfc/reference/cfieldexchange-class.md)オブジェクトへのポインター。 フレームワークでは、フィールド交換操作のコンテキストを指定するために、このオブジェクトが既に設定されています。

### <a name="remarks"></a>解説

バルク行フェッチが実装されていない場合、フレームワークはこのメンバー関数を呼び出して、レコードセットオブジェクトのフィールドデータメンバーと、データソースの現在のレコードの対応する列との間でデータを自動的に交換します。 `DoFieldExchange`また、パラメーターのデータメンバー (存在する場合) を、レコードセットの選択に使用する SQL ステートメント文字列のパラメータープレースホルダーにバインドします。

バルク行フェッチが実装されている場合、フレームワークは[DoBulkFieldExchange](#dobulkfieldexchange)を呼び出します。 バルク行フェッチを実装するには、 `CRecordset::useMultiRowFetch` [Open](#open)メンバー関数で*dwOptions*パラメーターのオプションを指定する必要があります。

> [!NOTE]
> `DoFieldExchange`は、から派生したクラスを使用している場合にのみ使用でき `CRecordset` ます。 から直接レコードセットオブジェクトを作成した場合は `CRecordset` 、 [GetFieldValue](#getfieldvalue)メンバー関数を呼び出してデータを取得する必要があります。

レコードフィールドエクスチェンジ (RFX) と呼ばれるフィールドデータの交換は、レコードセットオブジェクトのフィールドデータメンバーからデータソース上のレコードのフィールドへの変換と、データソースのレコードからレコードセットオブジェクトへの双方向で機能します。

派生レコードセットクラスのを実装するために通常必要な操作は、 `DoFieldExchange` ClassWizard でクラスを作成し、フィールドデータメンバーの名前とデータ型を指定することだけです。 パラメーターデータメンバーを指定したり、動的にバインドする列を処理したりするために、ClassWizard が書き込むコードを追加することもできます。 詳細については、「[レコードセット: 動的にデータ列をバインドする (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)」を参照してください。

ClassWizard で派生したレコードセットクラスを宣言すると、次の例に示すように、ウィザードによってのオーバーライドが書き込まれ `DoFieldExchange` ます。

[!code-cpp[NVC_MFCDatabase#19](../../mfc/codesnippet/cpp/crecordset-class_3.cpp)]

RFX 関数の詳細については、「[レコードフィールドエクスチェンジ関数](../../mfc/reference/record-field-exchange-functions.md)」を参照してください。

の詳細な例と詳細については `DoFieldExchange` 、「[レコードフィールドエクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。 RFX に関する一般的な情報については、「[レコードフィールドエクスチェンジ](../../data/odbc/record-field-exchange-rfx.md)」を参照してください。

## <a name="crecordsetedit"></a><a name="edit"></a>CRecordset:: Edit

現在のレコードを変更できるようにします。

```
virtual void Edit();
```

### <a name="remarks"></a>解説

を呼び出した後 `Edit` 、フィールドのデータメンバーを変更するには、その値を直接リセットします。 この操作は、後で[Update](#update)メンバー関数を呼び出して、変更内容をデータソースに保存すると完了します。

> [!NOTE]
> バルク行フェッチを実装している場合は、を呼び出すことはできません `Edit` 。 これにより、アサーションは失敗します。 クラスに `CRecordset` は、データの一括行を更新するためのメカニズムが用意されていませんが、ODBC API 関数を使用して独自の関数を記述することができ `SQLSetPos` ます。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

`Edit`レコードセットのデータメンバーの値を保存します。 を呼び出し、 `Edit` 変更を行ってからを `Edit` 再度呼び出すと、レコードの値は最初の呼び出しの前の値に復元され `Edit` ます。

場合によっては、Null (データを含まない) によって列を更新することが必要になることがあります。 これを行うには、パラメーターを TRUE に設定して[SetFieldNull](#setfieldnull)を呼び出し、フィールドを Null に設定します。これにより、列も更新されます。 値が変更されていない場合でも、データソースにフィールドを書き出す場合は、パラメーターを TRUE に設定して[SetFieldDirty](#setfielddirty)を呼び出します。 これは、フィールドの値が Null の場合でも機能します。

データソースでトランザクションがサポートされている場合は、 `Edit` トランザクションの呼び出し部分を作成できます。 レコードセットが開かれた後、およびを呼び出す前に、 [CDatabase:: BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans)を呼び出す必要があることに注意してください `Edit` 。 また、 [CDatabase:: CommitTrans](../../mfc/reference/cdatabase-class.md#committrans)の呼び出しは `Update` 、操作を完了するためにを呼び出すための代替ではないことにも注意してください。 `Edit` トランザクションの詳細については、「クラス[CDatabase](../../mfc/reference/cdatabase-class.md)」を参照してください。

現在のロックモードによっては、を呼び出すか別のレコードまでスクロールするまで、更新されるレコードがロックされる `Edit` `Update` か、呼び出し中にのみロックされることがあり `Edit` ます。 [Setロッキングモード](#setlockingmode)でロックモードを変更できます。

を呼び出す前に新しいレコードにスクロールすると、現在のレコードの前の値が復元され `Update` ます。 `CDBException` `Edit` 更新できないレコードセットに対してを呼び出した場合、または現在のレコードが存在しない場合は、がスローされます。

詳細については、記事「[トランザクション (odbc)](../../data/odbc/transaction-odbc.md) 」および「[レコードセット: レコードのロック (odbc)](../../data/odbc/recordset-locking-records-odbc.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#20](../../mfc/codesnippet/cpp/crecordset-class_4.cpp)]

## <a name="crecordsetflushresultset"></a><a name="flushresultset"></a>CRecordset:: FlushResultSet

複数の結果セットがある場合は、定義済みクエリ (ストアドプロシージャ) の次の結果セットを取得します。

```
BOOL FlushResultSet();
```

### <a name="return-value"></a>戻り値

取得する結果セットの数が多い場合は0以外。それ以外の場合は0です。

### <a name="remarks"></a>解説

`FlushResultSet`現在の結果セットでカーソルが完全に終了している場合にのみ、を呼び出す必要があります。 を呼び出して次の結果セットを取得すると `FlushResultSet` 、その結果セットでカーソルが有効にならないことに注意してください。を呼び出した後、 [MoveNext](#movenext)メンバー関数を呼び出す必要があり `FlushResultSet` ます。

定義済みのクエリで出力パラメーターまたは入出力パラメーターを使用する場合、 `FlushResultSet` `FALSE` これらのパラメーター値を取得するには、(値 0) を返すまでを呼び出す必要があります。

`FlushResultSet`ODBC API 関数を呼び出し `SQLMoreResults` ます。 が `SQLMoreResults` SQL_ERROR または SQL_INVALID_HANDLE を返した場合、は `FlushResultSet` 例外をスローします。 の詳細については `SQLMoreResults` 、Windows SDK を参照してください。

を呼び出す場合は、ストアドプロシージャにバインドされたフィールドが必要 `FlushResultSet` です。

### <a name="example"></a>例

次のコードで `COutParamRecordset` は、が、 `CRecordset` 入力パラメーターと出力パラメーターを使用し、複数の結果セットを持つ定義済みのクエリに基づいて、が派生するオブジェクトであることを前提としています。 [DoFieldExchange](#dofieldexchange)オーバーライドの構造を確認します。

[!code-cpp[NVC_MFCDatabase#21](../../mfc/codesnippet/cpp/crecordset-class_5.cpp)]

[!code-cpp[NVC_MFCDatabase#22](../../mfc/codesnippet/cpp/crecordset-class_6.cpp)]

## <a name="crecordsetgetbookmark"></a><a name="getbookmark"></a>CRecordset:: GetBookmark

現在のレコードのブックマーク値を取得します。

```cpp
void GetBookmark(CDBVariant& varBookmark);
```

### <a name="parameters"></a>パラメーター

*varBookmark*<br/>
現在のレコードのブックマークを表す[CDBVariant](../../mfc/reference/cdbvariant-class.md)オブジェクトへの参照。

### <a name="remarks"></a>解説

レコードセットでブックマークがサポートされているかどうかを判断するには、 [Canbookmark](#canbookmark)を呼び出します。 サポートされている場合にブックマークを使用できるようにするには、 `CRecordset::useBookmarks` [Open](#open)メンバー関数の*dwOptions*パラメーターでオプションを設定する必要があります。

> [!NOTE]
> ブックマークがサポートされていないか使用できない場合、を呼び出す `GetBookmark` と例外がスローされます。 ブックマークは、順方向専用のレコードセットではサポートされていません。

`GetBookmark`現在のレコードのブックマークの値をオブジェクトに割り当て `CDBVariant` ます。 別のレコードに移動した後、いつでもそのレコードに戻るには、対応するオブジェクトを使用して[SetBookmark](#setbookmark)を呼び出し `CDBVariant` ます。

> [!NOTE]
> 特定のレコードセット操作の後、ブックマークが無効になることがあります。 たとえば、を呼び出した後でを呼び出すと、 `GetBookmark` `Requery` でレコードに戻ることができなくなる可能性があり `SetBookmark` ます。 を安全に呼び出すことができるかどうかを確認するには、 [CDatabase:: GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence)を呼び出し `SetBookmark` ます。

ブックマークとレコードセットナビゲーションの詳細については、「[レコードセット: ブックマークと絶対位置 (odbc)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) 」および「[レコードセット: スクロール (odbc)](../../data/odbc/recordset-scrolling-odbc.md)」を参照してください。

## <a name="crecordsetgetdefaultconnect"></a><a name="getdefaultconnect"></a>CRecordset:: GetDefaultConnect

既定の接続文字列を取得するために呼び出されます。

```
virtual CString GetDefaultConnect();
```

### <a name="return-value"></a>戻り値

`CString`既定の接続文字列を格納している。

### <a name="remarks"></a>解説

フレームワークは、このメンバー関数を呼び出して、レコードセットの基になるデータソースの既定の接続文字列を取得します。 ClassWizard では、テーブルと列に関する情報を取得するために、ClassWizard で使用するのと同じデータソースを識別することで、この関数を実装しています。 アプリケーションの開発中にこの既定の接続を利用すると便利な場合があります。 ただし、既定の接続は、アプリケーションのユーザーには適していない場合があります。 その場合は、ClassWizard のバージョンを破棄して、この関数を再実装する必要があります。 接続文字列の詳細については、「[データソース (ODBC)](../../data/odbc/data-source-odbc.md)」を参照してください。

## <a name="crecordsetgetdefaultsql"></a><a name="getdefaultsql"></a>CRecordset:: GetDefaultSQL

実行する既定の SQL 文字列を取得するために呼び出されます。

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>戻り値

`CString`既定の SQL ステートメントを含むです。

### <a name="remarks"></a>解説

フレームワークは、このメンバー関数を呼び出して、レコードセットの基になる既定の SQL ステートメントを取得します。 テーブル名または SQL **SELECT**ステートメントを指定できます。

ClassWizard でレコードセットクラスを宣言することで、既定の SQL ステートメントを間接的に定義すると、ClassWizard がこのタスクを実行します。

使用する SQL ステートメント文字列が必要な場合は `GetSQL` 、を呼び出します。これにより、レコードセットのレコードを開いたときに選択するために使用される sql ステートメントが返されます。 クラスのオーバーライドで、既定の SQL 文字列を編集でき `GetDefaultSQL` ます。 たとえば、 **call**ステートメントを使用して、事前定義されたクエリの呼び出しを指定できます。 ただし、を編集する場合は、 `GetDefaultSQL` `m_nFields` データソース内の列の数と一致するようにを変更する必要もあります。

詳細については、「[レコードセット: テーブルのクラスの宣言 (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)」を参照してください。

> [!CAUTION]
> フレームワークがテーブル名を識別できなかった場合、複数のテーブル名が指定された場合、または**CALL**ステートメントを解釈できなかった場合、テーブル名は空になります。 **Call**ステートメントを使用する場合は、中かっこと**call**キーワードの間に空白を挿入しないでください。また、 **select**ステートメントの中かっこの前、または**select**キーワードの前に空白を挿入することもできません。

## <a name="crecordsetgetfieldvalue"></a><a name="getfieldvalue"></a>CRecordset:: GetFieldValue

現在のレコード内のフィールドデータを取得します。

```cpp
void GetFieldValue(
    LPCTSTR lpszName,
    CDBVariant& varValue,
    short nFieldType = DEFAULT_FIELD_TYPE);

void GetFieldValue(
    short nIndex,
    CDBVariant& varValue,
    short nFieldType = DEFAULT_FIELD_TYPE);

void GetFieldValue(
    short nIndex,
    CStringA& strValue);

void GetFieldValue(
    short nIndex,
    CStringW& strValue);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
フィールドの名前。

*varValu*e フィールドの値を格納する[CDBVariant](../../mfc/reference/cdbvariant-class.md)オブジェクトへの参照。

*nFieldType*<br/>
フィールドの ODBC C データ型。 DEFAULT_FIELD_TYPE 既定値を使用すると、は `GetFieldValue` 次の表に基づいて、SQL データ型の C データ型を強制的に決定します。 それ以外の場合は、データ型を直接指定するか、互換性のあるデータ型を選択することができます。たとえば、任意のデータ型を SQL_C_CHAR に格納できます。

|C データ型|SQL データ型|
|-----------------|-------------------|
|SQL_C_BIT|SQL_BIT|
|SQL_C_UTINYINT|SQL_TINYINT|
|SQL_C_SSHORT|SQL_SMALLINT|
|SQL_C_SLONG|SQL_INTEGER|
|SQL_C_FLOAT|SQL_REAL|
|SQL_C_DOUBLE|SQL_FLOATSQL_DOUBLE|
|SQL_C_TIMESTAMP|SQL_DATESQL_TIMESQL_TIMESTAMP|
|SQL_C_CHAR|SQL_NUMERICSQL_DECIMALSQL_BIGINTSQL_CHARSQL_VARCHARSQL_LONGVARCHAR|
|SQL_C_BINARY|SQL_BINARYSQL_VARBINARYSQL_LONGVARBINARY|

ODBC データ型の詳細については、Windows SDK の付録 D の「SQL データ型」および「C データ型」を参照してください。

*nIndex*<br/>
フィールドの0から始まるインデックス。

*strValue*<br/>
フィールドのデータ型に関係なく、テキストに変換されたフィールドの値を格納する[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトへの参照。

### <a name="remarks"></a>解説

名前またはインデックスを使用して、フィールドを検索できます。 フィールド値は、オブジェクトまたはオブジェクトのいずれかに格納でき `CDBVariant` `CString` ます。

バルク行フェッチを実装している場合、現在のレコードは常に行セットの最初のレコードに配置されます。 特定の `GetFieldValue` 行セット内のレコードでを使用するには、まず、 [SetRowsetCursorPosition](#setrowsetcursorposition)メンバー関数を呼び出して、その行セット内の目的の行にカーソルを移動する必要があります。 その `GetFieldValue` 行に対してを呼び出します。 バルク行フェッチを実装するには、 `CRecordset::useMultiRowFetch` [Open](#open)メンバー関数で*dwOptions*パラメーターのオプションを指定する必要があります。

を使用すると、 `GetFieldValue` デザイン時に静的にバインドするのではなく、実行時にフィールドを動的にフェッチできます。 たとえば、からレコードセットオブジェクトを直接宣言した場合は、を使用して `CRecordset` フィールドデータを取得する必要があります。 `GetFieldValue` レコードフィールドエクスチェンジ (RFX)、またはバルクレコードフィールドエクスチェンジ (bulk RFX) は実装されていません。

> [!NOTE]
> から派生せずにレコードセットオブジェクトを宣言する場合は、 `CRecordset` ODBC カーソルライブラリを読み込まないでください。 カーソルライブラリでは、レコードセットに少なくとも1つのバインドされた列が必要です。ただし、を直接使用する場合は、 `CRecordset` どの列もバインドされません。 メンバー関数[cdatabase:: OpenEx](../../mfc/reference/cdatabase-class.md#openex)および[CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open)は、カーソルライブラリが読み込まれるかどうかを制御します。

`GetFieldValue`ODBC API 関数を呼び出し `SQLGetData` ます。 ドライバーがフィールド値の実際の長さに SQL_NO_TOTAL 値を出力する場合、は `GetFieldValue` 例外をスローします。 の詳細については `SQLGetData` 、Windows SDK を参照してください。

### <a name="example"></a>例

次のサンプルコードは、 `GetFieldValue` から直接宣言されたレコードセットオブジェクトのへの呼び出しを示してい `CRecordset` ます。

[!code-cpp[NVC_MFCDatabase#23](../../mfc/codesnippet/cpp/crecordset-class_7.cpp)]

> [!NOTE]
> DAO クラスとは異なり `CDaoRecordset` 、に `CRecordset` はメンバー関数がありません `SetFieldValue` 。 オブジェクトをから直接作成した場合 `CRecordset` は、事実上読み取り専用になります。

バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

## <a name="crecordsetgetodbcfieldcount"></a><a name="getodbcfieldcount"></a>CRecordset:: GetODBCFieldCount

レコードセットオブジェクトのフィールドの合計数を取得します。

```
short GetODBCFieldCount() const;
```

### <a name="return-value"></a>戻り値

レコードセット内のフィールドの数。

### <a name="remarks"></a>解説

レコードセットの作成の詳細については、「[レコードセット: レコードセットの作成と終了 (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)」を参照してください。

## <a name="crecordsetgetodbcfieldinfo"></a><a name="getodbcfieldinfo"></a>CRecordset:: GetODBCFieldInfo

レコードセット内のフィールドに関する情報を取得します。

```cpp
void GetODBCFieldInfo(
    LPCTSTR lpszName,
    CODBCFieldInfo& fieldinfo);

void GetODBCFieldInfo(
    short nIndex,
    CODBCFieldInfo& fieldinfo);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
フィールドの名前。

*fieldinfo*<br/>
構造体への参照 `CODBCFieldInfo` 。

*nIndex*<br/>
フィールドの0から始まるインデックス。

### <a name="remarks"></a>解説

関数の1つのバージョンでは、名前でフィールドを検索できます。 もう1つのバージョンでは、インデックスを使用してフィールドを検索できます。

返される情報の説明については、 [Codbcfieldinfo](../../mfc/reference/codbcfieldinfo-structure.md)構造体を参照してください。

レコードセットの作成の詳細については、「[レコードセット: レコードセットの作成と終了 (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)」を参照してください。

## <a name="crecordsetgetrecordcount"></a><a name="getrecordcount"></a>CRecordset:: GetRecordCount

レコードセットのサイズを決定します。

```
long GetRecordCount() const;
```

### <a name="return-value"></a>戻り値

レコードセット内のレコードの数。レコードセットにレコードが含まれていない場合は0。レコード数を特定できない場合は-1。

### <a name="remarks"></a>解説

> [!CAUTION]
> レコード数は、ユーザーがレコードを移動したときに表示されている最も大きい番号のレコードである "high watermark" として維持されます。 レコードの合計数は、ユーザーが最後のレコードを超えた後にのみ認識されます。 パフォーマンス上の理由から、を呼び出してもカウントは更新されません `MoveLast` 。 レコードを自分でカウントするには、が `MoveNext` `IsEOF` 0 以外の値を返すまで繰り返しを呼び出します。 を使用してレコードを追加する `CRecordset:AddNew` と、 `Update` カウントが増加します。を使用してレコードを削除すると `CRecordset::Delete` 、カウントが減少します。

## <a name="crecordsetgetrowsetsize"></a><a name="getrowsetsize"></a>CRecordset:: GetRowsetSize

特定のフェッチ中に取得する行数の現在の設定を取得します。

```
DWORD GetRowsetSize() const;
```

### <a name="return-value"></a>戻り値

特定のフェッチ中に取得する行の数。

### <a name="remarks"></a>解説

バルク行フェッチを使用している場合、レコードセットを開いたときの既定の行セットサイズは25です。それ以外の場合は1になります。

バルク行フェッチを実装するには、 `CRecordset::useMultiRowFetch` [Open](#open)メンバー関数の*dwOptions*パラメーターでオプションを指定する必要があります。 行セットサイズの設定を変更するには、 [SetRowsetSize](#setrowsetsize)を呼び出します。

バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

## <a name="crecordsetgetrowsfetched"></a><a name="getrowsfetched"></a>CRecordset:: GetRowsFetched

フェッチ後に実際に取得されたレコードの数を決定します。

```
DWORD GetRowsFetched() const;
```

### <a name="return-value"></a>戻り値

特定のフェッチの後にデータソースから取得された行の数。

### <a name="remarks"></a>解説

これは、バルク行フェッチを実装している場合に便利です。 行セットのサイズは通常、フェッチから取得する行の数を示します。ただし、レコードセット内の行の合計数は、行セットで取得される行の数にも影響します。 たとえば、レコードセットの行セットサイズが4に設定されているレコードが10個ある場合、を呼び出してレコードセットをループ処理すると、 `MoveNext` 最終的な行セットには2つのレコードしか含まれません。

バルク行フェッチを実装するには、 `CRecordset::useMultiRowFetch` [Open](#open)メンバー関数の*dwOptions*パラメーターでオプションを指定する必要があります。 行セットのサイズを指定するには、 [SetRowsetSize](#setrowsetsize)を呼び出します。

バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#24](../../mfc/codesnippet/cpp/crecordset-class_8.cpp)]

## <a name="crecordsetgetrowstatus"></a><a name="getrowstatus"></a>CRecordset:: GetRowStatus

現在の行セットの行の状態を取得します。

```
WORD GetRowStatus(WORD wRow) const;
```

### <a name="parameters"></a>パラメーター

*wRow*<br/>
現在の行セット内の行の1から始まる位置。 この値の範囲は、1から行セットのサイズまでです。

### <a name="return-value"></a>戻り値

行の状態の値です。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

`GetRowStatus`行がデータソースから最後に取得されたときの状態の変更を示す値を返します。または、 *Wrow*に対応する行がフェッチされなかったかどうかを示します。 次の表は、可能性のある戻り値の一覧です。

|ステータス値|説明|
|------------------|-----------------|
|SQL_ROW_SUCCESS|行は変更されません。|
|SQL_ROW_UPDATED|行が更新されました。|
|SQL_ROW_DELETED|行が削除されました。|
|SQL_ROW_ADDED|行が追加されました。|
|SQL_ROW_ERROR|エラーが発生したため、行が unretrievable されています。|
|SQL_ROW_NOROW|*Wrow*に対応する行がありません。|

詳細については、Windows SDK の ODBC API 関数に関する説明を参照してください `SQLExtendedFetch` 。

## <a name="crecordsetgetstatus"></a><a name="getstatus"></a>CRecordset:: GetStatus

レコードセット内の現在のレコードのインデックスと、最後のレコードが表示されたかどうかを確認します。

```cpp
void GetStatus(CRecordsetStatus& rStatus) const;
```

### <a name="parameters"></a>パラメーター

*rStatus*<br/>
`CRecordsetStatus` オブジェクトへの参照です。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

`CRecordset`はインデックスの追跡を試みますが、状況によってはこれが不可能な場合があります。 説明については、「 [GetRecordCount](#getrecordcount) 」を参照してください。

`CRecordsetStatus`構造体の形式は次のとおりです。

```cpp
struct CRecordsetStatus
{
    long m_lCurrentRecord;
    BOOL m_bRecordCountFinal;
};
```

の2つのメンバーの `CRecordsetStatus` 意味は次のとおりです。

- `m_lCurrentRecord`レコードセット内の現在のレコードの0から始まるインデックスを格納します (既知の場合)。 インデックスを特定できない場合、このメンバーには AFX_CURRENT_RECORD_UNDEFINED (-2) が含まれます。 `IsBOF`が TRUE (空のレコードセットであるか、最初のレコードの前にスクロールしようとする) の場合、 `m_lCurrentRecord` は AFX_CURRENT_RECORD_BOF (-1) に設定されます。 最初のレコードの場合は、0、2番目のレコード1などに設定されます。

- `m_bRecordCountFinal`レコードセット内のレコードの合計数が決定された場合は0以外の値。 通常、これを行うには、レコードセットの先頭から開始し、を呼び出す必要があり `MoveNext` `IsEOF` ます。 このメンバーがゼロの場合、によって返されるレコード数 ( `GetRecordCount` -1 ではない場合) は、レコードの "high watermark" カウントにすぎません。

## <a name="crecordsetgetsql"></a><a name="getsql"></a>CRecordset:: GetSQL

レコードセットのレコードを開いたときにそのレコードを選択するために使用された SQL ステートメントを取得するには、このメンバー関数を呼び出します。

```
const CString& GetSQL() const;
```

### <a name="return-value"></a>戻り値

**`const`** `CString` SQL ステートメントを格納しているへの参照。

### <a name="remarks"></a>解説

通常、これは SQL **SELECT**ステートメントです。 によって返される文字列 `GetSQL` は読み取り専用です。

によって返される文字列 `GetSQL` は、通常、メンバー関数の*lpszSQL*パラメーターのレコードセットに渡された文字列とは異なり `Open` ます。 これは、レコードセットによって、に渡された内容に基づいて完全な SQL ステートメントが作成されるため、ClassWizard で指定した内容、 `Open` およびデータメンバーで指定した内容、および指定したパラメーターに基づいて、完全な SQL ステートメントが作成され `m_strFilter` `m_strSort` ます。 レコードセットがこの SQL ステートメントを構築する方法の詳細については、「[レコードセット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)」を参照してください。

> [!NOTE]
> [Open](#open)を呼び出した後にのみ、このメンバー関数を呼び出します。

## <a name="crecordsetgettablename"></a><a name="gettablename"></a>CRecordset:: GetTableName

レコードセットのクエリの基になっている SQL テーブルの名前を取得します。

```
const CString& GetTableName() const;
```

### <a name="return-value"></a>戻り値

**`const`** `CString` レコードセットがテーブルに基づいている場合は、テーブル名を格納しているへの参照。それ以外の場合は空の文字列。

### <a name="remarks"></a>解説

`GetTableName`は、レコードセットがテーブルに基づいており、複数のテーブルまたは定義済みのクエリ (ストアドプロシージャ) の結合ではない場合にのみ有効です。 名前は読み取り専用です。

> [!NOTE]
> [Open](#open)を呼び出した後にのみ、このメンバー関数を呼び出します。

## <a name="crecordsetisbof"></a><a name="isbof"></a>CRecordset:: IsBOF

レコードセットが最初のレコードの前に配置されている場合は、0以外の値を返します。 現在のレコードが存在しません。

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>戻り値

レコードセットにレコードが含まれていない場合、または最初のレコードの前に後方にスクロールした場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

レコードごとにスクロールしてレコードセットの最初のレコードの前に移動したかどうかを調べるには、このメンバー関数を呼び出します。 と共にを使用して `IsBOF` `IsEOF` 、レコードセットにレコードが含まれているか、空であるかどうかを確認することもできます。 を呼び出した直後、レコード `Open` セットにレコードが含まれていない場合、は `IsBOF` 0 以外の値を返します。少なくとも1つのレコードを含むレコードセットを開くと、最初のレコードが現在のレコードになり、 `IsBOF` 0 が返されます。

最初のレコードが現在のレコードであり、を呼び出すと `MovePrev` 、 `IsBOF` は0以外の値を返します。 が `IsBOF` 0 以外の値を返し、を呼び出すと `MovePrev` 、エラーが発生します。 が `IsBOF` 0 以外の値を返した場合、現在のレコードは未定義であり、現在のレコードを必要とするすべてのアクションでエラーが発生します。

### <a name="example"></a>例

この例では、とを使用 `IsBOF` し `IsEOF` て、コードが双方向でレコードセットをスクロールするときに、レコードセットの制限を検出します。

[!code-cpp[NVC_MFCDatabase#25](../../mfc/codesnippet/cpp/crecordset-class_9.cpp)]

## <a name="crecordsetisdeleted"></a><a name="isdeleted"></a>CRecordset:: IsDeleted

現在のレコードが削除されているかどうかを判断します。

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>戻り値

レコードセットが削除されたレコードに配置されている場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

レコードをスクロールして、 `IsDeleted` TRUE (0 以外) を返した場合は、他のレコードセット操作を実行する前に、別のレコードまでスクロールする必要があります。

の結果は、レコードセットの `IsDeleted` 種類、レコードセットが更新可能かどうか、レコードセットを開いたときにオプションを指定したかどうか、ドライバーが削除されたレコードを削除したかどうか、複数のユーザーがいるかどうかなど、さまざまな要因によって異なり `CRecordset::skipDeletedRecords` ます。

とドライバーパッキングの詳細については、 `CRecordset::skipDeletedRecords` 「 [Open](#open)メンバー関数」を参照してください。

> [!NOTE]
> バルク行フェッチを実装している場合は、を呼び出さないで `IsDeleted` ください。 代わりに、 [Getrowstatus](#getrowstatus)メンバー関数を呼び出します。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

## <a name="crecordsetiseof"></a><a name="iseof"></a>CRecordset:: IsEOF

レコードセットが最後のレコードの後に配置されている場合は0以外の値を返します。 現在のレコードが存在しません。

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>戻り値

レコードセットにレコードが含まれていない場合、または最後のレコードを超えてスクロールした場合は0以外。それ以外の場合は0です。

### <a name="remarks"></a>解説

レコードごとにスクロールしてレコードセットの最後のレコードを超えたかどうかを確認するには、このメンバー関数を呼び出します。 また `IsEOF` 、を使用して、レコードセットにレコードが含まれているか、空であるかを確認することもできます。 を呼び出した直後、レコード `Open` セットにレコードが含まれていない場合、は `IsEOF` 0 以外の値を返します。 少なくとも1つのレコードを含むレコードセットを開くと、最初のレコードが現在のレコードになり、 `IsEOF` 0 が返されます。

を呼び出すと最後のレコードが現在のレコードである場合 `MoveNext` 、 `IsEOF` は0以外の値を返します。 が `IsEOF` 0 以外の値を返し、を呼び出すと `MoveNext` 、エラーが発生します。 が `IsEOF` 0 以外の値を返した場合、現在のレコードは未定義であり、現在のレコードを必要とするすべてのアクションでエラーが発生します。

### <a name="example"></a>例

「 [IsBOF](#isbof)」の例を参照してください。

## <a name="crecordsetisfielddirty"></a><a name="isfielddirty"></a>CRecordset:: IsFieldDirty

指定されたフィールドデータメンバーが、 [Edit](#edit)または[AddNew](#addnew)の呼び出し以降に変更されたかどうかを判断します。

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
状態を確認するフィールドデータメンバーへのポインター。または、いずれかのフィールドがダーティかどうかを判断する場合は NULL。

### <a name="return-value"></a>戻り値

またはを呼び出した後に、指定したフィールドデータメンバーが変更された場合は0以外の `AddNew` `Edit` 。それ以外の場合は0。

### <a name="remarks"></a>解説

の[Update](#update)メンバー関数の呼び出しによって現在のレコードが更新されたときに、すべてのダーティフィールドデータメンバーのデータがデータソースのレコードに転送され `CRecordset` ます (またはの呼び出しの後 `Edit` `AddNew` )。

> [!NOTE]
> このメンバー関数は、バルク行フェッチを使用しているレコードセットには適用されません。 バルク行フェッチを実装している場合、 `IsFieldDirty` は常に FALSE を返し、アサーションは失敗します。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

を呼び出す `IsFieldDirty` と、フィールドのダーティステータスが再評価されるため、 [SetFieldDirty](#setfielddirty)への先行呼び出しの効果がリセットされます。 この場合 `AddNew` 、現在のフィールドの値が擬似的な null 値と異なる場合、フィールドの状態は "ダーティ" に設定されます。 この `Edit` 場合、フィールドの値がキャッシュされた値と異なる場合は、フィールドの状態がダーティに設定されます。

`IsFieldDirty`は[DoFieldExchange](#dofieldexchange)を使用して実装されます。

ダーティフラグの詳細については、「レコード[セット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)」を参照してください。

## <a name="crecordsetisfieldnull"></a><a name="isfieldnull"></a>CRecordset:: IsFieldNull

現在のレコード内の指定されたフィールドが Null (値がない) の場合は、0以外の値を返します。

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
状態を確認するフィールドデータメンバーへのポインター。または、いずれかのフィールドが Null かどうかを判断する場合は NULL。

### <a name="return-value"></a>戻り値

指定されたフィールドデータメンバーに Null のフラグが設定されている場合は0以外の値。それ以外の場合は0です。

### <a name="remarks"></a>解説

このメンバー関数を呼び出して、レコードセットの指定したフィールドデータメンバーに Null としてフラグが設定されているかどうかを確認します。 (データベース用語では、Null は "値がない" ことを意味し、C++ では NULL とは異なります)。フィールドデータメンバーに Null のフラグが設定されている場合、そのメンバーは、値がない現在のレコードの列として解釈されます。

> [!NOTE]
> このメンバー関数は、バルク行フェッチを使用しているレコードセットには適用されません。 バルク行フェッチを実装している場合、 `IsFieldNull` は常に FALSE を返し、アサーションは失敗します。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

`IsFieldNull`は[DoFieldExchange](#dofieldexchange)を使用して実装されます。

## <a name="crecordsetisfieldnullable"></a><a name="isfieldnullable"></a>CRecordset:: IsFieldNullable

現在のレコード内の指定されたフィールドを Null に設定できる場合 (値がない場合) は0以外の値を返します。

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
状態を確認するフィールドデータメンバーへのポインター。または、いずれかのフィールドが Null 値に設定できるかどうかを判断する場合は NULL。

### <a name="remarks"></a>解説

このメンバー関数を呼び出して、指定されたフィールドデータメンバーが "nullable" である (Null 値に設定できる) かどうかを確認します。C++ の NULL は Null と同じではありません。これは、データベース用語では、"値がありません" を意味します。

> [!NOTE]
> バルク行フェッチを実装している場合は、を呼び出すことはできません `IsFieldNullable` 。 代わりに、 [Getodbcfieldinfo](#getodbcfieldinfo)メンバー関数を呼び出して、フィールドを Null 値に設定できるかどうかを判断します。 `GetODBCFieldInfo`バルク行フェッチを実装したかどうかにかかわらず、常にを呼び出すことができることに注意してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

Null にできないフィールドには値が必要です。 レコードを追加または更新するときにこのようなフィールドを Null に設定しようとすると、データソースは追加または更新を拒否し、 [update](#update)は例外をスローします。 この例外は `Update` 、 [SetFieldNull](#setfieldnull)を呼び出したときではなく、を呼び出したときに発生します。

関数の最初の引数に NULL を使用すると、フィールドではなくフィールドのみに関数が適用され `outputColumn` `param` ます。 たとえば、

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

フィールドのみが NULL に設定されます。 `outputColumn` `param` フィールドは影響を受けません。

フィールドを操作するには、次のように、 `param` 作業する個人の実際のアドレスを指定する必要があり `param` ます。

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

これは `param` 、フィールドの場合と同様に、すべてのフィールドを NULL に設定することができないことを意味し `outputColumn` ます。

`IsFieldNullable`は[DoFieldExchange](#dofieldexchange)を使用して実装されます。

## <a name="crecordsetisopen"></a><a name="isopen"></a>CRecordset:: IsOpen

レコードセットが既に開いているかどうかを判断します。

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>戻り値

レコードセットオブジェクトの[Open](#open)または[Requery](#requery)メンバー関数が既に呼び出されていて、レコードセットが閉じられていない場合は0以外。それ以外の場合は0です。

## <a name="crecordsetm_hstmt"></a><a name="m_hstmt"></a>CRecordset:: m_hstmt

レコードセットに関連付けられた、HSTMT 型の ODBC ステートメントデータ構造体を表すハンドルを格納します。

### <a name="remarks"></a>解説

ODBC データソースに対する各クエリは、HSTMT に関連付けられています。

> [!CAUTION]
> `m_hstmt` [Open](#open)が呼び出される前には使用しないでください。

通常、HSTMT に直接アクセスする必要はありませんが、SQL ステートメントを直接実行するために必要になる場合があります。 `ExecuteSQL`クラスのメンバー関数は、 `CDatabase` の使用例を示して `m_hstmt` います。

## <a name="crecordsetm_nfields"></a><a name="m_nfields"></a>CRecordset:: m_nFields

レコードセットクラスのフィールドデータメンバーの数を格納します。これは、データソースからレコードセットによって選択された列の数です。

### <a name="remarks"></a>解説

レコードセットクラスのコンストラクターは、正しい数値で初期化する必要があり `m_nFields` ます。 バルク行フェッチを実装していない場合、ClassWizard では、レコードセットクラスを宣言するときに、この初期化が書き込まれます。 また、手動で書き込むこともできます。

フレームワークは、この数値を使用して、フィールドデータメンバーと、データソースの現在のレコードの対応する列との間の対話を管理します。

> [!CAUTION]
> この数値は、に登録されている "出力列" の数、またはパラメーターを使用した SetFieldType の呼び出し後に対応する必要があり `DoFieldExchange` `DoBulkFieldExchange` [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) `CFieldExchange::outputColumn` ます。

記事「レコードセット: 動的にデータ列をバインドする」で説明されているように、列を動的にバインドできます。 その場合は、のカウントを増やして、動的にバインドされた `m_nFields` `DoFieldExchange` 列の関数またはメンバー関数における rfx 関数または Bulk rfx 関数呼び出しの数を反映させる必要があり `DoBulkFieldExchange` ます。

詳細については、「レコード[セット: 動的にデータ列をバインドする (odbc)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) 」および「レコード[セット: レコードを一括でフェッチする (odbc)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

### <a name="example"></a>例

「[レコードフィールドエクスチェンジ: RFX の使用](../../data/odbc/record-field-exchange-using-rfx.md)」を参照してください。

## <a name="crecordsetm_nparams"></a><a name="m_nparams"></a>CRecordset:: m_nParams

Recordset クラスのパラメーターデータメンバーの数を格納します。つまり、レコードセットのクエリで渡されるパラメーターの数です。

### <a name="remarks"></a>解説

レコードセットクラスにパラメーターデータメンバーがある場合、クラスのコンストラクターは正しい数値を使用して初期化する必要があり `m_nParams` ます。 既定値は `m_nParams` 0 です。 パラメーターデータメンバー (手動で行う必要があります) を追加する場合は、パラメーターの数を反映するために、クラスコンストラクターに初期化を手動で追加する必要もあります (これは、または文字列の ' ' プレースホルダーの数以上である必要があり `m_strFilter` `m_strSort` ます)。

フレームワークは、レコードセットのクエリをパラメーター化するときに、この数値を使用します。

> [!CAUTION]
> この数値は、に登録されている "params" の数、 `DoFieldExchange` または、、、 `DoBulkFieldExchange` またはのパラメーター値を持つ[SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype)の呼び出し後に対応する必要があり `CFieldExchange::inputParam` `CFieldExchange::param` `CFieldExchange::outputParam` `CFieldExchange::inoutParam` ます。

### <a name="example"></a>例

  「レコードセット[: レコードセットのパラメーター化 (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) 」および「[レコードフィールドエクスチェンジ: RFX の使用](../../data/odbc/record-field-exchange-using-rfx.md)」を参照してください。

## <a name="crecordsetm_pdatabase"></a><a name="m_pdatabase"></a>CRecordset:: m_pDatabase

`CDatabase`レコードセットをデータソースに接続するために使用するオブジェクトへのポインターを格納します。

### <a name="remarks"></a>解説

この変数は2つの方法で設定されます。 通常は、レコードセットオブジェクトを構築するときに、既に接続されているオブジェクトへのポインターを渡し `CDatabase` ます。 代わりに NULL を渡すと、に `CRecordset` よってオブジェクトが作成さ `CDatabase` れ、接続されます。 どちらの場合も、に `CRecordset` よってこの変数にポインターが格納されます。

通常は、に格納されているポインターを直接使用する必要はありません `m_pDatabase` 。 ただし、独自の拡張機能をに記述する場合は、 `CRecordset` ポインターの使用が必要になることがあります。 たとえば、独自のをスローする場合は、ポインターが必要になることがあり `CDBException` ます。 また、 `CDatabase` トランザクションの実行、タイムアウトの設定、 `ExecuteSQL` クラスのメンバー関数を呼び出して `CDatabase` SQL ステートメントを直接実行するなど、同じオブジェクトを使用して何らかの操作を行う必要がある場合もあります。

## <a name="crecordsetm_strfilter"></a><a name="m_strfilter"></a>CRecordset:: m_strFilter

レコードセットオブジェクトを作成した後、そのメンバー関数を呼び出す前に、 `Open` このデータメンバーを使用して、 `CString` SQL **WHERE**句を含むを格納します。

### <a name="remarks"></a>解説

レコードセットは、この文字列を使用して、またはの呼び出し時に選択するレコードを制限 (またはフィルター処理) し `Open` `Requery` ます。 これは、"カリフォルニアに基づくすべての販売員" ("state = CA") など、レコードのサブセットを選択する場合に便利です。 **WHERE**句の ODBC SQL 構文は、

`WHERE search-condition`

文字列に**WHERE**キーワードを含めないことに注意してください。 フレームワークによって提供されます。

また、フィルター文字列をパラメーター化するには、プレースホルダーに ' ' プレースホルダーを配置し、各プレースホルダーのクラスでパラメーターデータメンバーを宣言し、実行時にパラメーターをレコードセットに渡すこともできます。 これにより、実行時にフィルターを構築できます。 詳細については、「[レコードセット: レコードセットのパラメーター化 (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)」を参照してください。

SQL の**WHERE**句の詳細については、「 [sql](../../data/odbc/sql.md)」を参照してください。 レコードの選択とフィルター処理の詳細については、「レコード[セット: レコードのフィルター処理 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#30](../../mfc/codesnippet/cpp/crecordset-class_12.cpp)]

## <a name="crecordsetm_strsort"></a><a name="m_strsort"></a>CRecordset:: m_strSort

レコードセットオブジェクトを作成した後、そのメンバー関数を呼び出す前に、 `Open` このデータメンバーを使用し `CString` て、SQL **ORDER by**句を含むを格納します。

### <a name="remarks"></a>解説

レコードセットは、この文字列を使用して、またはの呼び出し時に選択したレコードを並べ替え `Open` `Requery` ます。 この機能を使用して、1つまたは複数の列のレコードセットを並べ替えることができます。 **ORDER by**句の ODBC SQL 構文は、

`ORDER BY sort-specification [, sort-specification]...`

ここで、並べ替え指定は整数または列名です。 また、並べ替え文字列の列リストに "ASC" または "DESC" を追加して、昇順または降順の順序を指定することもできます (既定では昇順です)。 選択したレコードは、最初にリストされている最初の列、次に2番目の列の順に並べ替えられます。 たとえば、"Customers" レコードセットを姓、名、および名で並べ替えることができます。 表示できる列の数は、データソースによって異なります。 詳細については、Windows SDK を参照してください。

文字列に**ORDER BY**キーワードを含めないことに注意してください。 フレームワークによって提供されます。

SQL 句の詳細については、「 [sql](../../data/odbc/sql.md)」を参照してください。 レコードの並べ替えの詳細については、「レコード[セット: レコードの並べ替え (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#31](../../mfc/codesnippet/cpp/crecordset-class_13.cpp)]

## <a name="crecordsetmove"></a><a name="move"></a>CRecordset:: Move

レコードセット内の現在のレコードポインターを前方または後方に移動します。

```
virtual void Move(
    long nRows,
    WORD wFetchType = SQL_FETCH_RELATIVE);
```

### <a name="parameters"></a>パラメーター

*nRows*<br/>
前方または後方に移動する行の数。 正の値は、レコードセットの末尾に向かって前方に移動します。 負の値は、先頭に向かって後方に移動します。

*wFetchType*<br/>
フェッチする行セットを決定し `Move` ます。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

*NRows*に値0を渡すと、は `Move` 現在のレコードを更新します。は現在の `Move` `AddNew` または `Edit` モードを終了し、が呼び出される前に現在のレコードの値を復元し `AddNew` `Edit` ます。

> [!NOTE]
> レコードセット内を移動するときに、削除されたレコードをスキップすることはできません。 詳細については、「 [CRecordset:: IsDeleted](#isdeleted) 」を参照してください。 `CRecordset`オプションセットを指定してを開くと `skipDeletedRecords` 、 `Move` *nRows*パラメーターが0の場合にアサートされます。 この動作により、同じデータを使用して他のクライアントアプリケーションによって削除された行を更新できなくなります。 の説明については、 [Open](#open)の*dwoption*パラメーターを参照してください `skipDeletedRecords` 。

`Move`行セットによってレコードセットを再配置します。 *NRows*と*wFetchType*の値に基づいて、 `Move` 適切な行セットをフェッチし、その行セットの最初のレコードを現在のレコードにします。 バルク行フェッチを実装していない場合、行セットのサイズは常に1になります。 行セットをフェッチするときに、は、 `Move` [CheckRowsetError](#checkrowseterror)メンバー関数を直接呼び出して、フェッチによって発生したエラーを処理します。

渡す値によって、 `Move` は他のメンバー関数と等価です `CRecordset` 。 特に、 *wFetchType*の値は、より直観的で、多くの場合、現在のレコードを移動するために推奨される方法であるメンバー関数を示すことができます。

次の表に、 *wFetchType*に使用できる値、 `Move` *wFetchType*と*nRows*に基づいてフェッチされる行セット、および*wFetchType*に対応する同等のメンバー関数を示します。

|wFetchType|フェッチされる行セット|同等のメンバー関数|
|----------------|--------------------|--------------------------------|
|SQL_FETCH_RELATIVE (既定値)|現在の行セットの最初の行から*nRows*行を開始する行セット。||
|SQL_FETCH_NEXT|次の行セット。*nRows*は無視されます。|[MoveNext](#movenext)|
|SQL_FETCH_PRIOR|前の行セット。*nRows*は無視されます。|[MovePrev](#moveprev)|
|SQL_FETCH_FIRST|レコードセット内の最初の行セット。*nRows*は無視されます。|[MoveFirst](#movefirst)|
|SQL_FETCH_LAST|レコードセット内の最後の完全な行セットです。*nRows*は無視されます。|[MoveLast](#movelast)|
|SQL_FETCH_ABSOLUTE|*NRows* > 0 の場合、行セットの先頭から*nRows*行が開始されます。 *NRows* < 0 の場合、行セットの末尾から*nRows*行が開始されます。 *NRows* = 0 の場合、ファイルの先頭 (BOF) 条件が返されます。|[SetAbsolutePosition](#setabsoluteposition)|
|SQL_FETCH_BOOKMARK|*NRows*に対応するブックマーク値を持つ行から始まる行セット。|[SetBookmark](#setbookmark)|

> [!NOTE]
> 前方参照専用のレコードセットの場合、 `Move` は*wFetchType*の値 SQL_FETCH_NEXT でのみ有効です。

> [!CAUTION]
> レコード `Move` セットにレコードがない場合、を呼び出すと例外がスローされます。 レコードセットにレコードがあるかどうかを確認するには、 [IsBOF](#isbof)と[IsEOF](#iseof)を呼び出します。

> [!NOTE]
> レコードセットの先頭または末尾を超えてスクロールした場合 ( `IsBOF` または `IsEOF` 0 以外の値を返した場合)、関数を呼び出すと `Move` 、がスローされる可能性があり `CDBException` ます。 たとえば、が0以外の値を返し、ではない場合、 `IsEOF` `IsBOF` `MoveNext` は例外をスローしますが、は例外をスロー `MovePrev` しません。

> [!NOTE]
> `Move`現在のレコードが更新または追加されている間にを呼び出した場合、更新は警告なしに失われます。

レコードセットナビゲーションの詳細については、「[レコードセット: スクロール (odbc)](../../data/odbc/recordset-scrolling-odbc.md) 」および「[レコードセット: ブックマークと絶対位置 (odbc)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)」を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。 関連情報については、Windows SDK の ODBC API 関数を参照してください `SQLExtendedFetch` 。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#28](../../mfc/codesnippet/cpp/crecordset-class_14.cpp)]

## <a name="crecordsetmovefirst"></a><a name="movefirst"></a>CRecordset:: MoveFirst

最初の行セットの最初のレコードを現在のレコードにします。

```cpp
void MoveFirst();
```

### <a name="remarks"></a>解説

バルク行フェッチが実装されているかどうかにかかわらず、これは常にレコードセットの最初のレコードになります。

レコードセットを開いた直後にを呼び出す必要はありません `MoveFirst` 。 その時点で、最初のレコード (存在する場合) が自動的に現在のレコードになります。

> [!NOTE]
> このメンバー関数は、順方向専用レコードセットでは無効です。

> [!NOTE]
> レコードセット内を移動するときに、削除されたレコードをスキップすることはできません。 詳細については、 [IsDeleted](#isdeleted)メンバー関数を参照してください。

> [!CAUTION]
> レコードセットにレコードがない場合、いずれかの関数を呼び出すと `Move` 例外がスローされます。 レコードセットにレコードがあるかどうかを確認するには、およびを呼び出し `IsBOF` `IsEOF` ます。

> [!NOTE]
> `Move`現在のレコードを更新または追加するときに関数のいずれかを呼び出すと、更新は警告なしに失われます。

レコードセットナビゲーションの詳細については、「[レコードセット: スクロール (odbc)](../../data/odbc/recordset-scrolling-odbc.md) 」および「[レコードセット: ブックマークと絶対位置 (odbc)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)」を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

### <a name="example"></a>例

  「 [IsBOF](#isbof)」の例を参照してください。

## <a name="crecordsetmovelast"></a><a name="movelast"></a>CRecordset:: MoveLast

最後の行セットの最初のレコードを現在のレコードにします。

```cpp
void MoveLast();
```

### <a name="remarks"></a>解説

バルク行フェッチを実装していない場合、レコードセットの行セットサイズは1であるため、 `MoveLast` 単にレコードセットの最後のレコードに移動します。

> [!NOTE]
> このメンバー関数は、順方向専用レコードセットでは無効です。

> [!NOTE]
> レコードセット内を移動するときに、削除されたレコードをスキップすることはできません。 詳細については、 [IsDeleted](#isdeleted)メンバー関数を参照してください。

> [!CAUTION]
> レコードセットにレコードがない場合、いずれかの関数を呼び出すと `Move` 例外がスローされます。 レコードセットにレコードがあるかどうかを確認するには、およびを呼び出し `IsBOF` `IsEOF` ます。

> [!NOTE]
> `Move`現在のレコードを更新または追加するときに関数のいずれかを呼び出すと、更新は警告なしに失われます。

レコードセットナビゲーションの詳細については、「[レコードセット: スクロール (odbc)](../../data/odbc/recordset-scrolling-odbc.md) 」および「[レコードセット: ブックマークと絶対位置 (odbc)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)」を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

### <a name="example"></a>例

  「 [IsBOF](#isbof)」の例を参照してください。

## <a name="crecordsetmovenext"></a><a name="movenext"></a>CRecordset:: MoveNext

次の行セットの最初のレコードを現在のレコードにします。

```cpp
void MoveNext();
```

### <a name="remarks"></a>解説

バルク行フェッチを実装していない場合、レコードセットの行セットサイズは1であるため、 `MoveNext` 次のレコードに移動するだけです。

> [!NOTE]
> レコードセット内を移動するときに、削除されたレコードをスキップすることはできません。 詳細については、 [IsDeleted](#isdeleted)メンバー関数を参照してください。

> [!CAUTION]
> レコードセットにレコードがない場合、いずれかの関数を呼び出すと `Move` 例外がスローされます。 レコードセットにレコードがあるかどうかを確認するには、およびを呼び出し `IsBOF` `IsEOF` ます。

> [!NOTE]
> を呼び出す前に、を呼び出すこともお勧め `IsEOF` `MoveNext` します。 たとえば、レコードセットの末尾を超えてスクロールした場合、 `IsEOF` は0以外の値を返します。後続のへの呼び出しでは、 `MoveNext` 例外がスローされます。

> [!NOTE]
> `Move`現在のレコードを更新または追加するときに関数のいずれかを呼び出すと、更新は警告なしに失われます。

レコードセットナビゲーションの詳細については、「[レコードセット: スクロール (odbc)](../../data/odbc/recordset-scrolling-odbc.md) 」および「[レコードセット: ブックマークと絶対位置 (odbc)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)」を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

### <a name="example"></a>例

  「 [IsBOF](#isbof)」の例を参照してください。

## <a name="crecordsetmoveprev"></a><a name="moveprev"></a>CRecordset:: MovePrev

前の行セットの最初のレコードを現在のレコードにします。

```cpp
void MovePrev();
```

### <a name="remarks"></a>解説

バルク行フェッチを実装していない場合、レコードセットの行セットサイズは1であるため、 `MovePrev` 単に前のレコードに移動します。

> [!NOTE]
> このメンバー関数は、順方向専用レコードセットでは無効です。

> [!NOTE]
> レコードセット内を移動するときに、削除されたレコードをスキップすることはできません。 詳細については、 [IsDeleted](#isdeleted)メンバー関数を参照してください。

> [!CAUTION]
> レコードセットにレコードがない場合、いずれかの関数を呼び出すと `Move` 例外がスローされます。 レコードセットにレコードがあるかどうかを確認するには、およびを呼び出し `IsBOF` `IsEOF` ます。

> [!NOTE]
> を呼び出す前に、を呼び出すこともお勧め `IsBOF` `MovePrev` します。 たとえば、レコードセットの先頭を前にスクロールした場合、 `IsBOF` は0以外の値を返します。それ以降のへの呼び出しでは、 `MovePrev` 例外がスローされます。

> [!NOTE]
> `Move`現在のレコードを更新または追加するときに関数のいずれかを呼び出すと、更新は警告なしに失われます。

レコードセットナビゲーションの詳細については、「[レコードセット: スクロール (odbc)](../../data/odbc/recordset-scrolling-odbc.md) 」および「[レコードセット: ブックマークと絶対位置 (odbc)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)」を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

### <a name="example"></a>例

  「 [IsBOF](#isbof)」の例を参照してください。

## <a name="crecordsetonsetoptions"></a><a name="onsetoptions"></a>CRecordset:: OnSetOptions

指定された ODBC ステートメントのオプション (選択時に使用される) を設定するために呼び出されます。

```
virtual void OnSetOptions(HSTMT hstmt);
```

### <a name="parameters"></a>パラメーター

*hstmt*<br/>
オプションを設定する ODBC ステートメントの HSTMT です。

### <a name="remarks"></a>解説

を呼び出して `OnSetOptions` 、指定した ODBC ステートメントのオプション (選択時に使用) を設定します。 フレームワークは、このメンバー関数を呼び出して、レコードセットの初期オプションを設定します。 `OnSetOptions`スクロール可能なカーソルおよびカーソルの同時実行に対するデータソースのサポートを決定し、それに応じてレコードセットのオプションを設定します。 ( `OnSetOptions` は選択操作に使用され `OnSetUpdateOptions` ますが、は更新操作に使用されます)。

`OnSetOptions`ドライバーまたはデータソースに固有のオプションを設定するには、をオーバーライドします。 たとえば、データソースで排他アクセスのためのオープンがサポートされている場合は、をオーバーライドし `OnSetOptions` てその機能を利用することができます。

カーソルの詳細については、「 [ODBC](../../data/odbc/odbc-basics.md)」を参照してください。

## <a name="crecordsetonsetupdateoptions"></a><a name="onsetupdateoptions"></a>CRecordset:: OnSetUpdateOptions

指定された ODBC ステートメントに対してオプション (update で使用) を設定するために呼び出されます。

```
virtual void OnSetUpdateOptions(HSTMT hstmt);
```

### <a name="parameters"></a>パラメーター

*hstmt*<br/>
オプションを設定する ODBC ステートメントの HSTMT です。

### <a name="remarks"></a>解説

を呼び出して `OnSetUpdateOptions` 、指定した ODBC ステートメントのオプション (update で使用) を設定します。 このメンバー関数は、レコードセット内のレコードを更新するための HSTMT を作成した後に、フレームワークによって呼び出されます。 ( `OnSetOptions` は選択操作に使用されますが、は更新操作に使用され `OnSetUpdateOptions` ます)。は、スクロール可能な `OnSetUpdateOptions` カーソルおよびカーソルの同時実行に対するデータソースのサポートを決定し、それに応じてレコードセットのオプションを設定します。

をオーバーライド `OnSetUpdateOptions` すると、そのステートメントを使用してデータベースにアクセスする前に、ODBC ステートメントのオプションを設定できます。

カーソルの詳細については、「 [ODBC](../../data/odbc/odbc-basics.md)」を参照してください。

## <a name="crecordsetopen"></a><a name="open"></a>CRecordset:: Open

テーブルを取得するか、レコードセットが表すクエリを実行して、レコードセットを開きます。

```
virtual BOOL Open(
    UINT nOpenType = AFX_DB_USE_DEFAULT_TYPE,
    LPCTSTR lpszSQL = NULL,
    DWORD dwOptions = none);
```

### <a name="parameters"></a>パラメーター

*Noて Type*<br/>
既定値をそのまま使用するか、AFX_DB_USE_DEFAULT_TYPE します。または、の次のいずれかの値を使用し `enum OpenType` ます。

- `CRecordset::dynaset`双方向スクロールを含むレコードセット。 レコードのメンバーシップおよび順序は、レコードセットを開いたときに決定されますが、他のユーザーによるデータ値の変更は、フェッチ操作後に表示されます。 ダイナセットは、キーセット ドリブン レコードセットとも呼ばれます。

- `CRecordset::snapshot`双方向スクロールを持つ静的レコードセット。 レコードのメンバーシップと順序は、レコードセットを開いたときに決定されます。データ値は、レコードをフェッチしたときに決定されます。 他のユーザーが行った変更は、レコードセットを閉じてから再度開くまで表示されません。

- `CRecordset::dynamic`双方向スクロールを含むレコードセット。 他のユーザーが行ったメンバーシップ、順序、およびデータ値の変更は、フェッチ操作後に表示されます。 多くの ODBC ドライバーでは、この型のレコードセットはサポートされていません。

- `CRecordset::forwardOnly`前方スクロールのみを含む読み取り専用のレコードセット。

   の場合 `CRecordset` 、既定値は `CRecordset::snapshot` です。 既定値の機構により、Visual C++ ウィザードで既定値の異なる ODBC `CRecordset` と DAO `CDaoRecordset` 両方を操作できます。

これらのレコードセットの種類の詳細については、「[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)」を参照してください。 関連情報については、Windows SDK の「ブロックカーソルとスクロール可能なカーソルの使用」を参照してください。

> [!CAUTION]
> 要求した型がサポートされていない場合、例外がスローされます。

*lpszSQL*<br/>
次のいずれかを含む文字列ポインター:

- NULL ポインター。

- テーブルの名前。

- SQL **SELECT**ステートメント (必要に応じて、sql **WHERE**句または**ORDER by**句を使用します)。

- 定義済みクエリ (ストアドプロシージャ) の名前を指定する**CALL**ステートメント。 中かっこと**CALL**キーワードの間に空白を挿入しないように注意してください。

この文字列の詳細については、「[解説](#remarks)」の表と ClassWizard のロールの説明を参照してください。

> [!NOTE]
> 結果セットの列の順序は、 [DoFieldExchange](#dofieldexchange)関数または[DoBulkFieldExchange](#dobulkfieldexchange)関数のオーバーライドで、Rfx 関数または Bulk rfx 関数呼び出しの順序と一致している必要があります。

*dwOptions*<br/>
以下に示す値の組み合わせを指定できるビットマスク。 これらの値の一部は同時に指定できません。 既定値は**none**です。

- `CRecordset::none`オプションは設定しません。 このパラメーター値は、他のすべての値と同時に指定できません。 既定では、レコードセットは、 [Edit](#edit)または[Delete](#delete)を使用して更新し、 [AddNew](#addnew)を使用して新しいレコードを追加することができます。 更新可能性は、指定した*Noて type*オプションだけでなく、データソースによっても異なります。 バルク追加の最適化は使用できません。 バルク行フェッチは実装されません。 削除されたレコードはレコードセットの移動中にスキップされません。 ブックマークは使用できません。 自動ダーティ フィールド チェックが実装されます。

- `CRecordset::appendOnly``Edit` `Delete` レコードセットに対してまたはを許可しません。 `AddNew` のみ実行できます。 このオプションは `CRecordset::readOnly` と同時に指定できません。

- `CRecordset::readOnly`レコードセットを読み取り専用として開きます。 このオプションは `CRecordset::appendOnly` と同時に指定できません。

- `CRecordset::optimizeBulkAdd`準備された SQL ステートメントを使用して、一度に多数のレコードを追加するように最適化します。 ODBC API 関数を使用してレコードセットを更新しない場合にのみ適用され `SQLSetPos` ます。 最新の更新で、ダーティとマークされるフィールドが決まります。 このオプションは `CRecordset::useMultiRowFetch` と同時に指定できません。

- `CRecordset::useMultiRowFetch`バルク行フェッチを実装して、1回のフェッチ操作で複数の行を取得できるようにします。 これは、パフォーマンスを向上するために設計された拡張機能です。ただし、バルク レコード フィールド エクスチェンジは ClassWizard ではサポートされていません。 このオプションは `CRecordset::optimizeBulkAdd` と同時に指定できません。 を指定した場合、 `CRecordset::useMultiRowFetch` オプションは自動的にオンになります `CRecordset::noDirtyFieldCheck` (ダブルバッファリングは使用できません)。順方向専用のレコードセットでは、このオプションは自動的に有効になり `CRecordset::useExtendedFetch` ます。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

- `CRecordset::skipDeletedRecords`レコードセット内を移動するときに、削除されたすべてのレコードをスキップします。 これにより、特定の相対フェッチでパフォーマンスが低下します。 このオプションは前方スクロール専用レコードセットでは無効です。 *NRows*パラメーターを0に設定し、オプションを設定して[Move](#move)を呼び出すと、に `CRecordset::skipDeletedRecords` よって `Move` アサートされます。 `CRecordset::skipDeletedRecords`は*ドライバーパッキング*に似ていることに注意してください。これは、削除された行がレコードセットから削除されることを意味します。 ただし、ドライバーによってレコードがパックされる場合、ユーザー自身が削除するレコードだけがスキップされます。レコードセットを開いている間に他のユーザーによって削除されたレコードはスキップされません。 `CRecordset::skipDeletedRecords`他のユーザーによって削除された行はスキップされます。

- `CRecordset::useBookmarks`サポートされている場合は、レコードセットでブックマークを使用できます。 ブックマークを使用すると、データの取得速度は低下しますが、データ移動のパフォーマンスが向上します。 前方スクロール専用レコードセットでは無効です。 詳細については、「[レコードセット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)」を参照してください。

- `CRecordset::noDirtyFieldCheck`自動ダーティフィールドチェック (ダブルバッファリング) をオフにします。 これにより、パフォーマンスは向上しますが、`SetFieldDirty` メンバー関数と `SetFieldNull` メンバー関数を呼び出して手動でフィールドをダーティとしてマークする必要があります。`CRecordset` クラスのダブル バッファリングは、`CDaoRecordset` クラスのダブル バッファリングに似ています。 ただし、`CRecordset` では、個別のフィールドに対してダブル バッファリングを有効にできません。すべてのフィールドに対して有効にするか、またはすべてのフィールドに対して無効にします。 オプションを指定すると `CRecordset::useMultiRowFetch` 、は自動的に有効になります `CRecordset::noDirtyFieldCheck` 。ただし、 `SetFieldDirty` `SetFieldNull` 一括行フェッチを実装するレコードセットでは、およびを使用できません。

- `CRecordset::executeDirect`準備された SQL ステートメントは使用しないでください。 パフォーマンスを向上させるために、メンバー関数を呼び出さない場合は、このオプションを指定し `Requery` ます。

- `CRecordset::useExtendedFetch``SQLExtendedFetch`の代わりにを実装 `SQLFetch` します。 これは、前方スクロール専用レコードセットに対してバルク行フェッチを実装するために設計されています。 前方参照専用レコードセットでオプションを指定すると `CRecordset::useMultiRowFetch` 、 `CRecordset::useExtendedFetch` が自動的に有効になります。

- `CRecordset::userAllocMultiRowBuffers`ユーザーは、データのストレージバッファーを割り当てます。 独自の格納バッファーを割り当てる場合は、このオプションと一緒に `CRecordset::useMultiRowFetch` を使用します。使用しない場合、必要な格納バッファーが自動的に割り当てられます。 詳細については、「レコード[セット: レコードを一括フェッチする (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。 を指定せずにを指定すると、アサーションが失敗することに注意 `CRecordset::userAllocMultiRowBuffers` `CRecordset::useMultiRowFetch` してください。

### <a name="return-value"></a>戻り値

`CRecordset`オブジェクトが正常に開かれた場合は0以外の値。 [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open) (呼び出された場合) が0を返す場合は0。

### <a name="remarks"></a>解説

レコードセットによって定義されたクエリを実行するには、このメンバー関数を呼び出す必要があります。 を呼び出す前に `Open` 、レコードセットオブジェクトを作成する必要があります。

このレコードセットのデータソースへの接続は、を呼び出す前にレコードセットを作成する方法によって異なり `Open` ます。 データソースに接続されていないレコードセットコンストラクターに[CDatabase](../../mfc/reference/cdatabase-class.md)オブジェクトを渡した場合、このメンバー関数は[GetDefaultConnect](#getdefaultconnect)を使用してデータベースオブジェクトを開こうとします。 レコードセットコンストラクターに NULL を渡すと、コンストラクターによってオブジェクトが構築され、 `CDatabase` `Open` データベースオブジェクトへの接続が試行されます。 これらのさまざまな状況下でレコードセットと接続を閉じる方法の詳細については、「 [Close](#close)」を参照してください。

> [!NOTE]
> `CRecordset` オブジェクトを使用したデータ ソースへのアクセスは常に共有されます。 `CDaoRecordset` クラスとは異なり、`CRecordset` オブジェクトを使用して排他アクセスでデータ ソースを開くことはできません。

を呼び出すと、 `Open` クエリ (通常は SQL **SELECT**ステートメント) によって、次の表に示す条件に基づいてレコードが選択されます。

|lpszSQL パラメーターの値|レコードの選択基準|例|
|------------------------------------|----------------------------------------|-------------|
|NULL|`GetDefaultSQL` の返す文字列。||
|SQL テーブル名|`DoFieldExchange` または `DoBulkFieldExchange` のテーブル リストのすべての列。|`"Customer"`|
|定義済みクエリ (ストアド プロシージャ) の名前|返すためにクエリが定義された列。|`"{call OverDueAccts}"`|
|テーブルリスト**から**列リストを**選択し**ます|指定したテーブルの指定した列。|`"SELECT CustId, CustName FROM`<br /><br /> `Customer"`|

> [!CAUTION]
> SQL 文字列に余分な空白を挿入しないでください。 たとえば、中かっこと**CALL**キーワードの間に空白を挿入すると、MFC は SQL 文字列をテーブル名として誤って解釈し、 **SELECT**ステートメントに組み込みます。これにより、例外がスローされます。 同様に、定義済みのクエリで出力パラメーターを使用する場合は、中かっこと ' ' 記号の間に空白を挿入しないでください。 最後に、 **CALL**ステートメントの中かっこの前、または**Select**ステートメントの**select**キーワードの前に空白を挿入しないようにする必要があります。

通常の手順では、NULL をに渡します。 `Open` この場合、は `Open` [GetDefaultSQL](#getdefaultsql)を呼び出します。 派生クラスを使用している場合は `CRecordset` 、 `GetDefaultSQL` ClassWizard で指定したテーブル名がによって指定されます。 代わりに、その他の情報を `lpszSQL` パラメーターに指定できます。

どのような場合でも、は `Open` クエリの最終的な sql 文字列を構築します (文字列には、渡された文字列に Sql **WHERE**句と**ORDER BY**句が追加されている場合があり `lpszSQL` ます)。その後、クエリを実行します。 を呼び出した後に[GetSQL](#getsql)を呼び出すことによって、構築された文字列を調べることができ `Open` ます。 レコードセットが SQL ステートメントを作成してレコードを選択する方法の詳細については、「[レコードセット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)」を参照してください。

レコードセット クラスのフィールド データ メンバーは、選択したデータの列に結び付けられています。 いくつかのレコードが返された場合、最初のレコードが現在のレコードになります。

フィルターや並べ替えなどのレコードセットのオプションを設定する場合は、レコードセットオブジェクトを作成した後でを呼び出す前に、これらのオプションを指定し `Open` ます。 レコードセットが既に開いている状態でレコードセット内のレコードを更新する場合は、 [Requery](#requery)を呼び出します。

その他の例を含む詳細については、「[レコードセット (odbc)](../../data/odbc/recordset-odbc.md)」、「[レコードセット: レコード選択のしくみ (odbc)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)」、および「[レコードセット: レコードセットの作成と終了 (odbc)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)」を参照してください。

### <a name="example"></a>例

次のコード例は、さまざまな形式の呼び出しを示して `Open` います。

[!code-cpp[NVC_MFCDatabase#16](../../mfc/codesnippet/cpp/crecordset-class_15.cpp)]

## <a name="crecordsetrefreshrowset"></a><a name="refreshrowset"></a>CRecordset:: RefreshRowset

現在の行セット内の行のデータと状態を更新します。

```cpp
void RefreshRowset(
    WORD wRow,
    WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>パラメーター

*wRow*<br/>
現在の行セット内の行の1から始まる位置。 この値の範囲は、0から行セットのサイズまでです。

*wLockType*<br/>
更新後に行をロックする方法を示す値。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

*Wrow*に値0を渡すと、行セット内のすべての行が更新されます。

を使用するには、 `RefreshRowset` `CRecordset::useMulitRowFetch` [Open](#open)メンバー関数でオプションを指定してバルク行フェッチを実装している必要があります。

`RefreshRowset`ODBC API 関数を呼び出し `SQLSetPos` ます。 *Wlocktype*パラメーターは、が実行された後の行のロック状態を指定し `SQLSetPos` ます。 次の表では、 *Wlocktype*に使用できる値について説明します。

|wLockType|説明|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE (既定値)|ドライバーまたはデータソースによって、が呼び出される前と同じロックまたはロック解除された状態になるようにし `RefreshRowset` ます。|
|SQL_LOCK_EXCLUSIVE|ドライバーまたはデータソースは、行を排他的にロックします。 一部のデータソースでは、この種類のロックがサポートされていません。|
|SQL_LOCK_UNLOCK|ドライバーまたはデータソースによって行のロックが解除されます。 一部のデータソースでは、この種類のロックがサポートされていません。|

の詳細については `SQLSetPos` 、Windows SDK を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

## <a name="crecordsetrequery"></a><a name="requery"></a>CRecordset:: Requery

レコードセットを再構築 (更新) します。

```
virtual BOOL Requery();
```

### <a name="return-value"></a>戻り値

レコードセットが正常に再構築された場合は0以外の場合は。それ以外の場合は0です。

### <a name="remarks"></a>解説

いくつかのレコードが返された場合、最初のレコードが現在のレコードになります。

ユーザーまたは他のユーザーがデータソースに対して行った追加や削除をレコードセットに反映させるには、を呼び出してレコードセットを再構築する必要があり `Requery` ます。 レコードセットがダイナセットである場合は、自分または他のユーザーが既存のレコードに対して行った更新が自動的に反映されます (ただし、追加することはできません)。 レコードセットがスナップショットの場合は、を呼び出して、 `Requery` 他のユーザーによる編集と、追加や削除を反映する必要があります。

ダイナセットまたはスナップショットの場合、 `Requery` 新しいフィルターや並べ替え、または新しいパラメーター値を使用してレコードセットを再構築するときに、いつでもを呼び出します。 を呼び出す前に、新しい値をとに割り当てて新しいフィルターまたは並べ替えプロパティを設定し `m_strFilter` `m_strSort` `Requery` ます。 を呼び出す前に、パラメーターデータメンバーに新しい値を割り当てることによって、新しいパラメーターを設定 `Requery` します。 フィルター文字列と並べ替え文字列が変更されていない場合は、クエリを再利用できます。これにより、パフォーマンスが向上します。

レコードセットを再構築しようとして失敗した場合、レコードセットは閉じられます。 を呼び出す前に `Requery` 、メンバー関数を呼び出してレコードセットを再度実行できるかどうかを判断でき `CanRestart` ます。 `CanRestart`は、が成功するとは限りません `Requery` 。

> [!CAUTION]
> Open を呼び出した `Requery` 後に[Open](#open)のみ、を呼び出します。

### <a name="example"></a>例

この例では、レコードセットを再構築して別の並べ替え順序を適用します。

[!code-cpp[NVC_MFCDatabase#29](../../mfc/codesnippet/cpp/crecordset-class_16.cpp)]

## <a name="crecordsetsetabsoluteposition"></a><a name="setabsoluteposition"></a>CRecordset:: SetAbsolutePosition

指定されたレコード番号に対応するレコードにレコードセットを配置します。

```cpp
void SetAbsolutePosition(long nRows);
```

### <a name="parameters"></a>パラメーター

*nRows*<br/>
レコードセット内の現在のレコードの、1から始まる序数の位置。

### <a name="remarks"></a>解説

`SetAbsolutePosition`この序数位置に基づいて現在のレコードポインターを移動します。

> [!NOTE]
> このメンバー関数は、順方向専用レコードセットでは無効です。

ODBC レコードセットの場合、絶対位置の設定1はレコードセット内の最初のレコードを表します。0の設定は、ファイルの先頭 (BOF) の位置を示します。

負の値をに渡すこともでき `SetAbsolutePosition` ます。 この場合、レコードセットの位置はレコードセットの末尾から評価されます。 たとえば、は、 `SetAbsolutePosition( -1 )` 現在のレコードポインターをレコードセット内の最後のレコードに移動します。

> [!NOTE]
> 絶対位置は、サロゲートレコード番号として使用するためのものではありません。 ブックマークは、前のレコードが削除されたときにレコードの位置が変更されるため、指定した位置に保持して返すことをお勧めします。 また、レコードセットが再作成された場合、特定のレコードの絶対位置が同じであることを保証することはできません。これは、レコードセット内の個々のレコードの順序が、 **ORDER BY**句を使用して SQL ステートメントで作成されている場合を除き、そのレコードが確実に再作成されるためです。

レコードセットナビゲーションとブックマークの詳細については、「[レコードセット: スクロール (odbc)](../../data/odbc/recordset-scrolling-odbc.md) 」および「[レコードセット: ブックマークと絶対位置 (odbc)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)」を参照してください。

## <a name="crecordsetsetbookmark"></a><a name="setbookmark"></a>CRecordset:: SetBookmark

指定されたブックマークを含むレコードにレコードセットを配置します。

```cpp
void SetBookmark(const CDBVariant& varBookmark);
```

### <a name="parameters"></a>パラメーター

*varBookmark*<br/>
特定のレコードのブックマーク値を格納している[CDBVariant](../../mfc/reference/cdbvariant-class.md)オブジェクトへの参照。

### <a name="remarks"></a>解説

レコードセットでブックマークがサポートされているかどうかを判断するには、 [Canbookmark](#canbookmark)を呼び出します。 サポートされている場合にブックマークを使用できるようにするには、 `CRecordset::useBookmarks` [Open](#open)メンバー関数の*dwOptions*パラメーターでオプションを設定する必要があります。

> [!NOTE]
> ブックマークがサポートされていないか使用できない場合、を呼び出す `SetBookmark` と例外がスローされます。 ブックマークは、順方向専用のレコードセットではサポートされていません。

最初に現在のレコードのブックマークを取得するには、 [GetBookmark](#getbookmark)を呼び出します。これにより、ブックマーク値がオブジェクトに保存さ `CDBVariant` れます。 その後、保存されている `SetBookmark` ブックマーク値を使用してを呼び出すことにより、そのレコードに戻ることができます。

> [!NOTE]
> 特定のレコードセット操作の後、を呼び出す前に、ブックマークの永続化を確認する必要があり `SetBookmark` ます。 たとえば、を使用してブックマークを取得し `GetBookmark` 、を呼び出すと、 `Requery` ブックマークが無効になることがあります。 を安全に呼び出すことができるかどうかを確認するには、 [CDatabase:: GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence)を呼び出し `SetBookmark` ます。

ブックマークとレコードセットナビゲーションの詳細については、「[レコードセット: ブックマークと絶対位置 (odbc)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) 」および「[レコードセット: スクロール (odbc)](../../data/odbc/recordset-scrolling-odbc.md)」を参照してください。

## <a name="crecordsetsetfielddirty"></a><a name="setfielddirty"></a>CRecordset:: SetFieldDirty

レコードセットのフィールドデータメンバーを変更済みとして、または変更せずにフラグを付けます。

```cpp
void SetFieldDirty(void* pv, BOOL bDirty = TRUE);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
レコードセットのフィールドデータメンバーのアドレス、または NULL を格納します。 NULL の場合、レコードセット内のすべてのフィールドデータメンバーにフラグが設定されます。 (C++ NULL は、データベース用語では Null と同じではありません。つまり、"値がない" ことを意味します)。

*bDirty*<br/>
フィールドデータメンバーに "ダーティ" としてフラグを設定する場合は TRUE (変更された場合)。 それ以外の場合は、フィールドデータメンバーに "clean" (変更なし) のフラグを設定する場合は FALSE。

### <a name="remarks"></a>解説

フィールドを変更せずにマークすると、フィールドが更新されず、SQL トラフィックが少なくなります。

> [!NOTE]
> このメンバー関数は、バルク行フェッチを使用しているレコードセットには適用されません。 バルク行フェッチを実装している場合は、によって `SetFieldDirty` アサーションが失敗します。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

フレームワークは、変更されたフィールドのデータメンバーを、レコードフィールドエクスチェンジ (RFX) メカニズムによってデータソースのレコードに書き込まれるようにマークします。 フィールドの値を変更すると、通常はダーティフィールドが自動的にダーティに設定されるため、自分で呼び出す必要はほとんどあり `SetFieldDirty` ませんが、フィールドのデータメンバーに含まれる値に関係なく、明示的に列が更新または挿入されるようにすることが必要になる場合があります。

> [!CAUTION]
> このメンバー関数は、 [Edit](#edit)または[AddNew](#addnew)を呼び出した後にのみ呼び出してください。

関数の最初の引数に NULL を使用すると、フィールドではなくフィールドのみに関数が適用され `outputColumn` `param` ます。 たとえば、

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

フィールドのみが NULL に設定されます。 `outputColumn` `param` フィールドは影響を受けません。

フィールドを操作するには、次のように、 `param` 作業する個人の実際のアドレスを指定する必要があり `param` ます。

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

これは `param` 、フィールドの場合と同様に、すべてのフィールドを NULL に設定することができないことを意味し `outputColumn` ます。

## <a name="crecordsetsetfieldnull"></a><a name="setfieldnull"></a>CRecordset:: SetFieldNull

レコードセットのフィールドデータメンバーに Null としてフラグを付けます (特に値を含まない)。または、Null 以外の値としてフラグを指定します。

```cpp
void SetFieldNull(void* pv, BOOL bNull = TRUE);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
レコードセットのフィールドデータメンバーのアドレス、または NULL を格納します。 NULL の場合、レコードセット内のすべてのフィールドデータメンバーにフラグが設定されます。 (C++ NULL は、データベース用語では Null と同じではありません。つまり、"値がない" ことを意味します)。

*bNull*<br/>
フィールドデータメンバーに値がないことを示すフラグが設定されている場合は0以外 (Null)。 それ以外の場合は、フィールドデータメンバーに Null 以外のフラグが設定されている場合は0になります。

### <a name="remarks"></a>解説

レコードセットに新しいレコードを追加すると、すべてのフィールドデータメンバーは最初に Null 値に設定され、"ダーティ" (変更) としてフラグが設定されます。 データソースからレコードを取得する場合、その列には既に値があるか、または Null になります。

> [!NOTE]
> バルク行フェッチを使用しているレコードセットでは、このメンバー関数を呼び出さないでください。 バルク行フェッチを実装している場合、を呼び出すと、 `SetFieldNull` アサーションが失敗します。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

現在のレコードのフィールドに値を設定しないことを明示的に指定する場合は、 `SetFieldNull` *BNULL*を TRUE に設定してを呼び出し、null としてフラグを設定します。 フィールドが以前は Null とマークされていて、値を指定する必要がある場合は、単に新しい値を設定します。 で Null フラグを削除する必要はありません `SetFieldNull` 。 フィールドを Null にできるかどうかを判断するには、を呼び出し `IsFieldNullable` ます。

> [!CAUTION]
> このメンバー関数は、 [Edit](#edit)または[AddNew](#addnew)を呼び出した後にのみ呼び出してください。

関数の最初の引数に NULL を使用すると、フィールドではなくフィールドのみに関数が適用され `outputColumn` `param` ます。 たとえば、

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

フィールドのみが NULL に設定されます。 `outputColumn` `param` フィールドは影響を受けません。

フィールドを操作するには、次のように、 `param` 作業する個人の実際のアドレスを指定する必要があり `param` ます。

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

これは `param` 、フィールドの場合と同様に、すべてのフィールドを NULL に設定することができないことを意味し `outputColumn` ます。

> [!NOTE]
> パラメーターを Null に設定すると、 `SetFieldNull` レコードセットが開かれる前にを呼び出すと、アサーションが発生します。 この場合は、 [Setparamnull](#setparamnull)を呼び出します。

`SetFieldNull`は[DoFieldExchange](#dofieldexchange)を使用して実装されます。

## <a name="crecordsetsetlockingmode"></a><a name="setlockingmode"></a>CRecordset:: Setロックモード

ロックモードを "オプティミスティック" ロック (既定値) または "ペシミスティック" ロックに設定します。 更新のためにレコードをロックする方法を指定します。

```cpp
void SetLockingMode(UINT nMode);
```

### <a name="parameters"></a>パラメーター

*Evaluationmode*<br/>
には、の次のいずれかの値が含まれ `enum LockMode` ます。

- `optimistic`オプティミスティックロックは、の呼び出し中にのみ更新されるレコードをロックし `Update` ます。

- `pessimistic`ペシミスティックロックは、が呼び出されるとすぐにレコードをロック `Edit` し、 `Update` 呼び出しが完了するか新しいレコードに移動するまでロックを保持します。

### <a name="remarks"></a>解説

レコードセットが更新に使用する2つのレコードロックの方法を指定する必要がある場合は、このメンバー関数を呼び出します。 既定では、レコードセットのロックモードは `optimistic` です。 これは、より慎重なロック戦略に変更でき `pessimistic` ます。 を `SetLockingMode` 呼び出す前に、レコードセットオブジェクトを構築して開いた後で、を呼び出し `Edit` ます。

## <a name="crecordsetsetparamnull"></a><a name="setparamnull"></a>CRecordset:: SetParamNull

パラメーターに Null (具体的には値がない) または非 Null としてフラグを付けます。

```cpp
void SetParamNull(
    int nIndex,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
パラメーターの 0 から始まるインデックス。

*bNull*<br/>
TRUE (既定値) の場合、パラメーターは Null としてフラグが設定されます。 それ以外の場合、パラメーターには Null 以外のフラグが設定されます。

### <a name="remarks"></a>解説

[SetFieldNull](#setfieldnull)とは異なり、 `SetParamNull` レコードセットを開く前にを呼び出すことができます。

`SetParamNull`は、通常、定義済みのクエリ (ストアドプロシージャ) と共に使用されます。

## <a name="crecordsetsetrowsetcursorposition"></a><a name="setrowsetcursorposition"></a>CRecordset:: SetRowsetCursorPosition

現在の行セット内の行にカーソルを移動します。

```cpp
void SetRowsetCursorPosition(WORD wRow, WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>パラメーター

*wRow*<br/>
現在の行セット内の行の1から始まる位置。 この値の範囲は、1から行セットのサイズまでです。

*wLockType*<br/>
更新後に行をロックする方法を示す値。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

バルク行フェッチを実装する場合、レコードは行セットによって取得され、フェッチされた行セットの最初のレコードが現在のレコードになります。 行セット内の別のレコードを現在のレコードにするには、を呼び出し `SetRowsetCursorPosition` ます。 たとえば、 `SetRowsetCursorPosition` [GetFieldValue](#getfieldvalue)メンバー関数を組み合わせて、レコードセットの任意のレコードからデータを動的に取得することができます。

を使用するには `SetRowsetCursorPosition` 、 `CRecordset::useMultiRowFetch` [Open](#open)メンバー関数で*dwOptions*パラメーターのオプションを指定して、バルク行フェッチを実装している必要があります。

`SetRowsetCursorPosition`ODBC API 関数を呼び出し `SQLSetPos` ます。 *Wlocktype*パラメーターは、が実行された後の行のロック状態を指定し `SQLSetPos` ます。 次の表では、 *Wlocktype*に使用できる値について説明します。

|wLockType|説明|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE (既定値)|ドライバーまたはデータソースによって、が呼び出される前と同じロックまたはロック解除された状態になるようにし `SetRowsetCursorPosition` ます。|
|SQL_LOCK_EXCLUSIVE|ドライバーまたはデータソースは、行を排他的にロックします。 一部のデータソースでは、この種類のロックがサポートされていません。|
|SQL_LOCK_UNLOCK|ドライバーまたはデータソースによって行のロックが解除されます。 一部のデータソースでは、この種類のロックがサポートされていません。|

の詳細については `SQLSetPos` 、Windows SDK を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

## <a name="crecordsetsetrowsetsize"></a><a name="setrowsetsize"></a>CRecordset:: SetRowsetSize

フェッチ中に取得するレコードの数を指定します。

```
virtual void SetRowsetSize(DWORD dwNewRowsetSize);
```

### <a name="parameters"></a>パラメーター

*dwNewRowsetSize*<br/>
特定のフェッチ中に取得する行の数。

### <a name="remarks"></a>解説

この仮想メンバー関数は、バルク行フェッチを使用しているときに、1つのフェッチ中に取得する行数を指定します。 バルク行フェッチを実装するには、 `CRecordset::useMultiRowFetch` [Open](#open)メンバー関数の*dwOptions*パラメーターでオプションを設定する必要があります。

> [!NOTE]
> `SetRowsetSize`バルク行フェッチを実装せずにを呼び出すと、アサーションは失敗します。

`SetRowsetSize`を呼び出す前に `Open` 、を呼び出して、レコードセットの行セットのサイズを初期設定します。 バルク行フェッチを実装する場合の既定の行セットサイズは25です。

> [!NOTE]
> を呼び出すときは注意が必要 `SetRowsetSize` です。 の dwOptions パラメーターのオプションで指定されているように、データのストレージを手動で割り当てる場合は `CRecordset::userAllocMultiRowBuffers` `Open` 、を呼び出した後 `SetRowsetSize` 、カーソルナビゲーション操作を実行する前に、これらのストレージバッファーを再割り当てする必要があるかどうかを確認する必要があります。

行セットサイズの現在の設定を取得するには、 [GetRowsetSize](#getrowsetsize)を呼び出します。

バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

## <a name="crecordsetupdate"></a><a name="update"></a>CRecordset:: Update

`AddNew` `Edit` 新しいデータまたは編集されたデータをデータソースに保存することによって、操作または操作を完了します。

```
virtual BOOL Update();
```

### <a name="return-value"></a>戻り値

1つのレコードが正常に更新された場合は0以外。それ以外の場合は、列が変更されていない場合は0です。 レコードが更新されなかった場合、または複数のレコードが更新された場合は、例外がスローされます。 また、データソースのその他のエラーに対しても例外がスローされます。

### <a name="remarks"></a>解説

このメンバー関数は、 [AddNew](#addnew)または[Edit](#edit)メンバー関数の呼び出しの後に呼び出します。 この呼び出しは、または操作を完了するために必要です `AddNew` `Edit` 。

> [!NOTE]
> バルク行フェッチを実装している場合は、を呼び出すことはできません `Update` 。 これにより、アサーションは失敗します。 クラスに `CRecordset` は、データの一括行を更新するためのメカニズムが用意されていませんが、ODBC API 関数を使用して独自の関数を記述することができ `SQLSetPos` ます。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

とはどちらも、 `AddNew` `Edit` データソースに保存するために追加または編集されたデータを格納する編集バッファーを準備します。 `Update`データを保存します。 変更済みとしてマークまたは検出されたフィールドのみが更新されます。

データソースがトランザクションをサポートしている場合は、 `Update` トランザクションの呼び出し (およびそれに対応する `AddNew` または呼び出し) を行うことができ `Edit` ます。 トランザクションの詳細については、「[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)」を参照してください。

> [!CAUTION]
> `Update`最初にまたはのいずれかを呼び出さずにを呼び出すと `AddNew` `Edit` 、 `Update` がスローさ `CDBException` れます。 `AddNew`またはを呼び出す場合 `Edit` は、 `Update` 操作を呼び出す前に、 `Move` またはレコードセットまたはデータソース接続を閉じる前にを呼び出す必要があります。 そうしないと、変更内容が通知なしに失われます。

エラーの処理の詳細につい `Update` ては、「レコード[セット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)」を参照してください。

### <a name="example"></a>例

「[トランザクション: レコードセットでのトランザクションの実行 (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CDatabase クラス](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordView クラス](../../mfc/reference/crecordview-class.md)
