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
ms.openlocfilehash: efb833a8d4cc0b801f75951bc648d6b83df5bae8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372206"
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
|[CRecordset::CRecordset](#crecordset)|`CRecordset` オブジェクトを構築します。 派生クラスでは、この関数を呼び出すコンス トラクターを指定する必要があります。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CRecordset::AddNew](#addnew)|新しいレコードを追加する準備をします。 呼び出す`Update`追加を完了します。|
|[CRecordset::CanAppend](#canappend)|使用してレコード セットに新しいレコードを追加する場合は 0 以外を返します、`AddNew`メンバー関数。|
|[CRecordset::CanBookmark](#canbookmark)|レコード セットは、ブックマークをサポートしている場合、0 以外の値を返します。|
|[CRecordset::Cancel](#cancel)|非同期操作または 2 番目のスレッドからのプロセスをキャンセルします。|
|[CRecordset::CancelUpdate](#cancelupdate)|ために、保留中の更新をキャンセル、`AddNew`または`Edit`操作。|
|[CRecordset::CanRestart](#canrestart)|場合は 0 以外の値を返します`Requery`レコード セットのクエリを再実行を呼び出すことができます。|
|[CRecordset::CanScroll](#canscroll)|レコードをスクロールする場合は 0 以外を返します。|
|[CRecordset::CanTransact](#cantransact)|データ ソースは、トランザクションをサポートしている場合、0 以外の値を返します。|
|[CRecordset::CanUpdate](#canupdate)|レコード セットを更新する場合は 0 以外を返します (することができますを追加、更新、またはレコードを削除) します。|
|[CRecordset::CheckRowsetError](#checkrowseterror)|レコードのフェッチ中にエラーを処理するために呼び出されます。|
|[ような場合](#close)|レコード セットと関連付けられている ODBC HSTMT を閉じます。|
|[CRecordset::Delete](#delete)|レコード セットから現在のレコードを削除します。 削除後は、別のレコードに明示的にスクロールする必要があります。|
|[CRecordset::DoBulkFieldExchange](#dobulkfieldexchange)|データ ソースからレコード セットへのデータのバルク行と呼ばれます。 実装はバルク レコード フィールド エクス チェンジ (Bulk RFX) します。|
|[CRecordset::DoFieldExchange](#dofieldexchange)|レコード セットのフィールド データ メンバーと、データ ソースに対応するレコード間を双方向) でデータを交換するには、呼び出されます。 レコード フィールド エクス (チェンジ RFX) をを実装します。|
|[CRecordset::Edit](#edit)|現在のレコードへの変更の準備を行います。 呼び出す`Update`編集を完了します。|
|[CRecordset::FlushResultSet](#flushresultset)|もう 1 つの結果がある場合は 0 以外を返します。 は、定義済みのクエリを使用する場合は、取得する設定します。|
|[CRecordset::GetBookmark](#getbookmark)|パラメーター オブジェクトには、レコードのブックマークの値を割り当てます。|
|[CRecordset::GetDefaultConnect](#getdefaultconnect)|既定の接続文字列を取得するには、呼び出されます。|
|[CRecordset::GetDefaultSQL](#getdefaultsql)|実行する既定の SQL 文字列を取得するには、呼び出されます。|
|[CRecordset::GetFieldValue](#getfieldvalue)|レコード セット内のフィールドの値を返します。|
|[CRecordset::GetODBCFieldCount](#getodbcfieldcount)|レコード セットのフィールドの数を返します。|
|[CRecordset::GetODBCFieldInfo](#getodbcfieldinfo)|レコード セットの特定の種類のフィールドの詳細についての情報を返します。|
|[CRecordset::GetRecordCount](#getrecordcount)|レコード セットのレコードの数を返します。|
|[CRecordset::GetRowsetSize](#getrowsetsize)|1 回のフェッチ中に取得するレコードの数を返します。|
|[CRecordset::GetRowsFetched](#getrowsfetched)|フェッチ中に取得される行の実際の数を返します。|
|[CRecordset::GetRowStatus](#getrowstatus)|フェッチ後に、行の状態を返します。|
|[CRecordset::GetSQL](#getsql)|レコード セットのレコードを選択するために使用する SQL 文字列を取得します。|
|[CRecordset::GetStatus](#getstatus)|レコード セットの状態を取得します。 現在のレコードとレコードの最後の数が取得されているかどうかのインデックス。|
|[CRecordset::GetTableName](#gettablename)|レコード セットの基になるテーブルの名前を取得します。|
|[CRecordset::IsBOF](#isbof)|レコード セットは、最初のレコードの前に位置付けられている場合は 0 以外を返します。 現在のレコードはありません。|
|[CRecordset::IsDeleted](#isdeleted)|レコード セットが削除されたレコードに配置されている場合は 0 以外を返します。|
|[CRecordset::IsEOF](#iseof)|レコード セットは、後の最後のレコードに位置付けられている場合は 0 以外を返します。 現在のレコードはありません。|
|[CRecordset::IsFieldDirty](#isfielddirty)|現在のレコードで指定されたフィールドが変更されている場合、0 以外の値を返します。|
|[CRecordset::IsFieldNull](#isfieldnull)|現在のレコードで指定されたフィールドが null の場合、0 以外の値を返します (値はありません)。|
|[CRecordset::IsFieldNullable](#isfieldnullable)|現在のレコードで指定したフィールドは、(値を持たない) を null に設定することができる場合、0 以外の値を返します。|
|[CRecordset::IsOpen](#isopen)|場合は 0 以外の値を返します`Open`が既に呼び出されています。|
|[CRecordset::Move](#move)|いずれかの方向で現在のレコードから指定された数のレコードをレコード セットを配置します。|
|[CRecordset::MoveFirst](#movefirst)|現在のレコードをレコード セットの最初のレコードに位置付けます。 テスト`IsBOF`最初。|
|[CRecordset::MoveLast](#movelast)|最後のレコードまたは最後の行セットは、現在のレコードを配置します。 テスト`IsEOF`最初。|
|[CRecordset::MoveNext](#movenext)|現在のレコードは、次のレコードや次の行セット上に配置します。 テスト`IsEOF`最初。|
|[CRecordset::MovePrev](#moveprev)|前のレコードまたは前の行セットは、現在のレコードを配置します。 テスト`IsBOF`最初。|
|[CRecordset::OnSetOptions](#onsetoptions)|指定された ODBC ステートメントのオプション (選択に使用される) を設定すると呼ばれます。|
|[CRecordset::OnSetUpdateOptions](#onsetupdateoptions)|指定された ODBC ステートメントのオプション (更新プログラムで使用される) を設定すると呼ばれます。|
|[:Open](#open)|テーブルを取得するか、レコードセットが表すクエリを実行して、レコードセットを開きます。|
|[CRecordset::RefreshRowset](#refreshrowset)|データと指定した行の状態を更新します。|
|[CRecordset::Requery](#requery)|選択したレコードを更新するには、もう一度、レコード セットのクエリを実行します。|
|[CRecordset::SetAbsolutePosition](#setabsoluteposition)|指定されたレコードの数に対応するレコードをレコード セットを配置します。|
|[CRecordset::SetBookmark](#setbookmark)|ブックマークで指定されたレコードをレコード セットを配置します。|
|[CRecordset::SetFieldDirty](#setfielddirty)|変更されたものとしては、現在のレコードで指定したフィールドをマークします。|
|[CRecordset::SetFieldNull](#setfieldnull)|Null (値がない) には、現在のレコードで指定されたフィールドの値を設定します。|
|[CRecordset::SetLockingMode](#setlockingmode)|ロック モードを「オプティミスティック」(既定値) をロックまたは「ペシミスティック」ロックを設定します。 更新プログラムのレコードをロックする方法を決定します。|
|[CRecordset::SetParamNull](#setparamnull)|指定されたパラメーターを null (値がない) に設定します。|
|[CRecordset::SetRowsetCursorPosition](#setrowsetcursorposition)|行セット内の指定した行にカーソルを位置付けます。|
|[CRecordset::SetRowsetSize](#setrowsetsize)|フェッチ中に取得するレコードの数を指定します。|
|[CRecordset::Update](#update)|完了すると、`AddNew`または`Edit`データ ソースの新規または編集されたデータを保存することで操作します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CRecordset::m_hstmt](#m_hstmt)|レコード セットの ODBC ステートメント ハンドルを格納します。 「`HSTMT`」と入力します。|
|[CRecordset::m_nFields](#m_nfields)|レコード セットのフィールド データ メンバーの数が含まれています。 「`UINT`」と入力します。|
|[CRecordset::m_nParams](#m_nparams)|レコード セットのパラメーターのデータ メンバーの数が含まれています。 「`UINT`」と入力します。|
|[CRecordset::m_pDatabase](#m_pdatabase)|ポインターが含まれています、`CDatabase`オブジェクトにより、レコード セットはデータ ソースに接続します。|
|[CRecordset::m_strFilter](#m_strfilter)|含まれています、 `CString` Structured Query Language (SQL) を指定する`WHERE`句。 フィルターとして使用すると、特定の条件を満たすレコードだけを選択します。|
|[CRecordset::m_strSort](#m_strsort)|含まれています、 `CString` SQL を指定する`ORDER BY`句。 レコードの並べ替え方法を制御するために使用します。|

## <a name="remarks"></a>Remarks

「レコード セット」と呼ばれる`CRecordset`オブジェクトは、2 つの形式で通常使用: ダイナセットを使う場合とスナップショット。 ダイナセットはまだ他のユーザーが行ったデータの更新を同期します。 スナップショットは、データの静的ビューです。 各フォームはレコードをレコード セットが開かれたときに固定のセットを表しますが、ダイナセットでレコードをスクロールすると、他のユーザーまたはアプリケーションで他のレコード セットのいずれかのレコードに加えられた変更が反映されます。

> [!NOTE]
>  Open Database Connectivity (ODBC) クラスではなく、データ アクセス オブジェクト (DAO) クラスを使用している場合は、クラスを使用して[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)代わりにします。 詳細については、この記事を参照してください。[概要。データベース プログラミング](../../data/data-access-programming-mfc-atl.md)します。

レコード セットのいずれかの種類を使用する通常クラスを派生する、アプリケーション固有のレコード セットから`CRecordset`します。 レコード セットは、データ ソースからレコードを選択しを選択できます。

- レコードをスクロールします。

- レコードを更新し、ロックのモードを指定します。

- データ ソースで利用可能なからを選択するレコードを制限するレコード セットをフィルター処理します。

- レコード セットを並べ替えます。

- 実行時までわからない情報を使用して選択をカスタマイズするレコード セットをパラメーター化します。

クラスを使用するデータベースを開くし、コンス トラクターへのポインターを渡して、レコード セット オブジェクトを構築、`CDatabase`オブジェクト。 まず、レコード セットの`Open`メンバー関数、オブジェクトがダイナセットまたはスナップショットであるかどうかを指定できます。 呼び出す`Open`データ ソースからデータを選択します。 レコード セット オブジェクトが開かれた後に、レコードをスクロールし、それを操作するそのメンバー関数とデータ メンバーを使用します。 使用可能な操作かどうか、オブジェクトが異なりますダイナセットか、スナップショットは更新可能または読み取り専用かどうか (このオープン データベース コネクティビティ (ODBC) のデータ ソースの機能) に依存し、バルク行フェッチを実装するかどうか。 可能性がありますが変更または追加された後のレコードを更新する、`Open`呼び出し、オブジェクトの`Requery`メンバー関数。 オブジェクトの`Close`メンバー関数をそれが完了したら、オブジェクトを破棄します。

派生で`CRecordset`クラス、レコード フィールド エクス (チェンジ RFX) または読み取りとレコードのフィールドの更新をサポートするためにバルク レコード フィールド エクス チェンジ (Bulk RFX) を使用します。

レコード セットとレコード フィールド エクス チェンジの詳細については、記事をご覧ください。[概要。データベース プログラミング](../../data/data-access-programming-mfc-atl.md)、 [(Odbc)](../../data/odbc/recordset-odbc.md)、[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)、および[レコード フィールド エクス (チェンジ RFX)](../../data/odbc/record-field-exchange-rfx.md)します。 ダイナセットを使う場合のスナップショットに重点を置いて、記事をご覧ください。[ダイナセット](../../data/odbc/dynaset.md)と[スナップショット](../../data/odbc/snapshot.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CRecordset`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

##  <a name="addnew"></a>  CRecordset::AddNew

テーブルに新しいレコードを追加するために準備します。

```
virtual void AddNew();
```

### <a name="remarks"></a>Remarks

呼び出す必要があります、 [Requery](#requery)メンバー関数を新しく追加したレコードを参照してください。 レコードのフィールドが最初に Null です。 (データベース用語では、Null「値を持たない」手段と C++ では NULL の場合と同じではありません)。操作を完了するには、呼び出す必要がある、 [Update](#update)メンバー関数。 `Update` データ ソースに変更を保存します。

> [!NOTE]
>  バルク行フェッチを実装した場合を呼び出すことはできません`AddNew`します。 これにより、失敗したアサーションが発生します。 クラス`CRecordset`メカニズムが用意されていないデータの一括行を更新するには、ODBC API 関数を使用して、独自の関数を記述することができます`SQLSetPos`します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

`AddNew` レコード セットのフィールド データ メンバーを使用して、新しい空のレコードを準備します。 呼び出した後`AddNew`、レコード セットのフィールド データ メンバーで使用値を設定します。 (を呼び出す必要はありません、[編集](#edit)この目的のためのメンバー関数は使用`Edit`の既存のレコードのみ)。関数を呼び出すと`Update`、変更、フィールド データ メンバーの値は、データ ソースに保存されます。

> [!CAUTION]
>  呼び出す前に新しいレコードをスクロールする`Update`、新しいレコードが失われると、警告が指定されていません。

データ ソースは、トランザクションをサポートする場合は、`AddNew`トランザクションの一部を呼び出します。 トランザクションの詳細については、クラスを参照してください。 [CDatabase](../../mfc/reference/cdatabase-class.md)します。 呼び出す必要がありますので注意[CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans)呼び出す前に`AddNew`します。

> [!NOTE]
>  ダイナセットを使う場合、新しいレコードは、最後のレコードとしてレコード セットに追加されます。 追加したレコードは、スナップショットには追加されません。呼び出す必要があります`Requery`をレコード セットを更新します。

呼び出すことはできません`AddNew`レコード セットを持つ`Open`メンバー関数が呼び出されていません。 A`CDBException`を呼び出す場合にスローされる`AddNew`レコード セットに追加することはできません。 呼び出すことによって、レコード セットは更新可能かどうかを判断する[CanAppend](#canappend)します。

詳細については、次の記事を参照してください。[レコードセット: レコード セットの更新プログラムによる (ODBC) の記録](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)、[レコード セット。追加、更新、および削除 (Odbc)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)、および[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)します。

### <a name="example"></a>例

記事をご覧ください[トランザクション。レコード セット (ODBC) からのトランザクション実行](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)します。

##  <a name="canappend"></a>  CRecordset::CanAppend

新しいレコードを追加する前に開かれたレコード セットができるかどうかを判断します。

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>戻り値

レコード セットが新しいレコードを追加できる場合は 0 以外それ以外の場合 0 を返します。 `CanAppend` 読み取り専用レコード セットを開いた場合 0 を返します。

##  <a name="canbookmark"></a>  CRecordset::CanBookmark

レコード セットが、ブックマークを使用してレコードをマークすることでできるかどうかを判断します。

```
BOOL CanBookmark() const;
```

### <a name="return-value"></a>戻り値

レコード セットは、ブックマークをサポートしている場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

この関数は独立して、`CRecordset::useBookmarks`オプション、 *dwOptions*のパラメーター、[オープン](#open)メンバー関数。 `CanBookmark` 特定の ODBC ドライバーとカーソルがサポートのブックマークを入力するかどうかを示します。 `CRecordset::useBookmarks` サポートされていれば、ブックマークが使用できるかどうかを示します。

> [!NOTE]
>  ブックマークは順方向専用のレコード セットではサポートされていません。

ブックマークとレコード セットのナビゲーションの詳細については、記事をご覧ください。[レコード セット。ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)と[レコード セット。スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)します。

##  <a name="cancel"></a>  CRecordset::Cancel

実行中の非同期操作または 2 つ目のスレッドからのプロセスのいずれかにキャンセルするデータ ソースに要求します。

```
void Cancel();
```

### <a name="remarks"></a>Remarks

MFC ODBC クラスは、非同期処理を不要になった使用に注意してください。非同期操作を実行する ODBC API 関数を直接に呼び出す必要があります`SQLSetConnectOption`します。 詳細については、「関数の非同期実行」のトピックを参照してください、 *ODBC SDK プログラマー ガイド*します。

##  <a name="cancelupdate"></a>  CRecordset::CancelUpdate

キャンセルによって生じる更新保留中の[編集](#edit)または[AddNew](#addnew)操作の前に[Update](#update)が呼び出されます。

```
void CancelUpdate();
```

### <a name="remarks"></a>Remarks

> [!NOTE]
>  このメンバー関数はバルク行フェッチ、このようなレコード セットを呼び出すことはできませんのでを使用しているレコード セットに適用可能でない`Edit`、 `AddNew`、または`Update`します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

自動ダーティ フィールド チェックが有効になっている場合`CancelUpdate`メンバー変数を前の値に復元されます`Edit`または`AddNew`が呼び出された場合は、任意の値の変更は保持されます。 既定では、フィールドの自動チェックが有効になっているレコード セットを開いたときにします。 指定する必要がありますそれを無効にする、`CRecordset::noDirtyFieldCheck`で、 *dwOptions*のパラメーター、[オープン](#open)メンバー関数。

データの更新の詳細については、記事を参照してください。[レコード セット。追加、更新、および削除 (Odbc)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)します。

##  <a name="canrestart"></a>  CRecordset::CanRestart

レコード セットでは、(そのレコードを更新) するためには、そのクエリを呼び出すことによって再起動できるかどうかを決定する、`Requery`メンバー関数。

```
BOOL CanRestart() const;
```

### <a name="return-value"></a>戻り値

再クエリが使用できる場合、0 以外の場合それ以外の場合 0 を返します。

##  <a name="canscroll"></a>  CRecordset::CanScroll

レコード セットでは、スクロールできるかどうかを判断します。

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>戻り値

レコード セットがスクロールできる場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

スクロールの詳細については、記事を参照してください。[レコード セット。スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)します。

##  <a name="cantransact"></a>  CRecordset::CanTransact

レコード セットにトランザクションができるかどうかを判断します。

```
BOOL CanTransact() const;
```

### <a name="return-value"></a>戻り値

レコード セットがトランザクションを許可する場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

詳細については、この記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)します。

##  <a name="canupdate"></a>  CRecordset::CanUpdate

レコード セットを更新できるかどうかを判断します。

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>戻り値

レコード セットが更新できる場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

レコード セットは、その基になるデータ ソースが読み取り専用の場合、または指定した場合読み取り専用である可能性があります`CRecordset::readOnly`で、 *dwOptions*パラメーター、レコード セットを開いたときにします。

##  <a name="checkrowseterror"></a>  CRecordset::CheckRowsetError

レコードのフェッチ中にエラーを処理するために呼び出されます。

```
virtual void CheckRowsetError(RETCODE nRetCode);
```

### <a name="parameters"></a>パラメーター

*nRetCode*<br/>
ODBC API 関数には、コードが返されます。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>Remarks

この仮想メンバー関数は、レコードは、フェッチされるときに発生するエラーを処理中に、バルク行フェッチときに便利です。 オーバーライドを検討することも`CheckRowsetError`独自のエラー処理を実装します。

`CheckRowsetError` 自動的に呼び出されるカーソルのナビゲーション操作でなど`Open`、 `Requery`、または any`Move`操作。 ODBC API 関数の戻り値が渡される`SQLExtendedFetch`します。 次の表に、可能な値、*呼び出した*パラメーター。

|nRetCode|説明|
|--------------|-----------------|
|SQL_SUCCESS|関数は正常に完了しました追加の情報はありません。|
|SQL_SUCCESS_WITH_INFO|関数は可能性がある重大なエラーを正常に完了します。 追加情報を呼び出すことによって取得できる`SQLError`します。|
|SQL_NO_DATA_FOUND|結果セットからすべての行がフェッチされました。|
|SQL_ERROR|関数が失敗しました。 追加情報を呼び出すことによって取得できる`SQLError`します。|
|SQL_INVALID_HANDLE|関数は、無効な環境ハンドルを接続ハンドルでは、ステートメント ハンドルの理由により失敗しました。 これは、プログラミング エラーを示します。 追加情報が利用できない`SQLError`します。|
|SQL_STILL_EXECUTING|非同期的に開始された関数が実行中です。 既定では、MFC が決して合格するには、この値に注意してください`CheckRowsetError`;。MFC の呼び出しは引き続き`SQLExtendedFetch`SQL_STILL_EXECUTING が返されなくなるまでです。|

詳細については`SQLError`、Windows SDK を参照してください。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

##  <a name="close"></a>  CRecordset::Close

レコード セットを閉じます。

```
virtual void Close();
```

### <a name="remarks"></a>Remarks

ODBC HSTMT とレコード セットに割り当てられた、framework のすべてのメモリを解放します。 通常は後で呼び出す`Close`で割り当てられた場合は、C++ のレコード セット オブジェクトを削除する**新しい**します。

呼び出すことができます`Open`呼び出した後でもう一度`Close`します。 これにより、レコード セット オブジェクトを再利用できます。 呼び出す場合は`Requery`します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#17](../../mfc/codesnippet/cpp/crecordset-class_1.cpp)]

##  <a name="crecordset"></a>  CRecordset::CRecordset

`CRecordset` オブジェクトを構築します。

```
CRecordset(CDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>パラメーター

*pDatabase*<br/>
ポインターが含まれています、`CDatabase`オブジェクトまたは値が NULL です。 NULL でない場合、`CDatabase`オブジェクトの`Open`データ ソースに接続するメンバー関数が呼び出されていない、レコード セットが、独自の中を開くしようとしています。`Open`呼び出します。 Null チェックを実行する場合、`CDatabase`オブジェクトが構築され、ClassWizard でレコード セット クラスを派生するときに指定したデータ ソース情報を使用して接続します。

### <a name="remarks"></a>Remarks

使用するか`CRecordset`直接または、アプリケーション固有のクラスから派生した`CRecordset`します。 ClassWizard を使用して、レコード セット クラスを派生させることができます。

> [!NOTE]
>  派生クラス*する必要があります*独自のコンス トラクターを指定します。 派生クラスのコンス トラクターでコンス トラクターを呼び出す`CRecordset::CRecordset`に沿った適切なパラメーターを渡します。

レコード セットのコンス トラクターに NULL を渡す、`CDatabase`オブジェクトが構築され、自動的に結合します。 これは便利な簡単な構築し、接続を必要としない、`CDatabase`レコード セットを作成する前にオブジェクト。

### <a name="example"></a>例

詳細については、この記事を参照してください。[レコード セット。クラスの宣言 (ODBC) テーブル](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)します。

##  <a name="delete"></a>  CRecordset::Delete

現在のレコードを削除します。

```
virtual void Delete();
```

### <a name="remarks"></a>Remarks

削除が成功した後、レコード セットのフィールド データ メンバーは、Null 値に設定されのいずれかを明示的に呼び出す必要があります、`Move`削除されたレコードを移動するために機能します。 削除されたレコードを移行した後に戻ることはできません。 データ ソースは、トランザクションをサポートする場合は、`Delete`トランザクションの一部を呼び出します。 詳細については、この記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)します。

> [!NOTE]
>  バルク行フェッチを実装した場合を呼び出すことはできません`Delete`します。 これにより、失敗したアサーションが発生します。 クラス`CRecordset`メカニズムが用意されていないデータの一括行を更新するには、ODBC API 関数を使用して、独自の関数を記述することができます`SQLSetPos`します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

> [!CAUTION]
>  レコード セットは更新可能である必要がありする必要がありますがある有効なレコードの現在のレコード セットを呼び出すとき`Delete`、それ以外のエラーが発生します。 たとえば、レコードを削除しても、呼び出す前に新しいレコードをスクロールしません`Delete`、もう一度`Delete`がスローされます、 [CDBException](../../mfc/reference/cdbexception-class.md)します。

異なり[AddNew](#addnew)と[編集](#edit)への呼び出し`Delete`への呼び出しによってに従わない[Update](#update)します。 場合、`Delete`呼び出しが失敗した場合は、変更されていないフィールドのデータ メンバーのままにします。

### <a name="example"></a>例

この例では、関数のフレームで作成されたレコード セットを示します。 例では、ことを想定の`m_dbCust`、型のメンバー変数`CDatabase`既にデータ ソースに接続されています。

[!code-cpp[NVC_MFCDatabase#18](../../mfc/codesnippet/cpp/crecordset-class_2.cpp)]

##  <a name="dobulkfieldexchange"></a>  CRecordset::DoBulkFieldExchange

データ ソースからレコード セットへのデータのバルク行と呼ばれます。 実装はバルク レコード フィールド エクス チェンジ (Bulk RFX) します。

```
virtual void DoBulkFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
ポインターを[CFieldExchange](../../mfc/reference/cfieldexchange-class.md)オブジェクト。 フレームワークは、フィールド交換操作のコンテキストを指定する、このオブジェクトは、既に設定があります。

### <a name="remarks"></a>Remarks

バルク行フェッチを実装すると、フレームワークは、レコード セット オブジェクトにデータ ソースからデータを自動的に転送するには、このメンバー関数を呼び出します。 `DoBulkFieldExchange` レコード セットの選択用の SQL ステートメントの文字列内のパラメーターのプレース ホルダーに存在する場合も、パラメーターのデータ メンバーをバインドします。

バルク行フェッチが実装されていない場合、フレームワーク[DoFieldExchange](#dofieldexchange)します。 バルク行フェッチを実装することを指定する必要があります、`CRecordset::useMultiRowFetch`のオプション、 *dwOptions*パラメーター、[オープン](#open)メンバー関数。

> [!NOTE]
> `DoBulkFieldExchange` 派生したクラスを使用している場合にのみ使用できますが`CRecordset`します。 直接、レコード セット オブジェクトを作成した場合`CRecordset`、呼び出す必要があります、 [GetFieldValue](#getfieldvalue)データを取得します。

バルク レコード フィールド エクス チェンジ (Bulk RFX) は、レコード フィールド エクス (チェンジ RFX) に似ています。 データは、レコード セット オブジェクトをデータ ソースから自動的に転送されます。 ただし、呼び出すことはできません`AddNew`、 `Edit`、 `Delete`、または`Update`変更をデータ ソースに転送します。 クラス`CRecordset`現在一括データの行を更新するメカニズムが用意されていませんが、ODBC API 関数を使用して、独自の関数を記述するただし、`SQLSetPos`します。

ClassWizard では、バルク レコード フィールド エクス チェンジ; はサポートされていないことに注意してください。そのため、オーバーライドする必要があります`DoBulkFieldExchange`バルク RFX 関数の呼び出しを記述して手動でします。 これらの関数の詳細については、トピックを参照してください。[レコード フィールド エクス チェンジ関数](../../mfc/reference/record-field-exchange-functions.md)します。

バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。 関連情報については、記事を参照してください。[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)します。

##  <a name="dofieldexchange"></a>  CRecordset::DoFieldExchange

レコード セットのフィールド データ メンバーと、データ ソースに対応するレコード間を双方向) でデータを交換するには、呼び出されます。 レコード フィールド エクス (チェンジ RFX) をを実装します。

```
virtual void DoFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>パラメーター

*pFX*<br/>
ポインターを[CFieldExchange](../../mfc/reference/cfieldexchange-class.md)オブジェクト。 フレームワークは、フィールド交換操作のコンテキストを指定する、このオブジェクトは、既に設定があります。

### <a name="remarks"></a>Remarks

バルク行フェッチが実装されていない場合、フレームワークは自動的に、レコード セット オブジェクトのフィールド データ メンバーと、データ ソースの現在のレコードの対応する列の間のデータを交換するには、このメンバー関数を呼び出します。 `DoFieldExchange` レコード セットの選択用の SQL ステートメントの文字列内のパラメーターのプレース ホルダーに存在する場合も、パラメーターのデータ メンバーをバインドします。

バルク行フェッチが実装されている場合、フレームワーク[DoBulkFieldExchange](#dobulkfieldexchange)します。 バルク行フェッチを実装することを指定する必要があります、`CRecordset::useMultiRowFetch`のオプション、 *dwOptions*パラメーター、[オープン](#open)メンバー関数。

> [!NOTE]
> `DoFieldExchange` 派生したクラスを使用している場合にのみ使用できますが`CRecordset`します。 直接、レコード セット オブジェクトを作成した場合`CRecordset`、呼び出す必要があります、 [GetFieldValue](#getfieldvalue)データを取得します。

レコード フィールド エクス チェンジ (RFX) と呼ばれるフィールドのデータの交換が双方向で機能します。 レコード セット オブジェクトをデータ ソースのレコードと、データ ソースのレコードのフィールドをレコード セット オブジェクトのフィールド データ メンバーから。

唯一のアクションを実装するために通常必要`DoFieldExchange`クラスは、派生したレコード セットを ClassWizard でクラスを作成し、フィールド データ メンバーの名前とデータ型を指定します。 ClassWizard がデータ メンバーのパラメーターを指定するかを動的にバインドする列を扱うに記述するコードを追加することも可能性があります。 詳細については、この記事を参照してください。[レコード セット。動的に結びつける方法 (ODBC) のデータ列](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)します。

ClassWizard でレコード セットの派生クラスを宣言するときに書き込まれますのオーバーライドを`DoFieldExchange`次の例のようにします。

[!code-cpp[NVC_MFCDatabase#19](../../mfc/codesnippet/cpp/crecordset-class_3.cpp)]

RFX 関数の詳細については、トピックを参照してください。[レコード フィールド エクス チェンジ関数](../../mfc/reference/record-field-exchange-functions.md)します。

さらに例と詳細`DoFieldExchange`、記事をご覧ください[レコード フィールド エクス チェンジ。RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。 RFX の詳細については、記事を参照してください。[レコード フィールド エクス チェンジ](../../data/odbc/record-field-exchange-rfx.md)します。

##  <a name="edit"></a>  CRecordset::Edit

現在のレコードを変更をできます。

```
virtual void Edit();
```

### <a name="remarks"></a>Remarks

呼び出した後`Edit`、直接その値をリセットして、フィールド データ メンバーを変更することができます。 その後に呼び出すときに、操作が完了、 [Update](#update)メンバー関数は、データ ソースで変更を保存します。

> [!NOTE]
>  バルク行フェッチを実装した場合を呼び出すことはできません`Edit`します。 これにより、失敗したアサーションが発生します。 クラス`CRecordset`メカニズムが用意されていないデータの一括行を更新するには、ODBC API 関数を使用して、独自の関数を記述することができます`SQLSetPos`します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

`Edit` レコード セットのデータ メンバーの値を保存します。 呼び出す場合`Edit`を呼び出して、変更を行う`Edit`1 つ目の前に、レコードの値を復元する、もう一度`Edit`呼び出し。

場合によっては、Null (データを含まない) ようにすることで、列を更新する場合があります。 これを行うには、呼び出す[な](#setfieldnull)マーク フィールドを Null の場合は true のパラメーターを使ってこれもにより、更新する列。 場合は、フィールドの値が変更されていない場合でも、データ ソースに書き込む、呼び出し[き](#setfielddirty)TRUE の場合のパラメーターを使用します。 これは、フィールド値が Null 場合でも機能します。

データ ソースは、トランザクションをサポートする場合は、`Edit`トランザクションの一部を呼び出します。 呼び出す必要がありますので注意[CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans)呼び出す前に`Edit`後、レコード セットが開かれているとします。 その呼び出し元にも注意してください[CDatabase::CommitTrans](../../mfc/reference/cdatabase-class.md#committrans)通話に代わるものでない`Update`を完了する、`Edit`操作。 トランザクションの詳細については、クラスを参照してください。 [CDatabase](../../mfc/reference/cdatabase-class.md)します。

現在のロック モードによって更新されるレコードをロックすることがあります`Edit`を呼び出すまで`Update`かスクロールして、別のレコードまたは中のみにロックされている可能性がありますが、`Edit`呼び出します。 ロック モードを変更する[SetLockingMode](#setlockingmode)します。

呼び出しの前に新しいレコードをスクロールする場合、現在のレコードの前の値が復元されます`Update`します。 A`CDBException`を呼び出す場合にスローされる`Edit`更新できないレコード セットまたは現在のレコードがないかどうか。

詳細については、記事をご覧ください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)と[レコード セット。レコードのロック (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#20](../../mfc/codesnippet/cpp/crecordset-class_4.cpp)]

##  <a name="flushresultset"></a>  CRecordset::FlushResultSet

複数の結果セットがある場合は、定義済みクエリ (ストアド プロシージャ) の次の結果セットを取得します。

```
BOOL FlushResultSet();
```

### <a name="return-value"></a>戻り値

取得する結果セットがある場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

呼び出す必要があります`FlushResultSet`のみ完全に終了したら、現在の結果セットの上にカーソルをします。 次の結果を呼び出して設定を取得する場合は注意`FlushResultSet`、カーソルは、その結果セットでは無効です。 呼び出す必要があります、 [MoveNext](#movenext)メンバー関数の呼び出し後`FlushResultSet`します。

呼び出す必要がある場合、定義済みのクエリは、出力パラメーターまたは入力/出力パラメーターを使用して、`FlushResultSet`返されるまで`FALSE`(値は 0)、これらのパラメーター値を取得するためにします。

`FlushResultSet` ODBC API 関数を呼び出す`SQLMoreResults`します。 場合`SQLMoreResults`、SQL_ERROR または SQL_INVALID_HANDLE を返します`FlushResultSet`例外がスローされます。 詳細については`SQLMoreResults`、Windows SDK を参照してください。

ストアド プロシージャを呼び出そうとする場合、フィールドにバインドする必要があります`FlushResultSet`します。

### <a name="example"></a>例

次のコードで`COutParamRecordset`は、 `CRecordset`-入力パラメーターと出力パラメーター、定義済みのクエリに基づいており、複数の結果セットを持つ派生オブジェクト。 構造に注意してください、 [DoFieldExchange](#dofieldexchange)をオーバーライドします。

[!code-cpp[NVC_MFCDatabase#21](../../mfc/codesnippet/cpp/crecordset-class_5.cpp)]

[!code-cpp[NVC_MFCDatabase#22](../../mfc/codesnippet/cpp/crecordset-class_6.cpp)]

##  <a name="getbookmark"></a>  CRecordset::GetBookmark

現在のレコードのブックマークの値を取得します。

```
void GetBookmark(CDBVariant& varBookmark);
```

### <a name="parameters"></a>パラメーター

*varBookmark*<br/>
参照を[CDBVariant](../../mfc/reference/cdbvariant-class.md)現在のレコード、ブックマークを表すオブジェクト。

### <a name="remarks"></a>Remarks

ブックマークが、レコード セットでサポートされているかどうかを決定するには、呼び出す[調べる](#canbookmark)します。 ブックマークで使用できるようにサポートされている場合に設定する必要があります、`CRecordset::useBookmarks`オプション、 *dwOptions*のパラメーター、[オープン](#open)メンバー関数。

> [!NOTE]
>  ブックマークはサポートされていないか使用できない場合、呼び出す`GetBookmark`例外がスローされます。 ブックマークは順方向専用のレコード セットではサポートされていません。

`GetBookmark` 現在のレコードのブックマークの値を割り当てます、`CDBVariant`オブジェクト。 別のレコードに移動した後、いつでも、そのレコードに戻って、呼び出す[SetBookmark](#setbookmark)で対応する`CDBVariant`オブジェクト。

> [!NOTE]
>  レコード セットの特定の操作の後のブックマークの有効な不要になった場合があります。 呼び出す場合など、`GetBookmark`続けて`Requery`を持つレコードを返すことはできない`SetBookmark`します。 呼び出す[CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence)を安全に呼び出すことができるかどうかを確認する`SetBookmark`します。

ブックマークとレコード セットのナビゲーションの詳細については、記事をご覧ください。[レコード セット。ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)と[レコード セット。スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)します。

##  <a name="getdefaultconnect"></a>  CRecordset::GetDefaultConnect

既定の接続文字列を取得するには、呼び出されます。

```
virtual CString GetDefaultConnect();
```

### <a name="return-value"></a>戻り値

A`CString`既定の接続文字列を格納しています。

### <a name="remarks"></a>Remarks

フレームワークは、レコード セットの基になるデータ ソースの既定の接続文字列を取得するには、このメンバー関数を呼び出します。 ClassWizard では、ClassWizard で、テーブルと列に関する情報を取得、使用して同じデータ ソースを特定することをこの関数を実装します。 便利にアプリケーションの開発中にこの既定の接続に依存します。 既定の接続は、アプリケーションのユーザーに適したできない可能性があります。 場合は、ClassWizard のバージョンを破棄すること、この関数を修正する必要があります。 接続文字列の詳細については、記事を参照してください。[データ ソース (ODBC)](../../data/odbc/data-source-odbc.md)します。

##  <a name="getdefaultsql"></a>  CRecordset::GetDefaultSQL

実行する既定の SQL 文字列を取得するには、呼び出されます。

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>戻り値

A`CString`既定の SQL ステートメントを格納しています。

### <a name="remarks"></a>Remarks

フレームワークは、レコード セットの基になる既定の SQL ステートメントを取得するには、このメンバー関数を呼び出します。 これは、テーブル名または SQL**選択**ステートメント。

直接定義する既定の SQL ステートメントで ClassWizard、レコード セット クラスを宣言することで、ClassWizard では、このタスクを実行できます。

SQL ステートメントの文字列を使用するため必要がある場合は、呼び出す`GetSQL`、開かれたときに、レコード セットのレコードを選択するために使用する SQL ステートメントが返されます。 クラスのオーバーライドで、既定の SQL 文字列を編集する`GetDefaultSQL`します。 使用して、定義済みクエリへの呼び出しを指定するなど、**呼び出す**ステートメント。 (注、編集する場合に、 `GetDefaultSQL`、変更する必要も`m_nFields`データ ソース内の列の数と一致する)。

詳細については、この記事を参照してください。[レコード セット。クラスの宣言 (ODBC) テーブル](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)します。

> [!CAUTION]
>  テーブル名が空の場合、複数のテーブル名が指定された場合、または場合、フレームワークは、テーブル名を識別できませんでしたが、**呼び出す**ステートメントを解釈できませんでした。 使用する場合に注意して、**呼び出し**ステートメントでは、中かっこの間の空白を挿入する必要があります、**呼び出し**キーワード、中かっこの前に、または前に空白を挿入する必要がありますも、 **選択**キーワード、**選択**ステートメント。

##  <a name="getfieldvalue"></a>  CRecordset::GetFieldValue

現在のレコードのフィールドのデータを取得します。

```
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

*varValu*への参照を e A、 [CDBVariant](../../mfc/reference/cdbvariant-class.md)フィールドの値を格納するオブジェクト。

*nFieldType*<br/>
フィールドの ODBC C データ型。 既定値、DEFAULT_FIELD_TYPE を使用した`GetFieldValue`次の表に基づいて、SQL データ型から C データ型を決定します。 それ以外の場合、データを直接入力または互換性のあるデータの種類の選択を指定できます。たとえば、SQL_C_CHAR に任意のデータ型を格納することができます。

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

ODBC データ型の詳細については、「SQL データ型」および Windows SDK の付録 D にある「C データ型」トピックを参照してください。

*nIndex*<br/>
フィールドの 0 から始まるインデックス。

*strValue*<br/>
参照を[CString](../../atl-mfc-shared/reference/cstringt-class.md)フィールドの値を格納するオブジェクトをフィールドのデータ型に関係なく、テキストに変換します。

### <a name="remarks"></a>Remarks

名前またはインデックスを使用して、フィールドを検索できます。 いずれかのフィールドの値を格納することができます、`CDBVariant`オブジェクトまたは`CString`オブジェクト。

バルク行フェッチを実装した場合、現在のレコードが常に行セットの最初のレコード上に配置します。 使用する`GetFieldValue`で指定された行セット内のレコード、最初に呼び出す必要があります、 [SetRowsetCursorPosition](#setrowsetcursorposition)メンバー関数は、その行セット内で目的の行にカーソルを移動します。 呼び出して`GetFieldValue`その行のできます。 バルク行フェッチを実装することを指定する必要があります、`CRecordset::useMultiRowFetch`のオプション、 *dwOptions*パラメーター、[オープン](#open)メンバー関数。

使用することができます`GetFieldValue`デザイン時に静的にバインドするのではなく、実行時にフィールドを動的に取得します。 直接、レコード セット オブジェクトを宣言した場合など、 `CRecordset`、使用する必要があります`GetFieldValue`を取得するフィールドのデータはレコード フィールド エクス チェンジ (RFX) またはバルク レコード フィールド エクス チェンジ (Bulk RFX) が実装されていません。

> [!NOTE]
>  派生することがなく、レコード セット オブジェクトを宣言する場合`CRecordset`、読み込まれた ODBC カーソル ライブラリではありません。 カーソル ライブラリでは、レコード セットは、バインドされた列を少なくとも 1 つである必要があります。ただし、使用`CRecordset`列がないが、直接バインドされます。 メンバー関数は、 [cdatabase::openex](../../mfc/reference/cdatabase-class.md#openex)と[cdatabase::open](../../mfc/reference/cdatabase-class.md#open)カーソル ライブラリが読み込まれるかどうかを制御します。

`GetFieldValue` ODBC API 関数を呼び出す`SQLGetData`します。 ドライバーは、フィールドの値の実際の長さの値 SQL_NO_TOTAL を出力する場合`GetFieldValue`例外をスローします。 詳細については`SQLGetData`、Windows SDK を参照してください。

### <a name="example"></a>例

次のサンプル コードへの呼び出しを示しています。`GetFieldValue`から直接、レコード セット オブジェクトが宣言された`CRecordset`します。

[!code-cpp[NVC_MFCDatabase#23](../../mfc/codesnippet/cpp/crecordset-class_7.cpp)]

> [!NOTE]
>  DAO クラスとは異なり`CDaoRecordset`、`CRecordset`はありません、`SetFieldValue`メンバー関数。 直接オブジェクトを作成する場合`CRecordset`、効果的に読み取り専用になります。

バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

##  <a name="getodbcfieldcount"></a>  CRecordset::GetODBCFieldCount

レコード セット オブジェクト内のフィールドの合計数を取得します。

```
short GetODBCFieldCount() const;
```

### <a name="return-value"></a>戻り値

レコード セットのフィールドの数。

### <a name="remarks"></a>Remarks

レコード セットの作成の詳細については、この記事を参照してください。[レコード セット。作成、レコード セット (ODBC) を閉じる](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)します。

##  <a name="getodbcfieldinfo"></a>  CRecordset::GetODBCFieldInfo

レコード セット内のフィールドに関する情報を取得します。

```
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
参照を`CODBCFieldInfo`構造体。

*nIndex*<br/>
フィールドの 0 から始まるインデックス。

### <a name="remarks"></a>Remarks

関数の 1 つのバージョンでは、フィールド名で検索できます。 その他のバージョンでは、インデックスを使用してフィールドを検索できます。

返される情報の詳細については、次を参照してください。、 [CODBCFieldInfo](../../mfc/reference/codbcfieldinfo-structure.md)構造体。

レコード セットの作成の詳細については、この記事を参照してください。[レコード セット。作成、レコード セット (ODBC) を閉じる](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)します。

##  <a name="getrecordcount"></a>  CRecordset::GetRecordCount

レコード セットのサイズを決定します。

```
long GetRecordCount() const;
```

### <a name="return-value"></a>戻り値

レコード セット内のレコードの数レコード セットにレコードが含まれていない場合は 0または、レコードの数を特定できない場合は-1。

### <a name="remarks"></a>Remarks

> [!CAUTION]
>  レコードの数は、"high watermark"番号が最大のレコードとして維持がまだユーザーがレコードを移動すると表示されます。 レコードの合計数は、最後のレコードを超えるユーザーが移動した後にだけ呼ばれます。 パフォーマンス上の理由から、呼び出すときに、カウントは更新されません`MoveLast`します。 自分でレコードをカウント、呼び出す`MoveNext`まで繰り返し`IsEOF`0 以外の値を返します。 使用してレコードを追加する`CRecordset:AddNew`と`Update`のカウントを増やします。 を使用してレコードを削除する`CRecordset::Delete`数が減少します。

##  <a name="getrowsetsize"></a>  CRecordset::GetRowsetSize

特定のフェッチ中に取得する行の数の現在の設定を取得します。

```
DWORD GetRowsetSize() const;
```

### <a name="return-value"></a>戻り値

特定のフェッチ中に取得する行の数。

### <a name="remarks"></a>Remarks

レコード セットを開いたときに、既定の行セット サイズは 25;、バルク行フェッチを使用している場合それ以外の場合は 1 です。

バルク行フェッチを実装することを指定する必要があります、`CRecordset::useMultiRowFetch`オプション、 *dwOptions*のパラメーター、[オープン](#open)メンバー関数。 行セット サイズの設定を変更するには、呼び出す[SetRowsetSize](#setrowsetsize)します。

バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

##  <a name="getrowsfetched"></a>  CRecordset::GetRowsFetched

フェッチ後に実際に取得されたレコード数を決定します。

```
DWORD GetRowsFetched() const;
```

### <a name="return-value"></a>戻り値

行の数は、指定されたフェッチ後にデータ ソースから取得します。

### <a name="remarks"></a>Remarks

これは、機能は、バルク行フェッチを実装するときに便利です。 行セットのサイズが通常フェッチ; から取得する行の数を示しますただし、レコード セット内の行の合計数にも影響を行セットの行の数が取得されます。 など、レコード セットに行セット サイズ設定が 4 の 10 個のレコードがある場合は、ループ レコード セットを呼び出すことによって`MoveNext`2 レコードだけ行セットの最後になります。

バルク行フェッチを実装することを指定する必要があります、`CRecordset::useMultiRowFetch`オプション、 *dwOptions*のパラメーター、[オープン](#open)メンバー関数。 行セットのサイズを指定するには、呼び出す[SetRowsetSize](#setrowsetsize)します。

バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#24](../../mfc/codesnippet/cpp/crecordset-class_8.cpp)]

##  <a name="getrowstatus"></a>  CRecordset::GetRowStatus

現在の行セット内の行の状態を取得します。

```
WORD GetRowStatus(WORD wRow) const;
```

### <a name="parameters"></a>パラメーター

*wRow*<br/>
1 から始まる位置の行の現在の行セット。 この値の範囲は 1 から行セットのサイズです。

### <a name="return-value"></a>戻り値

行の状態値。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>Remarks

`GetRowStatus` 最後の行に状態の変更を示す値を取得またはデータ ソースから取得する対応する行*wRow*がフェッチされました。 次の表は、可能性のある戻り値の一覧です。

|状態値|説明|
|------------------|-----------------|
|SQL_ROW_SUCCESS|行は変更されません。|
|SQL_ROW_UPDATED|行が更新されました。|
|SQL_ROW_DELETED になります|行が削除されました。|
|SQL_ROW_ADDED|行が追加されました。|
|SQL_ROW_ERROR|行はエラーのために取得可能ではありません。|
|SQL_ROW_NOROW であって|対応する行がない*wRow*します。|

詳細については、ODBC API 関数を参照してください。 `SQLExtendedFetch` Windows SDK に含まれています。

##  <a name="getstatus"></a>  CRecordset::GetStatus

レコード セットと最後のレコードが認識されているかどうかで現在のレコードのインデックスを調べます。

```
void GetStatus(CRecordsetStatus& rStatus) const;
```

### <a name="parameters"></a>パラメーター

*rStatus*<br/>
`CRecordsetStatus` オブジェクトへの参照。 詳細については、次の「解説」を参照してください。

### <a name="remarks"></a>Remarks

`CRecordset` インデックスを追跡しようとしていますが、特定の状況でこのできない場合があります。 参照してください[GetRecordCount](#getrecordcount)説明します。

`CRecordsetStatus`構造体は、次の形式。

```cpp
struct CRecordsetStatus
{
    long m_lCurrentRecord;
    BOOL m_bRecordCountFinal;
};
```

2 つのメンバー`CRecordsetStatus`は次の意味があります。

- `m_lCurrentRecord` 既知の場合は、現在のレコードのレコード セット内の 0 から始まるインデックスに含まれています。 インデックスを決定できない場合、このメンバーには、AFX_CURRENT_RECORD_UNDEFINED (-2) が含まれています。 場合`IsBOF`は (空のレコード セットまたは最初のレコードの前にスクロールしよう) を TRUE `m_lCurrentRecord` AFX_CURRENT_RECORD_BOF (-1) に設定されます。 最初のレコードで、このプロパティを設定を 0 に場合は、1 を記録し、2 つ目。

- `m_bRecordCountFinal` レコード セット内のレコードの合計数が特定された場合 0 以外の値。 レコード セットの先頭から開始し、呼び出すことによって、その一般にこの記述しなければならない`MoveNext`まで`IsEOF`0 以外の値を返します。 このメンバーが 0 の場合は、によって返されるレコードのカウント`GetRecordCount`-1 ではありませんが、レコードの"high watermark"カウントのみの場合。

##  <a name="getsql"></a>  CRecordset::GetSQL

このメンバー関数 get が開かれたときに、レコード セットのレコードを選択するために使用された SQL ステートメントを呼び出します。

```
const CString& GetSQL() const;
```

### <a name="return-value"></a>戻り値

A **const**への参照を`CString`SQL ステートメントを格納しています。

### <a name="remarks"></a>Remarks

SQL はこれが、一般に**選択**ステートメント。 によって返される文字列`GetSQL`は読み取り専用です。

によって返される文字列`GetSQL`通常とは異なる任意の文字列でレコード セットに渡した場合がありますが、 *lpszSQL*パラメーターを`Open`メンバー関数。 これは、レコード セットに渡される内容に基づく完全な SQL ステートメントを作成するため`Open`、どのような場合がありますで指定した ClassWizard で指定した、`m_strFilter`と`m_strSort`データ メンバー、および必要に応じて任意のパラメーター指定します。 レコード セットがこの SQL ステートメントを作成する方法の詳細については、情報の記事を参照してください。[レコード セット。レコード選択による (ODBC) の記録](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)します。

> [!NOTE]
>  このメンバー関数を呼び出した後にのみ呼び出す[オープン](#open)します。

##  <a name="gettablename"></a>  CRecordset::GetTableName

レコード セットのクエリの基になる SQL テーブルの名前を取得します。

```
const CString& GetTableName() const;
```

### <a name="return-value"></a>戻り値

A **const**への参照を`CString`テーブルを格納しているレコード セットがテーブルに基づく。 それ以外の場合、空の文字列の名前。

### <a name="remarks"></a>Remarks

`GetTableName` のみ、レコード セットが複数のテーブルまたは定義済みクエリ (ストアド プロシージャ) の結合ではなく、テーブルに基づいている場合に有効です。 名前とは、読み取り専用です。

> [!NOTE]
>  このメンバー関数を呼び出した後にのみ呼び出す[オープン](#open)します。

##  <a name="isbof"></a>  CRecordset::IsBOF

レコード セットは、最初のレコードの前に位置付けられている場合は 0 以外を返します。 現在のレコードはありません。

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>戻り値

レコード セットにレコードが含まれていない場合、または最初のレコードの前にスクロールした場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

レコードからレコードについては、レコード セットの最初のレコードの前に位置しているかどうかにスクロールする前に、このメンバー関数を呼び出します。 使用することも`IsBOF`と共に`IsEOF`をレコード セットにレコードがかが空かどうかを判断します。 呼び出した後にすぐに`Open`、レコード セットにレコードが含まれていない場合は、 `IsBOF` 0 以外の値を返します。少なくとも 1 つのレコードがレコード セットを開くと、最初のレコードは、現在のレコードと`IsBOF`0 を返します。

最初のレコードが現在のレコードを呼び出す場合`MovePrev`、`IsBOF`後以外を返します。 場合`IsBOF`呼び出す 0 以外を返しますと`MovePrev`エラーが発生します。 場合`IsBOF`戻り値は 0 以外の場合、現在のレコードが定義されていないと、現在のレコードを必要とする任意のアクション、エラーが発生します。

### <a name="example"></a>例

この例では`IsBOF`と`IsEOF`双方向でレコード セットをコードがスクロールすると、レコード セットの制限を検出するためにします。

[!code-cpp[NVC_MFCDatabase#25](../../mfc/codesnippet/cpp/crecordset-class_9.cpp)]

##  <a name="isdeleted"></a>  CRecordset::IsDeleted

現在のレコードが削除されたかどうかを判断します。

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>戻り値

レコード セットが削除済みのレコードに配置されている場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

レコードをスクロールする場合と`IsDeleted`TRUE (0 以外) が返されますし、その他のレコード セットの操作を実行する前に、別のレコードをスクロールする必要があります。

結果`IsDeleted`レコード セットを指定するかどうかが、更新可能かどうか、レコード セットの種類など、さまざまな要因によって異なります、`CRecordset::skipDeletedRecords`オプションがあるかどうかと、ドライバー パック、レコードを削除するかどうか、レコード セットが開かれたときに複数のユーザー。

詳細については`CRecordset::skipDeletedRecords`し、梱包、ドライバーを参照してください、[オープン](#open)メンバー関数。

> [!NOTE]
>  バルク行フェッチを実装した場合は、呼び出す必要はありません`IsDeleted`します。 代わりに、 [GetRowStatus](#getrowstatus)メンバー関数。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

##  <a name="iseof"></a>  CRecordset::IsEOF

レコード セットは、後の最後のレコードに位置付けられている場合は 0 以外を返します。 現在のレコードはありません。

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>戻り値

レコード セットにレコードが含まれていない場合、または最後のレコードより後にスクロールする場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

レコードからレコードについては、レコード セットの最後のレコードを越えているかどうかにスクロールするには、このメンバー関数を呼び出します。 使用することも`IsEOF`をレコード セットにレコードがかが空かどうかを判断します。 呼び出した後にすぐに`Open`、レコード セットにレコードが含まれていない場合は、 `IsEOF` 0 以外の値を返します。 少なくとも 1 つのレコードがレコード セットを開くと、最初のレコードは、現在のレコードと`IsEOF`0 を返します。

呼び出すときに、最後のレコードが現在のレコードがかどうか`MoveNext`、`IsEOF`後以外を返します。 場合`IsEOF`呼び出す 0 以外を返しますと`MoveNext`エラーが発生します。 場合`IsEOF`戻り値は 0 以外の場合、現在のレコードが定義されていないと、現在のレコードを必要とする任意のアクション、エラーが発生します。

### <a name="example"></a>例

例をご覧ください[IsBOF](#isbof)します。

##  <a name="isfielddirty"></a>  CRecordset::IsFieldDirty

以降、指定されたフィールド データ メンバーが変更されたかどうかを判断します[編集](#edit)または[AddNew](#addnew)が呼び出されました。

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>パラメーター

*現在価値*<br/>
チェック、またはフィールドのいずれがダーティかどうかを判断する場合は NULL を状態フィールド データ メンバーへのポインター。

### <a name="return-value"></a>戻り値

呼び出した後、指定されたフィールド データ メンバーが変更された場合は 0 以外`AddNew`または`Edit`。 それ以外の場合に 0 です。

### <a name="remarks"></a>Remarks

すべてのダーティ フィールド データ メンバー内のデータ転送されます、レコードをデータ ソースへの呼び出しによって、現在のレコードが更新されたときに、 [Update](#update)のメンバー関数`CRecordset`(の呼び出しに続く`Edit`または`AddNew`).

> [!NOTE]
>  このメンバー関数では、バルク行フェッチを使用しているレコード セットに適用されません。 実装している場合、バルク行フェッチし`IsFieldDirty`は常に FALSE を返し、失敗したアサーションになります。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

呼び出す`IsFieldDirty`への呼び出しの前の効果はリセット[き](#setfielddirty)フィールドのダーティ状態が再評価されるためです。 `AddNew`場合は、擬似 null 値では、現在のフィールドの値と異なる場合、フィールド ステータスが設定ダーティです。 `Edit`場合は、フィールドの値は、フィールドの状態がダーティに設定し、キャッシュされた値とは異なります。 します。

`IsFieldDirty` によって実装[DoFieldExchange](#dofieldexchange)します。

ダーティ フラグの詳細については、記事を参照してください。[レコード セット。レコード選択による (ODBC) の記録](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)します。

##  <a name="isfieldnull"></a>  CRecordset::IsFieldNull

現在のレコードで指定されたフィールドが Null の場合、0 以外の値を返します (値はありません)。

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>パラメーター

*現在価値*<br/>
チェック、またはフィールドのいずれかが Null であるかどうかを判断する場合は NULL を状態フィールド データ メンバーへのポインター。

### <a name="return-value"></a>戻り値

指定したフィールドのデータ メンバーが Null としてフラグが設定された場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

レコード セットの指定したフィールドのデータ メンバーを Null としてマークされているかどうかを判断するには、このメンバー関数を呼び出します。 (データベース用語では、Null「値を持たない」手段と C++ では NULL の場合と同じではありません)。フィールド データ メンバーが Null としてフラグが設定した場合は、対象の値がない現在のレコードの列として解釈されます。

> [!NOTE]
>  このメンバー関数では、バルク行フェッチを使用しているレコード セットに適用されません。 実装している場合、バルク行フェッチし`IsFieldNull`は常に FALSE を返し、失敗したアサーションになります。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

`IsFieldNull` によって実装[DoFieldExchange](#dofieldexchange)します。

##  <a name="isfieldnullable"></a>  CRecordset::IsFieldNullable

現在のレコードで指定されたフィールドに設定できます Null (値がない) 場合は 0 以外を返します。

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>パラメーター

*現在価値*<br/>
チェック、または Null 値に設定するかどうか、フィールドのいずれかを判断する場合は NULL を状態フィールド データ メンバーへのポインター。

### <a name="remarks"></a>Remarks

指定したフィールドのデータ メンバーは"null 値を許容"するかどうかを判断する (できますに設定する、Null 値です。 このメンバー関数を呼び出すC++ の NULL でないと null の場合、つまり、データベース用語では、同じ「値を持たない」)。

> [!NOTE]
>  バルク行フェッチを実装した場合を呼び出すことはできません`IsFieldNullable`します。 代わりに、 [GetODBCFieldInfo](#getodbcfieldinfo)メンバー関数は、フィールドを Null 値に設定できるかどうかを判断します。 いつでも呼び出すことに注意してください`GetODBCFieldInfo`バルク行フェッチを実装するかどうかに関係なく、します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

Null 値はフィールド値が必要です。 このようなフィールドを追加またはレコードを更新する場合は Null に設定しようとすると、データ ソースは、追加または更新を拒否し、[更新](#update)例外がスローされます。 呼び出すときに、例外が発生した`Update`を呼び出すときではなく、[な](#setfieldnull)します。

NULL を使用して、関数の最初の引数は、関数にのみ適用されます`outputColumn`フィールド、いない`param`フィールド。 たとえば、呼び出し

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

設定時のみが`outputColumn`フィールドを NULL です。`param`フィールドが影響を受けません。

作業する`param`フィールド、個人の実際のアドレスを指定する必要があります`param`など、作業します。

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

つまり、すべてを設定することはできません`param`と同様に NULL フィールド`outputColumn`フィールド。

`IsFieldNullable` によって実装[DoFieldExchange](#dofieldexchange)します。

##  <a name="isopen"></a>  CRecordset::IsOpen

レコード セットが既に開いているかを決定します。

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>戻り値

0 以外の値、レコード セット オブジェクトの[オープン](#open)または[Requery](#requery)メンバー関数が呼び出された以前とレコード セットが終了されていない。 それ以外の場合 0。

##  <a name="m_hstmt"></a>  CRecordset::m_hstmt

レコード セットに関連付けられている型 HSTMT の ODBC ステートメントのデータ構造体を識別するハンドルが含まれています。

### <a name="remarks"></a>Remarks

ODBC データ ソースには、各クエリは、HSTMT に関連付けられます。

> [!CAUTION]
>  使用しない`m_hstmt`する前に[オープン](#open)が呼び出されました。

通常、HSTMT に直接アクセスする必要はありませんが、SQL ステートメントを直接実行の必要があります。 `ExecuteSQL`クラスのメンバー関数`CDatabase`を使用する例を提供します。`m_hstmt`します。

##  <a name="m_nfields"></a>  CRecordset::m_nFields

レコード セット クラスのフィールド データ メンバーの数が含まれていますつまり、データ ソースからレコード セットが選択した列の数。

### <a name="remarks"></a>Remarks

レコード セット クラスのコンス トラクターを初期化する必要があります`m_nFields`正しい番号。 バルク行フェッチを実装していない場合、ClassWizard は、レコード セット クラスを宣言に使用するときにこの初期化を書き込みます。 手動で記述することもできます。

フレームワークでは、この番号を使用して、フィールド データ メンバーと、データ ソースの現在のレコードの対応する列の間の相互作用を管理します。

> [!CAUTION]
>  この番号は、「出力列」に登録されている数に対応する必要があります`DoFieldExchange`または`DoBulkFieldExchange`呼び出しの後に[SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype)パラメーターと共に`CFieldExchange::outputColumn`します。

この記事で説明したように、動的に列をバインドすることができます"レコード セット。動的にバインドのデータ列です。" これを行う場合は、内のカウントを増やす必要があります`m_nFields`呼び出し rfx 関数または Bulk RFX 関数の数を反映するように、`DoFieldExchange`または`DoBulkFieldExchange`動的にバインドされた列のメンバー関数。

詳細については、記事をご覧ください。[レコード セット。動的に結びつける方法 (ODBC) のデータ列](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)と[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

### <a name="example"></a>例

記事をご覧ください[レコード フィールド エクス チェンジ。RFX の使い方](../../data/odbc/record-field-exchange-using-rfx.md)します。

##  <a name="m_nparams"></a>  CRecordset::m_nParams

レコード セット クラスでパラメーターのデータ メンバーの数が含まれていますつまり、パラメーターの数は、レコード セットのクエリで渡されます。

### <a name="remarks"></a>Remarks

クラスのコンス トラクターを初期化する必要があります、レコード セット クラスにパラメーター データ メンバーがある場合は、`m_nParams`正しい番号。 値`m_nParams`既定値は 0。 パラメーターの数を反映するようにクラスのコンス トラクターで、初期化を手動で追加する必要があります (これは、手動で行う必要があります) パラメーターのデータ メンバーを追加する場合 (数とサイズ以上である必要がありますが ' 内のプレース ホルダー、`m_strFilter`または`m_strSort`文字列)。

フレームワークは、レコード セットのクエリをパラメーター化するときに、この番号を使用します。

> [!CAUTION]
>  この番号は、"params"に登録されている数に対応する必要があります`DoFieldExchange`または`DoBulkFieldExchange`呼び出しの後に[SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype)のパラメーター値を持つ`CFieldExchange::inputParam`、 `CFieldExchange::param`、 `CFieldExchange::outputParam`、または`CFieldExchange::inoutParam`.

### <a name="example"></a>例

  記事を参照して[レコード セット。レコード セット (ODBC) をパラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)と[レコード フィールド エクス。RFX の使い方](../../data/odbc/record-field-exchange-using-rfx.md)します。

##  <a name="m_pdatabase"></a>  CRecordset::m_pDatabase

ポインターが含まれています、`CDatabase`オブジェクトにより、レコード セットはデータ ソースに接続します。

### <a name="remarks"></a>Remarks

この変数は、2 つの方法で設定されます。 通常、既に接続されているにポインターを渡す`CDatabase`recordset オブジェクトを構築するときのオブジェクトします。 代わりに、NULL を渡す場合`CRecordset`作成、`CDatabase`のオブジェクトを接続します。 いずれの場合も、`CRecordset`この変数にマウス ポインターを格納します。

通常は直接不要に格納されているポインターを使用する`m_pDatabase`します。 独自の拡張機能を記述する場合`CRecordset`、ただし、ポインターを使用して必要な場合があります。 たとえば、する必要があります、ポインターをスローする場合、独自`CDBException`秒。 使用して同じ処理を実行する必要がある場合に必要なまたは`CDatabase`実行されるトランザクション、タイムアウトの設定や呼び出しなどのオブジェクト、`ExecuteSQL`クラスのメンバー関数`CDatabase`直接 SQL ステートメントを実行します。

##  <a name="m_strfilter"></a>  CRecordset::m_strFilter

呼び出す前に、レコード セット オブジェクトを構築した後、`Open`メンバー関数を格納する、このデータ メンバーを使用して、 `CString` SQL を含む**WHERE**句。

### <a name="remarks"></a>Remarks

レコード セットでは、この文字列を使用中に、選択されたレコードの制限 (またはフィルター処理) して、`Open`または`Requery`呼び出します。 これは「全販売員カリフォルニア州在住」など、レコードのサブセットを選択するために役立ちます ("の状態 = CA")。 ODBC SQL 構文、**WHERE**句は、

`WHERE search-condition`

メモを組み込んでいない、**WHERE**文字列のキーワードでします。 フレームワークを提供します。

配置することで、フィルター文字列をパラメーター化することもできます ' 内のプレース ホルダーの各プレース ホルダーをクラス内のパラメーター データ メンバーを宣言して、パラメーターを渡すことで、レコード セットを実行します。 これにより、実行時にフィルターを作成できます。 詳細については、この記事を参照してください。[レコード セット。レコード セット (ODBC) をパラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)します。

SQL の詳細については**WHERE**句は、記事をご覧ください。 [SQL](../../data/odbc/sql.md)します。 選択して、レコードのフィルター処理する方法の詳細については、記事を参照してください。[レコード セット。レコード (ODBC) のフィルター処理](../../data/odbc/recordset-filtering-records-odbc.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#30](../../mfc/codesnippet/cpp/crecordset-class_12.cpp)]

##  <a name="m_strsort"></a>  CRecordset::m_strSort

呼び出す前に、レコード セット オブジェクトを構築した後、`Open`メンバー関数を格納する、このデータ メンバーを使用して、 `CString` SQL を含む**ORDER BY**句。

### <a name="remarks"></a>Remarks

レコード セットは、この文字列を使用して、並べ替え中に、選択されたレコード、`Open`または`Requery`呼び出します。 1 つまたは複数の列でレコード セットを並べ替えるには、この機能を使用することができます。 ODBC SQL 構文、 **ORDER BY**句は、

`ORDER BY sort-specification [, sort-specification]...`

ここで、並べ替え仕様は、整数または列の名前です。 並べ替え文字列の列リストに"ASC"または"DESC"が追加された (既定では、順序は昇順です)、昇順または降順の順序を指定することもできます。 選択されたレコードは、2 番目で、次の最初の列を表示するには、最初に並べ替えられます。 たとえば、姓、名の順で"Customers"レコード セットを注文する可能性があります。 表示できる列の数は、データ ソースに依存します。 詳細については、Windows SDK を参照してください。

メモを組み込んでいない、 **ORDER BY**文字列のキーワード。 フレームワークを提供します。

SQL 句の詳細については、記事を参照してください。 [SQL](../../data/odbc/sql.md)します。 レコードの並べ替えの詳細については、この記事を参照してください。[レコード セット。レコードの並べ替え (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#31](../../mfc/codesnippet/cpp/crecordset-class_13.cpp)]

##  <a name="move"></a>  CRecordset::Move

前方または後方のいずれか、レコード セット内の現在のレコード ポインターを移動します。

```
virtual void Move(
    long nRows,
    WORD wFetchType = SQL_FETCH_RELATIVE);
```

### <a name="parameters"></a>パラメーター

*nRows*<br/>
前方または後方に移動する行の数。 正の値は、レコード セットの末尾方向へ転送、移動します。 負の値は、先頭に向かって後方移動します。

*wFetchType*<br/>
行セットを決定する`Move`がフェッチされます。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>Remarks

値 0 を渡す場合*nRows*、 `Move` ; 現在のレコードを更新します。`Move`現在になります`AddNew`または`Edit`モードでは、復元する前に、現在のレコードの値と`AddNew`または`Edit`が呼び出されました。

> [!NOTE]
>  レコード セットを移動すると、削除されたレコードをスキップできません。 参照してください[CRecordset::IsDeleted](#isdeleted)詳細についてはします。 開くと、`CRecordset`で、`skipDeletedRecords`オプションを設定、`Move`アサートの場合、 *nRows*パラメーターが 0 です。 この動作には、同じデータを使用して他のクライアント アプリケーションによって削除される行の更新ができないようにします。 参照してください、 *dwOption*パラメーター[オープン](#open)の説明については`skipDeletedRecords`します。

`Move` 行セットによって、レコード セットの位置を変更します。 値に基づいて*nRows*と*wFetchType*、`Move`適切な行セットをフェッチし、最初のレコードを行セットの現在のレコード。 バルク行フェッチを実装しない場合、行セットのサイズは常に 1 です。 行セットをフェッチするときに`Move`直接呼び出し、 [CheckRowsetError](#checkrowseterror)からのフェッチで、結果としてエラーを処理するメンバー関数。

渡すと、値に応じて`Move`は他に相当`CRecordset`メンバー関数。 具体的には、値で*wFetchType*より直感的であるメンバー関数と多くの場合、現在のレコードを移動するための推奨される方法を示す可能性があります。

次の表に、可能な値*wFetchType*、行セットを`Move`はフェッチに基づいて*wFetchType*と*nRows*、および、それに相当メンバー関数に対応する*wFetchType*します。

|wFetchType|フェッチされた行セット|同等のメンバー関数|
|----------------|--------------------|--------------------------------|
|SQL_FETCH_RELATIVE (既定値)|行セットの開始*nRows*現在の行セットの最初の行から行処理されました。||
|SQL_FETCH_NEXT|次の行セット*nRows*は無視されます。|[MoveNext](#movenext)|
|SQL_FETCH_PRIOR|前の行セット*nRows*は無視されます。|[MovePrev](#moveprev)|
|SQL_FETCH_FIRST|レコード セットの最初の行セット*nRows*は無視されます。|[MoveFirst](#movefirst)|
|SQL_FETCH_LAST|レコード セットの最後の完全な行セット*nRows*は無視されます。|[MoveLast](#movelast)|
|SQL_FETCH_ABSOLUTE|場合*nRows* > 0 で始まる行セット*nRows*レコード セットの先頭から行処理されました。 場合*nRows* < 0 で始まる行セット*nRows*レコード セットの末尾から行処理されました。 場合*nRows* = 0 の場合とファイルの先頭 (BOF) の状態が返されます。|[SetAbsolutePosition](#setabsoluteposition)|
|SQL_FETCH_BOOKMARK|ブックマークの値に対応する行で始まる行セット*nRows*します。|[SetBookmark](#setbookmark)|

> [!NOTE]
>  順方向専用レコード セットの場合、`Move`は sql_fetch_next の値でのみ有効*wFetchType*します。

> [!CAUTION]
>  呼び出す`Move`レコード セットにレコードが存在しない場合は、例外をスローします。 レコード セットにレコードがあるかどうかを確認するのには、呼び出す[IsBOF](#isbof)と[IsEOF](#iseof)します。

> [!NOTE]
>  先頭またはレコード セットの末尾を越えてスクロールした場合 (`IsBOF`または`IsEOF`0 以外の値を返します) を呼び出すと、`Move`関数がスローする可能性があります、`CDBException`します。 たとえば場合、 `IsEOF` 0 以外の値を返しますと`IsBOF`していない`MoveNext`、例外がスローされますが、`MovePrev`されません。

> [!NOTE]
>  呼び出す場合`Move`現在のレコードがされている間に更新または追加、更新は警告なしに破棄します。

レコード セットのナビゲーションの詳細については、記事をご覧ください。[レコード セット。スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)と[レコード セット。ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。 関連情報については、ODBC API 関数を参照してください。 `SQLExtendedFetch` Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#28](../../mfc/codesnippet/cpp/crecordset-class_14.cpp)]

##  <a name="movefirst"></a>  CRecordset::MoveFirst

現在のレコードを最初の行セットの最初のレコードになります。

```
void MoveFirst();
```

### <a name="remarks"></a>Remarks

かどうかバルク行フェッチの実装に関係なくは、常に、レコード セットの最初のレコードです。

呼び出す必要はありません`MoveFirst`レコード セットを開いた直後後。 その時点では、(ある場合) は、最初のレコードは、現在のレコードでは自動的にします。

> [!NOTE]
>  前方スクロール専用レコードのこのメンバー関数が正しくありません。

> [!NOTE]
>  レコード セットを移動すると、削除されたレコードをスキップできません。 参照してください、 [IsDeleted](#isdeleted)詳細については、メンバー関数。

> [!CAUTION]
>  いずれかを呼び出し、`Move`レコード セットにレコードが存在しない場合、関数が例外をスローします。 レコード セットにレコードがあるかどうかを確認するのには、呼び出す`IsBOF`と`IsEOF`します。

> [!NOTE]
>  呼び出す場合、`Move`関数の現在のレコードがされている間に更新または追加、更新は警告なしに破棄します。

レコード セットのナビゲーションの詳細については、記事をご覧ください。[レコード セット。スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)と[レコード セット。ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

### <a name="example"></a>例

  例をご覧ください[IsBOF](#isbof)します。

##  <a name="movelast"></a>  CRecordset::MoveLast

現在のレコードを最後の行セット全体で最初のレコードになります。

```
void MoveLast();
```

### <a name="remarks"></a>Remarks

バルク行フェッチを実装しない場合、レコード セットがあり、行セットのサイズは 1、その`MoveLast`レコード セットの移動最後のレコードがだけです。

> [!NOTE]
>  前方スクロール専用レコードのこのメンバー関数が正しくありません。

> [!NOTE]
>  レコード セットを移動すると、削除されたレコードをスキップできません。 参照してください、 [IsDeleted](#isdeleted)詳細については、メンバー関数。

> [!CAUTION]
>  いずれかを呼び出し、`Move`レコード セットにレコードが存在しない場合、関数が例外をスローします。 レコード セットにレコードがあるかどうかを確認するのには、呼び出す`IsBOF`と`IsEOF`します。

> [!NOTE]
>  呼び出す場合、`Move`関数の現在のレコードがされている間に更新または追加、更新は警告なしに破棄します。

レコード セットのナビゲーションの詳細については、記事をご覧ください。[レコード セット。スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)と[レコード セット。ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

### <a name="example"></a>例

  例をご覧ください[IsBOF](#isbof)します。

##  <a name="movenext"></a>  CRecordset::MoveNext

現在のレコードを次の行セットの最初のレコードになります。

```
void MoveNext();
```

### <a name="remarks"></a>Remarks

バルク行フェッチを実装しない場合、レコード セットがあり、行セットのサイズは 1、その`MoveNext`単純に次のレコードに移動します。

> [!NOTE]
>  レコード セットを移動すると、削除されたレコードをスキップできません。 参照してください、 [IsDeleted](#isdeleted)詳細については、メンバー関数。

> [!CAUTION]
>  いずれかを呼び出し、`Move`レコード セットにレコードが存在しない場合、関数が例外をスローします。 レコード セットにレコードがあるかどうかを確認するのには、呼び出す`IsBOF`と`IsEOF`します。

> [!NOTE]
>  呼び出すことは推奨も`IsEOF`呼び出す前に`MoveNext`します。 たとえば、レコード セットの末尾にスクロールして`IsEOF`; 0 以外の値を返します後続の呼び出し`MoveNext`は例外をスローします。

> [!NOTE]
>  呼び出す場合、`Move`関数の現在のレコードがされている間に更新または追加、更新は警告なしに破棄します。

レコード セットのナビゲーションの詳細については、記事をご覧ください。[レコード セット。スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)と[レコード セット。ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

### <a name="example"></a>例

  例をご覧ください[IsBOF](#isbof)します。

##  <a name="moveprev"></a>  CRecordset::MovePrev

現在のレコードを前の行セットの最初のレコードになります。

```
void MovePrev();
```

### <a name="remarks"></a>Remarks

バルク行フェッチを実装しない場合、レコード セットがあり、行セットのサイズは 1、その`MovePrev`前のレコードに移動します。

> [!NOTE]
>  前方スクロール専用レコードのこのメンバー関数が正しくありません。

> [!NOTE]
>  レコード セットを移動すると、削除されたレコードをスキップできません。 参照してください、 [IsDeleted](#isdeleted)詳細については、メンバー関数。

> [!CAUTION]
>  いずれかを呼び出し、`Move`レコード セットにレコードが存在しない場合、関数が例外をスローします。 レコード セットにレコードがあるかどうかを確認するのには、呼び出す`IsBOF`と`IsEOF`します。

> [!NOTE]
>  呼び出すことは推奨も`IsBOF`呼び出す前に`MovePrev`します。 たとえば、レコード セットの先頭をスクロールした`IsBOF`; 0 以外の値を返します後続の呼び出し`MovePrev`は例外をスローします。

> [!NOTE]
>  呼び出す場合、`Move`関数の現在のレコードがされている間に更新または追加、更新は警告なしに破棄します。

レコード セットのナビゲーションの詳細については、記事をご覧ください。[レコード セット。スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)と[レコード セット。ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

### <a name="example"></a>例

  例をご覧ください[IsBOF](#isbof)します。

##  <a name="onsetoptions"></a>  CRecordset::OnSetOptions

指定された ODBC ステートメントのオプション (選択に使用される) を設定すると呼ばれます。

```
virtual void OnSetOptions(HSTMT hstmt);
```

### <a name="parameters"></a>パラメーター

*hstmt*<br/>
オプションが設定するのには、ODBC ステートメントの HSTMT します。

### <a name="remarks"></a>Remarks

呼び出す`OnSetOptions`に指定された ODBC ステートメント オプション (選択に使用される) を設定します。 フレームワークは、レコード セットの最初のオプションを設定するには、このメンバー関数を呼び出します。 `OnSetOptions` スクロール可能なカーソル、カーソルの同時実行データ ソースのサポートを決定し、レコード セットのオプションを設定します。 (一方`OnSetOptions`選択操作では使用`OnSetUpdateOptions`更新操作のために使用します)。

オーバーライド`OnSetOptions`ドライバーまたはデータ ソースに固有のオプションを設定します。 たとえば場合は、データ ソースへの排他アクセスで開くことをサポートする方が優先されます`OnSetOptions`機能を活用するためにします。

カーソルの詳細については、記事を参照してください。 [ODBC](../../data/odbc/odbc-basics.md)します。

##  <a name="onsetupdateoptions"></a>  CRecordset::OnSetUpdateOptions

指定された ODBC ステートメントのオプション (更新プログラムで使用される) を設定すると呼ばれます。

```
virtual void OnSetUpdateOptions(HSTMT hstmt);
```

### <a name="parameters"></a>パラメーター

*hstmt*<br/>
オプションが設定するのには、ODBC ステートメントの HSTMT します。

### <a name="remarks"></a>Remarks

呼び出す`OnSetUpdateOptions`に指定された ODBC ステートメント オプション (更新プログラムで使用される) を設定します。 フレームワークは、レコード セット内のレコードを更新する HSTMT が作成された後に、このメンバー関数を呼び出します。 (一方`OnSetOptions`選択操作では使用`OnSetUpdateOptions`更新操作のために使用します)。`OnSetUpdateOptions`スクロール可能なカーソル、カーソルの同時実行データ ソースのサポートを決定し、レコード セットのオプションを設定します。

オーバーライド`OnSetUpdateOptions`そのステートメントを使用してデータベースにアクセスする前に、ODBC ステートメントのオプションを設定します。

カーソルの詳細については、記事を参照してください。 [ODBC](../../data/odbc/odbc-basics.md)します。

##  <a name="open"></a>  CRecordset::Open

テーブルを取得するか、レコードセットが表すクエリを実行して、レコードセットを開きます。

```
virtual BOOL Open(
    UINT nOpenType = AFX_DB_USE_DEFAULT_TYPE,
    LPCTSTR lpszSQL = NULL,
    DWORD dwOptions = none);
```

### <a name="parameters"></a>パラメーター

*できるかどうか*<br/>
既定値、AFX_DB_USE_DEFAULT_TYPE、または使用してから、次のいずれかの値を受け入れる、 `enum OpenType`:

- `CRecordset::dynaset` 双方向のスクロールを持つレコード セット。 レコードのメンバーシップおよび順序は、レコードセットを開いたときに決定されますが、他のユーザーによるデータ値の変更は、フェッチ操作後に表示されます。 ダイナセットは、キーセット ドリブン レコードセットとも呼ばれます。

- `CRecordset::snapshot` 双方向のスクロールを持つ静的レコード セット。 レコードのメンバーシップと順序は、レコードセットを開いたときに決定されます。データ値は、レコードをフェッチしたときに決定されます。 他のユーザーが行った変更は、レコードセットを閉じてから再度開くまで表示されません。

- `CRecordset::dynamic` 双方向のスクロールを持つレコード セット。 他のユーザーが行ったメンバーシップ、順序、およびデータ値の変更は、フェッチ操作後に表示されます。 多くの ODBC ドライバーでは、この型のレコードセットはサポートされていません。

- `CRecordset::forwardOnly` 読み取り専用レコード セット前方スクロールのみです。

   `CRecordset`、既定値は`CRecordset::snapshot`します。 既定値の機構により、Visual C++ ウィザードで既定値の異なる ODBC `CRecordset` と DAO `CDaoRecordset` 両方を操作できます。

これらのレコード セットの種類の詳細については、この記事を参照してください。[レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)します。 関連情報については、「を使用してブロックし、スクロール可能なカーソル」Windows SDK の記事を参照してください。

> [!CAUTION]
>  要求した型がサポートされていない場合、例外がスローされます。

*lpszSQL*<br/>
次のいずれかを含む文字列ポインター:

- NULL のポインター。

- テーブルの名前。

- SQL**選択**ステートメント (SQL オプションで**場所**または**ORDER BY**句)。

- A**呼び出す**ステートメントの定義済みクエリ (ストアド プロシージャ) の名前を指定します。 中かっこの間にスペースを挿入しないように注意してください、**呼び出す**キーワード。

この文字列の詳細については、「解説」の表と ClassWizard のロールの説明を参照してください。

> [!NOTE]
>  結果セットの列の順序は、RFX の順序と一致する必要がありますまたはバルク RFX 関数の呼び出し、 [DoFieldExchange](#dofieldexchange)または[DoBulkFieldExchange](#dobulkfieldexchange)関数オーバーライドします。

*dwOptions*<br/>
以下に示す値の組み合わせを指定できるビットマスク。 これらの値の一部は同時に指定できません。 既定値は**none**します。

- `CRecordset::none` オプションが設定されていません。 このパラメーター値は、他のすべての値と同時に指定できません。 既定では、レコード セットを更新できる[編集](#edit)または[削除](#delete)で新しいレコードを追加できます[AddNew](#addnew)します。 更新の依存データ ソース上ではなく、*できるかどうか*オプションを指定します。 バルク追加の最適化は使用できません。 バルク行フェッチは実装されません。 削除されたレコードはレコードセットの移動中にスキップされません。 ブックマークは使用できません。 自動ダーティ フィールド チェックが実装されます。

- `CRecordset::appendOnly` 許可しない`Edit`または`Delete`レコード セットにします。 `AddNew` のみ実行できます。 このオプションは `CRecordset::readOnly` と同時に指定できません。

- `CRecordset::readOnly` 読み取り専用レコード セットを開きます。 このオプションは `CRecordset::appendOnly` と同時に指定できません。

- `CRecordset::optimizeBulkAdd` 準備された SQL ステートメントを使用して、一度に多数のレコードを追加することを最適化します。 ODBC API 関数を使用していない場合にのみ適用されます`SQLSetPos`をレコード セットを更新します。 最新の更新で、ダーティとマークされるフィールドが決まります。 このオプションは `CRecordset::useMultiRowFetch` と同時に指定できません。

- `CRecordset::useMultiRowFetch` 1 回のフェッチ操作で取得する複数の行を許可するバルク行フェッチを実装します。 これは、パフォーマンスを向上するために設計された拡張機能です。ただし、バルク レコード フィールド エクスチェンジは ClassWizard ではサポートされていません。 このオプションは `CRecordset::optimizeBulkAdd` と同時に指定できません。 指定した場合`CRecordset::useMultiRowFetch`、オプションし`CRecordset::noDirtyFieldCheck`自動的にオンになります (ダブル バッファリングは使用できません)。 前方スクロール専用レコード、オプションで`CRecordset::useExtendedFetch`自動的にオンになります。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

- `CRecordset::skipDeletedRecords` レコード セット間を移動する場合は、削除したすべてのレコードをスキップします。 これにより、特定の相対フェッチでパフォーマンスが低下します。 このオプションは前方スクロール専用レコードセットでは無効です。 呼び出す場合[移動](#move)で、 *nRows*パラメーターを 0 に設定し、`CRecordset::skipDeletedRecords`オプションを設定、`Move`アサートされます。 なお`CRecordset::skipDeletedRecords`のような*ドライバーによるパック*行を削除することを意味は、レコード セットから削除されます。 ただし、ドライバーによってレコードがパックされる場合、ユーザー自身が削除するレコードだけがスキップされます。レコードセットを開いている間に他のユーザーによって削除されたレコードはスキップされません。 `CRecordset::skipDeletedRecords` 他のユーザーによって削除された行はスキップされます。

- `CRecordset::useBookmarks` サポートされている場合、レコード セットにブックマークを使用することがあります。 ブックマークを使用すると、データの取得速度は低下しますが、データ移動のパフォーマンスが向上します。 前方スクロール専用レコードセットでは無効です。 詳細については、この記事を参照してください。[レコード セット。ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)します。

- `CRecordset::noDirtyFieldCheck` 自動のダーティ フィールド チェック (ダブル バッファリング) オフにします。 これにより、パフォーマンスは向上しますが、`SetFieldDirty` メンバー関数と `SetFieldNull` メンバー関数を呼び出して手動でフィールドをダーティとしてマークする必要があります。`CRecordset` クラスのダブル バッファリングは、`CDaoRecordset` クラスのダブル バッファリングに似ています。 ただし、`CRecordset` では、個別のフィールドに対してダブル バッファリングを有効にできません。すべてのフィールドに対して有効にするか、またはすべてのフィールドに対して無効にします。 オプションを指定する場合`CRecordset::useMultiRowFetch`、し`CRecordset::noDirtyFieldCheck`はオンになります。 ただし、、自動的に`SetFieldDirty`と`SetFieldNull`バルク行フェッチを実装したレコード セットでは使用できません。

- `CRecordset::executeDirect` 準備された SQL ステートメントを使わないでください。 パフォーマンスを向上させる場合にこのオプションを指定、`Requery`メンバー関数は呼び出されません。

- `CRecordset::useExtendedFetch` 実装`SQLExtendedFetch`の代わりに`SQLFetch`します。 これは、前方スクロール専用レコードセットに対してバルク行フェッチを実装するために設計されています。 オプションを指定する場合`CRecordset::useMultiRowFetch`順方向専用レコード セットで、`CRecordset::useExtendedFetch`自動的にオンになります。

- `CRecordset::userAllocMultiRowBuffers` ユーザーは、データの格納バッファーを割り当てられます。 独自の格納バッファーを割り当てる場合は、このオプションと一緒に `CRecordset::useMultiRowFetch` を使用します。使用しない場合、必要な格納バッファーが自動的に割り当てられます。 詳細については、この記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。 指定する`CRecordset::userAllocMultiRowBuffers`を指定せず`CRecordset::useMultiRowFetch`アサーションは失敗になります。

### <a name="return-value"></a>戻り値

0 以外の値、`CRecordset`オブジェクトが正常に開かれているそれ以外の場合は 0 [cdatabase::open](../../mfc/reference/cdatabase-class.md#open) (と呼ばれます) の場合は 0 を返します。

### <a name="remarks"></a>Remarks

レコードセットによって定義されたクエリを実行するには、このメンバー関数を呼び出す必要があります。 呼び出しの前に`Open`、レコード セット オブジェクトを構築する必要があります。

データ ソースへの接続をこのレコード セットは、呼び出す前に、レコード セットを作成する方法に依存`Open`します。 渡す場合、 [CDatabase](../../mfc/reference/cdatabase-class.md)このメンバー関数を使用して、オブジェクトがデータ ソースに接続されていないレコード セットのコンス トラクターを[GetDefaultConnect](#getdefaultconnect)しようとするデータベース オブジェクトを開きます。 コンス トラクターが構築する場合は、レコード セットのコンス トラクターに NULL を渡すと、 `CDatabase` 、オブジェクトと`Open`データベース オブジェクトの接続を試みます。 レコード セットとさまざまな状況で接続を閉じる方法の詳細については、次を参照してください。[閉じる](#close)します。

> [!NOTE]
>  `CRecordset` オブジェクトを使用したデータ ソースへのアクセスは常に共有されます。 `CDaoRecordset` クラスとは異なり、`CRecordset` オブジェクトを使用して排他アクセスでデータ ソースを開くことはできません。

呼び出すと`Open`、クエリ、通常、SQL**選択**ステートメントでは、次の表に示す条件に基づいてレコードを選択します。

|lpszSQL パラメーターの値|レコードの選択基準|例|
|------------------------------------|----------------------------------------|-------------|
|NULL|`GetDefaultSQL` の返す文字列。||
|SQL テーブル名|`DoFieldExchange` または `DoBulkFieldExchange` のテーブル リストのすべての列。|`"Customer"`|
|定義済みクエリ (ストアド プロシージャ) の名前|返すためにクエリが定義された列。|`"{call OverDueAccts}"`|
|**選択**列リスト**FROM**テーブル リスト|指定したテーブルの指定した列。|`"SELECT CustId, CustName FROM`<br /><br /> `Customer"`|

> [!CAUTION]
>  SQL 文字列に余分な空白を挿入しないでください。 中かっこの間に空白を挿入する場合など、**呼び出す**キーワード、MFC は SQL 文字列、テーブル名として誤って解釈およびに組み込む、**選択**ステートメントでは、この操作で、例外がスローされます。 同様に、定義済みクエリは、出力パラメーターを使用している場合を挿入しないでください、中かっこの間にスペース、' 記号。 中かっこの前に空白を挿入する最後に、必要があります、**を呼び出す**ステートメントまたはそれ以前、**選択**キーワード、**選択**ステートメント。

通常のプロシージャでは NULL を`Open`。 この場合、`Open`呼び出し[GetDefaultSQL](#getdefaultsql)します。 派生を使用している場合`CRecordset`クラス、 `GetDefaultSQL` ClassWizard で指定したテーブル名を提供します。 代わりに、その他の情報を `lpszSQL` パラメーターに指定できます。

渡したもの`Open`クエリの最終的な SQL 文字列を構築します (SQL も**場所**と**ORDER BY**句が追加された、`lpszSQL`渡された文字列) し実行しますクエリ。 呼び出すことによって作成された文字列を調べることができます[GetSQL](#getsql)呼び出した後`Open`します。 詳細については、レコード セットの SQL ステートメントを作成して、レコードを選択しますが、情報の記事を参照してください[レコード セット。レコード選択による (ODBC) の記録](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)します。

レコードセット クラスのフィールド データ メンバーは、選択したデータの列に結び付けられています。 いくつかのレコードが返された場合、最初のレコードが現在のレコードになります。

レコード セットは、フィルターや並べ替えなどのオプションを設定する場合を指定これらを呼び出す前に、レコード セット オブジェクトの構築後`Open`します。 レコード セットがまだ開いて後にレコード セットのレコードを更新する場合、呼び出す[Requery](#requery)します。

詳細については、その他の例を含む、記事をご覧ください。[レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)、[レコード セット。レコード選択による (ODBC) の記録](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)、および[レコード セット。作成、レコード セット (ODBC) を閉じる](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)します。

### <a name="example"></a>例

次のコード例のさまざまなフォームを表示する、`Open`呼び出します。

[!code-cpp[NVC_MFCDatabase#16](../../mfc/codesnippet/cpp/crecordset-class_15.cpp)]

##  <a name="refreshrowset"></a>  CRecordset::RefreshRowset

データと現在の行セット内の行の状態を更新します。

```
void RefreshRowset(
    WORD wRow,
    WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>パラメーター

*wRow*<br/>
1 から始まる位置の行の現在の行セット。 この値の範囲は 0 を行セットのサイズ。

*wLockType*<br/>
更新された後に行をロックする方法を示す値。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>Remarks

ゼロの値を渡す場合*wRow*、行セット内のすべての行が更新されます。

使用する`RefreshRowset`を指定してバルク行フェッチを実装する必要があります、`CRecordset::useMulitRowFetch`オプション、[オープン](#open)メンバー関数。

`RefreshRowset` ODBC API 関数を呼び出す`SQLSetPos`します。 *WLockType*パラメーターは指定した後の行のロック状態`SQLSetPos`が実行されます。 次の表に、可能な値*wLockType*します。

|wLockType|説明|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE (既定値)|ドライバーまたはデータ ソースにより、行は前に、と同じロックまたはロック解除の状態が`RefreshRowset`が呼び出されました。|
|SQL_LOCK_EXCLUSIVE|ドライバーまたはデータ ソースは、専用の行をロックします。 すべてのデータ ソースは、この種類のロックをサポートします。|
|SQL_LOCK_UNLOCK|ドライバーまたはデータ ソースには、行がロック解除します。 すべてのデータ ソースは、この種類のロックをサポートします。|

詳細については`SQLSetPos`、Windows SDK を参照してください。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

##  <a name="requery"></a>  CRecordset::Requery

(更新) を再構築、レコード セット。

```
virtual BOOL Requery();
```

### <a name="return-value"></a>戻り値

以外の場合は、レコード セットが再構築されました。それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

いくつかのレコードが返された場合、最初のレコードが現在のレコードになります。

追加と削除または他のユーザーがデータ ソースに行っているを反映するようにレコード セットの順序で呼び出すことによって、レコード セットをリビルドする必要があります`Requery`します。 レコード セットがダイナセットである場合は、または他のユーザーがその既存のレコード (ただし、追加機能ではない) を構成する更新プログラムが自動的に反映します。 呼び出す必要がある、レコード セットがスナップショットである場合は、`Requery`編集内容を他のユーザーだけでなく追加および削除を反映するようにします。

ダイナセットまたはスナップショットのいずれかを呼び出す`Requery`いつでも新しいフィルターや並べ替え、または新しいパラメーター値を使用してレコード セットを再構築します。 新しい値を割り当てることで、新しいフィルターまたは並べ替えのプロパティを設定`m_strFilter`と`m_strSort`呼び出す前に`Requery`します。 新しい値を呼び出す前にパラメーターのデータ メンバーに割り当てることで新しいパラメーターを設定`Requery`します。 フィルターと並べ替え文字列が変更されていない場合は、パフォーマンスを向上させると、クエリが再利用できます。

レコード セットを再構築に失敗した場合、レコード セットが閉じられます。 呼び出す前に`Requery`、呼び出すことによって、レコード セットを表示できるかどうかを指定できます、`CanRestart`メンバー関数。 `CanRestart` いるは限りません`Requery`は成功します。

> [!CAUTION]
>  呼び出す`Requery`を呼び出した後にのみ[オープン](#open)します。

### <a name="example"></a>例

この例では、さまざまな並べ替え順序を適用するレコード セットが再構築します。

[!code-cpp[NVC_MFCDatabase#29](../../mfc/codesnippet/cpp/crecordset-class_16.cpp)]

##  <a name="setabsoluteposition"></a>  CRecordset::SetAbsolutePosition

指定されたレコードの数に対応するレコードをレコード セットを配置します。

```
void SetAbsolutePosition(long nRows);
```

### <a name="parameters"></a>パラメーター

*nRows*<br/>
1 から始まる序数位置、現在のレコードのレコード セット。

### <a name="remarks"></a>Remarks

`SetAbsolutePosition` この序数位置に基づいて、現在のレコード ポインターを移動します。

> [!NOTE]
>  このメンバー関数は、順方向専用レコード セットでは無効です。

ODBC レコード セットの絶対位置の設定値が 1 は、レコード セットの最初のレコードを参照します。0 に設定とファイルの先頭 (BOF) の位置を指します。

負の値を渡すこともできます`SetAbsolutePosition`します。 この場合、レコード セットの位置は、レコード セットの末尾から評価されます。 たとえば、`SetAbsolutePosition( -1 )`レコード セットの最後のレコードを現在のレコード ポインターを移動します。

> [!NOTE]
>  絶対位置は、レコード番号の代わりとして使用するものではありません。 ブックマークは、まだ保持して、前のレコードが削除されたときに、レコードの位置が変更後、指定の位置を返すための推奨される方法です。 さらに、することはできませんを保証する場合は、レコード セットを再作成、を使用してSQLステートメントを使用して作成されたレコードセット内の各レコードの順序が保証されないために、特定のレコードが同じ絶対位置を持つこと**ORDER BY**句。

レコード セットのナビゲーションとブックマークの詳細については、記事をご覧ください。[レコード セット。スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)と[レコード セット。ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)します。

##  <a name="setbookmark"></a>  CRecordset::SetBookmark

指定されたブックマークを含むレコードをレコード セットを配置します。

```
void SetBookmark(const CDBVariant& varBookmark);
```

### <a name="parameters"></a>パラメーター

*varBookmark*<br/>
参照を[CDBVariant](../../mfc/reference/cdbvariant-class.md)特定のレコードのブックマークの値を格納しているオブジェクト。

### <a name="remarks"></a>Remarks

ブックマークが、レコード セットでサポートされているかどうかを決定するには、呼び出す[調べる](#canbookmark)します。 ブックマークで使用できるようにサポートされている場合に設定する必要があります、`CRecordset::useBookmarks`オプション、 *dwOptions*のパラメーター、[オープン](#open)メンバー関数。

> [!NOTE]
>  ブックマークはサポートされていないか使用できない場合、呼び出す`SetBookmark`例外がスローされます。 ブックマークは順方向専用のレコード セットではサポートされていません。

最初に現在のレコードのブックマークを取得する[GetBookmark](#getbookmark)、ブックマークの値を保存する`CDBVariant`オブジェクト。 呼び出してそのレコードを返すことができます、後で`SetBookmark`保存されているブックマークの値を使用します。

> [!NOTE]
>  レコード セットの特定の操作の後に呼び出す前に、ブックマークの永続性を確認する必要があります`SetBookmark`します。 持つブックマークを取得する場合など、`GetBookmark`を呼び出して`Requery`ブックマークは有効でなくなる可能性があります。 呼び出す[CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence)を安全に呼び出すことができるかどうかを確認する`SetBookmark`します。

ブックマークとレコード セットのナビゲーションの詳細については、記事をご覧ください。[レコード セット。ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)と[レコード セット。スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)します。

##  <a name="setfielddirty"></a>  CRecordset::SetFieldDirty

フィールド データ メンバーの変更されたレコード セットまたは変更なしのフラグを設定します。

```
void SetFieldDirty(void* pv, BOOL bDirty = TRUE);
```

### <a name="parameters"></a>パラメーター

*現在価値*<br/>
レコード セットのフィールド データ メンバーのアドレスが含まれています。 NULL の場合、レコード セット内のすべてのフィールド データ メンバーのフラグが設定されます。 (C++ の NULL は Null の場合と同じデータベース用語では、「値を持たない」を意味する)。

*bDirty*<br/>
フィールド データ メンバーは、「ダーティ」(変更) としてフラグを設定する場合は TRUE。 「クリーン」(変更されていない) としてフラグを設定する場合は、フィールド データ メンバーの場合は FALSE。

### <a name="remarks"></a>Remarks

フィールドの変更をマークすることにより、フィールドが更新されないと、SQL トラフィックの削減になります。

> [!NOTE]
>  このメンバー関数では、バルク行フェッチを使用しているレコード セットに適用されません。 実装している場合、バルク行フェッチし`SetFieldDirty`アサーションは失敗になります。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

フレームワークでは、フィールド データ メンバー レコード フィールド エクス (チェンジ RFX) メカニズムによって、データ ソースのレコードに記述が確実に変更されました。 フィールドの値を変更すると、通常フィールド ダーティ設定、自動的に呼び出す必要はめったにありません`SetFieldDirty`が、自分でことがありますようにすることも、列が明示的に更新または挿入フィールドのデータがどのような値に関係なくメンバー。

> [!CAUTION]
>  呼び出した後にのみ、このメンバー関数を呼び出す[編集](#edit)または[AddNew](#addnew)します。

NULL を使用して、関数の最初の引数は、関数にのみ適用されます`outputColumn`フィールド、いない`param`フィールド。 たとえば、呼び出し

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

設定時のみが`outputColumn`フィールドを NULL です。`param`フィールドが影響を受けません。

作業する`param`フィールド、個人の実際のアドレスを指定する必要があります`param`など、作業します。

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

つまり、すべてを設定することはできません`param`と同様に NULL フィールド`outputColumn`フィールド。

##  <a name="setfieldnull"></a>  CRecordset::SetFieldNull

Null 以外、または Null (値を持たない) として、レコード セットのフィールド データ メンバーのフラグを設定します。

```
void SetFieldNull(void* pv, BOOL bNull = TRUE);
```

### <a name="parameters"></a>パラメーター

*現在価値*<br/>
レコード セットのフィールド データ メンバーのアドレスが含まれています。 NULL の場合、レコード セット内のすべてのフィールド データ メンバーのフラグが設定されます。 (C++ の NULL は Null の場合と同じデータベース用語では、「値を持たない」を意味する)。

*bNull*<br/>
以外の値 (Null) がないものとしてフラグを設定する場合は、フィールド データ メンバー。 フィールド データ メンバーの非 Null としてフラグを設定する場合は 0 それ以外の場合。

### <a name="remarks"></a>Remarks

レコード セットに新しいレコードを追加するとすべてのフィールド データ メンバーが最初に Null 値を設定および「ダーティ」(変更) フラグが付けられます。 データ ソースからレコードを取得するときの列を既にが値か、null。

> [!NOTE]
>  バルク行フェッチを使用しているレコード セットでこのメンバー関数を呼び出さないでください。 バルク行フェッチを実装した場合は、呼び出す`SetFieldNull`アサーションは失敗になります。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

具体的には呼び出し、値を持っていない現在のレコードのフィールドを指定する場合`SetFieldNull`で*特別*Null としてフラグを TRUE に設定します。 Null フィールドが対象としてマーク済みの値を指定したい場合、単にその新しい値を設定します。 Null フラグを削除する必要はありません`SetFieldNull`します。 フィールドを Null にできるかどうかを確認するのには、呼び出す`IsFieldNullable`します。

> [!CAUTION]
>  呼び出した後にのみ、このメンバー関数を呼び出す[編集](#edit)または[AddNew](#addnew)します。

NULL を使用して、関数の最初の引数は、関数にのみ適用されます`outputColumn`フィールド、いない`param`フィールド。 たとえば、呼び出し

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

設定時のみが`outputColumn`フィールドを NULL です。`param`フィールドが影響を受けません。

作業する`param`フィールド、個人の実際のアドレスを指定する必要があります`param`など、作業します。

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

つまり、すべてを設定することはできません`param`と同様に NULL フィールド`outputColumn`フィールド。

> [!NOTE]
>  Null の場合への呼び出しにパラメーターを設定するときに`SetFieldNull`レコード セットが開かれた結果、アサーション内の前にします。 この場合は、呼び出して[SetParamNull](#setparamnull)します。

`SetFieldNull` によって実装[DoFieldExchange](#dofieldexchange)します。

##  <a name="setlockingmode"></a>  CRecordset::SetLockingMode

ロック モードを「オプティミスティック」(既定値) をロックまたは「ペシミスティック」ロックを設定します。 更新プログラムのレコードをロックする方法を決定します。

```
void SetLockingMode(UINT nMode);
```

### <a name="parameters"></a>パラメーター

*nMode*<br/>
次の値のいずれかが含まれています、 `enum LockMode`:

- `optimistic` 呼び出し中にのみ更新されるレコードをロックするオプティミスティック ロック`Update`します。

- `pessimistic` レコードがロック ペシミスティック ロックとすぐに`Edit`と呼びます。 するまでロック状態に保ちます、`Update`呼び出しが完了するか、新しいレコードに移動します。

### <a name="remarks"></a>Remarks

レコード セットが更新プログラムを使用して、2 つのレコードのロック戦略を指定する必要がある場合は、このメンバー関数を呼び出します。 既定では、レコード セットのロック モードは`optimistic`します。 より慎重に変更することができます`pessimistic`戦略をロックします。 呼び出す`SetLockingMode`を呼び出す前に、構築して、レコード セット オブジェクトを開いた後`Edit`します。

##  <a name="setparamnull"></a>  CRecordset::SetParamNull

パラメーター (値を持たない) Null または null 以外のフラグを設定します。

```
void SetParamNull(
    int nIndex,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
パラメーターの 0 から始まるインデックス。

*bNull*<br/>
場合は TRUE (既定値)、パラメーターが Null としてフラグが設定されます。 それ以外の場合、パラメーターは、非 Null としてフラグが設定されます。

### <a name="remarks"></a>Remarks

異なり[な](#setfieldnull)、呼び出すことができます`SetParamNull`レコード セットを開く前にします。

`SetParamNull` 定義済みクエリ (ストアド プロシージャ) で通常使用されます。

##  <a name="setrowsetcursorposition"></a>  CRecordset::SetRowsetCursorPosition

現在の行セット内の行にカーソルを移動します。

```
void SetRowsetCursorPosition(WORD wRow, WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>パラメーター

*wRow*<br/>
1 から始まる位置の行の現在の行セット。 この値の範囲は 1 から行セットのサイズです。

*wLockType*<br/>
更新された後に行をロックする方法を示す値。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>Remarks

バルク行フェッチを実装する場合は、レコードがフェッチされた行セットの最初のレコードが現在のレコードは、行セットで取得されます。 行セット内の別のレコードを現在のレコードにするには、するために呼び出す`SetRowsetCursorPosition`します。 たとえば、結合`SetRowsetCursorPosition`で、 [GetFieldValue](#getfieldvalue)レコード セットの任意のレコードからデータを動的に取得するメンバー関数。

使用する`SetRowsetCursorPosition`を指定してバルク行フェッチを実装する必要があります、`CRecordset::useMultiRowFetch`のオプション、 *dwOptions*パラメーター、[オープン](#open)メンバー関数。

`SetRowsetCursorPosition` ODBC API 関数を呼び出す`SQLSetPos`します。 *WLockType*パラメーターは指定した後の行のロック状態`SQLSetPos`が実行されます。 次の表に、可能な値*wLockType*します。

|wLockType|説明|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE (既定値)|ドライバーまたはデータ ソースにより、行は前に、と同じロックまたはロック解除の状態が`SetRowsetCursorPosition`が呼び出されました。|
|SQL_LOCK_EXCLUSIVE|ドライバーまたはデータ ソースは、専用の行をロックします。 すべてのデータ ソースは、この種類のロックをサポートします。|
|SQL_LOCK_UNLOCK|ドライバーまたはデータ ソースには、行がロック解除します。 すべてのデータ ソースは、この種類のロックをサポートします。|

詳細については`SQLSetPos`、Windows SDK を参照してください。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

##  <a name="setrowsetsize"></a>  CRecordset::SetRowsetSize

フェッチ中に取得するレコードの数を指定します。

```
virtual void SetRowsetSize(DWORD dwNewRowsetSize);
```

### <a name="parameters"></a>パラメーター

*dwNewRowsetSize*<br/>
特定のフェッチ中に取得する行の数。

### <a name="remarks"></a>Remarks

この仮想メンバー関数は、バルク行フェッチを使用する場合は、1 回のフェッチ中に取得する行の数を指定します。 バルク行フェッチを実装するに設定する必要があります、`CRecordset::useMultiRowFetch`オプション、 *dwOptions*のパラメーター、[オープン](#open)メンバー関数。

> [!NOTE]
>  呼び出す`SetRowsetSize`一括を実装することがなく、失敗したアサーションの行をフェッチしていますが発生します。

呼び出す`SetRowsetSize`呼び出す前に`Open`最初に、レコード セットの行セット サイズを設定します。 バルク行フェッチを実装する場合、既定の行セット サイズには 25 です。

> [!NOTE]
>  呼び出すときに警告を使用して`SetRowsetSize`します。 データの記憶域を手動で割り当てている場合 (で指定されたとおり、 `CRecordset::userAllocMultiRowBuffers` dwOptions のパラメーターのオプション`Open`) を呼び出した後、これらのストレージ バッファーを再割り当てする必要があるかどうかを確認する必要があります`SetRowsetSize`、する前にカーソルのナビゲーション操作を実行します。

行セットのサイズの現在の設定を取得するには、呼び出す[GetRowsetSize](#getrowsetsize)します。

バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

##  <a name="update"></a>  CRecordset::Update

完了すると、`AddNew`または`Edit`データ ソースの新規または編集されたデータを保存することで操作します。

```
virtual BOOL Update();
```

### <a name="return-value"></a>戻り値

以外の場合は 1 つのレコードが正常に更新されました。列が変更されていない場合は 0 それ以外の場合。 レコードが更新されない、または 1 つのレコードが更新された数より多い場合、例外がスローされます。 例外は、データ ソースにもその他のエラーに対してスローされます。

### <a name="remarks"></a>Remarks

呼び出しの後にこのメンバー関数を呼び出し、 [AddNew](#addnew)または[編集](#edit)メンバー関数。 この呼び出しが完了するために必要な`AddNew`または`Edit`操作。

> [!NOTE]
>  バルク行フェッチを実装した場合を呼び出すことはできません`Update`します。 これにより、失敗したアサーションが発生します。 クラス`CRecordset`メカニズムが用意されていないデータの一括行を更新するには、ODBC API 関数を使用して、独自の関数を記述することができます`SQLSetPos`します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット。(ODBC) バルク行フェッチ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

両方`AddNew`と`Edit`データ ソースに保存するため、追加または編集したデータが置かれているをエディット バッファーを準備します。 `Update` データを保存します。 マークまたは変更されたものとして検出されたフィールドのみ更新されます。

データ ソースは、トランザクションをサポートする場合は、`Update`呼び出し (とその対応する`AddNew`または`Edit`呼び出し)、トランザクションの一部です。 トランザクションの詳細については、記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)します。

> [!CAUTION]
>  呼び出す場合`Update`最初にいずれかの操作を呼び出すこと`AddNew`または`Edit`、`Update`スロー、`CDBException`します。 呼び出す場合`AddNew`または`Edit`、呼び出す必要があります`Update`を呼び出す前に、`Move`操作またはレコード セットまたはデータ ソース接続を閉じる前にします。 それ以外の場合、その変更は通知なしで失われます。

詳細については処理の`Update`障害、記事をご覧ください[レコード セット。レコード セットの更新プログラムによる (ODBC) の記録](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)します。

### <a name="example"></a>例

記事をご覧ください[トランザクション。レコード セット (ODBC) からのトランザクション実行](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)します。

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CDatabase クラス](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordView クラス](../../mfc/reference/crecordview-class.md)
