---
title: クラス
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
ms.openlocfilehash: ab6cde9f478dc6f2e3cb0ba5bb338a3852f083fd
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750507"
---
# <a name="crecordset-class"></a>クラス

データ ソースから選択された 1 組のレコードセットを表現します。

## <a name="syntax"></a>構文

```
class CRecordset : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[レコードセット::Cレコードセット](#crecordset)|`CRecordset` オブジェクトを構築します。 派生クラスは、このコンストラクターを呼び出すコンストラクターを提供する必要があります。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[レコードセット::新しい追加](#addnew)|新しいレコードを追加する準備をします。 追加`Update`を完了するために呼び出します。|
|[Cレコードセット::缶詰](#canappend)|メンバ関数を使用してレコードセットに新しいレコードを追加できる`AddNew`場合は、0 以外を返します。|
|[レコードセット::缶ブックマーク](#canbookmark)|レコードセットがブックマークをサポートする場合は、0 以外を返します。|
|[レコードセット::キャンセル](#cancel)|非同期操作または 2 番目のスレッドからのプロセスをキャンセルします。|
|[レコードセット::キャンセル更新](#cancelupdate)|または`AddNew``Edit`操作のため、保留中の更新をキャンセルします。|
|[レコードセット::缶リスタート](#canrestart)|レコードセットのクエリ`Requery`を再度実行するために呼び出すことができる場合は、0 以外を返します。|
|[レコードセット::缶詰](#canscroll)|レコードをスクロールできる場合は、0 以外を返します。|
|[Cレコード::缶トランスアクト](#cantransact)|データ ソースがトランザクションをサポートする場合は、0 以外を返します。|
|[Cレコード::スキャンアップデート](#canupdate)|レコードセットを更新できる場合 (レコードを追加、更新、または削除できる場合)、0 以外を返します。|
|[エラーをチェックします。](#checkrowseterror)|レコードのフェッチ中に生成されたエラーを処理するために呼び出されます。|
|[レコードセット::閉じる](#close)|レコードセットとそれに関連付けられた ODBC HSTMT を閉じます。|
|[Cレコード::D](#delete)|レコードセットから現在のレコードを削除します。 削除後に別のレコードに明示的にスクロールする必要があります。|
|[:Dレコードセット::Dバルクフィールドエクスチェンジ](#dobulkfieldexchange)|データ ソースからレコードセットにデータのバルク行を交換するために呼び出されます。 バルク レコード フィールド エクスチェンジ (Bulk RFX) を実装します。|
|[レコードセット::Dフィールドエクスチェンジ](#dofieldexchange)|レコードセットのフィールド データ メンバーとデータ ソースの対応するレコードの間でデータを (双方向で) 交換するために呼び出されます。 レコード フィールド エクスチェンジ (RFX) を実装します。|
|[レコードセット::編集](#edit)|現在のレコードに対する変更の準備をします。 編集`Update`を完了するために呼び出します。|
|[を返します。](#flushresultset)|定義済みクエリを使用する場合に、取得する別の結果セットがある場合は、0 以外を返します。|
|[を見る](#getbookmark)|レコードのブックマーク値をパラメーター オブジェクトに割り当てます。|
|[レコードセット::デフォルト接続を取得します。](#getdefaultconnect)|既定の接続文字列を取得するために呼び出されます。|
|[を使用します。](#getdefaultsql)|実行する既定の SQL 文字列を取得するために呼び出されます。|
|[レコードセット::フィールド値を取得します。](#getfieldvalue)|レコードセット内のフィールドの値を返します。|
|[レコードセット::取得ODBCフィールドカウント](#getodbcfieldcount)|レコードセット内のフィールド数を返します。|
|[レコードセット::取得ODBCフィールド情報](#getodbcfieldinfo)|レコードセット内のフィールドに関する特定の種類の情報を返します。|
|[レコードセット::レコードカウントを取得します。](#getrecordcount)|レコードセット内のレコード数を返します。|
|[レコードセット::ゲットローセットサイズ](#getrowsetsize)|1 回のフェッチ中に取得するレコードの数を返します。|
|[レコードセット::GetRowsフェッチ](#getrowsfetched)|フェッチ中に取得された実際の行数を返します。|
|[レコードセット::ゲットローステータス](#getrowstatus)|フェッチ後の行のステータスを返します。|
|[レコードセット::GetSQL](#getsql)|レコードセットのレコードを選択するために使用する SQL 文字列を取得します。|
|[レコードセット::ステータスを取得します。](#getstatus)|レコードセットの状態 (現在のレコードのインデックス、およびレコードの最終カウントが取得されたかどうか) を取得します。|
|[レコードセット::テーブル名を取得します。](#gettablename)|レコードセットの基になるテーブルの名前を取得します。|
|[レコードセット::イズブフ](#isbof)|レコードセットが最初のレコードの前に配置されている場合は、0 以外を返します。 現在のレコードが存在しません。|
|[レコードセット::削除](#isdeleted)|レコードセットが削除されたレコードに配置されている場合は、0 以外を返します。|
|[レコードセット::イセフ](#iseof)|レコードセットが最後のレコードの後に配置されている場合は、0 以外を返します。 現在のレコードが存在しません。|
|[Cレコード::イズフィールドダーティ](#isfielddirty)|現在のレコードの指定されたフィールドが変更されている場合は、0 以外を返します。|
|[レコードセット::イズフィールドヌル](#isfieldnull)|現在のレコードの指定されたフィールドが null (値がない) の場合は、0 以外を返します。|
|[レコードセット::イズフィールドNull可能](#isfieldnullable)|現在のレコードの指定されたフィールドを null (値なし) に設定できる場合は、0 以外を返します。|
|[レコードセット::IsOpen](#isopen)|前に呼び`Open`出された場合は、0 以外を返します。|
|[レコードセット::移動](#move)|レコードセットを、現在のレコードの指定した数のレコードを、いずれかの方向に移動します。|
|[レコードセット::最初に移動](#movefirst)|カレント レコードをレコードセットの最初のレコードに配置します。 最初の`IsBOF`テスト。|
|[レコードセット::移動ラスト](#movelast)|現在のレコードを最後のレコードまたは最後の行セットに配置します。 最初の`IsEOF`テスト。|
|[次に進む](#movenext)|現在のレコードを次のレコードまたは次の行セットに配置します。 最初の`IsEOF`テスト。|
|[レコードセット::ムーヴプレフ](#moveprev)|現在のレコードを前のレコードまたは前の行セットに配置します。 最初の`IsBOF`テスト。|
|[レコードセット::オンセットオプション](#onsetoptions)|指定した ODBC ステートメントのオプション (選択時に使用) を設定するために呼び出されます。|
|[レコードセット::オンセットアップデートオプション](#onsetupdateoptions)|指定した ODBC ステートメントのオプション (更新時に使用) を設定するために呼び出されます。|
|[レコードセット::オープン](#open)|テーブルを取得するか、レコードセットが表すクエリを実行して、レコードセットを開きます。|
|[レコードセット::リフレッシュローセット](#refreshrowset)|指定した行のデータとステータスを更新します。|
|[レコードセット::再クエリ](#requery)|レコードセットのクエリを再実行して、選択したレコードを更新します。|
|[レコードセット::絶対位置を設定します。](#setabsoluteposition)|指定したレコード番号に対応するレコードにレコードセットを配置します。|
|[を設定します。](#setbookmark)|ブックマークで指定されたレコードにレコードセットを配置します。|
|[Cレコード::セットフィールドダーティ](#setfielddirty)|カレント レコードの指定したフィールドに変更をマークします。|
|[レコードセット::セットフィールドNull](#setfieldnull)|現在のレコードの指定されたフィールドの値を null (値なし) に設定します。|
|[レコードセット::セットロックモード](#setlockingmode)|ロックモードを「オプティミスティック」ロック(デフォルト)または「悲観的」ロックに設定します。 更新のためにレコードをロックする方法を指定します。|
|[レコードセット::セットパラムヌル](#setparamnull)|指定したパラメーターを null (値を持たない) に設定します。|
|[カーソル位置を設定します。](#setrowsetcursorposition)|行セット内の指定した行にカーソルを移動します。|
|[セットレコード::セットローセットサイズ](#setrowsetsize)|フェッチ中に取得するレコードの数を指定します。|
|[レコードセット::更新](#update)|新規または編集`AddNew`した`Edit`データをデータ ソースに保存して、または 操作を完了します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[レコードセット::m_hstmt](#m_hstmt)|レコードセットの ODBC ステートメント ハンドルを格納します。 「`HSTMT`」と入力します。|
|[レコードセット::m_nFields](#m_nfields)|レコードセット内のフィールド データ メンバの数を格納します。 「`UINT`」と入力します。|
|[レコードセット::m_nParams](#m_nparams)|レコードセット内のパラメータ データ メンバの数を格納します。 「`UINT`」と入力します。|
|[レコードセット::m_pDatabase](#m_pdatabase)|レコードセットが`CDatabase`データ ソースに接続されているオブジェクトへのポインターを格納します。|
|[レコードセット::m_strFilter](#m_strfilter)|構造化照会`CString`言語 (SQL) 句を指定`WHERE`する を含みます。 特定の条件を満たすレコードのみを選択するためのフィルタとして使用されます。|
|[レコードセット::m_strSort](#m_strsort)|SQL `ORDER BY` `CString`句を指定するを含みます。 レコードの並べ替え方法を制御するために使用します。|

## <a name="remarks"></a><a name="remarks"></a> 解説

"レコードセット" と`CRecordset`呼ばれるオブジェクトは、通常、ダイナセットとスナップショットの 2 つの形式で使用されます。 ダイナセットは、他のユーザーが行ったデータ更新と同期されたままです。 スナップショットは、データの静的ビューです。 各フォームは、レコードセットが開かれた時点で固定されたレコードのセットを表しますが、ダイナセット内のレコードにスクロールすると、その後、他のユーザーまたはアプリケーション内の他のレコードセットによってレコードに加えられた変更が反映されます。

> [!NOTE]
> ODBC クラスではなく、データ アクセス オブジェクト (DAO) クラスを使用する場合は、代わりに[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)クラスを使用します。 詳細については、「[概要: データベース プログラミング](../../data/data-access-programming-mfc-atl.md)」を参照してください。

どちらの種類のレコードセットを使用する場合も、通常は アプリケーション固有のレコード`CRecordset`セット クラスを から派生させます。 レコードセットはデータ ソースからレコードを選択し、次のことができます。

- レコードをスクロールします。

- レコードを更新し、ロック モードを指定します。

- レコードセットをフィルタして、データ ソースで使用できるレコードから選択するレコードを制限します。

- レコードセットを並べ替えます。

- 実行時まで不明な情報で選択をカスタマイズするには、レコードセットをパラメータ化します。

クラスを使用するには、データベースを開き、オブジェクトへのポインタをコンストラクターに渡して、レコードセット`CDatabase`オブジェクトを構築します。 次に、オブジェクトがダイ`Open`ナセットかスナップショットかを指定できるレコードセットのメンバー関数を呼び出します。 呼`Open`び出しは、データ ソースからデータを選択します。 レコードセット オブジェクトを開いた後、そのメンバー関数とデータ メンバーを使用してレコードをスクロールし、操作します。 使用できる操作は、オブジェクトがダイナセットかスナップショットか、更新可能か読み取り専用か (これは、オープン・データベース接続 (ODBC) データ・ソースの機能によって異なります) およびバルク行フェッチを実装しているかどうかによって異なります。 呼び出し後に変更または追加された可能性のある`Open`レコードを更新するには、オブジェクトの`Requery`メンバー関数を呼び出します。 オブジェクトの`Close`メンバー関数を呼び出し、オブジェクトを終了すると破棄します。

派生`CRecordset`クラスでは、レコード フィールド の読み取りと更新をサポートするためにレコード フィールド エクスチェンジ (RFX) またはバルク レコード フィールド エクスチェンジ (Bulk RFX) を使用します。

レコードセットとレコード フィールドエクスチェンジの詳細については、「[概要: データベース プログラミング](../../data/data-access-programming-mfc-atl.md)」、「[レコードセット (ODBC)」、「](../../data/odbc/recordset-odbc.md)[レコードセット: レコードの一括フェッチ (ODBC)」、「](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)[レコード フィールド エクスチェンジ (RFX)」](../../data/odbc/record-field-exchange-rfx.md)を参照してください。 ダイナセットとスナップショットに焦点を当てるには、記事[ダイナセット](../../data/odbc/dynaset.md)と[スナップショット](../../data/odbc/snapshot.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CRecordset`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="crecordsetaddnew"></a><a name="addnew"></a>レコードセット::新しい追加

テーブルに新しいレコードを追加する準備をします。

```
virtual void AddNew();
```

### <a name="remarks"></a>解説

新しく追加されたレコードを表示するには[、Requery](#requery)メンバー関数を呼び出す必要があります。 レコードのフィールドは、最初は Null です。 (データベース用語では、Null は "値を持たない" ことを意味し、C++ では NULL と同じではありません。操作を完了するには[、Update](#update)メンバー関数を呼び出す必要があります。 `Update`データ ソースに対する変更を保存します。

> [!NOTE]
> バルク行フェッチを実装している場合は、 を呼び`AddNew`出すことはできません。 これにより、アサーションが失敗します。 クラス`CRecordset`は、データのバルク行を更新するためのメカニズムを提供していませんが、ODBC API 関数`SQLSetPos`を使用して独自の関数を記述できます。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

`AddNew`レコードセットのフィールド データ メンバーを使用して、新しい空のレコードを準備します。 を呼び`AddNew`出した後、レコードセットのフィールド データ メンバに必要な値を設定します。 (この目的`Edit`のために[Edit](#edit)メンバー関数を呼び出す必要はありません。その後で`Update`を呼び出すと、フィールド データ メンバーの変更された値がデータ ソースに保存されます。

> [!CAUTION]
> 呼び出す`Update`前に新しいレコードまでスクロールすると、新しいレコードは失われ、警告は表示されません。

データ ソースがトランザクションをサポートしている場合は、`AddNew`トランザクションの一部を呼び出すことができます。 トランザクションの詳細については、「クラス[CDatabase」](../../mfc/reference/cdatabase-class.md)を参照してください。 呼び出す前に[CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans)を呼び出す`AddNew`必要があることに注意してください。

> [!NOTE]
> ダイナセットの場合、新しいレコードはレコードセットに最後のレコードとして追加されます。 追加されたレコードはスナップショットに追加されません。レコードセットを`Requery`更新するには、呼び出す必要があります。

メンバー関数が呼び`AddNew`出されていないレコードセットを呼び出す方法は無効です。 `Open` A`CDBException`は、追加できない`AddNew`レコードセットを呼び出すとスローされます。 CanAppend を呼び出すことで、レコードセットが[CanAppend](#canappend)更新可能かどうかを判断できます。

詳細については、「[レコードセットによるレコード更新方法 (ODBC)」、](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)[レコードセット: レコードの追加、更新、および削除 (ODBC)、](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)[およびトランザクション (ODBC)](../../data/odbc/transaction-odbc.md)を参照してください。

### <a name="example"></a>例

「[トランザクション: レコードセットでのトランザクションの実行 (ODBC)」](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)を参照してください。

## <a name="crecordsetcanappend"></a><a name="canappend"></a>Cレコードセット::缶詰

以前に開いたレコードセットで新しいレコードを追加できるかどうかを判断します。

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>戻り値

レコードセットで新しいレコードを追加できる場合は 0 以外の値を指定します。それ以外の場合は 0。 `CanAppend`レコードセットを読み取り専用で開いた場合は 0 を返します。

## <a name="crecordsetcanbookmark"></a><a name="canbookmark"></a>レコードセット::缶ブックマーク

ブックマークを使用してレコードにマークを付けることができるかどうかを決定します。

```
BOOL CanBookmark() const;
```

### <a name="return-value"></a>戻り値

レコードセットがブックマークをサポートする場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数は[、Open](#open) `CRecordset::useBookmarks`メンバー関数の*dwOptions*パラメーターのオプションとは無関係です。 `CanBookmark`指定された ODBC ドライバーとカーソルの種類がブックマークをサポートするかどうかを示します。 `CRecordset::useBookmarks`ブックマークがサポートされている場合、ブックマークが使用可能かどうかを示します。

> [!NOTE]
> 前方のみのレコードセットではブックマークはサポートされていません。

ブックマークとレコードセットナビゲーションの詳細については、「[レコードセット: ブックマークと絶対位置 (ODBC)」](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)および「[レコードセット: スクロール (ODBC)」](../../data/odbc/recordset-scrolling-odbc.md)を参照してください。

## <a name="crecordsetcancel"></a><a name="cancel"></a>レコードセット::キャンセル

データ ソースが、進行中の非同期操作または 2 番目のスレッドからのプロセスのいずれかを取り消すように要求します。

```cpp
void Cancel();
```

### <a name="remarks"></a>解説

MFC ODBC クラスは非同期処理を使用しなくなります。アサイクロナス操作を実行するには、ODBC API 関数`SQLSetConnectOption`を直接呼び出す必要があります。 詳細については *、『ODBC SDK プログラマ ガイド*』の「関数を非同期に実行する」を参照してください。

## <a name="crecordsetcancelupdate"></a><a name="cancelupdate"></a>レコードセット::キャンセル更新

更新が呼び出される前に、[編集](#edit)または[AddNew](#addnew)操作によって発生した保留中の[更新](#update)をキャンセルします。

```cpp
void CancelUpdate();
```

### <a name="remarks"></a>解説

> [!NOTE]
> このメンバ関数は、バルク行フェッチを使用しているレコードセット`Edit``AddNew`には適用できません。 `Update` バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

ダーティ フィールドの自動チェックが`CancelUpdate`有効になっている場合、メンバ変数は以前の値`Edit`または`AddNew`呼び出された値に復元されます。それ以外の場合、値の変更は残ります。 既定では、レコードセットを開いたときに自動フィールド チェックが有効になります。 この関数を無効にするには[、Open](#open) `CRecordset::noDirtyFieldCheck`メンバー関数の*dwOptions*パラメーターで を指定する必要があります。

データの更新の詳細については、「[レコードセット : レコードの追加、更新、および削除 (ODBC)」](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)を参照してください。

## <a name="crecordsetcanrestart"></a><a name="canrestart"></a>レコードセット::缶リスタート

レコードセットが、メンバー関数を呼び出してクエリを再開 (レコードを`Requery`更新) できるかどうかを判断します。

```
BOOL CanRestart() const;
```

### <a name="return-value"></a>戻り値

再クエリが許可されている場合は 0 以外。それ以外の場合は 0。

## <a name="crecordsetcanscroll"></a><a name="canscroll"></a>レコードセット::缶詰

レコードセットでスクロールを許可するかどうかを決定します。

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>戻り値

レコードセットでスクロールが許可されている場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

スクロールの詳細については、「[レコードセット: スクロール (ODBC) 」](../../data/odbc/recordset-scrolling-odbc.md)を参照してください。

## <a name="crecordsetcantransact"></a><a name="cantransact"></a>Cレコード::缶トランスアクト

レコードセットでトランザクションを許可するかどうかを決定します。

```
BOOL CanTransact() const;
```

### <a name="return-value"></a>戻り値

レコードセットでトランザクションが許可されている場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

詳細については、記事[「トランザクション (ODBC)」を](../../data/odbc/transaction-odbc.md)参照してください。

## <a name="crecordsetcanupdate"></a><a name="canupdate"></a>Cレコード::スキャンアップデート

レコードセットを更新できるかどうかを判断します。

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>戻り値

レコードセットを更新できる場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

基になるデータ ソースが読み取り専用の場合、またはレコードセットを開いたときに`CRecordset::readOnly` *dwOptions*パラメータで指定した場合、レコードセットは読み取り専用になる可能性があります。

## <a name="crecordsetcheckrowseterror"></a><a name="checkrowseterror"></a>エラーをチェックします。

レコードのフェッチ中に生成されたエラーを処理するために呼び出されます。

```
virtual void CheckRowsetError(RETCODE nRetCode);
```

### <a name="parameters"></a>パラメーター

*nレットコード*<br/>
ODBC API 関数の戻りコード。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

この仮想メンバー関数は、レコードのフェッチ時に発生するエラーを処理します。 独自のエラー処理を`CheckRowsetError`実装するためにオーバーライドを検討する必要がある場合があります。

`CheckRowsetError`は、`Open``Requery`カーソルナビゲーション操作で自動的に呼び出されます`Move`。 ODBC API 関数`SQLExtendedFetch`の戻り値が渡されます。 次の表は *、nRetCode*パラメーターに使用できる値を示しています。

|nレットコード|説明|
|--------------|-----------------|
|SQL_SUCCESS|関数は正常に完了しました。追加情報はありません。|
|SQL_SUCCESS_WITH_INFO|関数が正常に完了しました。 を呼び出`SQLError`すことで、追加情報を取得できます。|
|SQL_NO_DATA_FOUND|結果セットのすべての行がフェッチされました。|
|SQL_ERROR|関数に失敗しました。 を呼び出`SQLError`すことで、追加情報を取得できます。|
|SQL_INVALID_HANDLE|環境ハンドル、接続ハンドル、またはステートメント ハンドルが無効なため、関数が失敗しました。 これは、プログラミング エラーを示します。 から追加情報を入手できません`SQLError`。|
|SQL_STILL_EXECUTING|非同期的に開始された関数は、まだ実行中です。 既定では、MFC はこの値を`CheckRowsetError`に渡しません。MFC は、SQL_STILL_EXECUTINGを返さないまで呼び出し`SQLExtendedFetch`を続行します。|

の詳細については`SQLError`、Windows SDK を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

## <a name="crecordsetclose"></a><a name="close"></a>レコードセット::閉じる

レコードセットを閉じます。

```
virtual void Close();
```

### <a name="remarks"></a>解説

ODBC HSTMT と、レコードセットに割り当てられたフレームワークのすべてのメモリが割り当て解除されます。 通常は、`Close`を呼び出した後に **、C++** レコードセット オブジェクトが new で割り当てられた場合は削除します。

を呼び`Open`出した後`Close`、もう一度呼び出すことができます。 これにより、レコードセット オブジェクトを再利用できます。 代わりに、 を`Requery`呼び出す方法があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#17](../../mfc/codesnippet/cpp/crecordset-class_1.cpp)]

## <a name="crecordsetcrecordset"></a><a name="crecordset"></a>レコードセット::Cレコードセット

`CRecordset` オブジェクトを構築します。

```
CRecordset(CDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>パラメーター

*データベース*<br/>
`CDatabase`オブジェクトへのポインターまたは値 NULL を格納します。 NULL でない場合、`CDatabase`オブジェクトの`Open`メンバー関数がデータ ソースに接続するために呼び出されていない場合、レコードセットは、独自`Open`の呼び出し中に、オブジェクトのメンバー関数を開こうとします。 NULL を渡すと、ClassWizard を使用してレコードセット クラスを派生したときに指定したデータ ソース情報を使用して`CDatabase`、オブジェクトが構築され、接続されます。

### <a name="remarks"></a>解説

を直接使用`CRecordset`することも、アプリケーション固有のクラスを から`CRecordset`派生することもできます。 クラス ウィザードを使用して、レコードセット クラスを派生させることができます。

> [!NOTE]
> 派生クラスは、独自のコンストラクターを提供*する必要があります*。 派生クラスのコンストラクターで、コンストラクター`CRecordset::CRecordset`を呼び出して、適切なパラメーターを渡します。

オブジェクトを自動的に作成して接続するには`CDatabase`、レコードセット コンストラクターに NULL を渡します。 これは、レコードセットを構築する前にオブジェクトを構築および接続する必要`CDatabase`がない便利な短縮形です。

### <a name="example"></a>例

詳細については、「[レコードセット : テーブルのクラスの宣言 (ODBC) 」](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)を参照してください。

## <a name="crecordsetdelete"></a><a name="delete"></a>Cレコード::D

現在のレコードを削除します。

```
virtual void Delete();
```

### <a name="remarks"></a>解説

削除が成功すると、レコードセットのフィールド データ メンバーは Null 値に設定され、削除されたレコードから移動するには`Move`、いずれかの関数を明示的に呼び出す必要があります。 削除したレコードから移動すると、そのレコードに戻ることはできなくなります。 データ ソースがトランザクションをサポートしている場合は、トランザクション`Delete`の呼び出しの一部を作成できます。 詳細については、記事[「トランザクション (ODBC)」を](../../data/odbc/transaction-odbc.md)参照してください。

> [!NOTE]
> バルク行フェッチを実装している場合は、 を呼び`Delete`出すことはできません。 これにより、アサーションが失敗します。 クラス`CRecordset`は、データのバルク行を更新するためのメカニズムを提供していませんが、ODBC API 関数`SQLSetPos`を使用して独自の関数を記述できます。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

> [!CAUTION]
> レコードセットは更新可能でなければならず、呼び出`Delete`すときにはレコードセットに有効なレコードが現在存在している必要があります。それ以外の場合は、エラーが発生します。 たとえば、レコードを削除しても、再度呼び出す`Delete`前に新しいレコードまでスクロールしない場合`Delete`[、CDBException](../../mfc/reference/cdbexception-class.md)がスローされます。

[AddNew](#addnew)および[Edit](#edit)とは`Delete`異なり、 への呼び出しの後に[Update](#update)の呼び出しは行いません。 呼び`Delete`出しが失敗した場合、フィールド データ メンバーは変更されません。

### <a name="example"></a>例

この例では、関数のフレームに作成されたレコードセットを示します。 この例では、データ`m_dbCust`ソースに既に接続されている`CDatabase`型のメンバー変数 が存在することを前提としています。

[!code-cpp[NVC_MFCDatabase#18](../../mfc/codesnippet/cpp/crecordset-class_2.cpp)]

## <a name="crecordsetdobulkfieldexchange"></a><a name="dobulkfieldexchange"></a>:Dレコードセット::Dバルクフィールドエクスチェンジ

データ ソースからレコードセットにデータのバルク行を交換するために呼び出されます。 バルク レコード フィールド エクスチェンジ (Bulk RFX) を実装します。

```
virtual void DoBulkFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
[オブジェクト](../../mfc/reference/cfieldexchange-class.md)へのポインター。 フレームワークは、フィールド交換操作のコンテキストを指定するために、このオブジェクトを既に設定しています。

### <a name="remarks"></a>解説

バルク行フェッチが実装されている場合、フレームワークはこのメンバー関数を呼び出して、データ ソースからレコードセット オブジェクトにデータを自動的に転送します。 `DoBulkFieldExchange`また、パラメータ データ メンバーがある場合は、レコードセットの選択用の SQL ステートメント文字列内のパラメータ プレースホルダにバインドします。

バルク行フェッチが実装されていない場合、フレームワークは[DoFieldExchange](#dofieldexchange)を呼び出します。 バルク行フェッチを実装するには[、Open](#open)メンバー関数`CRecordset::useMultiRowFetch`で*dwOptions*パラメーターのオプションを指定する必要があります。

> [!NOTE]
> `DoBulkFieldExchange`は、 から`CRecordset`派生したクラスを使用している場合にのみ使用できます。 レコードセット オブジェクトをから直接`CRecordset`作成した場合は[、GetFieldValue](#getfieldvalue)メンバー関数を呼び出してデータを取得する必要があります。

バルク レコード フィールド エクスチェンジ (バルク RFX) は、レコード フィールド エクスチェンジ (RFX) に似ています。 データは、データ ソースからレコードセット オブジェクトに自動的に転送されます。 ただし`AddNew`、 、 `Edit`、 `Delete`、または`Update`を呼び出して、変更をデータ ソースに戻すことはできません。 クラス`CRecordset`は現在、データのバルク行を更新するメカニズムを提供していません。ただし、ODBC API 関数 を使用して独自の関数`SQLSetPos`を記述できます。

クラス ウィザードは、バルク レコード フィールドエクスチェンジをサポートしていません。したがって、Bulk RFX 関数への呼び出しを記述して手動でオーバーライド`DoBulkFieldExchange`する必要があります。 これらの関数の詳細については、トピック「レコード[フィールドエクスチェンジ関数](../../mfc/reference/record-field-exchange-functions.md)」を参照してください。

バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。 関連情報については、記事[「レコード フィールド エクスチェンジ (RFX)」](../../data/odbc/record-field-exchange-rfx.md)を参照してください。

## <a name="crecordsetdofieldexchange"></a><a name="dofieldexchange"></a>レコードセット::Dフィールドエクスチェンジ

レコードセットのフィールド データ メンバーとデータ ソースの対応するレコードの間でデータを (双方向で) 交換するために呼び出されます。 レコード フィールド エクスチェンジ (RFX) を実装します。

```
virtual void DoFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>パラメーター

*Pfx*<br/>
[オブジェクト](../../mfc/reference/cfieldexchange-class.md)へのポインター。 フレームワークは、フィールド交換操作のコンテキストを指定するために、このオブジェクトを既に設定しています。

### <a name="remarks"></a>解説

バルク行フェッチが実装されていない場合、フレームワークはこのメンバー関数を呼び出して、レコードセット オブジェクトのフィールド データ メンバーとデータ ソースの現在のレコードの対応する列との間で自動的にデータを交換します。 `DoFieldExchange`また、パラメータ データ メンバーがある場合は、レコードセットの選択用の SQL ステートメント文字列内のパラメータ プレースホルダにバインドします。

バルク行フェッチが実装されている場合、フレームワークは[DoBulkFieldExchange](#dobulkfieldexchange)を呼び出します。 バルク行フェッチを実装するには[、Open](#open)メンバー関数`CRecordset::useMultiRowFetch`で*dwOptions*パラメーターのオプションを指定する必要があります。

> [!NOTE]
> `DoFieldExchange`は、 から`CRecordset`派生したクラスを使用している場合にのみ使用できます。 レコードセット オブジェクトをから直接`CRecordset`作成した場合は[、GetFieldValue](#getfieldvalue)メンバー関数を呼び出してデータを取得する必要があります。

レコード フィールド エクスチェンジ (RFX) と呼ばれるフィールド データの交換は、レコードセット オブジェクトのフィールド データ メンバーからデータ ソースのレコードのフィールド、およびデータ ソースのレコードからレコードセット オブジェクトへの両方向で機能します。

派生レコードセット クラスに実装`DoFieldExchange`するために通常必要な操作は、ClassWizard を使用してクラスを作成し、フィールド データ メンバーの名前とデータ型を指定する必要があります。 また、ClassWizard が書き込んだコードに、パラメータ データ メンバを指定したり、動的にバインドする列を処理したりするためにコードを追加することもできます。 詳細については、「[レコードセット: データ列の動的連結 (ODBC)」](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)を参照してください。

ClassWizard を使用して派生レコードセット クラスを宣言すると、ウィザードによって`DoFieldExchange`、次の例のようなオーバーライドが書き込まれます。

[!code-cpp[NVC_MFCDatabase#19](../../mfc/codesnippet/cpp/crecordset-class_3.cpp)]

RFX 関数の詳細については、トピック「[フィールドエクスチェンジ関数の記録](../../mfc/reference/record-field-exchange-functions.md)」を参照してください。

の詳細については、「`DoFieldExchange`[レコード フィールド エクスチェンジ : RFX の動作」](../../data/odbc/record-field-exchange-how-rfx-works.md)を参照してください。 RFX の一般的な情報については、記事[レコード フィールド エクスチェンジ](../../data/odbc/record-field-exchange-rfx.md)を参照してください。

## <a name="crecordsetedit"></a><a name="edit"></a>レコードセット::編集

現在のレコードに対する変更を許可します。

```
virtual void Edit();
```

### <a name="remarks"></a>解説

を呼び`Edit`出した後、フィールド データ メンバーの値を直接リセットして、フィールド データ メンバーを変更できます。 この操作は、後で[Update](#update)メンバー関数を呼び出してデータ ソースに対する変更を保存すると完了します。

> [!NOTE]
> バルク行フェッチを実装している場合は、 を呼び`Edit`出すことはできません。 これにより、アサーションが失敗します。 クラス`CRecordset`は、データのバルク行を更新するためのメカニズムを提供していませんが、ODBC API 関数`SQLSetPos`を使用して独自の関数を記述できます。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

`Edit`レコードセットのデータ メンバの値を保存します。 を呼び`Edit`出した場合、変更を`Edit`加えてから再度呼び出すと、レコードの値は最初`Edit`の呼び出しの前の値に戻ります。

場合によっては、列を Null (データを含み) にして更新する必要がある場合があります。 これを行うには、TRUE のパラメーターを指定して[SetFieldNull](#setfieldnull)を呼び出して、フィールドを Null にマークします。これにより、列も更新されます。 値が変更されていない場合でも、フィールドをデータ ソースに書き込む場合は、パラメーター TRUE を指定して[SetFieldDirty](#setfielddirty)を呼び出します。 これは、フィールドに Null 値が設定されている場合でも機能します。

データ ソースがトランザクションをサポートしている場合は、トランザクション`Edit`の呼び出しの一部を作成できます。 呼び出しの前とレコードセットが開かれた後`Edit`に[、CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans)を呼び出す必要があります。 また[、CDatabase::CommitTrans](../../mfc/reference/cdatabase-class.md#committrans)を呼び出すことは、操作`Update`を完了するための`Edit`呼び出しの代わりになされないことに注意してください。 トランザクションの詳細については、「クラス[CDatabase」](../../mfc/reference/cdatabase-class.md)を参照してください。

現在のロック モードによっては、更新中のレコードは、別の`Edit`レコードを呼`Update`び出すかスクロールするまでロックされるか、`Edit`呼び出し中にのみロックされる場合があります。 ロック モードは[、SetLockingMode](#setlockingmode)で変更できます。

呼び出し`Update`前に新しいレコードまでスクロールすると、現在のレコードの以前の値が復元されます。 更新`CDBException`できないレコードセットを呼`Edit`び出した場合、またはカレント レコードがない場合に A がスローされます。

詳細については、「[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md) 」および「[レコードセット: レコードのロック (ODBC)」](../../data/odbc/recordset-locking-records-odbc.md)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#20](../../mfc/codesnippet/cpp/crecordset-class_4.cpp)]

## <a name="crecordsetflushresultset"></a><a name="flushresultset"></a>を返します。

複数の結果セットがある場合は、定義済みクエリ (ストアド プロシージャ) の次の結果セットを取得します。

```
BOOL FlushResultSet();
```

### <a name="return-value"></a>戻り値

取得する結果セットが他にもある場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

現在の結果`FlushResultSet`セットにカーソルが完全に表示された場合にのみ呼び出す必要があります。 呼び出`FlushResultSet`しによって次の結果セットを取得する場合、カーソルはその結果セットでは無効です。呼び出し後に[、MoveNext](#movenext) `FlushResultSet`メンバー関数を呼び出す必要があります。

定義済みクエリで出力パラメータまたは入出力パラメータを使用する場合、これらのパラメータ値を`FlushResultSet`取得するためには`FALSE`、返す値 (0) まで呼び出す必要があります。

`FlushResultSet`ODBC API 関数`SQLMoreResults`を呼び出します。 SQL_ERROR`SQLMoreResults`またはSQL_INVALID_HANDLEを返した場合`FlushResultSet`は、例外がスローされます。 の詳細については`SQLMoreResults`、Windows SDK を参照してください。

を呼び出`FlushResultSet`す場合は、ストアド プロシージャに連結フィールドが必要です。

### <a name="example"></a>例

次のコードでは、`COutParamRecordset`入力パラメーター`CRecordset`と出力パラメーターを持つ定義済みクエリに基づく派生オブジェクトであり、複数の結果セットを持つものと想定しています。 オーバーライドの構造[に](#dofieldexchange)注意してください。

[!code-cpp[NVC_MFCDatabase#21](../../mfc/codesnippet/cpp/crecordset-class_5.cpp)]

[!code-cpp[NVC_MFCDatabase#22](../../mfc/codesnippet/cpp/crecordset-class_6.cpp)]

## <a name="crecordsetgetbookmark"></a><a name="getbookmark"></a>を見る

現在のレコードのブックマーク値を取得します。

```cpp
void GetBookmark(CDBVariant& varBookmark);
```

### <a name="parameters"></a>パラメーター

*を見る*<br/>
現在のレコードのブックマークを表す[CDBVariant](../../mfc/reference/cdbvariant-class.md)オブジェクトへの参照。

### <a name="remarks"></a>解説

ブックマークがレコードセットでサポートされているかどうかを確認するには、 [CanBookmark](#canbookmark)を呼び出します。 ブックマークがサポートされている場合にブックマークを使用できるようにするには[、Open](#open)メンバー`CRecordset::useBookmarks`関数の*dwOptions*パラメーターでオプションを設定する必要があります。

> [!NOTE]
> ブックマークがサポートされていないか、使用できない場合、`GetBookmark`呼び出しは例外がスローされます。 前方のみのレコードセットではブックマークはサポートされていません。

`GetBookmark`は、現在のレコードのブックマークの値をオブジェクトに`CDBVariant`割り当てます。 別のレコードに移動した後、いつでもそのレコードに戻るには、対応する`CDBVariant`オブジェクトを指定して[SetBookmark](#setbookmark)を呼び出します。

> [!NOTE]
> 特定のレコードセット操作の後、ブックマークが無効になる場合があります。 たとえば、 を呼び`GetBookmark`出すと`Requery`、 を使用`SetBookmark`して レコードに戻ることができない場合があります。 [を](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence)呼び出して、安全に呼び出`SetBookmark`すことができるかどうかを確認します。

ブックマークとレコードセットナビゲーションの詳細については、「[レコードセット: ブックマークと絶対位置 (ODBC)」](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)および「[レコードセット: スクロール (ODBC)」](../../data/odbc/recordset-scrolling-odbc.md)を参照してください。

## <a name="crecordsetgetdefaultconnect"></a><a name="getdefaultconnect"></a>レコードセット::デフォルト接続を取得します。

既定の接続文字列を取得するために呼び出されます。

```
virtual CString GetDefaultConnect();
```

### <a name="return-value"></a>戻り値

既定`CString`の接続文字列を含む A。

### <a name="remarks"></a>解説

フレームワークは、このメンバー関数を呼び出して、レコードセットの基になるデータ ソースの既定の接続文字列を取得します。 ClassWizard は、テーブルと列に関する情報を取得するために ClassWizard で使用するのと同じデータ ソースを識別することによって、この関数を実装します。 アプリケーションの開発中に、この既定の接続に依存すると便利です。 ただし、既定の接続は、アプリケーションのユーザーには適していない場合があります。 その場合は、ClassWizard のバージョンを破棄して、この関数を再実装する必要があります。 接続文字列の詳細については、「[データ ソース (ODBC) 」](../../data/odbc/data-source-odbc.md)を参照してください。

## <a name="crecordsetgetdefaultsql"></a><a name="getdefaultsql"></a>を使用します。

実行する既定の SQL 文字列を取得するために呼び出されます。

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>戻り値

既定`CString`の SQL ステートメントを含む A。

### <a name="remarks"></a>解説

フレームワークは、このメンバー関数を呼び出して、レコードセットの基になる既定の SQL ステートメントを取得します。 これは、テーブル名または SQL **SELECT**ステートメントの場合があります。

ClassWizard を使用してレコードセット クラスを宣言することで、既定の SQL ステートメントを間接的に定義すると、ClassWizard によってこのタスクが実行されます。

SQL ステートメント文字列が必要な場合は、 を呼`GetSQL`び出して、レコードセットを開いたときにレコードセットのレコードを選択するために使用した SQL ステートメントを返します。 クラスの オーバーライドで既定の`GetDefaultSQL`SQL 文字列を編集できます。 たとえば **、CALL**ステートメントを使用して、定義済みクエリの呼び出しを指定できます。 ただし、 を編集`GetDefaultSQL`する場合は、データ ソースの列数`m_nFields`に合わせて変更する必要があります。

詳細については、「[レコードセット : テーブルのクラスの宣言 (ODBC) 」](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)を参照してください。

> [!CAUTION]
> 複数のテーブル名が指定されている場合、または**CALL**ステートメントを解釈できない場合、フレームワークがテーブル名を識別できなかった場合、テーブル名は空になります。 **CALL**ステートメントを使用する場合、中括弧と**CALL**キーワードの間に空白文字を挿入したり、中括弧の前または**SELECT**キーワードの前に空白を**SELECT**ステートメントで挿入したりしてはならないことに注意してください。

## <a name="crecordsetgetfieldvalue"></a><a name="getfieldvalue"></a>レコードセット::フィールド値を取得します。

現在のレコードのフィールド データを取得します。

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

*名前を指定します。*<br/>
フィールドの名前。

*varValu*e フィールドの値を格納する[CDBVariant](../../mfc/reference/cdbvariant-class.md)オブジェクトへの参照。

*フィールドタイプ*<br/>
フィールドの ODBC C データ型。 デフォルト値の DEFAULT_FIELD_TYPE を使用`GetFieldValue`して、次の表に基づいて、強制的に SQL データ型から C データ型を決定します。 それ以外の場合は、データ型を直接指定するか、互換性のあるデータ型を選択できます。たとえば、任意のデータ型をSQL_C_CHARに格納できます。

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

ODBC データ型の詳細については、Windows SDK の付録 D の「SQL データ型」および「C データ型」のトピックを参照してください。

*nIndex*<br/>
フィールドの 0 から始まるインデックス。

*strValue*<br/>
フィールドのデータ型に関係なく、テキストに変換されたフィールドの値を格納する[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトへの参照。

### <a name="remarks"></a>解説

フィールドは、名前またはインデックスで検索できます。 フィールド値は、オブジェクトまたは`CDBVariant``CString`オブジェクトに格納できます。

バルク行フェッチを実装している場合、現在のレコードは常に行セットの最初のレコードに配置されます。 指定した`GetFieldValue`行セット内のレコードで使用するには、まず[SetRowsetCursorPosition](#setrowsetcursorposition)メンバー関数を呼び出して、カーソルをその行セット内の目的の行に移動する必要があります。 その後`GetFieldValue`、その行を呼び出します。 バルク行フェッチを実装するには[、Open](#open)メンバー関数`CRecordset::useMultiRowFetch`で*dwOptions*パラメーターのオプションを指定する必要があります。

デザイン時に`GetFieldValue`静的に連結するのではなく、実行時に動的にフィールドをフェッチするために使用できます。 たとえば、 から`CRecordset`直接レコードセット オブジェクトを宣言した場合は、`GetFieldValue`を使用してフィールド データを取得する必要があります。レコード フィールド エクスチェンジ (RFX) またはバルク レコード フィールド エクスチェンジ (Bulk RFX) は実装されていません。

> [!NOTE]
> から`CRecordset`派生せずにレコードセット オブジェクトを宣言する場合は、ODBC カーソル ライブラリを読み込まないようにします。 カーソル ライブラリでは、レコードセットにバインドされた列が少なくとも 1 つ必要です。ただし、直接使用`CRecordset`する場合、列はバインドされません。 メンバー関数[CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex)と[CDatabase::Open](../../mfc/reference/cdatabase-class.md#open)は、カーソル ライブラリを読み込むかどうかを制御します。

`GetFieldValue`ODBC API 関数`SQLGetData`を呼び出します。 ドライバーがフィールド値の実際の長さの値SQL_NO_TOTALを出力する場合は、`GetFieldValue`例外をスローします。 の詳細については`SQLGetData`、Windows SDK を参照してください。

### <a name="example"></a>例

から直接宣言されたレコードセット オブジェクト`GetFieldValue`の呼び出しを次`CRecordset`のサンプル コードに示します。

[!code-cpp[NVC_MFCDatabase#23](../../mfc/codesnippet/cpp/crecordset-class_7.cpp)]

> [!NOTE]
> DAO クラス`CDaoRecordset`とは`CRecordset`異なり、`SetFieldValue`メンバー関数はありません。 から`CRecordset`直接オブジェクトを作成すると、読み取り専用になります。

バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

## <a name="crecordsetgetodbcfieldcount"></a><a name="getodbcfieldcount"></a>レコードセット::取得ODBCフィールドカウント

レコードセット オブジェクト内のフィールドの合計数を取得します。

```
short GetODBCFieldCount() const;
```

### <a name="return-value"></a>戻り値

レコードセット内のフィールドの数。

### <a name="remarks"></a>解説

レコードセットの作成の詳細については、「[レコードセット : レコードセットの作成と終了 (ODBC)」](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)を参照してください。

## <a name="crecordsetgetodbcfieldinfo"></a><a name="getodbcfieldinfo"></a>レコードセット::取得ODBCフィールド情報

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

*名前を指定します。*<br/>
フィールドの名前。

*Fieldinfo*<br/>
`CODBCFieldInfo`構造体への参照。

*nIndex*<br/>
フィールドの 0 から始まるインデックス。

### <a name="remarks"></a>解説

関数の 1 つのバージョンでは、名前でフィールドを検索できます。 もう 1 つのバージョンでは、インデックスでフィールドを検索できます。

返される情報の詳細については[、CODBCFieldInfo](../../mfc/reference/codbcfieldinfo-structure.md)構造体を参照してください。

レコードセットの作成の詳細については、「[レコードセット : レコードセットの作成と終了 (ODBC)」](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)を参照してください。

## <a name="crecordsetgetrecordcount"></a><a name="getrecordcount"></a>レコードセット::レコードカウントを取得します。

レコードセットのサイズを決定します。

```
long GetRecordCount() const;
```

### <a name="return-value"></a>戻り値

レコードセット内のレコードの数。レコードセットにレコードが含まれなかった場合は 0。レコード数を判別できない場合は -1。

### <a name="remarks"></a>解説

> [!CAUTION]
> レコード数は、ユーザーがレコードを移動する場合に表示される、最高の番号のレコードである"最高水準点"として維持されます。 レコードの総数は、ユーザーが最後のレコードを超えて移動した後にのみ認識されます。 パフォーマンス上の理由から、 を呼び出`MoveLast`してもカウントは更新されません。 レコードを自分でカウントするには、0 以外`IsEOF`の値が返されるまで繰り返し呼び出`MoveNext`します。 を介`CRecordset:AddNew`してレコードを`Update`追加し、カウントを増加させます。を使用して`CRecordset::Delete`レコードを削除すると、カウントが減少します。

## <a name="crecordsetgetrowsetsize"></a><a name="getrowsetsize"></a>レコードセット::ゲットローセットサイズ

指定されたフェッチ中に取得する行数の現在の設定を取得します。

```
DWORD GetRowsetSize() const;
```

### <a name="return-value"></a>戻り値

特定のフェッチ中に取得する行数。

### <a name="remarks"></a>解説

バルク行フェッチを使用している場合、レコードセットを開くときのデフォルトの行セットサイズは 25 です。それ以外の場合は 1 です。

バルク行フェッチを実装するには[、Open](#open)メンバー関数`CRecordset::useMultiRowFetch`の*dwOptions*パラメーターでオプションを指定する必要があります。 行セットのサイズの設定を変更するには[、SetRowsetSize](#setrowsetsize)を呼び出します。

バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

## <a name="crecordsetgetrowsfetched"></a><a name="getrowsfetched"></a>レコードセット::GetRowsフェッチ

フェッチ後に実際に取得されたレコードの数を決定します。

```
DWORD GetRowsFetched() const;
```

### <a name="return-value"></a>戻り値

特定のフェッチ後にデータ ソースから取得された行の数。

### <a name="remarks"></a>解説

これは、バルク行フェッチを実装している場合に便利です。 行セットのサイズは、通常、フェッチから取得される行数を示します。ただし、レコードセットの行の合計数は、行セットで取得される行数にも影響します。 たとえば、レコードセットに行セット サイズの設定が 4 のレコードが 10 個含まれる場合、`MoveNext`レコードセットを呼び出してレコードセットをループすると、最終行セットのレコードは 2 つしかありません。

バルク行フェッチを実装するには[、Open](#open)メンバー関数`CRecordset::useMultiRowFetch`の*dwOptions*パラメーターでオプションを指定する必要があります。 行セットのサイズを指定するには[、SetRowsetSize](#setrowsetsize)を呼び出します。

バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#24](../../mfc/codesnippet/cpp/crecordset-class_8.cpp)]

## <a name="crecordsetgetrowstatus"></a><a name="getrowstatus"></a>レコードセット::ゲットローステータス

現在の行セットの行の状態を取得します。

```
WORD GetRowStatus(WORD wRow) const;
```

### <a name="parameters"></a>パラメーター

*wRow*<br/>
現在の行セット内の行の 1 から 1 から成る位置。 この値は、1 から行セットのサイズまでの範囲です。

### <a name="return-value"></a>戻り値

行のステータス値。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

`GetRowStatus`は、データ ソースから最後に取得された行の状態の変化、または*wRow*に対応する行がフェッチされなくなったことを示す値を返します。 次の表は、可能性のある戻り値の一覧です。

|ステータス値|説明|
|------------------|-----------------|
|SQL_ROW_SUCCESS|行は変更されません。|
|SQL_ROW_UPDATED|行が更新されました。|
|SQL_ROW_DELETED|行が削除されました。|
|SQL_ROW_ADDED|行が追加されました。|
|SQL_ROW_ERROR|エラーのため、行を取得できません。|
|SQL_ROW_NOROW|*wRow*に対応する行がありません。|

詳細については、Windows SDK の`SQLExtendedFetch`ODBC API 関数を参照してください。

## <a name="crecordsetgetstatus"></a><a name="getstatus"></a>レコードセット::ステータスを取得します。

レコードセット内の現在のレコードのインデックスと、最後のレコードが見られたかどうかを判断します。

```cpp
void GetStatus(CRecordsetStatus& rStatus) const;
```

### <a name="parameters"></a>パラメーター

*rステータス*<br/>
`CRecordsetStatus` オブジェクトへの参照です。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

`CRecordset`インデックスを追跡しようとしますが、状況によっては、これが不可能な場合があります。 詳細については、[レコード数の取得](#getrecordcount)を参照してください。

構造`CRecordsetStatus`の形式は次のとおりです。

```cpp
struct CRecordsetStatus
{
    long m_lCurrentRecord;
    BOOL m_bRecordCountFinal;
};
```

の 2`CRecordsetStatus`つのメンバーは、次の意味を持ちます。

- `m_lCurrentRecord`レコードセット内の現在のレコードの 0 から始まるインデックスが含まれます (既知の場合)。 インデックスを決定できない場合、このメンバにはAFX_CURRENT_RECORD_UNDEFINED (-2) が含まれます。 TRUE`IsBOF`の場合 (空のレコードセットまたは最初のレコードの`m_lCurrentRecord`前にスクロールを試みます)、AFX_CURRENT_RECORD_BOF (-1) に設定されます。 最初のレコードの場合は、0、2 番目のレコード 1、というように設定されます。

- `m_bRecordCountFinal`レコードセット内のレコードの合計数が決定された場合は、0 以外の値を返します。 通常、これはレコードセットの先頭から開始し、0 以外の`MoveNext`値`IsEOF`が返されるまで呼び出すことによって実行する必要があります。 このメンバーがゼロの場合、-1 でない場合`GetRecordCount`、レコードのカウントはレコードの「最高水準点」のカウントに過ぎません。

## <a name="crecordsetgetsql"></a><a name="getsql"></a>レコードセット::GetSQL

レコードセットを開いたときにレコードセットのレコードを選択するために使用された SQL ステートメントを取得します。

```
const CString& GetSQL() const;
```

### <a name="return-value"></a>戻り値

SQL ステートメントを含`CString`む を参照する**const。**

### <a name="remarks"></a>解説

これは通常、SQL **SELECT**ステートメントになります。 によって返される`GetSQL`文字列は読み取り専用です。

返される`GetSQL`文字列は、通常`Open`*、lpszSQL*パラメーターのレコードセットに渡した文字列とは異なります。 これは、レコードセットが`Open`、渡した内容、ClassWizard で指定した内容、`m_strFilter`および`m_strSort`データ メンバで指定した内容、および指定したパラメータに基づいて完全な SQL ステートメントを作成するためです。 レコードセットがこの SQL ステートメントを構築する方法の詳細については、「[レコードセット : レコードセットがレコードを選択する方法 (ODBC)」](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)を参照してください。

> [!NOTE]
> このメンバー関数は[、 Open](#open)を呼び出した後にのみ呼び出されます。

## <a name="crecordsetgettablename"></a><a name="gettablename"></a>レコードセット::テーブル名を取得します。

レコードセットのクエリの基になる SQL テーブルの名前を取得します。

```
const CString& GetTableName() const;
```

### <a name="return-value"></a>戻り値

レコード**const**セットがテーブルに`CString`基づいている場合は、テーブル名を含むを参照する const 参照。それ以外の場合は空の文字列。

### <a name="remarks"></a>解説

`GetTableName`は、レコードセットがテーブルに基づいている場合にのみ有効であり、複数のテーブルの結合や定義済みのクエリ (ストアド プロシージャ) ではありません。 名前は読み取り専用です。

> [!NOTE]
> このメンバー関数は[、 Open](#open)を呼び出した後にのみ呼び出されます。

## <a name="crecordsetisbof"></a><a name="isbof"></a>レコードセット::イズブフ

レコードセットが最初のレコードの前に配置されている場合は、0 以外を返します。 現在のレコードが存在しません。

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>戻り値

レコードセットにレコードが含まれなかったり、最初のレコードの前にスクロールした場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

レコードからレコードへスクロールする前に、このメンバー関数を呼び出して、レコードセットの最初のレコードより前に移動したかどうかを確認します。 レコードセットにレコード`IsBOF`が含`IsEOF`まれているか、空かを調べる場合にも、 を使用できます。 を呼び出`Open`した直後に、レコードセットにレコード`IsBOF`が含まれている場合は、0 以外の値が返されます。レコードが少なくとも 1 つあるレコードを開くと、最初のレコードはカレント`IsBOF`レコードになり、0 を返します。

最初のレコードが現在のレコードで、 を`MovePrev``IsBOF`呼び出すと、その後に 0 以外の値が返されます。 0`IsBOF`以外を返し、`MovePrev`を呼び出すと、エラーが発生します。 0`IsBOF`以外の値を返すと、現在のレコードは未定義になり、現在のレコードを必要とするアクションはエラーになります。

### <a name="example"></a>例

この例では`IsBOF`、`IsEOF`コードが両方向にレコードセットをスクロールする場合に、レコードセットの制限を使用して検出します。

[!code-cpp[NVC_MFCDatabase#25](../../mfc/codesnippet/cpp/crecordset-class_9.cpp)]

## <a name="crecordsetisdeleted"></a><a name="isdeleted"></a>レコードセット::削除

現在のレコードが削除されているかどうかを判断します。

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>戻り値

レコードセットが削除されたレコードに配置されている場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

レコードまでスクロールして`IsDeleted`TRUE (ゼロ以外) を返す場合は、他のレコードセット操作を実行する前に別のレコードまでスクロールする必要があります。

結果は、`IsDeleted`レコードセットの種類、レコードセットが更新可能かどうか、レコードセットを開いたときに`CRecordset::skipDeletedRecords`オプションを指定したかどうか、ドライバーパックがレコードを削除したかどうか、複数のユーザーがいるかどうかなど、多くの要因によって異なります。

ドライバーのパッキング`CRecordset::skipDeletedRecords`の詳細については[、Open](#open)メンバー関数を参照してください。

> [!NOTE]
> バルク行フェッチを実装している場合は、 を呼び出`IsDeleted`すべきではありません。 代わりに[、メンバー関数](#getrowstatus)を呼び出します。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

## <a name="crecordsetiseof"></a><a name="iseof"></a>レコードセット::イセフ

レコードセットが最後のレコードの後に配置されている場合は、0 以外を返します。 現在のレコードが存在しません。

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>戻り値

レコードセットにレコードが含まれなかったり、最後のレコードを越えてスクロールした場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

レコードからレコードへスクロールして、レコードセットの最後のレコードを超えたかどうかを確認するときに、このメンバー関数を呼び出します。 レコードセット`IsEOF`にレコードが含まれているか、空かを調べることもできます。 を呼び出`Open`した直後に、レコードセットにレコード`IsEOF`が含まれている場合は、0 以外の値が返されます。 レコードが少なくとも 1 つあるレコードを開くと、最初のレコードはカレント`IsEOF`レコードになり、0 を返します。

最後のレコードが 呼`MoveNext``IsEOF`び出すときに現在のレコードの場合は、その後 0 以外の値が返されます。 0`IsEOF`以外を返し、`MoveNext`を呼び出すと、エラーが発生します。 0`IsEOF`以外の値を返すと、現在のレコードは未定義になり、現在のレコードを必要とするアクションはエラーになります。

### <a name="example"></a>例

[IsBOF](#isbof)の例を参照してください。

## <a name="crecordsetisfielddirty"></a><a name="isfielddirty"></a>Cレコード::イズフィールドダーティ

[Edit](#edit)または[AddNew](#addnew)が呼び出された後に、指定したフィールド データ メンバーが変更されたかどうかを判断します。

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
状態をチェックするフィールド データ メンバーへのポインター。またはいずれかのフィールドがダーティかどうかを判断する場合は NULL。

### <a name="return-value"></a>戻り値

呼び出し後に、指定したフィールド データ`AddNew``Edit`メンバーが変更された場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

すべてのダーティ フィールド データ メンバーのデータは、(または`AddNew`を呼び出した後) の[Update](#update)メンバー関数の呼び`CRecordset`出しによって現在の`Edit`レコードが更新されると、データ ソースのレコードに転送されます。

> [!NOTE]
> このメンバー関数は、バルク行フェッチを使用しているレコードセットには適用できません。 バルク行フェッチを実装している場合は、常に`IsFieldDirty`FALSE を返し、アサーションが失敗します。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

呼`IsFieldDirty`び出しは、フィールドのダーティ ステータスが再評価されるため[、SetFieldDirty](#setfielddirty)への先行呼び出しの影響をリセットします。 `AddNew`この場合、現在のフィールド値が疑似ヌル値と異なる場合、フィールド状況はダーティに設定されます。 `Edit`この場合、フィールド値がキャッシュされた値と異なる場合、フィールドステータスはダーティに設定されます。

`IsFieldDirty`は[、ドフィールドエクスチェンジ](#dofieldexchange)を通じて実装されます。

ダーティ フラグの詳細については、「[レコードセット: レコードセットがレコードを選択する方法 (ODBC)」](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)を参照してください。

## <a name="crecordsetisfieldnull"></a><a name="isfieldnull"></a>レコードセット::イズフィールドヌル

現在のレコードの指定されたフィールドが Null (値なし) の場合は、0 以外を返します。

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
状態を確認するフィールド データ メンバーへのポインター、または NULL を指定してフィールドのいずれかが Null かどうかを判断します。

### <a name="return-value"></a>戻り値

指定されたフィールド データ メンバーに Null のフラグが設定されている場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

レコードセットの指定されたフィールド データ メンバーに Null のフラグが設定されているかどうかを調べます。 (データベース用語では、Null は "値を持たない" ことを意味し、C++ では NULL と同じではありません。フィールド データ メンバーに Null というフラグが設定されている場合、そのフィールド データ メンバーは、値がない現在のレコードの列として解釈されます。

> [!NOTE]
> このメンバー関数は、バルク行フェッチを使用しているレコードセットには適用できません。 バルク行フェッチを実装している場合は、常に`IsFieldNull`FALSE を返し、アサーションが失敗します。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

`IsFieldNull`は[、ドフィールドエクスチェンジ](#dofieldexchange)を通じて実装されます。

## <a name="crecordsetisfieldnullable"></a><a name="isfieldnullable"></a>レコードセット::イズフィールドNull可能

現在のレコードの指定されたフィールドが Null (値なし) に設定できる場合は、0 以外を返します。

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
状態をチェックするフィールド データ メンバーへのポインター、または NULL を指定して、いずれかのフィールドを Null 値に設定できるかどうかを判断します。

### <a name="remarks"></a>解説

指定したフィールド データ メンバーが "null 許容" であるかどうかを調べます ( Null 値に設定できます。C++ NULL は NULL と同じではありません。

> [!NOTE]
> バルク行フェッチを実装している場合は、 を呼び`IsFieldNullable`出すことはできません。 代わりに[、GetODBCFieldInfo](#getodbcfieldinfo)メンバー関数を呼び出して、フィールドを Null 値に設定できるかどうかを判断します。 バルク行フェッチを実装しているかどうか`GetODBCFieldInfo`に関係なく、 を常に呼び出すことができます。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

Null にできないフィールドには値が必要です。 レコードの追加または更新時にこのようなフィールドを Null に設定しようとすると、データ ソースはその追加または更新を拒否し[、Update](#update)は例外をスローします。 例外は、 を呼び`Update`出すときではなく、[を](#setfieldnull)呼び出すときに発生します。

関数の最初の引数に NULL を使用すると、関数は`outputColumn`フィールドに対`param`してのみ適用され、フィールドには適用されません。 たとえば、コール

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

フィールドのみを`outputColumn`NULL に設定します。`param`フィールドは影響を受けません。

フィールドで`param`作業するには、次のような作業を行う個人`param`の実際のアドレスを指定する必要があります。

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

つまり、フィールドの場合と`param`同様`outputColumn`に、すべてのフィールドを NULL に設定することはできません。

`IsFieldNullable`は[、ドフィールドエクスチェンジ](#dofieldexchange)を通じて実装されます。

## <a name="crecordsetisopen"></a><a name="isopen"></a>レコードセット::IsOpen

レコードセットが既に開いているかどうかを判断します。

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>戻り値

レコードセット オブジェクトの[Open](#open)または[Requery](#requery)メンバー関数が以前に呼び出され、レコードセットが閉じられていない場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="crecordsetm_hstmt"></a><a name="m_hstmt"></a>レコードセット::m_hstmt

レコードセットに関連付けられた、HSTMT 型の ODBC ステートメント データ構造体へのハンドルを格納します。

### <a name="remarks"></a>解説

ODBC データ ソースに対する各クエリは、HSTMT に関連付けられます。

> [!CAUTION]
> Open が`m_hstmt`呼[Open](#open)び出される前に使用しないでください。

通常は HSTMT に直接アクセスする必要はありませんが、SQL ステートメントを直接実行するために必要な場合があります。 クラス`ExecuteSQL``CDatabase`のメンバー関数は、 の使用例を`m_hstmt`示します。

## <a name="crecordsetm_nfields"></a><a name="m_nfields"></a>レコードセット::m_nFields

レコードセット クラス内のフィールド データ メンバーの数を格納します。つまり、データ ソースからレコードセットによって選択された列の数です。

### <a name="remarks"></a>解説

レコードセット クラスのコンストラクターは、`m_nFields`正しい数値で初期化する必要があります。 バルク行フェッチを実装していない場合、ClassWizard を使用してレコードセット クラスを宣言するときに、この初期化が書き込まれます。 手動で書き込む方法もあります。

フレームワークは、この数を使用して、フィールド データ メンバーと、データ ソース上の現在のレコードの対応する列との間の相互作用を管理します。

> [!CAUTION]
> この番号は`DoFieldExchange`、パラメータ`DoBulkFieldExchange``CFieldExchange::outputColumn`を指定して[SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype)を呼び出した後に登録された "出力列" の数に対応している必要があります。

「レコードセット: 動的にデータ列をバインドする」で説明されているように、列を動的にバインドできます。 この場合、動的にバインドされた列の`m_nFields`または`DoFieldExchange``DoBulkFieldExchange`メンバー関数の RFX または Bulk RFX 関数呼び出しの数を反映するために、カウントを増やす必要があります。

詳細については、「[レコードセット : データ列の動的連結 (ODBC)」](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)および「[レコードセット: レコードの一括フェッチ (ODBC)」](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)を参照してください。

### <a name="example"></a>例

「レコード[フィールド エクスチェンジ : RFX の使用」](../../data/odbc/record-field-exchange-using-rfx.md)を参照してください。

## <a name="crecordsetm_nparams"></a><a name="m_nparams"></a>レコードセット::m_nParams

レコードセット クラス内のパラメーター データ メンバーの数を格納します。つまり、レコードセットのクエリで渡されるパラメータの数です。

### <a name="remarks"></a>解説

レコードセット クラスにパラメータ データ メンバーがある場合、クラスのコンストラクターは`m_nParams`正しい数値で初期化する必要があります。 デフォルト値`m_nParams`は 0 です。 パラメーター データ メンバーを追加する場合 (手動で行う必要があります)、クラス コンストラクターに初期化を手動で追加して、パラメーターの数を反映する必要があります (これは、少なくとも、または`m_strFilter``m_strSort`文字列の中の '' プレースホルダーの数と同じ大きさである必要があります)。

フレームワークは、レコードセットのクエリをパラメーター化するときにこの数値を使用します。

> [!CAUTION]
> この数値は`DoFieldExchange`、パラメータ値 、 `DoBulkFieldExchange` `CFieldExchange::inputParam` `CFieldExchange::param`、、`CFieldExchange::outputParam`または`CFieldExchange::inoutParam`のパラメータ値を持つ[SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype)の呼び出し後に登録された "params" の数に対応している必要があります。

### <a name="example"></a>例

  「[レコードセット: レコードセット (ODBC) のパラメータ化」](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)および「[レコード フィールド エクスチェンジ: RFX を使用する](../../data/odbc/record-field-exchange-using-rfx.md)」を参照してください。

## <a name="crecordsetm_pdatabase"></a><a name="m_pdatabase"></a>レコードセット::m_pDatabase

レコードセットが`CDatabase`データ ソースに接続されているオブジェクトへのポインターを格納します。

### <a name="remarks"></a>解説

この変数は、2 つの方法で設定されます。 通常は、レコードセット オブジェクトを構築するときに`CDatabase`、既に接続されているオブジェクトへのポインターを渡します。 代わりに NULL を`CRecordset`渡すと`CDatabase`、オブジェクトが作成され、接続されます。 いずれの場合も、`CRecordset`この変数にポインターを格納します。

通常は、 に格納されているポインターを直接使用する必要`m_pDatabase`はありません。 ただし、 に独自の拡張機能`CRecordset`を記述する場合は、ポインターを使用する必要があります。 たとえば、独自`CDBException`の s をスローする場合は、ポインターが必要な場合があります。 または、トランザクションの実行、タイムアウトの設定、クラスの`CDatabase``ExecuteSQL`メンバー関数の呼び出しなど、同じオブジェクトを使用して SQL ステートメント`CDatabase`を直接実行する必要がある場合は、この操作が必要になる場合もあります。

## <a name="crecordsetm_strfilter"></a><a name="m_strfilter"></a>レコードセット::m_strFilter

レコードセット オブジェクトを構築した後、そのメンバー関数`Open`を呼び出す前に、このデータ`CString`メンバーを使用して SQL **WHERE**句を含むを格納します。

### <a name="remarks"></a>解説

レコードセットは、この文字列を使用して、`Open`または`Requery`呼び出し中に選択したレコードを制限 (またはフィルター) します。 これは、"カリフォルニア州に拠点を置くすべての営業担当者" ("州 = CA" ) などのレコードのサブセットを選択する場合に便利です。 **WHERE**句の ODBC SQL 構文は次のとおりです。

`WHERE search-condition`

文字列に**WHERE**キーワードを含まないことに注意してください。 フレームワークはそれを提供します。

また、フィルタ文字列に '' プレースホルダを配置し、各プレースホルダのパラメータ データ メンバをクラスで宣言し、実行時にレコードセットにパラメータを渡すことで、パラメータを設定することもできます。 これにより、実行時にフィルターを作成できます。 詳細については、「[レコードセット: レコードセットのパラメータ化 (ODBC)」](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)を参照してください。

SQL **WHERE**句の詳細については[、SQL](../../data/odbc/sql.md)を参照してください。 レコードの選択とフィルタ処理の詳細については、「[レコードセット: レコードのフィルタ処理 (ODBC)」](../../data/odbc/recordset-filtering-records-odbc.md)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#30](../../mfc/codesnippet/cpp/crecordset-class_12.cpp)]

## <a name="crecordsetm_strsort"></a><a name="m_strsort"></a>レコードセット::m_strSort

レコードセット オブジェクトを構築した後、そのメンバー関数`Open`を呼び出す前に、このデータ`CString`メンバーを使用して、SQL **ORDER BY**句を含むデータ メンバーを格納します。

### <a name="remarks"></a>解説

レコードセットは、この文字列を使用して、 または`Open``Requery`呼び出し中に選択したレコードを並べ替えます。 この機能を使用して、1 つ以上の列のレコードセットを並べ替えることができます。 **ORDER BY**句の ODBC SQL 構文は次のとおりです。

`ORDER BY sort-specification [, sort-specification]...`

ソート指定は整数または列名です。 並べ替え文字列の列リストに "ASC" または "DESC" を追加して、昇順または降順 (既定では昇順) を指定することもできます。 選択したレコードは、最初に一覧に表示された最初の列、次に 2 番目の列順に並べ替えられます。 たとえば、"得意先" レコードセットを姓、名順に並べ替えます。 表示できる列数は、データ ソースによって異なります。 詳細については、Windows SDK を参照してください。

文字列に**ORDER BY**キーワードを含まないことに注意してください。 フレームワークはそれを提供します。

SQL 句の詳細については[、SQL](../../data/odbc/sql.md)句を参照してください。 レコードの並べ替えの詳細については、「[レコードセット: レコードの並べ替え (ODBC)」](../../data/odbc/recordset-sorting-records-odbc.md)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#31](../../mfc/codesnippet/cpp/crecordset-class_13.cpp)]

## <a name="crecordsetmove"></a><a name="move"></a>レコードセット::移動

レコードセット内で、現在のレコード ポインタを前方または後方に移動します。

```
virtual void Move(
    long nRows,
    WORD wFetchType = SQL_FETCH_RELATIVE);
```

### <a name="parameters"></a>パラメーター

*nRows*<br/>
前方または後方に移動する行の数。 正の値は、レコードセットの末尾に向かって前方に移動します。 負の値は、先頭に向かって後方に移動します。

*型指定*<br/>
フェッチする行セットを`Move`決定します。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

*nRows*に 0 の値を`Move`渡すと、現在のレコードが更新されます。`Move``AddNew`は、現在`Edit`またはモードを終了し、呼び出される前または`AddNew``Edit`呼び出される前に現在のレコードの値を復元します。

> [!NOTE]
> レコードセット内を移動する場合、削除されたレコードをスキップすることはできません。 詳細については[、CRecordset::IsDeleted](#isdeleted)を参照してください。 オプション セットを`CRecordset`使用して を開`Move`くと *、nRows*パラメーターが 0 の場合にアサートされます。 `skipDeletedRecords` この動作により、同じデータを使用する他のクライアント アプリケーションによって削除された行の更新が防止されます。 の説明については、[開く](#open)の*dwOption* `skipDeletedRecords`パラメーターを参照してください。

`Move`レコードセットを行セットで再配置します。 *nRows*および*wFetchType*の値に`Move`基づいて、適切な行セットをフェッチし、その行セットの最初のレコードを現在のレコードにします。 バルク行フェッチを実装していない場合、行セットのサイズは常に 1 になります。 行セットをフェッチする場合は`Move`、直接呼び出す、 [CheckRowsetError](#checkrowseterror)取得から発生したエラーを処理します。

渡す値に応じて、`Move`他`CRecordset`のメンバー関数と同じです。 特に *、wFetchType*の値は、より直感的で、多くの場合、現在のレコードを移動するための推奨される方法であるメンバー関数を示している場合があります。

次の表は *、wFetchType 、wFetchType*および`Move`*nRows*に基づいてフェッチする行セット、および*wFetchType*に対応する同等のメンバー関数の値を示*しています*。

|型指定|フェッチされた行セット|等価メンバー関数|
|----------------|--------------------|--------------------------------|
|SQL_FETCH_RELATIVE (デフォルト値)|現在の行セットの最初の行から開始する行を示す*nRows*行。||
|SQL_FETCH_NEXT|次の行セット。*n行*は無視されます。|[MoveNext](#movenext)|
|SQL_FETCH_PRIOR|前の行セット。*n行*は無視されます。|[ムーブプレヴ](#moveprev)|
|SQL_FETCH_FIRST|レコードセットの最初の行セット。*n行*は無視されます。|[最初に移動](#movefirst)|
|SQL_FETCH_LAST|レコードセット内の最後の完全な行セット。*n行*は無視されます。|[Movelast](#movelast)|
|SQL_FETCH_ABSOLUTE|*nRows が*0 >場合、レコードセットの先頭から*nRows*行を開始する行セットです。 *nRows が*0 <場合、レコードセットの末尾から*nRows*行を開始する行セットです。 *nRows* = 0 の場合は、ファイルの先頭 (BOF) 条件が返されます。|[絶対位置の設定](#setabsoluteposition)|
|SQL_FETCH_BOOKMARK|ブックマーク値が*nRows*に対応する行から始まる行セット。|[Setbookmark](#setbookmark)|

> [!NOTE]
> 前方のレコードセットの場合は`Move`、 *wFetchType*の値が SQL_FETCH_NEXT でのみ有効です。

> [!CAUTION]
> レコード`Move`セットにレコードがない場合、呼び出しは例外をスローします。 レコードセットにレコードがあるかどうかを確認するには、 [IsBOF](#isbof)と[IsEOF](#iseof)を呼び出します。

> [!NOTE]
> レコードセットの先頭または末尾を越えてスクロールした場合 (`IsBOF`または`IsEOF`0 以外を返`Move`す)、関数を`CDBException`呼び出すと、 がスローされる可能性があります。 たとえば、0`IsEOF`以外を返し`IsBOF`、返さない場合`MoveNext`は例外をスローしますが`MovePrev`、スローしません。

> [!NOTE]
> 現在のレコード`Move`の更新または追加中に呼び出すと、警告なしに更新が失われます。

レコードセットのナビゲーションの詳細については、「[レコードセット: スクロール (ODBC)」](../../data/odbc/recordset-scrolling-odbc.md)および「[レコードセット: ブックマークと絶対位置 (ODBC)」](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。 関連情報については、Windows SDK の`SQLExtendedFetch`ODBC API 関数を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#28](../../mfc/codesnippet/cpp/crecordset-class_14.cpp)]

## <a name="crecordsetmovefirst"></a><a name="movefirst"></a>レコードセット::最初に移動

最初の行セットの最初のレコードをカレント レコードにします。

```cpp
void MoveFirst();
```

### <a name="remarks"></a>解説

バルク行フェッチが実装されているかどうかに関係なく、これは常にレコードセットの最初のレコードになります。

レコードセットを開いた直後`MoveFirst`に呼び出す必要はありません。 その時点で、最初のレコード (存在する場合) は自動的に現在のレコードになります。

> [!NOTE]
> このメンバ関数は、前方のレコードセットには無効です。

> [!NOTE]
> レコードセット内を移動する場合、削除されたレコードをスキップすることはできません。 詳細については[、IsDeleted](#isdeleted)メンバー関数を参照してください。

> [!CAUTION]
> レコードセットに`Move`レコードがない場合、関数を呼び出すと例外がスローされます。 レコードセットにレコードがあるかどうかを確認するには、 と`IsBOF``IsEOF`を呼び出します。

> [!NOTE]
> 現在のレコードの`Move`更新または追加中にいずれかの関数を呼び出すと、警告なしに更新が失われます。

レコードセットのナビゲーションの詳細については、「[レコードセット: スクロール (ODBC)」](../../data/odbc/recordset-scrolling-odbc.md)および「[レコードセット: ブックマークと絶対位置 (ODBC)」](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

### <a name="example"></a>例

  [IsBOF](#isbof)の例を参照してください。

## <a name="crecordsetmovelast"></a><a name="movelast"></a>レコードセット::移動ラスト

最後の完全な行セットの最初のレコードをカレント レコードにします。

```cpp
void MoveLast();
```

### <a name="remarks"></a>解説

バルク行フェッチを実装していない場合、レコードセットのサイズは 1 なので`MoveLast`、レコードセットの最後のレコードに移動します。

> [!NOTE]
> このメンバ関数は、前方のレコードセットには無効です。

> [!NOTE]
> レコードセット内を移動する場合、削除されたレコードをスキップすることはできません。 詳細については[、IsDeleted](#isdeleted)メンバー関数を参照してください。

> [!CAUTION]
> レコードセットに`Move`レコードがない場合、関数を呼び出すと例外がスローされます。 レコードセットにレコードがあるかどうかを確認するには、 と`IsBOF``IsEOF`を呼び出します。

> [!NOTE]
> 現在のレコードの`Move`更新または追加中にいずれかの関数を呼び出すと、警告なしに更新が失われます。

レコードセットのナビゲーションの詳細については、「[レコードセット: スクロール (ODBC)」](../../data/odbc/recordset-scrolling-odbc.md)および「[レコードセット: ブックマークと絶対位置 (ODBC)」](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

### <a name="example"></a>例

  [IsBOF](#isbof)の例を参照してください。

## <a name="crecordsetmovenext"></a><a name="movenext"></a>次に進む

次の行セットの最初のレコードをカレント レコードにします。

```cpp
void MoveNext();
```

### <a name="remarks"></a>解説

バルク行フェッチを実装していない場合、レコードセットの行セットサイズは 1 なので`MoveNext`、次のレコードに移動するだけです。

> [!NOTE]
> レコードセット内を移動する場合、削除されたレコードをスキップすることはできません。 詳細については[、IsDeleted](#isdeleted)メンバー関数を参照してください。

> [!CAUTION]
> レコードセットに`Move`レコードがない場合、関数を呼び出すと例外がスローされます。 レコードセットにレコードがあるかどうかを確認するには、 と`IsBOF``IsEOF`を呼び出します。

> [!NOTE]
> また、 を呼び出`IsEOF`す前`MoveNext`に電話することをお勧めします。 たとえば、レコードセットの末尾を越えてスクロールした場合は、0`IsEOF`以外を返します。後続の呼び`MoveNext`出しは例外をスローします。

> [!NOTE]
> 現在のレコードの`Move`更新または追加中にいずれかの関数を呼び出すと、警告なしに更新が失われます。

レコードセットのナビゲーションの詳細については、「[レコードセット: スクロール (ODBC)」](../../data/odbc/recordset-scrolling-odbc.md)および「[レコードセット: ブックマークと絶対位置 (ODBC)」](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

### <a name="example"></a>例

  [IsBOF](#isbof)の例を参照してください。

## <a name="crecordsetmoveprev"></a><a name="moveprev"></a>レコードセット::ムーヴプレフ

前の行セットの最初のレコードをカレント レコードにします。

```cpp
void MovePrev();
```

### <a name="remarks"></a>解説

バルク行フェッチを実装していない場合、レコードセットの行セットサイズは 1 なので`MovePrev`、前のレコードに移動するだけです。

> [!NOTE]
> このメンバ関数は、前方のレコードセットには無効です。

> [!NOTE]
> レコードセット内を移動する場合、削除されたレコードをスキップすることはできません。 詳細については[、IsDeleted](#isdeleted)メンバー関数を参照してください。

> [!CAUTION]
> レコードセットに`Move`レコードがない場合、関数を呼び出すと例外がスローされます。 レコードセットにレコードがあるかどうかを確認するには、 と`IsBOF``IsEOF`を呼び出します。

> [!NOTE]
> また、 を呼び出`IsBOF`す前`MovePrev`に電話することをお勧めします。 たとえば、レコードセットの先頭より前にスクロールした場合は、0`IsBOF`以外を返します。後続の呼び`MovePrev`出しは例外をスローします。

> [!NOTE]
> 現在のレコードの`Move`更新または追加中にいずれかの関数を呼び出すと、警告なしに更新が失われます。

レコードセットのナビゲーションの詳細については、「[レコードセット: スクロール (ODBC)」](../../data/odbc/recordset-scrolling-odbc.md)および「[レコードセット: ブックマークと絶対位置 (ODBC)」](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

### <a name="example"></a>例

  [IsBOF](#isbof)の例を参照してください。

## <a name="crecordsetonsetoptions"></a><a name="onsetoptions"></a>レコードセット::オンセットオプション

指定した ODBC ステートメントのオプション (選択時に使用) を設定するために呼び出されます。

```
virtual void OnSetOptions(HSTMT hstmt);
```

### <a name="parameters"></a>パラメーター

*hstmt*<br/>
オプションを設定する ODBC ステートメントの HSTMT。

### <a name="remarks"></a>解説

指定`OnSetOptions`した ODBC ステートメントのオプション (選択時に使用) を設定する呼び出し。 フレームワークは、このメンバー関数を呼び出して、レコードセットの初期オプションを設定します。 `OnSetOptions`データ ソースがスクロール可能なカーソルとカーソルの同時実行に対するサポートを決定し、それに応じてレコードセットのオプションを設定します。 (一`OnSetOptions`方、選択操作に使用`OnSetUpdateOptions`され、更新操作に使用されます。

ドライバー`OnSetOptions`またはデータ ソースに固有のオプションを設定する場合はオーバーライドします。 たとえば、データ ソースが排他アクセス用に開くことをサポートしている場合`OnSetOptions`、その機能を利用するためにオーバーライドできます。

カーソルの詳細については[、ODBC](../../data/odbc/odbc-basics.md)を参照してください。

## <a name="crecordsetonsetupdateoptions"></a><a name="onsetupdateoptions"></a>レコードセット::オンセットアップデートオプション

指定した ODBC ステートメントのオプション (更新時に使用) を設定するために呼び出されます。

```
virtual void OnSetUpdateOptions(HSTMT hstmt);
```

### <a name="parameters"></a>パラメーター

*hstmt*<br/>
オプションを設定する ODBC ステートメントの HSTMT。

### <a name="remarks"></a>解説

指定`OnSetUpdateOptions`した ODBC ステートメントのオプション (更新時に使用) を設定する呼び出し。 フレームワークは、レコードセット内のレコードを更新する HSTMT を作成した後に、このメンバー関数を呼び出します。 (一`OnSetOptions`方、選択操作に使用`OnSetUpdateOptions`され、更新操作に使用されます。`OnSetUpdateOptions`データ ソースがスクロール可能なカーソルとカーソルの同時実行に対するサポートを決定し、それに応じてレコードセットのオプションを設定します。

データベース`OnSetUpdateOptions`へのアクセスに使用する前に、ODBC ステートメントのオプションを設定する場合は、オーバーライドします。

カーソルの詳細については[、ODBC](../../data/odbc/odbc-basics.md)を参照してください。

## <a name="crecordsetopen"></a><a name="open"></a>レコードセット::オープン

テーブルを取得するか、レコードセットが表すクエリを実行して、レコードセットを開きます。

```
virtual BOOL Open(
    UINT nOpenType = AFX_DB_USE_DEFAULT_TYPE,
    LPCTSTR lpszSQL = NULL,
    DWORD dwOptions = none);
```

### <a name="parameters"></a>パラメーター

*n開くタイプ*<br/>
既定値を受け入れるか、AFX_DB_USE_DEFAULT_TYPEするか、次のいずれかの値を使用`enum OpenType`します。

- `CRecordset::dynaset`双方向スクロールを行うレコードセット。 レコードのメンバーシップおよび順序は、レコードセットを開いたときに決定されますが、他のユーザーによるデータ値の変更は、フェッチ操作後に表示されます。 ダイナセットは、キーセット ドリブン レコードセットとも呼ばれます。

- `CRecordset::snapshot`双方向スクロールを伴う静的レコードセット。 レコードのメンバーシップと順序は、レコードセットを開いたときに決定されます。データ値は、レコードをフェッチしたときに決定されます。 他のユーザーが行った変更は、レコードセットを閉じてから再度開くまで表示されません。

- `CRecordset::dynamic`双方向スクロールを行うレコードセット。 他のユーザーが行ったメンバーシップ、順序、およびデータ値の変更は、フェッチ操作後に表示されます。 多くの ODBC ドライバーでは、この型のレコードセットはサポートされていません。

- `CRecordset::forwardOnly`前方スクロールのみを含む読み取り専用レコードセット。

   の`CRecordset`場合、既定値は`CRecordset::snapshot`です。 既定値の機構により、Visual C++ ウィザードで既定値の異なる ODBC `CRecordset` と DAO `CDaoRecordset` 両方を操作できます。

これらのレコードセットの種類の詳細については、「[レコードセット (ODBC) 」](../../data/odbc/recordset-odbc.md)を参照してください。 関連情報については、Windows SDK の「ブロックカーソルとスクロール可能なカーソルの使用」を参照してください。

> [!CAUTION]
> 要求した型がサポートされていない場合、例外がスローされます。

*Lpszsql*<br/>
次のいずれかを含む文字列ポインター:

- NULL ポインター。

- テーブルの名前。

- SQL **SELECT**ステートメント (オプションで SQL **WHERE**句または**ORDER BY**句を使用)。

- 定義済みクエリ (ストアド プロシージャ) の名前を指定する**CALL**ステートメント。 中かっこと**CALL**キーワードの間に空白を挿入しないように注意してください。

この文字列の詳細については、「解説」の表と ClassWizard の役割の説明を[参照してください](#remarks)。

> [!NOTE]
> 結果セット内の列の順序は、関数オーバーライドまたは[DoFieldExchange](#dofieldexchange)関数のオーバーライドにおける RFX 関数呼び出[DoBulkFieldExchange](#dobulkfieldexchange)しまたはバルク RFX 関数呼び出しの順序と一致している必要があります。

*dw オプション*<br/>
以下に示す値の組み合わせを指定できるビットマスク。 これらの値の一部は同時に指定できません。 デフォルト値は**none**です。

- `CRecordset::none`オプションが設定されていない。 このパラメーター値は、他のすべての値と同時に指定できません。 既定では、レコードセットは[[編集]](#edit)または[[削除]](#delete)を使用して更新でき[、AddNew](#addnew)を使用して新しいレコードを追加できます。 更新可能性は、指定した*nOpenType*オプションだけでなく、データ ソースによって異なります。 バルク追加の最適化は使用できません。 バルク行フェッチは実装されません。 削除されたレコードはレコードセットの移動中にスキップされません。 ブックマークは使用できません。 自動ダーティ フィールド チェックが実装されます。

- `CRecordset::appendOnly`レコードセットを`Edit`許可`Delete`しないか、レコードセットに対して使用しないでください。 `AddNew` のみ実行できます。 このオプションは `CRecordset::readOnly` と同時に指定できません。

- `CRecordset::readOnly`レコードセットを読み取り専用で開きます。 このオプションは `CRecordset::appendOnly` と同時に指定できません。

- `CRecordset::optimizeBulkAdd`準備済みの SQL ステートメントを使用して、一度に多数のレコードを追加することを最適化します。 レコードセットの更新に ODBC API 関数`SQLSetPos`を使用していない場合にのみ適用されます。 最新の更新で、ダーティとマークされるフィールドが決まります。 このオプションは `CRecordset::useMultiRowFetch` と同時に指定できません。

- `CRecordset::useMultiRowFetch`一括行フェッチを実装して、1 回のフェッチ操作で複数の行を取得できるようにします。 これは、パフォーマンスを向上するために設計された拡張機能です。ただし、バルク レコード フィールド エクスチェンジは ClassWizard ではサポートされていません。 このオプションは `CRecordset::optimizeBulkAdd` と同時に指定できません。 を指定`CRecordset::useMultiRowFetch`すると、オプション`CRecordset::noDirtyFieldCheck`が自動的にオンになります (ダブル バッファリングは使用できません)。転送専用レコードセットでは、このオプション`CRecordset::useExtendedFetch`は自動的にオンになります。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

- `CRecordset::skipDeletedRecords`レコードセット内を移動するときに、削除されたすべてのレコードをスキップします。 これにより、特定の相対フェッチでパフォーマンスが低下します。 このオプションは前方スクロール専用レコードセットでは無効です。 *nRows*パラメータを 0 に設定して[Move](#move)を`CRecordset::skipDeletedRecords`呼び出`Move`すと、オプションがアサートされます。 ドライバの`CRecordset::skipDeletedRecords`*パッキング*に似ており、削除された行がレコードセットから削除されることを意味します。 ただし、ドライバーによってレコードがパックされる場合、ユーザー自身が削除するレコードだけがスキップされます。レコードセットを開いている間に他のユーザーによって削除されたレコードはスキップされません。 `CRecordset::skipDeletedRecords`他のユーザーによって削除された行はスキップされます。

- `CRecordset::useBookmarks`サポートされている場合は、レコードセットでブックマークを使用できます。 ブックマークを使用すると、データの取得速度は低下しますが、データ移動のパフォーマンスが向上します。 前方スクロール専用レコードセットでは無効です。 詳細については、「[レコードセット: ブックマークと絶対位置 (ODBC)」](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)を参照してください。

- `CRecordset::noDirtyFieldCheck`ダーティ フィールドの自動チェック (ダブル バッファリング) をオフにします。 これにより、パフォーマンスは向上しますが、`SetFieldDirty` メンバー関数と `SetFieldNull` メンバー関数を呼び出して手動でフィールドをダーティとしてマークする必要があります。`CRecordset` クラスのダブル バッファリングは、`CDaoRecordset` クラスのダブル バッファリングに似ています。 ただし、`CRecordset` では、個別のフィールドに対してダブル バッファリングを有効にできません。すべてのフィールドに対して有効にするか、またはすべてのフィールドに対して無効にします。 オプション`CRecordset::useMultiRowFetch`を指定すると、`CRecordset::noDirtyFieldCheck`自動的にオンになります。ただし、`SetFieldDirty`バルク`SetFieldNull`行フェッチを実装するレコードセットでは使用できません。

- `CRecordset::executeDirect`準備済み SQL ステートメントは使用しないでください。 パフォーマンスを向上させるには、メンバー関数が`Requery`呼び出されることのない場合に、このオプションを指定します。

- `CRecordset::useExtendedFetch`の`SQLExtendedFetch`代わりに`SQLFetch`実装します。 これは、前方スクロール専用レコードセットに対してバルク行フェッチを実装するために設計されています。 前方スクロール専用レコードセット`CRecordset::useMultiRowFetch`にオプションを指定すると`CRecordset::useExtendedFetch`、自動的にオンになります。

- `CRecordset::userAllocMultiRowBuffers`ユーザーはデータのストレージ バッファを割り当てます。 独自の格納バッファーを割り当てる場合は、このオプションと一緒に `CRecordset::useMultiRowFetch` を使用します。使用しない場合、必要な格納バッファーが自動的に割り当てられます。 詳細については、「[レコードセット : レコードを一括でフェッチする (ODBC) 」](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)を参照してください。 指定せずに指定`CRecordset::useMultiRowFetch`すると`CRecordset::userAllocMultiRowBuffers`、アサーションが失敗することに注意してください。

### <a name="return-value"></a>戻り値

オブジェクトが正常に`CRecordset`開かれた場合は 0 以外の値を指定します。それ以外の場合は 0 を返す[場合 CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) (呼び出された場合) 0 を返します。

### <a name="remarks"></a>解説

レコードセットによって定義されたクエリを実行するには、このメンバー関数を呼び出す必要があります。 を呼`Open`び出す前に、レコードセット オブジェクトを作成する必要があります。

このレコードセットのデータ ソースへの接続は、 を呼び出す`Open`前にレコードセットを構築する方法によって異なります。 データ ソースに接続されていないレコードセット コンストラクターに[CDatabase](../../mfc/reference/cdatabase-class.md)オブジェクトを渡すと、このメンバー関数は[GetDefaultConnect](#getdefaultconnect)を使用してデータベース オブジェクトを開こうとします。 NULL をレコードセット コンストラクターに渡すと、コンストラクターはオブジェクト`CDatabase`を作成し`Open`、データベース オブジェクトの接続を試みます。 このような状況でレコードセットと接続を閉じる方法の詳細については、「[閉じる](#close)」を参照してください。

> [!NOTE]
> `CRecordset` オブジェクトを使用したデータ ソースへのアクセスは常に共有されます。 `CDaoRecordset` クラスとは異なり、`CRecordset` オブジェクトを使用して排他アクセスでデータ ソースを開くことはできません。

クエリ (`Open`通常は SQL **SELECT**ステートメント) を呼び出すと、次の表に示す条件に基づいてレコードが選択されます。

|lpszSQL パラメーターの値|レコードの選択基準|例|
|------------------------------------|----------------------------------------|-------------|
|NULL|`GetDefaultSQL` の返す文字列。||
|SQL テーブル名|`DoFieldExchange` または `DoBulkFieldExchange` のテーブル リストのすべての列。|`"Customer"`|
|定義済みクエリ (ストアド プロシージャ) の名前|返すためにクエリが定義された列。|`"{call OverDueAccts}"`|
|テーブルリスト**から**列リストを**選択**|指定したテーブルの指定した列。|`"SELECT CustId, CustName FROM`<br /><br /> `Customer"`|

> [!CAUTION]
> SQL 文字列に余分な空白を挿入しないでください。 たとえば、中かっこと**CALL**キーワードの間に空白を挿入すると、MFC は SQL 文字列をテーブル名として誤って解釈し **、SELECT**ステートメントに組み込むことで例外がスローされます。 同様に、定義済みクエリで出力パラメータを使用する場合は、中かっこと '' 記号の間に空白を挿入しないでください。 最後に **、CALL**ステートメントで中かっこの前に空白を挿入したり **、SELECT**ステートメントで**SELECT**キーワードの前に空白を挿入したりしないでください。

通常のプロシージャは NULL を`Open`に渡します。この場合は`Open`[、GetDefaultSQL](#getdefaultsql)を呼び出します。 派生`CRecordset`クラスを使用している場合は、ClassWizard`GetDefaultSQL`で指定したテーブル名を指定します。 代わりに、その他の情報を `lpszSQL` パラメーターに指定できます。

渡す値は`Open`何であれ、クエリの最終的な SQL 文字列を構築し (渡した文字列に SQL **WHERE** `lpszSQL`句と ORDER **BY**句が追加されている場合があります)、クエリを実行します。 を呼び出した後で[GetSQL](#getsql)を`Open`呼び出すことによって、構築された文字列を調べることができます。 レコードセットが SQL ステートメントを構築し、レコードを選択する方法の詳細については、「[レコードセット: レコードセットの選択方法 (ODBC)」](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)を参照してください。

レコードセット クラスのフィールド データ メンバーは、選択したデータの列に結び付けられています。 いくつかのレコードが返された場合、最初のレコードが現在のレコードになります。

フィルタや並べ替えなどのレコードセットのオプションを設定する場合は、レコードセット オブジェクトを構築した後、呼び出`Open`す前に、これらのオプションを指定します。 レコードセットが既に開かれた後でレコードセットのレコードを更新する場合は、 [Requery](#requery)を呼び出します。

その他の例を含む詳細については、「[レコードセット (ODBC)、](../../data/odbc/recordset-odbc.md)[レコードセット: レコードセットの選択方法 (ODBC)」、](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)および[「レコードセット: レコードセットの作成と終了 (ODBC)」](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)を参照してください。

### <a name="example"></a>例

次のコード例は、さまざまな形式の`Open`呼び出しを示しています。

[!code-cpp[NVC_MFCDatabase#16](../../mfc/codesnippet/cpp/crecordset-class_15.cpp)]

## <a name="crecordsetrefreshrowset"></a><a name="refreshrowset"></a>レコードセット::リフレッシュローセット

現在の行セットの行のデータと状態を更新します。

```cpp
void RefreshRowset(
    WORD wRow,
    WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>パラメーター

*wRow*<br/>
現在の行セット内の行の 1 から 1 から成る位置。 この値は、0 から行セットのサイズまでの範囲です。

*タイプ*<br/>
更新後に行をロックする方法を示す値。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

*wRow*に 0 の値を渡すと、行セット内のすべての行が更新されます。

を使用`RefreshRowset`するには`CRecordset::useMulitRowFetch`[、Open](#open)メンバー関数でオプションを指定してバルク行フェッチを実装している必要があります。

`RefreshRowset`ODBC API 関数`SQLSetPos`を呼び出します。 *wLockType*パラメーターは、実行後`SQLSetPos`の行のロック状態を指定します。 次の表は *、wLockType*の値を示しています。

|タイプ|説明|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE (デフォルト値)|ドライバまたはデータ ソースは、行が以前`RefreshRowset`に呼び出されたのと同じロック状態またはロック解除状態であることを保証します。|
|SQL_LOCK_EXCLUSIVE|ドライバーまたはデータ ソースは、行を排他的にロックします。 すべてのデータ ソースがこの種のロックをサポートしているわけではありません。|
|SQL_LOCK_UNLOCK|ドライバまたはデータ ソースが行のロックを解除します。 すべてのデータ ソースがこの種のロックをサポートしているわけではありません。|

の詳細については`SQLSetPos`、Windows SDK を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

## <a name="crecordsetrequery"></a><a name="requery"></a>レコードセット::再クエリ

レコードセットを再構築 (更新) します。

```
virtual BOOL Requery();
```

### <a name="return-value"></a>戻り値

レコードセットが正常に再構築された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

いくつかのレコードが返された場合、最初のレコードが現在のレコードになります。

レコードセットに、データ ソースに対して行った追加および削除を反映させるには、 を呼び出`Requery`してレコードセットを再構築する必要があります。 レコードセットがダイナセットの場合、ユーザーまたは他のユーザーが既存のレコードに対して行った更新が自動的に反映されます (追加は行いません)。 レコードセットがスナップショットの場合は、他の`Requery`ユーザーによる編集、追加、削除を反映するために呼び出す必要があります。

ダイナセットまたはスナップショットの場合は、新しい`Requery`フィルタまたは並べ替え、または新しいパラメータ値を使用してレコードセットを再構築する必要があるときはいつでも呼び出します。 を呼び出す前に新しい値を割り`m_strFilter`当`m_strSort`てることによって`Requery`、新しいフィルタまたは並べ替えのプロパティを設定します。 を呼び出す`Requery`前に、新しい値をパラメーター データ メンバーに割り当てることで、新しいパラメーターを設定します。 フィルタ文字列とソート文字列が変更されていない場合は、クエリを再利用できるため、パフォーマンスが向上します。

レコードセットの再構築に失敗すると、レコードセットは閉じられます。 を呼び`Requery`出す前に、メンバー関数を呼び出してレコードセットを`CanRestart`再クエリできるかどうかを確認できます。 `CanRestart`は成功を`Requery`保証するものではありません。

> [!CAUTION]
> `Requery` [[開く](#open)] を呼び出した後にのみ呼び出す。

### <a name="example"></a>例

次の使用例は、異なる並べ替え順序を適用するようにレコードセットを再構築します。

[!code-cpp[NVC_MFCDatabase#29](../../mfc/codesnippet/cpp/crecordset-class_16.cpp)]

## <a name="crecordsetsetabsoluteposition"></a><a name="setabsoluteposition"></a>レコードセット::絶対位置を設定します。

指定したレコード番号に対応するレコードにレコードセットを配置します。

```cpp
void SetAbsolutePosition(long nRows);
```

### <a name="parameters"></a>パラメーター

*nRows*<br/>
レコードセット内の現在のレコードの 1 から成る序数の位置。

### <a name="remarks"></a>解説

`SetAbsolutePosition`この序数の位置に基づいて、現在のレコード ポインタを移動します。

> [!NOTE]
> このメンバ関数は、前方のレコードセットでは無効です。

ODBC レコードセットの場合、絶対位置の設定が 1 の場合は、レコードセットの最初のレコードを参照します。0 の設定は、ファイルの先頭 (BOF) 位置を表します。

負の値を に`SetAbsolutePosition`渡すこともできます。 この場合、レコードセットの位置はレコードセットの末尾から評価されます。 たとえば、`SetAbsolutePosition( -1 )`カレント レコード ポインタをレコードセットの最後のレコードに移動します。

> [!NOTE]
> 絶対位置は、代理レコード番号として使用することを意図していません。 先行するレコードが削除されるとレコードの位置が変わるため、ブックマークは、指定された位置を保持して戻す場合に推奨される方法です。 また **、ORDER BY**句を使用して SQL ステートメントを使用して作成しない限り、レコードセット内の個々のレコードの順序は保証されないため、レコードセットを再作成しても、レコードセットの絶対位置が同じになることは保証されません。

レコードセットのナビゲーションとブックマークの詳細については、「[レコードセット: スクロール (ODBC)」](../../data/odbc/recordset-scrolling-odbc.md)および「[レコードセット: ブックマークと絶対位置 (ODBC)」](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)を参照してください。

## <a name="crecordsetsetbookmark"></a><a name="setbookmark"></a>を設定します。

指定したブックマークを含むレコードにレコードセットを配置します。

```cpp
void SetBookmark(const CDBVariant& varBookmark);
```

### <a name="parameters"></a>パラメーター

*を見る*<br/>
特定のレコードのブックマーク値を含む[CDBVariant](../../mfc/reference/cdbvariant-class.md)オブジェクトへの参照。

### <a name="remarks"></a>解説

ブックマークがレコードセットでサポートされているかどうかを確認するには、 [CanBookmark](#canbookmark)を呼び出します。 ブックマークがサポートされている場合にブックマークを使用できるようにするには[、Open](#open)メンバー`CRecordset::useBookmarks`関数の*dwOptions*パラメーターでオプションを設定する必要があります。

> [!NOTE]
> ブックマークがサポートされていないか、使用できない場合、`SetBookmark`呼び出しは例外がスローされます。 前方のみのレコードセットではブックマークはサポートされていません。

現在のレコードのブックマークを取得するには[、GetBookmark](#getbookmark)を呼び出して、オブジェクトにブックマーク`CDBVariant`値を保存します。 保存されたブックマーク値を使用して呼び出`SetBookmark`して、後でレコードに戻ることができます。

> [!NOTE]
> 特定のレコードセット操作の後、呼び出す`SetBookmark`前にブックマークの永続性を確認する必要があります。 たとえば、 で`GetBookmark`ブックマークを取得し、 を呼`Requery`び出すと、ブックマークが無効になることがあります。 [を](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence)呼び出して、安全に呼び出`SetBookmark`すことができるかどうかを確認します。

ブックマークとレコードセットナビゲーションの詳細については、「[レコードセット: ブックマークと絶対位置 (ODBC)」](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)および「[レコードセット: スクロール (ODBC)」](../../data/odbc/recordset-scrolling-odbc.md)を参照してください。

## <a name="crecordsetsetfielddirty"></a><a name="setfielddirty"></a>Cレコード::セットフィールドダーティ

レコードセットのフィールド データ メンバーに、変更済みまたは変更なしのフラグを設定します。

```cpp
void SetFieldDirty(void* pv, BOOL bDirty = TRUE);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
レコードセット内のフィールド データ メンバーのアドレスを格納します。 NULL の場合、レコードセット内のすべてのフィールド データ メンバにフラグが設定されます。 (C++ NULL は、データベース用語では NULL と同じではありません。

*bダーティ*<br/>
フィールド データ メンバーに "ダーティ" (変更) のフラグを付ける場合は TRUE。 それ以外の場合は FALSE を指定すると、フィールド データ メンバーは "クリーン" (変更なし) としてフラグが設定されます。

### <a name="remarks"></a>解説

フィールドを変更しないマークを付ければ、フィールドが更新されず、SQL トラフィックが少なくなります。

> [!NOTE]
> このメンバー関数は、バルク行フェッチを使用しているレコードセットには適用できません。 バルク行フェッチを実装している場合`SetFieldDirty`は、アサーションが失敗します。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

フレームワークは、変更されたフィールド データ メンバーをマークして、レコード フィールド エクスチェンジ (RFX) メカニズムによってデータ ソースのレコードに書き込まれるようにします。 フィールドの値を変更すると、通常はフィールドが自動的にダーティになるため、自分で`SetFieldDirty`呼び出す必要が生じることはめったにありませんが、フィールド データ メンバーの値に関係なく、列を明示的に更新または挿入する必要がある場合があります。

> [!CAUTION]
> このメンバー関数は、呼び出した後に[[編集]](#edit)または[[AddNew]](#addnew)を呼び出した後にのみ呼び出します。

関数の最初の引数に NULL を使用すると、関数は`outputColumn`フィールドに対`param`してのみ適用され、フィールドには適用されません。 たとえば、コール

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

フィールドのみを`outputColumn`NULL に設定します。`param`フィールドは影響を受けません。

フィールドで`param`作業するには、次のような作業を行う個人`param`の実際のアドレスを指定する必要があります。

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

つまり、フィールドの場合と`param`同様`outputColumn`に、すべてのフィールドを NULL に設定することはできません。

## <a name="crecordsetsetfieldnull"></a><a name="setfieldnull"></a>レコードセット::セットフィールドNull

レコードセットのフィールド データ メンバーに、Null (特に値がない) または Null 以外のフラグを設定します。

```cpp
void SetFieldNull(void* pv, BOOL bNull = TRUE);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
レコードセット内のフィールド データ メンバーのアドレスを格納します。 NULL の場合、レコードセット内のすべてのフィールド データ メンバにフラグが設定されます。 (C++ NULL は、データベース用語では NULL と同じではありません。

*を返す*<br/>
フィールド データ メンバーに値なし (Null) のフラグを設定する場合は、0 以外の値を指定します。 それ以外の場合は、フィールド データ メンバーに Null 以外のフラグが設定されます。

### <a name="remarks"></a>解説

レコードセットに新しいレコードを追加すると、すべてのフィールド データ メンバーは、最初は Null 値に設定され、"ダーティ" (変更) としてフラグが設定されます。 データ ソースからレコードを取得する場合、その列には既に値があるか、Null です。

> [!NOTE]
> バルク行フェッチを使用しているレコードセットでは、このメンバー関数を呼び出しません。 バルク行フェッチを実装している場合、呼び出`SetFieldNull`しはアサーションの失敗につながります。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

現在のレコードのフィールドに値がないものとして指定する場合は *、bNull*を`SetFieldNull`TRUE に設定して呼び出して Null としてフラグを設定します。 フィールドが以前に Null としてマークされている場合に値を指定する場合は、単に新しい値を設定します。 Null フラグを削除する必要はありません`SetFieldNull`。 フィールドが Null にできるかどうかを判断するには、 を`IsFieldNullable`呼び出します。

> [!CAUTION]
> このメンバー関数は、呼び出した後に[[編集]](#edit)または[[AddNew]](#addnew)を呼び出した後にのみ呼び出します。

関数の最初の引数に NULL を使用すると、関数は`outputColumn`フィールドに対`param`してのみ適用され、フィールドには適用されません。 たとえば、コール

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

フィールドのみを`outputColumn`NULL に設定します。`param`フィールドは影響を受けません。

フィールドで`param`作業するには、次のような作業を行う個人`param`の実際のアドレスを指定する必要があります。

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

つまり、フィールドの場合と`param`同様`outputColumn`に、すべてのフィールドを NULL に設定することはできません。

> [!NOTE]
> パラメーターを Null に設定すると、`SetFieldNull`レコードセットが開かれる前に呼び出されるとアサーションが発生します。 この場合は、を呼び出[します](#setparamnull)。

`SetFieldNull`は[、ドフィールドエクスチェンジ](#dofieldexchange)を通じて実装されます。

## <a name="crecordsetsetlockingmode"></a><a name="setlockingmode"></a>レコードセット::セットロックモード

ロックモードを「オプティミスティック」ロック(デフォルト)または「悲観的」ロックに設定します。 更新のためにレコードをロックする方法を指定します。

```cpp
void SetLockingMode(UINT nMode);
```

### <a name="parameters"></a>パラメーター

*nモード*<br/>
に次のいずれかの値が`enum LockMode`含まれています。

- `optimistic`オプティミスティック ロックは、 への呼び`Update`出し中にのみ更新されるレコードをロックします。

- `pessimistic`悲観的ロックは、呼び出し`Edit`が完了するか、新しいレコードに`Update`移動するまで、レコードをロックし、ロックしたままにします。

### <a name="remarks"></a>解説

レコードセットが更新に使用する 2 つのレコード ロック方式のうちどちらを指定する必要がある場合は、このメンバー関数を呼び出します。 既定では、レコードセットのロック モードは`optimistic`です。 より慎重`pessimistic`なロック戦略に変更できます。 レコード`SetLockingMode`セット オブジェクトを構築して開いた後、呼び`Edit`出す前に 呼び出します。

## <a name="crecordsetsetparamnull"></a><a name="setparamnull"></a>レコードセット::セットパラムヌル

パラメーターに Null (特に値がない) または Null 以外のフラグを設定します。

```cpp
void SetParamNull(
    int nIndex,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
パラメーターの 0 から始まるインデックス。

*を返す*<br/>
TRUE (既定値) の場合、パラメーターは Null としてフラグが設定されます。 それ以外の場合、パラメーターには Null 以外のフラグが付けられます。

### <a name="remarks"></a>解説

[SetFieldNull](#setfieldnull)とは異なり`SetParamNull`、レコードセットを開く前に呼び出すことができます。

`SetParamNull`通常は、定義済みのクエリ (ストアド プロシージャ) で使用されます。

## <a name="crecordsetsetrowsetcursorposition"></a><a name="setrowsetcursorposition"></a>カーソル位置を設定します。

カーソルを現在の行セット内の行に移動します。

```cpp
void SetRowsetCursorPosition(WORD wRow, WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>パラメーター

*wRow*<br/>
現在の行セット内の行の 1 から 1 から成る位置。 この値は、1 から行セットのサイズまでの範囲です。

*タイプ*<br/>
更新後に行をロックする方法を示す値です。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

バルク行フェッチを実装する場合、レコードは行セットによって取得され、フェッチされた行セットの最初のレコードが現在のレコードになります。 行セット内の別のレコードを現在のレコードにするには、 を`SetRowsetCursorPosition`呼び出します。 たとえば[、GetFieldValue](#getfieldvalue) `SetRowsetCursorPosition`メンバー関数と組み合わせて、レコードセットの任意のレコードからデータを動的に取得できます。

を使用`SetRowsetCursorPosition`するには[、Open](#open)メンバー関数で*dwOptions*パラメーターの`CRecordset::useMultiRowFetch`オプションを指定して、バルク行フェッチを実装している必要があります。

`SetRowsetCursorPosition`ODBC API 関数`SQLSetPos`を呼び出します。 *wLockType*パラメーターは、実行後`SQLSetPos`の行のロック状態を指定します。 次の表は *、wLockType*の値を示しています。

|タイプ|説明|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE (デフォルト値)|ドライバまたはデータ ソースは、行が以前`SetRowsetCursorPosition`に呼び出されたのと同じロック状態またはロック解除状態であることを保証します。|
|SQL_LOCK_EXCLUSIVE|ドライバーまたはデータ ソースは、行を排他的にロックします。 すべてのデータ ソースがこの種のロックをサポートしているわけではありません。|
|SQL_LOCK_UNLOCK|ドライバまたはデータ ソースが行のロックを解除します。 すべてのデータ ソースがこの種のロックをサポートしているわけではありません。|

の詳細については`SQLSetPos`、Windows SDK を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

## <a name="crecordsetsetrowsetsize"></a><a name="setrowsetsize"></a>セットレコード::セットローセットサイズ

フェッチ中に取得するレコードの数を指定します。

```
virtual void SetRowsetSize(DWORD dwNewRowsetSize);
```

### <a name="parameters"></a>パラメーター

*サイズを変更します。*<br/>
特定のフェッチ中に取得する行数。

### <a name="remarks"></a>解説

この仮想メンバー関数は、バルク行フェッチを使用する場合に、1 回のフェッチ時に取得する行数を指定します。 バルク行フェッチを実装するには[、Open](#open)メンバー関数`CRecordset::useMultiRowFetch`の*dwOptions*パラメーターでオプションを設定する必要があります。

> [!NOTE]
> バルク`SetRowsetSize`行フェッチを実装せずに呼び出すと、アサーションが失敗します。

最初`SetRowsetSize`にレコード`Open`セットのサイズを設定する呼び出しの前に呼び出します。 バルク行フェッチを実装する場合のデフォルトの行セットサイズは 25 です。

> [!NOTE]
> を呼び出`SetRowsetSize`す際には注意が必要です。 データのストレージを手動で割り当てる場合は ( `CRecordset::userAllocMultiRowBuffers` dwOptions パラメータのオプションで`Open`指定) を呼び出`SetRowsetSize`した後、カーソルナビゲーション操作を実行する前に、これらのストレージ バッファを再割り当てする必要があるかどうかを確認する必要があります。

行セットサイズの現在の設定を取得するには[、GetRowsetSize](#getrowsetsize)を呼び出します。

バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

## <a name="crecordsetupdate"></a><a name="update"></a>レコードセット::更新

新規または編集`AddNew`した`Edit`データをデータ ソースに保存して、または 操作を完了します。

```
virtual BOOL Update();
```

### <a name="return-value"></a>戻り値

1 つのレコードが正常に更新された場合は 0 以外の値を返します。それ以外の場合は 0 (列が変更されていない場合)。 レコードが更新されなかった場合、または複数のレコードが更新された場合は、例外がスローされます。 データ ソースで他のエラーが発生した場合も例外がスローされます。

### <a name="remarks"></a>解説

[AddNew](#addnew)または[Edit](#edit)メンバー関数を呼び出した後、このメンバー関数を呼び出します。 この呼び出しは、 `AddNew` `Edit`または 操作を完了するために必要です。

> [!NOTE]
> バルク行フェッチを実装している場合は、 を呼び`Update`出すことはできません。 これにより、アサーションが失敗します。 クラス`CRecordset`は、データのバルク行を更新するためのメカニズムを提供していませんが、ODBC API 関数`SQLSetPos`を使用して独自の関数を記述できます。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

また`AddNew`、`Edit`データ ソースに保存するために、追加または編集したデータが格納される編集バッファーを準備します。 `Update`データを保存します。 変更済みとしてマークまたは検出されたフィールドのみが更新されます。

データ ソースがトランザクションをサポートしている場合は、トランザクション`Update`の呼び出し`AddNew` `Edit` (およびそれに対応する呼び出し) の一部を作成できます。 トランザクションの詳細については、「[トランザクション (ODBC) 」](../../data/odbc/transaction-odbc.md)を参照してください。

> [!CAUTION]
> を最初に`Update`呼び出さず`AddNew`に`Edit`呼`Update`び出す`CDBException`場合は、 または をスローします。 または`AddNew``Edit`を呼び出す場合`Update`は、`Move`操作を呼び出す前、またはレコードセットまたはデータ ソース接続を閉じる前に呼び出す必要があります。 それ以外の場合、変更は通知なしで失われます。

失敗の`Update`処理の詳細については、「[レコードセット : レコードセットがレコードを更新する方法 (ODBC)」](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)を参照してください。

### <a name="example"></a>例

「[トランザクション: レコードセットでのトランザクションの実行 (ODBC)」](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)を参照してください。

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordView クラス](../../mfc/reference/crecordview-class.md)
