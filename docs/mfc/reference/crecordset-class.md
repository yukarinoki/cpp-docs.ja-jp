---
title: CRecordset クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98177ada976196da7590464ab5c6412b2c7f28a3
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079943"
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
|[CRecordset::CRecordset](#crecordset)|`CRecordset` オブジェクトを構築します。 派生クラスでは、この関数を呼び出すコンス トラクターを提供する必要があります。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRecordset::AddNew](#addnew)|新しいレコードを追加する準備をします。 呼び出す`Update`追加を完了します。|  
|[CRecordset::CanAppend](#canappend)|使用して、レコード セットに新しいレコードを追加する場合は 0 以外を返します、`AddNew`メンバー関数。|  
|[値](#canbookmark)|レコード セットは、ブックマークをサポートする場合は 0 以外を返します。|  
|[CRecordset::Cancel](#cancel)|非同期操作または 2 番目のスレッドからのプロセスをキャンセルします。|  
|[CRecordset::CancelUpdate](#cancelupdate)|キャンセルの理由のため、保留中の更新プログラム、`AddNew`または`Edit`操作します。|  
|[CRecordset::CanRestart](#canrestart)|場合は 0 以外を返します`Requery`レコード セットのクエリを再実行を呼び出すことができます。|  
|[CRecordset::CanScroll](#canscroll)|レコード間をスクロールできる場合は 0 以外を返します。|  
|[CRecordset::CanTransact](#cantransact)|データ ソースには、トランザクションがサポートしている場合は 0 以外を返します。|  
|[CRecordset::CanUpdate](#canupdate)|レコード セットを更新する場合は 0 以外を返します (することができますを追加、更新、またはレコードを削除) します。|  
|[CRecordset::CheckRowsetError](#checkrowseterror)|レコードのフェッチ中に生成されたエラーの処理と呼ばれます。|  
|[ような場合](#close)|レコード セットと、ODBC 閉じます**HSTMT**関連付けられています。|  
|[CRecordset::Delete](#delete)|レコード セットから現在のレコードを削除します。 削除された後は、別のレコードに明示的にスクロールする必要があります。|  
|[CRecordset::DoBulkFieldExchange](#dobulkfieldexchange)|バルク行をデータ ソースからレコード セットへのデータを交換するには、呼び出されます。 レコード フィールド エクス チェンジ (Bulk RFX) の一括を実装します。|  
|[CRecordset::DoFieldExchange](#dofieldexchange)|レコード セットのフィールド データ メンバーと、データ ソースに対応するレコードの間で (双方向) のデータを交換するには、呼び出されます。 レコード フィールド エクス (チェンジ RFX) をを実装します。|  
|[CRecordset::Edit](#edit)|現在のレコードへの変更を準備します。 呼び出す`Update`編集を完了します。|  
|[CRecordset::FlushResultSet](#flushresultset)|別の結果がある場合は 0 以外を返しますでは、定義済みクエリを使用する場合は、取得する設定。|  
|[CRecordset::GetBookmark](#getbookmark)|パラメーター オブジェクトには、レコードのブックマークの値を割り当てます。|  
|[:Getdefaultconnect](#getdefaultconnect)|既定の接続文字列を取得するには、呼び出されます。|  
|[CRecordset::GetDefaultSQL](#getdefaultsql)|実行する既定の SQL 文字列を取得するには、呼び出されます。|  
|[CRecordset::GetFieldValue](#getfieldvalue)|レコード セット内のフィールドの値を返します。|  
|[CRecordset::GetODBCFieldCount](#getodbcfieldcount)|レコード セットのフィールドの数を返します。|  
|[に](#getodbcfieldinfo)|レコード セットから特定の種類のフィールドに関する情報を返します。|  
|[CRecordset::GetRecordCount](#getrecordcount)|レコード セットのレコードの数を返します。|  
|[CRecordset::GetRowsetSize](#getrowsetsize)|1 回のフェッチ中に取得するレコードの数を返します。|  
|[CRecordset::GetRowsFetched](#getrowsfetched)|フェッチ中に取得される行の実際の数を返します。|  
|[CRecordset::GetRowStatus](#getrowstatus)|フェッチ後に、行の状態を返します。|  
|[CRecordset::GetSQL](#getsql)|レコード セットのレコードを選択するために使用する SQL 文字列を取得します。|  
|[CRecordset::GetStatus](#getstatus)|レコード セットの状態を取得します。 現在のレコードと、レコードの最後の数が取得されたかどうかのインデックス。|  
|[CRecordset::GetTableName](#gettablename)|レコード セットを基になるテーブルの名前を取得します。|  
|[CRecordset::IsBOF](#isbof)|レコード セットは、最初のレコードの前に位置付けられている場合は 0 以外を返します。 現在のレコードがありません。|  
|[CRecordset::IsDeleted](#isdeleted)|レコード セットが削除されたレコードに配置されている場合は 0 以外を返します。|  
|[CRecordset::IsEOF](#iseof)|レコード セットは、後の最後のレコードに位置付けられている場合は 0 以外を返します。 現在のレコードがありません。|  
|[CRecordset::IsFieldDirty](#isfielddirty)|現在のレコードで指定されたフィールドが変更された場合は 0 以外を返します。|  
|[CRecordset::IsFieldNull](#isfieldnull)|現在のレコードで指定されたフィールドが null の場合は 0 以外を返します (値はありません)。|  
|[CRecordset::IsFieldNullable](#isfieldnullable)|現在のレコードで指定されたフィールドは、(値を持たない) を null に設定することができる場合は 0 以外を返します。|  
|[CRecordset::IsOpen](#isopen)|場合は 0 以外を返します`Open`既に呼び出されています。|  
|[CRecordset::Move](#move)|どちらの方向に現在のレコードから指定した数のレコードに、レコード セットを配置します。|  
|[CRecordset::MoveFirst](#movefirst)|レコード セットの最初のレコードの現在のレコードを配置します。 テスト`IsBOF`最初。|  
|[CRecordset::MoveLast](#movelast)|最後のレコードまたは最後の行セットは、現在のレコードを位置付けます。 テスト`IsEOF`最初。|  
|[CRecordset::MoveNext](#movenext)|次のレコードまたは次の行セットは、現在のレコードを位置付けます。 テスト`IsEOF`最初。|  
|[CRecordset::MovePrev](#moveprev)|前のレコードまたは前の行セットは、現在のレコードを位置付けます。 テスト`IsBOF`最初。|  
|[CRecordset::OnSetOptions](#onsetoptions)|指定された ODBC ステートメントには、(選択に使用する) オプションを設定すると呼ばれます。|  
|[CRecordset::OnSetUpdateOptions](#onsetupdateoptions)|指定された ODBC ステートメントのオプション (更新プログラムで使用される) を設定すると呼ばれます。|  
|[:Open](#open)|テーブルを取得するか、レコードセットが表すクエリを実行して、レコードセットを開きます。|  
|[CRecordset::RefreshRowset](#refreshrowset)|指定した行の状態とデータを更新します。|  
|[:Requery](#requery)|選択したレコードを更新するには、もう一度、レコード セットのクエリを実行します。|  
|[CRecordset::SetAbsolutePosition](#setabsoluteposition)|指定されたレコード番号に対応するレコードのレコード セットを配置します。|  
|[CRecordset::SetBookmark](#setbookmark)|ブックマークが指定されたレコードのレコード セットを配置します。|  
|[CRecordset::SetFieldDirty](#setfielddirty)|変更されると、現在のレコードで指定したフィールドをマークします。|  
|[CRecordset::SetFieldNull](#setfieldnull)|現在のレコード (値を持たない) を null に指定されたフィールドの値を設定します。|  
|[CRecordset::SetLockingMode](#setlockingmode)|ロック (既定)「オプティミスティック」または「ペシミスティック」をロックするロック モードを設定します。 更新プログラムのレコードをロックする方法を決定します。|  
|[CRecordset::SetParamNull](#setparamnull)|Null (値を持たない) を指定されたパラメーターを設定します。|  
|[CRecordset::SetRowsetCursorPosition](#setrowsetcursorposition)|行セット内の指定された行にカーソルを位置付けます。|  
|[CRecordset::SetRowsetSize](#setrowsetsize)|フェッチ中に取得するレコードの数を指定します。|  
|[CRecordset::Update](#update)|完了、`AddNew`または`Edit`データ ソースで新しいまたは更新されたデータを保存することで操作します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CRecordset::m_hstmt](#m_hstmt)|レコード セットの ODBC ステートメント ハンドルが含まれています。 「`HSTMT`」と入力します。|  
|[CRecordset::m_nFields](#m_nfields)|レコード セットのフィールド データ メンバーの数が含まれています。 「`UINT`」と入力します。|  
|[CRecordset::m_nParams](#m_nparams)|レコード セット内のパラメーター データ メンバーの数が含まれています。 「`UINT`」と入力します。|  
|[CRecordset::m_pDatabase](#m_pdatabase)|ポインターが含まれています、`CDatabase`データ ソースに使用されるレコード セットが接続されているオブジェクト。|  
|[CRecordset::m_strFilter](#m_strfilter)|含まれています、 `CString` Structured Query Language (SQL) を指定する`WHERE`句。 特定の条件を満たすレコードだけを選択するフィルターとして使用します。|  
|[CRecordset::m_strSort](#m_strsort)|含まれています、 `CString` SQL を指定する`ORDER BY`句。 レコードの並べ替え方法を制御するために使用します。|  
  
## <a name="remarks"></a>Remarks  
 「レコード セット」と呼ばれる`CRecordset`オブジェクトが 2 つの形式に用いられます: ダイナセットを使う場合とスナップショット。 ダイナセットは、同期されているその他のユーザーによって行われたデータの更新プログラムにします。 スナップショットは、データの静的ビューです。 各フォームは、レコード セットを開いた時点で固定されたレコードのセットを表しますが、ダイナセットのレコードをスクロールする際に他のユーザーまたはアプリケーションで他のレコード セットのいずれかのレコードに加えられた変更が反映されます。  
  
> [!NOTE]
>  オープン データベース コネクティビティ (ODBC) クラスではなく、データ アクセス オブジェクト (DAO) クラスで作業している場合は、クラスを使用して[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)代わりにします。 詳細については、記事を参照してください。[概要: データベース プログラミング](../../data/data-access-programming-mfc-atl.md)です。  
  
 レコード セットのいずれかの種類を使用する通常クラスを派生する、アプリケーション固有のレコード セットから`CRecordset`です。 レコード セットは、データ ソースからレコードを選択しを選択できます。  
  
-   レコード間をスクロールします。  
  
-   レコードを更新し、ロックのモードを指定します。  
  
-   データ ソースで使用できるものからを選択するレコードを制限するレコード セットをフィルター処理します。  
  
-   レコード セットを並べ替えます。  
  
-   実行時まで不明情報で、選択範囲をカスタマイズするレコード セットをパラメーター化します。  
  
 クラスを使用するデータベースを開くし、へのポインターをコンス トラクターに渡して、レコード セット オブジェクトを構築、`CDatabase`オブジェクト。 レコード セットを呼び出す`Open`メンバー関数、オブジェクトは、ダイナセットまたはスナップショットかどうかを指定できます。 呼び出す`Open`データ ソースからデータを選択します。 レコード セット オブジェクトが開かれた後に、レコード間をスクロールし、それらを操作するメンバー関数とデータ メンバーを使用します。 使用できる操作は、更新可能または読み取り専用であるかどうかオブジェクトは、ダイナセットまたはスナップショットかどうかに依存 (これに依存オープン データベース コネクティビティ (ODBC) のデータ ソースの機能)、バルク行フェッチを実装するかどうかとします。 されている変更されたか、後に追加するレコードを更新する、`Open`呼び出し、オブジェクトの`Requery`メンバー関数。 オブジェクトの`Close`メンバー関数を関連付けが完了したら、オブジェクトを破棄します。  
  
 派生で`CRecordset`クラス、レコード フィールド エクス (チェンジ RFX) または読み取りとレコード フィールドの更新をサポートするためにバルク レコード フィールド エクス チェンジ (Bulk RFX) を使用します。  
  
 レコード セットとレコード フィールド エクス チェンジの詳細については、記事を参照してください[概要: データベース プログラミング](../../data/data-access-programming-mfc-atl.md)、[レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)、[レコード セット: レコードのフェッチ (ODBC)。](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)、および[レコード フィールド エクス (チェンジ RFX)](../../data/odbc/record-field-exchange-rfx.md)です。 ダイナセットを使う場合のスナップショットに重点を置いて、記事を参照してください。[ダイナセット](../../data/odbc/dynaset.md)と[スナップショット](../../data/odbc/snapshot.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CRecordset`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdb.h  
  
##  <a name="addnew"></a>  CRecordset::AddNew  
 テーブルに新しいレコードを追加する準備を行います。  
  
```  
virtual void AddNew();
```  
  
### <a name="remarks"></a>Remarks  
 呼び出す必要があります、 [Requery](#requery)メンバー関数を新しく追加したレコードを参照してください。 レコードのフィールドは、最初に null 値がします。 (データベース用語では、「値を持たない」手段を Null に設定と同じではありませんし**NULL** c++)。完了するには、操作を呼び出す必要があります、[更新](#update)メンバー関数。 `Update` データ ソースに変更を保存します。  
  
> [!NOTE]
>  バルク行フェッチを実装した場合を呼び出すことはできません`AddNew`です。 これにより、失敗したアサーションが発生します。 クラス`CRecordset`メカニズムが用意されていないデータの一括行を更新するには、ODBC API 関数を使用して、独自の関数を記述することができます**SQLSetPos**です。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
 `AddNew` レコード セットのフィールド データ メンバーを使用して、新しい空のレコードを準備します。 呼び出した後`AddNew`、レコード セットのフィールド データ メンバーに適用する値を設定します。 (呼び出しする必要はありません、[編集](#edit)この目的のためのメンバー関数以外の使用`Edit`のみの既存のレコードです)。関数を呼び出すと`Update`、変更されたフィールド データ メンバー内の値は、データ ソースに保存されます。  
  
> [!CAUTION]
>  呼び出す前に、新しいレコードをスクロールする`Update`、新しいレコードが失われ、警告が指定されていません。  
  
 データ ソースは、トランザクションをサポートすることができます、`AddNew`呼び出し、トランザクションの一部です。 トランザクションの詳細については、クラスを参照してください。 [CDatabase](../../mfc/reference/cdatabase-class.md)です。 呼び出す必要があります[CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans)呼び出す前に`AddNew`です。  
  
> [!NOTE]
>  ダイナセットを使う場合の新しいレコードは、最後のレコードとしてレコード セットに追加されます。 スナップショットに追加されたレコードは追加されません。呼び出す必要があります`Requery`をレコード セットを更新します。  
  
 呼び出すことはできません`AddNew`レコード セットを持つ`Open`メンバー関数が呼び出されていません。 A`CDBException`を呼び出す場合にスローされる`AddNew`レコード セットに追加することはできません。 呼び出すことによって、レコード セットは更新可能かどうかを判断できます[CanAppend](#canappend)です。  
  
 詳細については、次の記事を参照してください:[レコード セット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)、[レコード セット: 追加、更新、およびレコードの削除 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)、および[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)です。  
  
### <a name="example"></a>例  
 記事を参照して[トランザクション: レコード セット (ODBC) でのトランザクションを実行する](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)です。  
  
##  <a name="canappend"></a>  CRecordset::CanAppend  
 以前に開いたレコード セットが、新しいレコードを追加することができるかどうかを判断します。  
  
```  
BOOL CanAppend() const;  
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、レコード セットは、新しいレコードを追加できます。それ以外の場合 0 を返します。 `CanAppend` 読み取り専用とレコード セットを開いた場合 0 を返します。  
  
##  <a name="canbookmark"></a>  値  
 レコード セットが、ブックマークを使用してレコードをマークすることができるかどうかを判断します。  
  
```  
BOOL CanBookmark() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットは、ブックマークをサポートしている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数は独立して、 **crecordset::usebookmarks**オプション、 *dwOptions*のパラメーター、[開く](#open)メンバー関数。 `CanBookmark` 特定の ODBC ドライバーとカーソルがサポート ブックマークを入力するかどうかを示します。 **Crecordset::usebookmarks**はサポートされていれば、ブックマークが使用できるかどうかを示します。  
  
> [!NOTE]
>  順方向専用レコード セットでは、ブックマークはサポートされていません。  
  
 ブックマークとレコード セットの移動の詳細については、記事を参照してください。[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)と[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)です。  
  
##  <a name="cancel"></a>  CRecordset::Cancel  
 実行中の非同期操作または 2 番目のスレッドからのプロセスのいずれかのデータ ソースのキャンセルを要求します。  
  
```  
void Cancel();
```  
  
### <a name="remarks"></a>Remarks  
 MFC ODBC クラスに非同期処理が使用できなくに注意してください。非同期操作を実行する ODBC API 関数を直接に呼び出す必要があります**SQLSetConnectOption**です。 詳細についてを参照してください「関数の非同期実行」、 *ODBC SDK プログラマー ガイド*です。  
  
##  <a name="cancelupdate"></a>  CRecordset::CancelUpdate  
 保留中の原因で、更新をキャンセル、[編集](#edit)または[AddNew](#addnew)操作、前に[更新](#update)と呼びます。  
  
```  
void CancelUpdate();
```  
  
### <a name="remarks"></a>Remarks  
  
> [!NOTE]
>  このメンバー関数はバルク行フェッチ、このようなレコード セットを呼び出すことはできませんのでを使用しているレコード セットで適用できません`Edit`、 `AddNew`、または`Update`です。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
 自動ダーティ フィールド チェックが有効になっている場合`CancelUpdate`メンバー変数を前の値に復元されます`Edit`または`AddNew`が呼び出されたです。 それ以外の場合、その変更は保持されます。 既定では、自動フィールドが有効になって、レコード セットが開かれたときにします。 これを無効にする必要がありますを指定する、 **crecordset::nodirtyfieldcheck**で、 *dwOptions*のパラメーター、[開く](#open)メンバー関数。  
  
 データ更新の詳細については、記事を参照してください。[レコード セット: 追加、更新、およびレコードの削除 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)です。  
  
##  <a name="canrestart"></a>  CRecordset::CanRestart  
 レコード セットでは、呼び出すことによって、クエリを (そのレコードの更新) を再起動できるかどうかを判断、`Requery`メンバー関数。  
  
```  
BOOL CanRestart() const;  
```  
  
### <a name="return-value"></a>戻り値  
 再クエリが使用できる場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="canscroll"></a>  CRecordset::CanScroll  
 レコード セットでは、スクロールできるかどうかを判断します。  
  
```  
BOOL CanScroll() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットがスクロールできる場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 スクロールの詳細については、記事を参照してください。[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)です。  
  
##  <a name="cantransact"></a>  CRecordset::CanTransact  
 レコード セットがトランザクションを許可するかどうかを判断します。  
  
```  
BOOL CanTransact() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットがトランザクションを許可する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 詳細については、記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)です。  
  
##  <a name="canupdate"></a>  CRecordset::CanUpdate  
 レコード セットを更新できるかどうかを判断します。  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、レコード セットを更新することができます。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 基になるデータ ソースが読み取り専用の場合、または指定した場合、レコード セットを読み取り専用可能性があります**crecordset::readonly**で、 *dwOptions*パラメーターは、レコード セットが開かれたときにします。  
  
##  <a name="checkrowseterror"></a>  CRecordset::CheckRowsetError  
 レコードのフェッチ中に生成されたエラーの処理と呼ばれます。  
  
```  
virtual void CheckRowsetError(RETCODE nRetCode);
```  
  
### <a name="parameters"></a>パラメーター  
 *終了*  
 ODBC API 関数には、コードが返されます。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>Remarks  
 この仮想メンバー関数は、レコードをフェッチしたときに発生するエラーを処理とバルク行フェッチ中に便利です。 オーバーライドすることを検討することも`CheckRowsetError`独自のエラー処理を実装します。  
  
 `CheckRowsetError` 自動的に呼び出されますカーソル ナビゲーション操作では、ように`Open`、 `Requery`、または any`Move`操作します。 ODBC API 関数の戻り値が渡される**SQLExtendedFetch**です。 次の表に、可能な値、`nRetCode`パラメーター。  
  
|終了|説明|  
|--------------|-----------------|  
|**SQL_SUCCESS**|関数は正常に完了しました追加情報はありません。|  
|**SQL_SUCCESS_WITH_INFO**|関数が正常に完了して可能性のある重大なエラーをします。 追加情報を呼び出すことによって取得できます`SQLError`です。|  
|**SQL_NO_DATA_FOUND**|結果セットからすべての行がフェッチされました。|  
|**SQL_ERROR**|関数が失敗しました。 追加情報を呼び出すことによって取得できます`SQLError`です。|  
|**SQL_INVALID_HANDLE**|関数は、無効な環境ハンドル、接続ハンドル、またはステートメント ハンドルのため失敗しました。 これは、プログラミング エラーを示します。 追加情報が利用できない`SQLError`です。|  
|**SQL_STILL_EXECUTING**|非同期的に起動された関数が実行中です。 既定では、MFC は決して渡すことには、この値に注意してください`CheckRowsetError`です。MFC の呼び出しは引き続き`SQLExtendedFetch`返されなくなるまで**SQL_STILL_EXECUTING**です。|  
  
 詳細については`SQLError`、Windows SDK を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
##  <a name="close"></a>  ような場合  
 レコード セットを閉じます。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Remarks  
 ODBC **HSTMT**とレコード セットに割り当てられているフレームワークの割り当てが解除されるすべてのメモリ。 呼び出した後に通常`Close`で割り当てられた場合に、C++ のレコード セット オブジェクトを削除する**新しい**です。  
  
 呼び出すことができます`Open`呼び出した後にもう一度`Close`です。 これにより、レコード セット オブジェクトを再利用できます。 呼び出す場合は`Requery`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase#17](../../mfc/codesnippet/cpp/crecordset-class_1.cpp)]  
  
##  <a name="crecordset"></a>  CRecordset::CRecordset  
 `CRecordset` オブジェクトを構築します。  
  
```  
CRecordset(CDatabase* pDatabase = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDatabase*  
 ポインターが含まれています、`CDatabase`オブジェクトまたは値**NULL**です。 ない場合**NULL**と`CDatabase`オブジェクトの`Open`データ ソースに接続するメンバー関数が呼び出されていない、レコード セットが、ファイルを開いて、それ自体の中にしようとしています。`Open`を呼び出します。 渡す場合**NULL**、`CDatabase`オブジェクトが構築され、ClassWizard でレコード セット クラスの派生を指定したデータ ソース情報を使用するために接続します。  
  
### <a name="remarks"></a>Remarks  
 使用するか`CRecordset`直接からアプリケーションに固有のクラスを派生または`CRecordset`です。 ClassWizard を使用するには、レコード セット クラスを派生します。  
  
> [!NOTE]
>  派生クラス*必要があります*独自のコンス トラクターを指定します。 派生クラスのコンス トラクターで、コンス トラクターを呼び出します`CRecordset::CRecordset`、に沿って、適切なパラメーターを渡します。  
  
 渡す**NULL**がレコード セット コンス トラクターに、`CDatabase`オブジェクトが構築され、自動的に結合します。 これは、方法を使う構築し、接続を必要としない、`CDatabase`レコード セットを構築する前にオブジェクト。  
  
### <a name="example"></a>例  
 詳細については、記事を参照してください。[レコード セット: テーブル (ODBC) のクラスの宣言](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)です。  
  
##  <a name="delete"></a>  CRecordset::Delete  
 現在のレコードを削除します。  
  
```  
virtual void Delete();
```  
  
### <a name="remarks"></a>Remarks  
 削除が成功した後、レコード セットのフィールド データ メンバーは、Null 値に設定されのいずれかを明示的に呼び出す必要があります、`Move`削除されたレコードを移動するために機能します。 削除されたレコードから移動するに戻るにことはできません。 データ ソースは、トランザクションをサポートすることができます、`Delete`呼び出し、トランザクションの一部です。 詳細については、記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)です。  
  
> [!NOTE]
>  バルク行フェッチを実装した場合を呼び出すことはできません`Delete`です。 これにより、失敗したアサーションが発生します。 クラス`CRecordset`メカニズムが用意されていないデータの一括行を更新するには、ODBC API 関数を使用して、独自の関数を記述することができます**SQLSetPos**です。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
> [!CAUTION]
>  レコード セットは更新可能である必要があり、ありますの有効なレコードの現在のレコード セットを呼び出すとき`Delete`です。 それ以外の場合、エラーが発生します。 たとえば、レコードを削除してを呼び出す前に、新しいレコードをスクロールしません`Delete`もう一度、`Delete`スロー、 [CDBException](../../mfc/reference/cdbexception-class.md)です。  
  
 異なり[AddNew](#addnew)と[編集](#edit)への呼び出し`Delete`への呼び出しが続かない[更新](#update)です。 場合、`Delete`呼び出しが失敗した場合は、変更されていないフィールドのデータ メンバーのままにします。  
  
### <a name="example"></a>例  
 この例では、関数のフレームで作成されたレコード セットを示します。 例では、ことを想定の`m_dbCust`、型のメンバー変数`CDatabase`既にデータ ソースに接続されています。  
  
 [!code-cpp[NVC_MFCDatabase#18](../../mfc/codesnippet/cpp/crecordset-class_2.cpp)]  
  
##  <a name="dobulkfieldexchange"></a>  CRecordset::DoBulkFieldExchange  
 バルク行をデータ ソースからレコード セットへのデータを交換するには、呼び出されます。 レコード フィールド エクス チェンジ (Bulk RFX) の一括を実装します。  
  
```  
virtual void DoBulkFieldExchange(CFieldExchange* pFX);
```  
  
### <a name="parameters"></a>パラメーター  
 *pFX*  
 ポインター、 [CFieldExchange](../../mfc/reference/cfieldexchange-class.md)オブジェクト。 フレームワークは、フィールド交換操作のコンテキストを指定する、このオブジェクトは、既に設定しました。  
  
### <a name="remarks"></a>Remarks  
 バルク行フェッチが実装された場合、フレームワークは、レコード セット オブジェクトにデータ ソースからデータを自動的に転送するには、このメンバー関数を呼び出します。 `DoBulkFieldExchange` レコード セットの選択用の SQL ステートメント文字列内のパラメーターのプレース ホルダーに存在する場合も、パラメーターのデータ メンバーをバインドします。  
  
 バルク行フェッチが実装されていない場合、フレームワークによって呼び出されます[DoFieldExchange](#dofieldexchange)です。 バルク行フェッチを実装する必要がありますを指定する、`CRecordset::useMultiRowFetch`のオプション、`dwOptions`内のパラメーター、[開く](#open)メンバー関数。  
  
> [!NOTE]
> `DoBulkFieldExchange` 派生するクラスを使用している場合にのみ使用できますが`CRecordset`です。 直接からレコード セット オブジェクトを作成した場合`CRecordset`、呼び出す必要があります、 [GetFieldValue](#getfieldvalue)データを取得するメンバー関数。  
  
 バルク レコード フィールド エクス チェンジ (Bulk RFX) は、レコード フィールド エクス (チェンジ RFX) に似ています。 データは、レコード セット オブジェクトをデータ ソースから自動的に転送されます。 ただし、呼び出すことはできません`AddNew`、 `Edit`、 `Delete`、または`Update`変更をデータ ソースに転送します。 クラス`CRecordset`現在一括データの行を更新するためのメカニズムが用意されていませんただし、ODBC API 関数を使用して、独自の関数を記述することができます**SQLSetPos**です。  
  
 ClassWizard では、バルク レコード フィールド エクス チェンジ; はサポートされていないことに注意してください。このため、オーバーライドする必要があります`DoBulkFieldExchange`バルク RFX 関数の呼び出しを記述して手動でします。 これらの関数の詳細については、トピックを参照してください。[レコード フィールド エクス チェンジ関数](../../mfc/reference/record-field-exchange-functions.md)です。  
  
 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。 関連情報の記事を参照してください。[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)です。  
  
##  <a name="dofieldexchange"></a>  CRecordset::DoFieldExchange  
 レコード セットのフィールド データ メンバーと、データ ソースに対応するレコードの間で (双方向) のデータを交換するには、呼び出されます。 レコード フィールド エクス (チェンジ RFX) をを実装します。  
  
```  
virtual void DoFieldExchange(CFieldExchange* pFX);
```  
  
### <a name="parameters"></a>パラメーター  
 *pFX*  
 ポインター、 [CFieldExchange](../../mfc/reference/cfieldexchange-class.md)オブジェクト。 フレームワークは、フィールド交換操作のコンテキストを指定する、このオブジェクトは、既に設定しました。  
  
### <a name="remarks"></a>Remarks  
 バルク行フェッチが実装されていない場合、フレームワークは、レコード セット オブジェクトのフィールド データ メンバーと、データ ソースの現在のレコードの対応する列の間でデータを自動的に交換するには、このメンバー関数を呼び出します。 `DoFieldExchange` レコード セットの選択用の SQL ステートメント文字列内のパラメーターのプレース ホルダーに存在する場合も、パラメーターのデータ メンバーをバインドします。  
  
 バルク行フェッチが実装されている場合、フレームワークによって呼び出されます[DoBulkFieldExchange](#dobulkfieldexchange)です。 バルク行フェッチを実装する必要がありますを指定する、`CRecordset::useMultiRowFetch`のオプション、 *dwOptions*内のパラメーター、[開く](#open)メンバー関数。  
  
> [!NOTE]
> `DoFieldExchange` 派生するクラスを使用している場合にのみ使用できますが`CRecordset`です。 直接からレコード セット オブジェクトを作成した場合`CRecordset`、呼び出す必要があります、 [GetFieldValue](#getfieldvalue)データを取得するメンバー関数。  
  
 レコード フィールド エクス チェンジ (RFX) と呼ばれる、フィールドのデータの交換が両方向で動作します。 データ ソースのレコードのフィールドにレコード セット オブジェクトのフィールド データ メンバーと、レコード セット オブジェクトにデータ ソースのレコードからです。  
  
 唯一の操作を実装する通常実行する必要があります`DoFieldExchange`クラスは、派生したレコード セットを ClassWizard でクラスを作成し、フィールド データ メンバーの名前とデータ型を指定します。 ClassWizard をパラメーター データ メンバーを指定するか、動的に連結する列を処理するために記述するコードを追加することも可能性があります。 詳細については、記事を参照してください。[レコード セット: データ列を動的に結びつける (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)です。  
  
 ClassWizard で派生したレコード セット クラスを宣言するときのオーバーライドが書き込まれます`DoFieldExchange`次の例のようを。  
  
 [!code-cpp[NVC_MFCDatabase#19](../../mfc/codesnippet/cpp/crecordset-class_3.cpp)]  
  
 RFX 関数の詳細については、トピックを参照してください。[レコード フィールド エクス チェンジ関数](../../mfc/reference/record-field-exchange-functions.md)です。  
  
 さらに例と詳細`DoFieldExchange`、記事を参照して[レコード フィールド エクス チェンジ: RFX のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)です。 RFX に関する全般情報の記事を参照してください。[レコード フィールド エクス チェンジ](../../data/odbc/record-field-exchange-rfx.md)です。  
  
##  <a name="edit"></a>  CRecordset::Edit  
 現在のレコードに変更をできます。  
  
```  
virtual void Edit();
```  
  
### <a name="remarks"></a>Remarks  
 呼び出した後`Edit`、直接その値をリセットすることにより、フィールド データ メンバーを変更することができます。 後で呼び出すときに、操作が完了、[更新](#update)メンバー関数、データ ソースで変更を保存します。  
  
> [!NOTE]
>  バルク行フェッチを実装した場合を呼び出すことはできません`Edit`です。 これにより、失敗したアサーションが発生します。 クラス`CRecordset`メカニズムが用意されていないデータの一括行を更新するには、ODBC API 関数を使用して、独自の関数を記述することができます**SQLSetPos**です。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
 `Edit` レコード セットのデータ メンバーの値を保存します。 呼び出す場合`Edit`、変更では、まず、`Edit`元に 1 つ目の前に、レコードの値を復元する、もう一度`Edit`呼び出します。  
  
 場合によっては、(データを含まない) を Null にすることで、列を更新することがあります。 これを行うには、呼び出す[な](#setfieldnull)のパラメーターを持つ**TRUE** Null です。 このフィールドをマークするこれもにより、更新する列。 場合は、フィールドの値が変更されていない場合でも、データ ソースに書き込まれ、呼び出しを[き](#setfielddirty)のパラメーターを持つ**TRUE**です。 これは、フィールド値の Null であった場合でも機能します。  
  
 データ ソースは、トランザクションをサポートすることができます、`Edit`呼び出し、トランザクションの一部です。 呼び出す必要があります[CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans)呼び出す前に`Edit`とレコード セットが開かれた後。 その呼び出し元にも注意してください[CDatabase::CommitTrans](../../mfc/reference/cdatabase-class.md#committrans)呼び出しに代わるものではありません`Update`を完了する、`Edit`操作します。 トランザクションの詳細については、クラスを参照してください。 [CDatabase](../../mfc/reference/cdatabase-class.md)です。  
  
 現在のロック モードによって、レコードが更新されている可能性がありますによってロックされている`Edit`が呼び出されるまで`Update`または別のレコードをスクロール中だけにロックされる可能性がありますか、`Edit`を呼び出します。 ロック モードを変更する[SetLockingMode](#setlockingmode)です。  
  
 呼び出す前に新しいレコードをスクロールする場合に、現在のレコードの前の値が復元`Update`です。 A`CDBException`を呼び出す場合にスローされる`Edit`更新できないレコード セットまたはかどうかは、現在のレコードはありません。  
  
 詳細については、記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)と[レコード セット: ロック (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase#20](../../mfc/codesnippet/cpp/crecordset-class_4.cpp)]  
  
##  <a name="flushresultset"></a>  CRecordset::FlushResultSet  
 複数の結果セットがある場合は、定義済みクエリ (ストアド プロシージャ) の次の結果セットを取得します。  
  
```  
BOOL FlushResultSet();
```  
  
### <a name="return-value"></a>戻り値  
 取得する複数の結果セットがある場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 呼び出す必要があります`FlushResultSet`のみ完全に終了したら現在の結果セットにカーソルを使用します。 次の結果を呼び出してセットを取得するときに注意してください`FlushResultSet`、カーソルを置き、その結果セットでは有効ではなく呼び出す必要があります、 [MoveNext](#movenext)メンバー関数の呼び出し後`FlushResultSet`です。  
  
 定義済みのクエリでは、出力パラメーターまたは入出力パラメーターを使用する必要がありますを呼び出した場合`FlushResultSet`返されるまで`FALSE`(値は 0)、これらのパラメーター値を取得するためにします。  
  
 `FlushResultSet` ODBC API 関数を呼び出す`SQLMoreResults`です。 場合`SQLMoreResults`返します`SQL_ERROR`または`SQL_INVALID_HANDLE`、し`FlushResultSet`例外がスローされます。 詳細については`SQLMoreResults`、Windows SDK を参照してください。  
  
 ストアド プロシージャを呼び出そうとする場合、フィールドにバインドする必要があります`FlushResultSet`です。  
  
### <a name="example"></a>例  
 次のコードが想定する`COutParamRecordset`は、 `CRecordset`-入力パラメーターと出力パラメーター、定義済みのクエリに基づいており、複数の結果セットを持つ派生オブジェクト。 構造に注意してください、 [DoFieldExchange](#dofieldexchange)をオーバーライドします。  
  
 [!code-cpp[NVC_MFCDatabase#21](../../mfc/codesnippet/cpp/crecordset-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDatabase#22](../../mfc/codesnippet/cpp/crecordset-class_6.cpp)]  
  
##  <a name="getbookmark"></a>  CRecordset::GetBookmark  
 現在のレコードのブックマークの値を取得します。  
  
```  
void GetBookmark(CDBVariant& varBookmark);
```  
  
### <a name="parameters"></a>パラメーター  
 *varBookmark*  
 参照、 [CDBVariant](../../mfc/reference/cdbvariant-class.md)現在のレコード、ブックマークを表すオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 調べるには、レコード セットで、ブックマークがサポートされているかどうか、呼び出す[調べる](#canbookmark)です。 ブックマークを使用できるようにサポートされている場合に設定する必要があります、 **crecordset::usebookmarks**オプション、 *dwOptions*のパラメーター、[開く](#open)メンバー関数。  
  
> [!NOTE]
>  ブックマークはサポートされていないか使用できない場合、呼び出す`GetBookmark`例外がスローされます。 順方向専用レコード セットでは、ブックマークはサポートされていません。  
  
 `GetBookmark` 現在のレコードのブックマークの値を割り当てます、`CDBVariant`オブジェクト。 いつでも別のレコードに移動した後、そのレコードに戻り、呼び出す[SetBookmark](#setbookmark)で対応する`CDBVariant`オブジェクト。  
  
> [!NOTE]
>  特定のレコード セットの操作後のブックマークの有効な不要になった場合があります。 呼び出す場合など、`GetBookmark`続く`Requery`、レコードに戻ることはできません`SetBookmark`です。 呼び出す[CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence)を安全に呼び出すことができるかどうかを確認する`SetBookmark`です。  
  
 ブックマークとレコード セットの移動の詳細については、記事を参照してください。[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)と[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)です。  
  
##  <a name="getdefaultconnect"></a>  :Getdefaultconnect  
 既定の接続文字列を取得するには、呼び出されます。  
  
```  
virtual CString GetDefaultConnect();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`既定の接続文字列を格納しています。  
  
### <a name="remarks"></a>Remarks  
 フレームワークは、レコード セットの基になるデータ ソースの既定の接続文字列を取得するには、このメンバー関数を呼び出します。 ClassWizard では、テーブルと列に関する情報を取得する ClassWizard で使用する、同じデータ ソースを識別することによってのこの関数を実装します。 可能性がありますがわかりますが、アプリケーションの開発中に、この既定の接続に依存するは便利です。 既定の接続は、アプリケーションのユーザーに適したできない可能性があります。 場合は、する必要がありますを再実装この関数は、ClassWizard のバージョンを破棄します。 接続文字列の詳細については、記事を参照してください。[データ ソース (ODBC)](../../data/odbc/data-source-odbc.md)です。  
  
##  <a name="getdefaultsql"></a>  CRecordset::GetDefaultSQL  
 実行する既定の SQL 文字列を取得するには、呼び出されます。  
  
```  
virtual CString GetDefaultSQL();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`を既定の SQL ステートメントが含まれています。  
  
### <a name="remarks"></a>Remarks  
 フレームワークは、レコード セットの基になる既定の SQL ステートメントを取得するには、このメンバー関数を呼び出します。 これは、テーブル名または SQL**選択**ステートメントです。  
  
 直接定義していない既定の SQL ステートメントで ClassWizard、レコード セット クラスを宣言することによってと ClassWizard では、このタスクを実行します。  
  
 独自の SQL ステートメントの文字列が必要な場合`GetSQL`、開かれたときに、レコード セットのレコードを選択するために使用する SQL ステートメントが返されます。 クラスのオーバーライドで、既定の SQL 文字列を編集する`GetDefaultSQL`です。 使用して、定義済みクエリへの呼び出しを指定するなど、**呼び出す**ステートメントです。 (注、編集する場合、`GetDefaultSQL`も変更する必要があります`m_nFields`データ ソース内の列の数と一致する)。  
  
 詳細については、記事を参照してください。[レコード セット: テーブル (ODBC) のクラスの宣言](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)です。  
  
> [!CAUTION]
>  テーブル名は、フレームワークが複数のテーブル名が指定された場合、またはテーブル名を識別できない場合は空になります、**呼び出す**ステートメントを解釈できませんでした。 使用するときに注意してください、**呼び出す**ステートメントでは、中かっこの間の空白を挿入する必要がありますと**呼び出す**キーワード、中かっこの前に、または前に空白を挿入する必要がありますも、 **選択**キーワード、**選択**ステートメントです。  
  
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
 *lpszName*  
 フィールドの名前。  
  
 *varValu*e  
 参照、 [CDBVariant](../../mfc/reference/cdbvariant-class.md)フィールドの値を格納するオブジェクト。  
  
 *nFieldType*  
 フィールドの ODBC C データ型。 既定値を使用して**DEFAULT_FIELD_TYPE**、強制的に`GetFieldValue`次の表に基づいて SQL データ型から C データ型を判断します。 それ以外の場合、データを直接入力または互換性のあるデータの種類の選択を指定できます。たとえばに任意のデータ型を格納することができます**SQL_C_CHAR**です。  
  
|C データ型|SQL データ型|  
|-----------------|-------------------|  
|**SQL_C_BIT**|**SQL_BIT**|  
|**SQL_C_UTINYINT**|**SQL_TINYINT**|  
|**SQL_C_SSHORT**|**SQL_SMALLINT**|  
|**SQL_C_SLONG**|**SQL_INTEGER**|  
|**SQL_C_FLOAT**|**SQL_REAL**|  
|**SQL_C_DOUBLE**|**SQL_FLOATSQL_DOUBLE**|  
|**SQL_C_TIMESTAMP**|**SQL_DATESQL_TIMESQL_TIMESTAMP**|  
|**SQL_C_CHAR**|**SQL_NUMERICSQL_DECIMALSQL_BIGINTSQL_CHARSQL_VARCHARSQL_LONGVARCHAR**|  
|**SQL_C_BINARY**|**SQL_BINARYSQL_VARBINARYSQL_LONGVARBINARY**|  
  
 ODBC データ型の詳細については、「SQL データ型」および「C データ型」Windows SDK の「付録 D トピックを参照してください。  
  
 *nIndex*  
 フィールドの 0 から始まるインデックス。  
  
 *StrValue*  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)フィールドの値を格納するオブジェクトは、フィールドのデータ型に関係なく、テキストに変換します。  
  
### <a name="remarks"></a>Remarks  
 名前またはインデックスを使用して、フィールドを参照することができます。 いずれかのフィールドの値を格納することができます、`CDBVariant`オブジェクトまたは`CString`オブジェクト。  
  
 バルク行フェッチを実装した場合、現在のレコードは常に、行セットの最初のレコードに位置付けられます。 使用する`GetFieldValue`で指定された行セット内のレコード、最初に呼び出す必要があります、 [SetRowsetCursorPosition](#setrowsetcursorposition)その行セット内で目的の行にカーソルを移動するメンバー関数。 呼び出す`GetFieldValue`その行にします。 バルク行フェッチを実装する必要がありますを指定する、`CRecordset::useMultiRowFetch`のオプション、 *dwOptions*内のパラメーター、[開く](#open)メンバー関数。  
  
 使用することができます`GetFieldValue`を動的にデザイン時に静的にバインドするのではなく、実行時にフィールドを取得します。 たとえば、直接からレコード セット オブジェクトを宣言した場合`CRecordset`、使用する必要があります`GetFieldValue`を取得するフィールドのデータ以外の場合はレコード フィールド エクス チェンジ (RFX)、またはバルク レコード フィールド エクス チェンジ (Bulk RFX) が実装されていません。  
  
> [!NOTE]
>  派生することがなく、レコード セット オブジェクトを宣言する場合`CRecordset`、読み込まれた ODBC カーソル ライブラリはありません。 カーソル ライブラリが必要です、レコード セットに少なくとも 1 つのバインドされた列です。ただし、使用`CRecordset`直接、どの列もバインドされています。 メンバー関数は、 [cdatabase::openex](../../mfc/reference/cdatabase-class.md#openex)と[cdatabase::open](../../mfc/reference/cdatabase-class.md#open)カーソル ライブラリが読み込まれるかどうかを制御します。  
  
 `GetFieldValue` ODBC API 関数を呼び出す**SQLGetData**です。 ドライバーが値を出力する場合**SQL_NO_TOTAL**フィールドの値の実際の長さの`GetFieldValue`例外をスローします。 詳細については**SQLGetData**、Windows SDK を参照してください。  
  
### <a name="example"></a>例  
 次のサンプル コードへの呼び出しを示しています。`GetFieldValue`から直接宣言済みのレコード セット オブジェクトの`CRecordset`します。  
  
 [!code-cpp[NVC_MFCDatabase#23](../../mfc/codesnippet/cpp/crecordset-class_7.cpp)]  
  
> [!NOTE]
>  DAO クラスとは異なり`CDaoRecordset`、`CRecordset`はありません、`SetFieldValue`メンバー関数。 直接オブジェクトを作成する場合`CRecordset`、効果的に読み取り専用であります。  
  
 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
##  <a name="getodbcfieldcount"></a>  CRecordset::GetODBCFieldCount  
 レコード セット オブジェクト内のフィールドの合計数を取得します。  
  
```  
short GetODBCFieldCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットのフィールドの数。  
  
### <a name="remarks"></a>Remarks  
 レコード セットの作成に関する詳細については、記事を参照してください。[レコード セット: を作成すると、レコード セット (ODBC) を終了](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)です。  
  
##  <a name="getodbcfieldinfo"></a>  に  
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
 *lpszName*  
 フィールドの名前。  
  
 *fieldinfo*  
 参照、`CODBCFieldInfo`構造体。  
  
 *nIndex*  
 フィールドの 0 から始まるインデックス。  
  
### <a name="remarks"></a>Remarks  
 関数の 1 つのバージョンでは、名前、フィールドを検索することができます。 その他のバージョンでは、インデックスを使用してフィールドを検索できます。  
  
 詳細については、返される情報は、次を参照してください。、 [CODBCFieldInfo](../../mfc/reference/codbcfieldinfo-structure.md)構造体。  
  
 レコード セットの作成に関する詳細については、記事を参照してください。[レコード セット: を作成すると、レコード セット (ODBC) を終了](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)です。  
  
##  <a name="getrecordcount"></a>  CRecordset::GetRecordCount  
 レコード セットのサイズを決定します。  
  
```  
long GetRecordCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セット内のレコードの数レコード セットにレコードが含まれていない場合は 0または、レコード カウントを特定できない場合は-1。  
  
### <a name="remarks"></a>Remarks  
  
> [!CAUTION]
>  レコード カウントが、"high watermark"番号が最大レコードとして保持まだ、ユーザーがレコードを移動すると表示されます。 レコードの合計数は、最後のレコードを超えるユーザーが移動した後にだけ呼ばれます。 パフォーマンス上の理由を呼び出すと、数は更新されません`MoveLast`です。 レコードを自分でカウントを呼び出す`MoveNext`まで繰り返し`IsEOF`0 以外を返します。 使用してレコードを追加する`CRecordset:AddNew`と`Update`のカウントを増やします。 を使用してレコードを削除する`CRecordset::Delete`カウントが減少します。  
  
##  <a name="getrowsetsize"></a>  CRecordset::GetRowsetSize  
 回のフェッチ中に取得する行の数の現在の設定を取得します。  
  
```  
DWORD GetRowsetSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 回のフェッチ中に取得する行の数。  
  
### <a name="remarks"></a>Remarks  
 バルク行フェッチを使用しているレコード セットが開かれたときに、既定の行セット サイズが 25 です。それ以外の場合は 1 です。  
  
 バルク行フェッチを実装する必要がありますを指定する、`CRecordset::useMultiRowFetch`オプション、 *dwOptions*のパラメーター、[開く](#open)メンバー関数。 行セット サイズの設定を変更するには、呼び出す[SetRowsetSize](#setrowsetsize)です。  
  
 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
##  <a name="getrowsfetched"></a>  CRecordset::GetRowsFetched  
 フェッチ後に実際に取得されたレコード数を決定します。  
  
```  
DWORD GetRowsFetched() const;  
```  
  
### <a name="return-value"></a>戻り値  
 行の数は、指定されたフェッチ後に、データ ソースから取得します。  
  
### <a name="remarks"></a>Remarks  
 これは、機能は、バルク行フェッチを実装しているときに便利です。 行セットのサイズが通常フェッチ; から取得する行の数を示しますただし、レコード セット内の行の合計数にも影響行セットの行の数が取得されます。 たとえば、レコード セットに行セット サイズ設定が 4 の 10 個のレコードがある場合は、し、ループ レコード セットを呼び出して`MoveNext`最後の行セットのみに 2 つのレコードになります。  
  
 バルク行フェッチを実装する必要がありますを指定する、`CRecordset::useMultiRowFetch`オプション、 *dwOptions*のパラメーター、[開く](#open)メンバー関数。 行セットのサイズを指定するには、呼び出す[SetRowsetSize](#setrowsetsize)です。  
  
 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase#24](../../mfc/codesnippet/cpp/crecordset-class_8.cpp)]  
  
##  <a name="getrowstatus"></a>  CRecordset::GetRowStatus  
 現在の行セット内の行の状態を取得します。  
  
```  
WORD GetRowStatus(WORD wRow) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *wRow*  
 1 から始まる位置の行の現在の行セット。 この値の範囲は 1、行セットのサイズにします。  
  
### <a name="return-value"></a>戻り値  
 行の状態値です。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>Remarks  
 `GetRowStatus` 返しますまたは、データ ソースからが最後の行に状態の変更を示す値を取得ない行に対応する*wRow*がフェッチされました。 次の表は、可能性のある戻り値の一覧です。  
  
|状態値|説明|  
|------------------|-----------------|  
|`SQL_ROW_SUCCESS`|行は変更されません。|  
|`SQL_ROW_UPDATED`|行が更新されました。|  
|`SQL_ROW_DELETED`|行が削除されました。|  
|`SQL_ROW_ADDED`|行が追加されました。|  
|`SQL_ROW_ERROR`|行は、エラーのため取得することができます。|  
|`SQL_ROW_NOROW`|対応する行がない*wRow*です。|  
  
 詳細については、ODBC API 関数を参照してください。 **SQLExtendedFetch** Windows SDK に含まれています。  
  
##  <a name="getstatus"></a>  CRecordset::GetStatus  
 レコード セットと最後のレコードが認識されているかどうかの現在のレコードのインデックスを決定します。  
  
```  
void GetStatus(CRecordsetStatus& rStatus) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *rStatus*  
 参照、 **CRecordsetStatus**オブジェクト。 詳細については、次の「解説」を参照してください。  
  
### <a name="remarks"></a>Remarks  
 `CRecordset` 、インデックスを管理しようとしていますが、特定の状況でこのできない可能性があります。 参照してください[GetRecordCount](#getrecordcount)説明します。  
  
 **CRecordsetStatus**構造体には、次の形式。  
  
 `struct CRecordsetStatus`  
  
 `{`  
  
 `long m_lCurrentRecord;`  
  
 `BOOL m_bRecordCountFinal;`  
  
 `};`  
  
 2 つのメンバー **CRecordsetStatus**次の意味を持ちます。  
  
- **m_lCurrentRecord**既知の場合、レコード セットの現在のレコードの 0 から始まるインデックスが含まれています。 このメンバーを含むインデックスを特定できない場合**AFX_CURRENT_RECORD_UNDEFINED** (-2)。 場合`IsBOF`は**TRUE** (レコード セットを空にする、または先頭レコードの前にスクロールしようとしています)、 **m_lCurrentRecord**に設定されている**AFX_CURRENT_RECORD_BOF** (-1)。 最初のレコードで、設定されている場合に 0 を第 2 1, と記録にします。  
  
- **m_bRecordCountFinal** 0 以外の場合は、レコード セット内のレコードの合計数が決定されました。 レコード セットの先頭からを呼び出すことにより、その一般的にこれ行う必要があります`MoveNext`まで`IsEOF`0 以外を返します。 このメンバーは、0 は場合、によって返されるレコードのカウント`GetRecordCount`-1 ではありませんが、レコードの「ハイ ウォーターマーク」数だけの場合。  
  
##  <a name="getsql"></a>  CRecordset::GetSQL  
 開かれたときに、レコード セットのレコードを選択するために使用された SQL ステートメントを取得するには、このメンバー関数を呼び出します。  
  
```  
const CString& GetSQL() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A **const**への参照、 `CString` SQL ステートメントを含むです。  
  
### <a name="remarks"></a>Remarks  
 これは一般に、SQL になります**選択**ステートメントです。 によって返される文字列`GetSQL`は読み取り専用です。  
  
 によって返される文字列`GetSQL`通常とは異なる任意の文字列でレコード セットに渡された可能性があります、 *lpszSQL*パラメーターを`Open`メンバー関数。 これは、レコード セットに渡される内容に基づく完全な SQL ステートメントを作成するため`Open`、どのような場合がありますで指定した ClassWizard で指定した、**か**と`m_strSort`およびデータ メンバーパラメーターが指定した可能性があります。 レコード セットがこの SQL ステートメントを作成する方法の詳細については、記事を参照してください[レコード セット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)です。  
  
> [!NOTE]
>  呼び出した後にのみ、このメンバー関数を呼び出す[開く](#open)です。  
  
##  <a name="gettablename"></a>  CRecordset::GetTableName  
 レコード セットのクエリの基になる SQL テーブルの名前を取得します。  
  
```  
const CString& GetTableName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A **const**への参照、`CString`テーブルを格納しているレコード セットがテーブルに基づく、それ以外の場合、空の文字列の名前します。  
  
### <a name="remarks"></a>Remarks  
 `GetTableName` 有効なは、レコード セットが、複数のテーブルまたは定義済みクエリ (ストアド プロシージャ) の結合ではないテーブルに基づいている場合のみです。 名前は、読み取り専用です。  
  
> [!NOTE]
>  呼び出した後にのみ、このメンバー関数を呼び出す[開く](#open)です。  
  
##  <a name="isbof"></a>  CRecordset::IsBOF  
 レコード セットは、最初のレコードの前に位置付けられている場合は 0 以外を返します。 現在のレコードがありません。  
  
```  
BOOL IsBOF() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットにレコードが含まれていない場合、または最初のレコードの前にスクロールした場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 レコード セットの最初のレコードの前に位置しているかどうかを学習するレコードにレコードをスクロールする前に、このメンバー関数を呼び出します。 使用することも`IsBOF`と共に`IsEOF`レコード セットがすべてのレコードが含まれていますか空かどうかを確認します。 呼び出した後すぐに`Open`レコード セットに、レコードが含まれていない場合、 `IsBOF` 0 以外を返します。最初のレコードが現在のレコードには、少なくとも 1 つのレコードがレコード セットを開いたときと`IsBOF`0 を返します。  
  
 最初のレコードは、現在のレコードとを呼び出す場合`MovePrev`、`IsBOF`後以外を返します。 場合`IsBOF`呼び出す 0 以外を返しますと`MovePrev`エラーが発生します。 場合`IsBOF`0 以外を返します、現在のレコードが定義されていないと、現在のレコードを必要とする任意のアクション、エラーが発生します。  
  
### <a name="example"></a>例  
 この例では`IsBOF`と`IsEOF`レコード セットを双方向にスクロールすると、レコード セットの制限を検出するためにします。  
  
 [!code-cpp[NVC_MFCDatabase#25](../../mfc/codesnippet/cpp/crecordset-class_9.cpp)]  
  
##  <a name="isdeleted"></a>  CRecordset::IsDeleted  
 現在のレコードが削除されたかどうかを判断します。  
  
```  
BOOL IsDeleted() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットが削除されたレコードに配置されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 レコードをスクロールする場合と`IsDeleted`返します**TRUE** (0 以外)、スクロールして別のレコードに他のレコード セットの操作を実行する前にします。  
  
 結果`IsDeleted`レコード セットを指定するかどうかが、更新可能かどうか、レコード セットの種類など、さまざまな要因によって異なります、 **crecordset::skipdeletedrecords**オプションかどうか、レコード セットを開いたときに、ドライバーのパックが削除されたレコード、および複数のユーザーがあるかどうか。  
  
 詳細については**crecordset::skipdeletedrecords**とドライバーの梱包を参照してください、[開く](#open)メンバー関数。  
  
> [!NOTE]
>  バルク行フェッチを実装した場合は、呼び出す必要はありません`IsDeleted`です。 代わりを呼び出して、 [GetRowStatus](#getrowstatus)メンバー関数。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
##  <a name="iseof"></a>  CRecordset::IsEOF  
 レコード セットは、後の最後のレコードに位置付けられている場合は 0 以外を返します。 現在のレコードがありません。  
  
```  
BOOL IsEOF() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットにレコードが含まれていない場合、または最後のレコードより後にスクロールする場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 レコードからレコード セットの最後のレコードを越えているかどうかを説明するレコードをスクロールするときに、このメンバー関数を呼び出します。 使用することも`IsEOF`レコード セットがすべてのレコードが含まれていますか空かどうかを確認します。 呼び出した後すぐに`Open`レコード セットに、レコードが含まれていない場合、 `IsEOF` 0 以外を返します。 最初のレコードが現在のレコードには、少なくとも 1 つのレコードがレコード セットを開いたときと`IsEOF`0 を返します。  
  
 呼び出すときに、最後のレコードが現在のレコードがかどうか`MoveNext`、`IsEOF`後以外を返します。 場合`IsEOF`呼び出す 0 以外を返しますと`MoveNext`エラーが発生します。 場合`IsEOF`0 以外を返します、現在のレコードが定義されていないと、現在のレコードを必要とする任意のアクション、エラーが発生します。  
  
### <a name="example"></a>例  
 例を参照して[IsBOF](#isbof)です。  
  
##  <a name="isfielddirty"></a>  CRecordset::IsFieldDirty  
 以降、指定されたフィールド データ メンバーが変更されたかどうかを判断[編集](#edit)または[AddNew](#addnew)が呼び出されました。  
  
```  
BOOL IsFieldDirty(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 *pv*  
 状態を確認するにはフィールド データ メンバーへのポインターまたは**NULL**をフィールドのいずれがダーティかどうかを判断します。  
  
### <a name="return-value"></a>戻り値  
 指定されたフィールド データ メンバーが呼び出し以降に変更された場合は 0 以外`AddNew`または`Edit`。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>Remarks  
 すべてのダーティ フィールド データ メンバー内のデータは上を転送レコード、データ ソースへの呼び出しによって、現在のレコードが更新されたときに、[更新](#update)のメンバー関数`CRecordset`(の呼び出しに続く`Edit`または`AddNew`).  
  
> [!NOTE]
>  このメンバー関数では、バルク行フェッチを使用しているレコード セットに適用されません。 実装した場合、バルク行フェッチし、`IsFieldDirty`は常に返します**FALSE**と失敗したアサーションが発生します。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
 呼び出す`IsFieldDirty`への呼び出しの前の効果をリセット[き](#setfielddirty)フィールドのダーティ状態が再評価されるためです。 `AddNew`場合は、擬似、null 値と現在のフィールドの値が異なる場合、フィールド ステータスが設定ダーティです。 `Edit`大文字と小文字、フィールドの値が異なる場合、キャッシュされた値、フィールドの状態は、ダーティで設定されます。  
  
 `IsFieldDirty` によって実装され[DoFieldExchange](#dofieldexchange)です。  
  
 ダーティ フラグの詳細については、記事を参照してください。[レコード セット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)です。  
  
##  <a name="isfieldnull"></a>  CRecordset::IsFieldNull  
 現在のレコードで指定されたフィールドが Null の場合は 0 以外を返します (値はありません)。  
  
```  
BOOL IsFieldNull(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 *pv*  
 状態を確認するにはフィールド データ メンバーへのポインターまたは**NULL**をフィールドのいずれかが Null であるかどうかを判断します。  
  
### <a name="return-value"></a>戻り値  
 指定されたフィールド データ メンバーが Null です。 としてフラグが設定された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 レコード セットの指定したフィールド データ メンバーを Null としてマークされているかどうかを決定するには、このメンバー関数を呼び出します。 (データベース用語では、「値を持たない」手段を Null に設定と同じではありませんし**NULL** c++)。フィールド データ メンバーが Null としてフラグが設定した場合は、対象の値はありません、現在のレコードの列として解釈されます。  
  
> [!NOTE]
>  このメンバー関数では、バルク行フェッチを使用しているレコード セットに適用されません。 実装した場合、バルク行フェッチし、`IsFieldNull`は常に返します**FALSE**と失敗したアサーションが発生します。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
 `IsFieldNull` によって実装され[DoFieldExchange](#dofieldexchange)です。  
  
##  <a name="isfieldnullable"></a>  CRecordset::IsFieldNullable  
 現在のレコードで指定したフィールドを Null に設定する (値がない) 場合は 0 以外を返します。  
  
```  
BOOL IsFieldNullable(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 *pv*  
 状態を確認するにはフィールド データ メンバーへのポインターまたは**NULL**を Null 値に設定するかどうか、フィールドのいずれかを判断します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数、指定されたフィールド データ メンバーが"null 値を許容"するかどうかを判断する (できます; に Null 値に設定C++ **NULL** Null の場合、つまり、データベース用語と同じではありません「値を持たない」) です。  
  
> [!NOTE]
>  バルク行フェッチを実装した場合を呼び出すことはできません`IsFieldNullable`です。 代わりを呼び出して、 [GetODBCFieldInfo](#getodbcfieldinfo)フィールドを Null 値に設定できるかどうかを決定するメンバー関数。 常に呼び出すことのできる注`GetODBCFieldInfo`バルク行フェッチを実装するかどうかに関係なく、します。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
 Null 値は、フィールド値が必要です。 このようなフィールドを追加またはレコードを更新する場合は Null に設定しようとすると、データ ソースは追加または更新プログラムを拒否し、[更新](#update)例外がスローされます。 呼び出すときに例外が発生した`Update`を呼び出すときではなく、[な](#setfieldnull)します。  
  
 使用して**NULL**関数の最初の引数が関数にのみ適用されますの**outputColumn**フィールドいない**param**フィールドです。 インスタンスの呼び出し  
  
 [!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 セットのみが**outputColumn**フィールドを**NULL**です。**param**フィールドには影響ありません。  
  
 作業する**param**フィールドで、個々 の実際のアドレスを指定する必要があります**param**など、作業します。  
  
 [!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 つまり、すべて設定することはできません**param**フィールドを**NULL**と同様、 **outputColumn**フィールドです。  
  
 `IsFieldNullable` によって実装され[DoFieldExchange](#dofieldexchange)です。  
  
##  <a name="isopen"></a>  CRecordset::IsOpen  
 かどうか、レコード セットは既に開いてを決定します。  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、レコード セット オブジェクトの[開いている](#open)または[Requery](#requery)メンバー関数が呼び出されていたため、レコード セットが閉じられましたできません; 0 それ以外の場合。  
  
##  <a name="m_hstmt"></a>  CRecordset::m_hstmt  
 型の ODBC ステートメントのデータ構造体へのハンドルを含む**HSTMT**レコード セットに関連付けられている。  
  
### <a name="remarks"></a>Remarks  
 ODBC データ ソースには、各クエリに関連付けられている、 **HSTMT**です。  
  
> [!CAUTION]
>  使用しないでください**m_hstmt**する前に[開く](#open)呼び出されました。  
  
 通常にアクセスする必要はありません、 **HSTMT**を直接 SQL ステートメントの直接の実行にならない場合があります。 `ExecuteSQL`クラスのメンバー関数`CDatabase`の使用例を示します**m_hstmt**です。  
  
##  <a name="m_nfields"></a>  CRecordset::m_nFields  
 レコード セット クラスのフィールド データ メンバーの数が含まれていますつまり、データ ソースからレコード セットが選択した列の数。  
  
### <a name="remarks"></a>Remarks  
 レコード セット クラスのコンス トラクターを初期化する必要があります`m_nFields`を正しい値にします。 バルク行フェッチを実装していない場合、ClassWizard は、レコード セット クラスの宣言を使用するときにこの初期化を記述を書き込みます。 手動で記述することもできます。  
  
 フレームワークは、フィールド データ メンバーと、データ ソースの現在のレコードの対応する列間の相互作用を管理するのに、この番号を使用します。  
  
> [!CAUTION]
>  この数は、「出力列」に登録されている数に対応する必要があります`DoFieldExchange`または`DoBulkFieldExchange`への呼び出し後[SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype)パラメーターを使用して**CFieldExchange::outputColumn**です。  
  
 アーティクルの説明に従って、動的に列をバインドすることができます"レコード セット: 動的にバインディングのデータ列です"。 これを行う場合に含まれる数を大きく必要があります`m_nFields`呼び出し rfx 関数または Bulk RFX 関数の数を反映するように、`DoFieldExchange`または`DoBulkFieldExchange`動的にバインドされた列のメンバー関数。  
  
 詳細については、記事を参照してください。[レコード セット: データ列を動的に結びつける (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)と[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。  
  
### <a name="example"></a>例  
 記事を参照して[レコード フィールド エクス チェンジ: RFX の使い方](../../data/odbc/record-field-exchange-using-rfx.md)です。  
  
##  <a name="m_nparams"></a>  CRecordset::m_nParams  
 レコード セット クラスのパラメーター データ メンバーの数が含まれていますつまり、パラメーターの数は、レコード セットのクエリで渡されます。  
  
### <a name="remarks"></a>Remarks  
 クラスのコンス トラクターを初期化する必要があります、レコード セット クラスにパラメーター データ メンバーがある場合は、`m_nParams`を正しい値にします。 値`m_nParams`既定値は 0 です。 手動でパラメーターの数を反映するように、クラス コンス トラクターで初期化を追加する必要があります (を手動で行う必要があります) のパラメーター データ メンバーを追加する場合 (の数とサイズ以上である必要がありますが ' 内のプレース ホルダー、**か**または`m_strSort`文字列)。  
  
 フレームワークは、レコード セットのクエリをパラメーター化するときに、この番号を使用します。  
  
> [!CAUTION]
>  この数は、「パラメーター」に登録されている数に対応する必要があります`DoFieldExchange`または`DoBulkFieldExchange`への呼び出し後[SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype)のパラメーター値を持つ**CFieldExchange::inputParam**、 **CFieldExchange::param**、 **CFieldExchange::outputParam**、または**CFieldExchange::inoutParam**です。  
  
### <a name="example"></a>例  
  記事を参照して[レコード セット: レコード セット (ODBC) のパラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)と[レコード フィールド エクス チェンジ: RFX の使い方](../../data/odbc/record-field-exchange-using-rfx.md)です。  
  
##  <a name="m_pdatabase"></a>  CRecordset::m_pDatabase  
 ポインターが含まれています、`CDatabase`データ ソースに使用されるレコード セットが接続されているオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 この変数は、2 つの方法で設定されます。 通常、ポインターを渡して、既に接続されている`CDatabase`オブジェクトのレコード セット オブジェクトを構築するときにします。 渡す場合**NULL**代わりに、`CRecordset`を作成、`CDatabase`するオブジェクトを接続します。 どちらの場合、`CRecordset`この変数にポインターを格納します。  
  
 通常は直接不要に格納されているポインターを使用する**m_pDatabase**です。 独自の拡張機能を記述する場合`CRecordset`、ただし、ポインターを使用する必要があります。 たとえば、する必要があります、ポインターをスローする場合、独自`CDBException`s。 必要になるを使用して、同じ処理を行う必要がある場合または`CDatabase`、実行されるトランザクションのタイムアウト設定、または呼び出しなどのオブジェクト、`ExecuteSQL`クラスのメンバー関数`CDatabase`直接 SQL ステートメントを実行します。  
  
##  <a name="m_strfilter"></a>  CRecordset::m_strFilter  
 呼び出す前に、レコード セット オブジェクトを構築した後、その`Open`メンバー関数、ストアにこのデータ メンバーを使用して、 `CString` SQL を含む**場所**句。  
  
### <a name="remarks"></a>Remarks  
 レコード セットでは、この文字列を使用して、制約 (フィルター) 中に、選択されたレコード、`Open`または`Requery`呼び出します。 これは、「すべての販売員カリフォルニア州に基づいた」など、レコードのサブセットを選択するのに便利です ("の状態 = CA") です。 ODBC SQL 構文を**場所**句は、  
  
 `WHERE search-condition`  
  
 含めないようにすることに注意してください、**場所**文字列のキーワードでします。 フレームワークを指定します。  
  
 配置することで、フィルター文字列をパラメーター化することもできます ' 内のプレース ホルダー、各プレース ホルダーのクラスにパラメーター データ メンバーを宣言して、パラメーターを渡すことで、レコード セットを実行します。 これにより、実行時にフィルターを作成できます。 詳細については、記事を参照してください。[レコード セット: レコード セット (ODBC) のパラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)です。  
  
 SQL の詳細については**場所**句は、記事を参照して[SQL](../../data/odbc/sql.md)です。 選択して、レコードのフィルター処理する方法の詳細については、記事を参照してください。[レコード セット: レコードのフィルター処理 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase#30](../../mfc/codesnippet/cpp/crecordset-class_12.cpp)]  
  
##  <a name="m_strsort"></a>  CRecordset::m_strSort  
 呼び出す前に、レコード セット オブジェクトを構築した後、その`Open`メンバー関数、ストアにこのデータ メンバーを使用して、 `CString` SQL を含む**ORDER BY**句。  
  
### <a name="remarks"></a>Remarks  
 レコード セットは、この文字列を使用して、並べ替え中に、選択されたレコード、`Open`または`Requery`呼び出します。 1 つ以上の列をレコード セットを並べ替えるには、この機能を使用することができます。 ODBC SQL 構文を**ORDER BY**句は、  
  
 `ORDER BY sort-specification [, sort-specification]...`  
  
 並べ替え仕様は、整数または列の名前です。 (既定では、順序は昇順)、昇順または降順の順序は、並べ替え文字列の列リストに"ASC"または"DESC"を追加しても指定できます。 選択したレコードは、秒のように、次の最初の列が表示されている、最初に並べ替えられます。 たとえば、姓、名、姓で"Customers"レコード セットを注文する可能性があります。 表示できる列の数は、データ ソースに依存します。 詳細については、Windows SDK を参照してください。  
  
 含めないようにすることに注意してください、 **ORDER BY**文字列のキーワードでします。 フレームワークを指定します。  
  
 SQL 句の詳細については、記事を参照してください。 [SQL](../../data/odbc/sql.md)です。 レコードの並べ替えの詳細については、記事を参照してください。[レコード セット: レコードの並べ替え (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)です。  
  
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
 *nRows*  
 前方または後方に移動する行の数。 正の値は、レコード セットの末尾に向かって前方移動します。 負の値は、先頭に向かって後方移動します。  
  
 *wFetchType*  
 行セットを決定する`Move`がフェッチされます。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>Remarks  
 場合は 0 の値を渡す場合*nRows*、 `Move` ; 現在のレコードを更新`Move` 、現在は終了`AddNew`または`Edit`モードでは、前に、現在のレコードの値を復元および`AddNew`または`Edit`が呼び出されました。  
  
> [!NOTE]
>  レコード セット内を移動するときに、削除されたレコードをスキップできません。 参照してください[CRecordset::IsDeleted](#isdeleted)詳細についてはします。 開くと、`CRecordset`で、 **skipDeletedRecords**オプションを設定、`Move`場合アサート、 *nRows*パラメーターが 0 です。 この動作は、同じデータを使用して他のクライアント アプリケーションによって削除される行の更新を防止します。 参照してください、 *dwOption*パラメーター[開く](#open)の詳細については**skipDeletedRecords**です。  
  
 `Move` 行セットによって、レコード セットを再配置します。 値に基づく*nRows*と*wFetchType*、`Move`適切な行セットをフェッチし、最初のレコードを行セットの現在のレコードです。 バルク行フェッチを実装したされない場合、行セットのサイズは常に 1 です。 行セットをフェッチするときに`Move`直接呼び出し、 [CheckRowsetError](#checkrowseterror)メンバー関数からのフェッチで、結果として得られるエラーの処理をします。  
  
 渡すと、値に応じて`Move`は他のと同じ`CRecordset`メンバー関数。 特にの値で*wFetchType*より直感的であるメンバー関数と、多くの場合、現在のレコードを移動するための推奨される方法を示す可能性があります。  
  
 次の表に、可能な値*wFetchType*、行セットを`Move`がフェッチに基づいて*wFetchType*と*nRows*、および該当するショートカットは、メンバー関数に対応する*wFetchType*です。  
  
|wFetchType|フェッチされた行セット|同等のメンバー関数|  
|----------------|--------------------|--------------------------------|  
|`SQL_FETCH_RELATIVE` (既定値)|行セットの開始*nRows*現在の行セットの最初の行からの行。||  
|`SQL_FETCH_NEXT`|次の行セットです。*nRows*は無視されます。|[MoveNext](#movenext)|  
|`SQL_FETCH_PRIOR`|前の行セットです。*nRows*は無視されます。|[MovePrev](#moveprev)|  
|`SQL_FETCH_FIRST`|レコード セットの最初の行セット*nRows*は無視されます。|[MoveFirst](#movefirst)|  
|`SQL_FETCH_LAST`|レコード セットの最後の完全な行セット*nRows*は無視されます。|[MoveLast](#movelast)|  
|`SQL_FETCH_ABSOLUTE`|場合*nRows* > 0 で始まる行セット*nRows*レコード セットの先頭からの行。 場合*nRows* < 0 で始まる行セット*nRows*レコード セットの末尾から行です。 場合*nRows* = 0、先頭のファイル (BOF) の状態が返されます。|[SetAbsolutePosition](#setabsoluteposition)|  
|`SQL_FETCH_BOOKMARK`|ブックマーク値を持つは、行で始まる行セット*nRows*です。|[SetBookmark](#setbookmark)|  
  
> [!NOTE]
>  順方向専用レコード セットの場合、`Move`はの値でのみ有効`SQL_FETCH_NEXT`の`wFetchType`します。  
  
> [!CAUTION]
>  呼び出す`Move`レコード セットにレコードが存在しない場合、例外をスローします。 レコード セットがすべてのレコードを持つかどうかを確認するのには、呼び出す[IsBOF](#isbof)と[IsEOF](#iseof)です。  
  
> [!NOTE]
>  先頭またはレコード セットの末尾を越えてスクロールした場合 (`IsBOF`または`IsEOF`0 以外を返します) を呼び出す、`Move`関数がスローされますが、`CDBException`です。 たとえば場合、 `IsEOF` 0 以外を返しますと`IsBOF`しない、し`MoveNext`、例外がスローされますが、`MovePrev`は表示されません。  
  
> [!NOTE]
>  呼び出す場合`Move`現在のレコードがされている間に更新または追加、更新プログラムは警告なしに失われます。  
  
 レコード セットの移動の詳細については、記事を参照してください。[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)と[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)です。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。 関連情報については、ODBC API 関数を参照してください。 **SQLExtendedFetch** Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase#28](../../mfc/codesnippet/cpp/crecordset-class_14.cpp)]  
  
##  <a name="movefirst"></a>  CRecordset::MoveFirst  
 現在のレコードを最初の行セットの最初のレコードに位置付けます。  
  
```  
void MoveFirst();
```  
  
### <a name="remarks"></a>Remarks  
 かどうかバルク行フェッチが実装されてに関係なく、必ずこのレコード セットの最初のレコード。  
  
 呼び出していない`MoveFirst`レコード セットを開いた直後後。 その時点では、最初のレコード (存在する場合) と、現在のレコードでは自動的にします。  
  
> [!NOTE]
>  前方スクロール専用レコードのこのメンバー関数が正しくありません。  
  
> [!NOTE]
>  レコード セット内を移動するときに、削除されたレコードをスキップできません。 参照してください、 [IsDeleted](#isdeleted)詳細については、メンバー関数。  
  
> [!CAUTION]
>  いずれかを呼び出して、`Move`レコード セットにレコードが存在しない場合、関数が例外をスローします。 レコード セットがすべてのレコードを持つかどうかを確認するのには、呼び出す`IsBOF`と`IsEOF`です。  
  
> [!NOTE]
>  呼び出す場合、`Move`関数を現在のレコードがされている間に更新または追加、更新プログラムは警告なしに失われます。  
  
 レコード セットの移動の詳細については、記事を参照してください。[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)と[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)です。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
### <a name="example"></a>例  
  例を参照して[IsBOF](#isbof)です。  
  
##  <a name="movelast"></a>  CRecordset::MoveLast  
 現在のレコードを最後の完全な行セットの最初のレコードに位置付けます。  
  
```  
void MoveLast();
```  
  
### <a name="remarks"></a>Remarks  
 バルク行フェッチを実装したされない場合、レコード セットがあり、行セットのサイズは 1、その`MoveLast`だけレコードに移動最後のレコード セットにします。  
  
> [!NOTE]
>  前方スクロール専用レコードのこのメンバー関数が正しくありません。  
  
> [!NOTE]
>  レコード セット内を移動するときに、削除されたレコードをスキップできません。 参照してください、 [IsDeleted](#isdeleted)詳細については、メンバー関数。  
  
> [!CAUTION]
>  いずれかを呼び出して、`Move`レコード セットにレコードが存在しない場合、関数が例外をスローします。 レコード セットがすべてのレコードを持つかどうかを確認するのには、呼び出す`IsBOF`と`IsEOF`です。  
  
> [!NOTE]
>  呼び出す場合、`Move`関数を現在のレコードがされている間に更新または追加、更新プログラムは警告なしに失われます。  
  
 レコード セットの移動の詳細については、記事を参照してください。[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)と[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)です。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
### <a name="example"></a>例  
  例を参照して[IsBOF](#isbof)です。  
  
##  <a name="movenext"></a>  CRecordset::MoveNext  
 現在のレコードを次の行セットの最初のレコードに位置付けます。  
  
```  
void MoveNext();
```  
  
### <a name="remarks"></a>Remarks  
 バルク行フェッチを実装したされない場合、レコード セットがあり、行セットのサイズは 1、その`MoveNext`単純に次のレコードに移動します。  
  
> [!NOTE]
>  レコード セット内を移動するときに、削除されたレコードをスキップできません。 参照してください、 [IsDeleted](#isdeleted)詳細については、メンバー関数。  
  
> [!CAUTION]
>  いずれかを呼び出して、`Move`レコード セットにレコードが存在しない場合、関数が例外をスローします。 レコード セットがすべてのレコードを持つかどうかを確認するのには、呼び出す`IsBOF`と`IsEOF`です。  
  
> [!NOTE]
>  呼び出すことも推奨`IsEOF`呼び出す前に`MoveNext`です。 たとえば、レコード セットの末尾を越えてスクロールした`IsEOF`は 0 以外を返します後続の呼び出しに`MoveNext`例外をスローした場合します。  
  
> [!NOTE]
>  呼び出す場合、`Move`関数を現在のレコードがされている間に更新または追加、更新プログラムは警告なしに失われます。  
  
 レコード セットの移動の詳細については、記事を参照してください。[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)と[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)です。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
### <a name="example"></a>例  
  例を参照して[IsBOF](#isbof)です。  
  
##  <a name="moveprev"></a>  CRecordset::MovePrev  
 現在のレコードを前の行セットの最初のレコードに位置付けます。  
  
```  
void MovePrev();
```  
  
### <a name="remarks"></a>Remarks  
 バルク行フェッチを実装したされない場合、レコード セットがあり、行セットのサイズは 1、その`MovePrev`単純に前のレコードに移動します。  
  
> [!NOTE]
>  前方スクロール専用レコードのこのメンバー関数が正しくありません。  
  
> [!NOTE]
>  レコード セット内を移動するときに、削除されたレコードをスキップできません。 参照してください、 [IsDeleted](#isdeleted)詳細については、メンバー関数。  
  
> [!CAUTION]
>  いずれかを呼び出して、`Move`レコード セットにレコードが存在しない場合、関数が例外をスローします。 レコード セットがすべてのレコードを持つかどうかを確認するのには、呼び出す`IsBOF`と`IsEOF`です。  
  
> [!NOTE]
>  呼び出すことも推奨`IsBOF`呼び出す前に`MovePrev`です。 たとえば、レコード セットの先頭にスクロールして`IsBOF`は 0 以外を返します後続の呼び出しに`MovePrev`例外をスローした場合します。  
  
> [!NOTE]
>  呼び出す場合、`Move`関数を現在のレコードがされている間に更新または追加、更新プログラムは警告なしに失われます。  
  
 レコード セットの移動の詳細については、記事を参照してください。[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)と[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)です。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
### <a name="example"></a>例  
  例を参照して[IsBOF](#isbof)です。  
  
##  <a name="onsetoptions"></a>  CRecordset::OnSetOptions  
 指定された ODBC ステートメントには、(選択に使用する) オプションを設定すると呼ばれます。  
  
```  
virtual void OnSetOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>パラメーター  
 *hstmt*  
 **HSTMT**を設定するオプションは、ODBC ステートメントのです。  
  
### <a name="remarks"></a>Remarks  
 呼び出す`OnSetOptions`を指定された ODBC ステートメントのオプション (選択に使用される) を設定します。 フレームワークは、レコード セットの最初のオプションを設定するには、このメンバー関数を呼び出します。 `OnSetOptions` スクロール可能なカーソルとカーソルの同時実行のデータ ソースのサポートを決定し、レコード セットのオプションを設定します。 (一方`OnSetOptions`選択操作のために使用`OnSetUpdateOptions`更新操作のために使用します)。  
  
 オーバーライド`OnSetOptions`ドライバーまたはデータ ソースに固有のオプションを設定します。 たとえば場合は、データ ソースの排他アクセスのオープンをサポートする方が優先`OnSetOptions`その機能を利用するためにします。  
  
 カーソルの詳細については、記事を参照してください。 [ODBC](../../data/odbc/odbc-basics.md)です。  
  
##  <a name="onsetupdateoptions"></a>  CRecordset::OnSetUpdateOptions  
 指定された ODBC ステートメントのオプション (更新プログラムで使用される) を設定すると呼ばれます。  
  
```  
virtual void OnSetUpdateOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>パラメーター  
 *hstmt*  
 **HSTMT**を設定するオプションは、ODBC ステートメントのです。  
  
### <a name="remarks"></a>Remarks  
 呼び出す`OnSetUpdateOptions`を指定された ODBC ステートメントのオプション (更新プログラムで使用される) を設定します。 フレームワークは、レコード セットからレコードを更新する HSTMT が作成された後に、このメンバー関数を呼び出します。 (一方`OnSetOptions`選択操作のために使用`OnSetUpdateOptions`更新操作のために使用します)。`OnSetUpdateOptions`スクロール可能なカーソルとカーソルの同時実行のデータ ソースのサポートを決定し、レコード セットのオプションを設定します。  
  
 オーバーライド`OnSetUpdateOptions`をそのステートメントを使用して、データベースにアクセスする前に、ODBC ステートメントのオプションを設定します。  
  
 カーソルの詳細については、記事を参照してください。 [ODBC](../../data/odbc/odbc-basics.md)です。  
  
##  <a name="open"></a>  :Open  
 テーブルを取得するか、レコードセットが表すクエリを実行して、レコードセットを開きます。  
  
```  
virtual BOOL Open(
    UINT nOpenType = AFX_DB_USE_DEFAULT_TYPE,  
    LPCTSTR lpszSQL = NULL,  
    DWORD dwOptions = none);
```  
  
### <a name="parameters"></a>パラメーター  
 *できるかどうか*  
 既定値をそのまま**AFX_DB_USE_DEFAULT_TYPE**、または、次のいずれかの値を使用して、 **enum OpenType**:  
  
- **Crecordset::dynaset**双方向にスクロールできるレコード セット。 レコードのメンバーシップおよび順序は、レコードセットを開いたときに決定されますが、他のユーザーによるデータ値の変更は、フェッチ操作後に表示されます。 ダイナセットは、キーセット ドリブン レコードセットとも呼ばれます。  
  
- **Crecordset::snapshot**双方向にスクロールできる静的レコード セット。 レコードのメンバーシップと順序は、レコードセットを開いたときに決定されます。データ値は、レコードをフェッチしたときに決定されます。 他のユーザーが行った変更は、レコードセットを閉じてから再度開くまで表示されません。  
  
- **Crecordset::dynamic**双方向にスクロールできるレコード セット。 他のユーザーが行ったメンバーシップ、順序、およびデータ値の変更は、フェッチ操作後に表示されます。 多くの ODBC ドライバーでは、この型のレコードセットはサポートされていません。  
  
- **Crecordset::forwardonly**前方スクロールのみが読み取り専用レコード セット。  
  
     `CRecordset`、既定値は**crecordset::snapshot**です。 既定値の機構により、Visual C++ ウィザードで既定値の異なる ODBC `CRecordset` と DAO `CDaoRecordset` 両方を操作できます。  
  
 これらのレコード セットの種類の詳細については、記事を参照してください。[レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)です。 関連情報については、「「を使用してブロック カーソルとスクロール可能なカーソル」は Windows sdk」を参照してください。  
  
> [!CAUTION]
>  要求した型がサポートされていない場合、例外がスローされます。  
  
 *lpszSQL*  
 次のいずれかを含む文字列ポインター:  
  
-   A **NULL**ポインター。  
  
-   テーブルの名前。  
  
-   SQL**選択**ステートメント (SQL オプションで**場所**または**ORDER BY**句)。  
  
-   A**呼び出す**定義済みクエリ (ストアド プロシージャ) の名前を指定するステートメント。 中かっこの間にスペースを挿入しないように注意してください、**呼び出す**キーワード。  
  
 この文字列の詳細については、「解説」の表と ClassWizard のロールの説明を参照してください。  
  
> [!NOTE]
>  結果セットの列の順序は、RFX の順序と一致する必要がありますまたはバルク RFX 関数呼び出しに、 [DoFieldExchange](#dofieldexchange)または[DoBulkFieldExchange](#dobulkfieldexchange)関数オーバーライドします。  
  
 *dwOptions*  
 以下に示す値の組み合わせを指定できるビットマスク。 これらの値の一部は同時に指定できません。 既定値は**none**です。  
  
- **Crecordset::none**オプションが設定されていません。 このパラメーター値は、他のすべての値と同時に指定できません。 既定では、レコード セットを更新することができます[編集](#edit)または[削除](#delete)で新しいレコードを追加できると[AddNew](#addnew)です。 更新機能によって異なります、データ ソースではなく、*できるかどうか*オプションを指定します。 バルク追加の最適化は使用できません。 バルク行フェッチは実装されません。 削除されたレコードはレコードセットの移動中にスキップされません。 ブックマークは使用できません。 自動ダーティ フィールド チェックが実装されます。  
  
- **Crecordset::appendonly**許可しない`Edit`または`Delete`レコード セットでします。 `AddNew` のみ実行できます。 このオプションで相互に排他的**crecordset::readonly**です。  
  
- **Crecordset::readonly**読み取り専用とレコード セットを開きます。 このオプションで相互に排他的**crecordset::appendonly**です。  
  
- **Crecordset::optimizebulkadd**同時に多数のレコードを追加する方法を最適化するために準備された SQL ステートメントを使用します。 ODBC API 関数を使用していない場合にのみ適用**SQLSetPos**をレコード セットを更新します。 最新の更新で、ダーティとマークされるフィールドが決まります。 このオプションは `CRecordset::useMultiRowFetch` と同時に指定できません。  
  
- `CRecordset::useMultiRowFetch` 複数の行を 1 回のフェッチ操作で取得するようにするバルク行フェッチを実装します。 これは、パフォーマンスを向上するために設計された拡張機能です。ただし、バルク レコード フィールド エクスチェンジは ClassWizard ではサポートされていません。 このオプションで相互に排他的**crecordset::optimizebulkadd**です。 指定した場合`CRecordset::useMultiRowFetch`、オプションでは、 **crecordset::nodirtyfieldcheck**自動的に有効 (ダブル バッファリングは使用できません) 前方スクロール専用レコード セットをオプションで **。Crecordset::useextendedfetch**自動的に有効です。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
- **Crecordset::skipdeletedrecords**レコード セット内を移動するときに削除されたすべてのレコードをスキップします。 これにより、特定の相対フェッチでパフォーマンスが低下します。 このオプションは前方スクロール専用レコードセットでは無効です。 呼び出す場合[移動](#move)で、 *nRows*パラメーターを 0 に設定され、 **crecordset::skipdeletedrecords**オプションを設定、`Move`アサートされます。 注意してください**crecordset::skipdeletedrecords**に似ていますが*ドライバーによるパック*、削除された行を示しますが、レコード セットから削除されます。 ただし、ドライバーによってレコードがパックされる場合、ユーザー自身が削除するレコードだけがスキップされます。レコードセットを開いている間に他のユーザーによって削除されたレコードはスキップされません。 **Crecordset::skipdeletedrecords**は他のユーザーによって削除された行をスキップします。  
  
- **Crecordset::usebookmarks**サポートされている場合、レコード セットでブックマークの使用可能性があります。 ブックマークを使用すると、データの取得速度は低下しますが、データ移動のパフォーマンスが向上します。 前方スクロール専用レコードセットでは無効です。 詳細については、記事を参照してください。[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)です。  
  
- **Crecordset::nodirtyfieldcheck**自動ダーティ フィールド チェック (ダブル バッファリング) をオフにします。 これにより、パフォーマンスは向上しますが、`SetFieldDirty` メンバー関数と `SetFieldNull` メンバー関数を呼び出して手動でフィールドをダーティとしてマークする必要があります。`CRecordset` クラスのダブル バッファリングは、`CDaoRecordset` クラスのダブル バッファリングに似ています。 ただし、`CRecordset` では、個別のフィールドに対してダブル バッファリングを有効にできません。すべてのフィールドに対して有効にするか、またはすべてのフィールドに対して無効にします。 オプションを指定する場合は、 `CRecordset::useMultiRowFetch`、し**crecordset::nodirtyfieldcheck**有効になりますが、自動的に`SetFieldDirty`と`SetFieldNull`バルク行フェッチを実装したレコード セットでは使用できません。  
  
- **:Executedirect**準備された SQL ステートメントを使用しないでください。 パフォーマンスを向上させる場合にこのオプションを指定、`Requery`メンバー関数は呼び出されません。  
  
- **Crecordset::useextendedfetch**実装`SQLExtendedFetch** instead of `SQLFetch`. This is designed for implementing bulk row fetching on forward-only recordsets. If you specify the option `割り当てる '、順方向専用レコード セットで、 **crecordset::useextendedfetch**有効になります自動的に。  
  
- **Crecordset::userallocmultirowbuffers**ユーザーは、データの格納バッファーを割り当てます。 独自の格納バッファーを割り当てる場合は、このオプションと一緒に `CRecordset::useMultiRowFetch` を使用します。使用しない場合、必要な格納バッファーが自動的に割り当てられます。 詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。 指定する**crecordset::userallocmultirowbuffers**を指定せず`CRecordset::useMultiRowFetch`アサーションは失敗が発生します。  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、`CRecordset`オブジェクトが正常に開かれたそれ以外の場合は 0 [cdatabase::open](../../mfc/reference/cdatabase-class.md#open) (と呼ばれる) 場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 レコードセットによって定義されたクエリを実行するには、このメンバー関数を呼び出す必要があります。 呼び出しの前に`Open`、レコード セット オブジェクトを構築する必要があります。  
  
 このレコード セットのソースへの接続、データが呼び出す前に、レコード セットを作成する方法に依存`Open`です。 渡す場合、 [CDatabase](../../mfc/reference/cdatabase-class.md)このメンバー関数を使用してオブジェクト データ ソースに接続されていないレコード セットのコンス トラクターを[GetDefaultConnect](#getdefaultconnect)しようとするデータベース オブジェクトを開きます。 渡す場合**NULL**コンス トラクターを作成、レコード セットのコンス トラクターを`CDatabase`、オブジェクトおよび`Open`データベース オブジェクトを接続しようとしています。 レコード セットとさまざまな状況で接続を閉じる方法の詳細については、「[閉じる](#close)です。  
  
> [!NOTE]
>  `CRecordset` オブジェクトを使用したデータ ソースへのアクセスは常に共有されます。 `CDaoRecordset` クラスとは異なり、`CRecordset` オブジェクトを使用して排他アクセスでデータ ソースを開くことはできません。  
  
 呼び出すと`Open`、クエリ、通常、SQL**選択**ステートメントでは、次の表に示す条件に基づいてレコードを選択します。  
  
|lpszSQL パラメーターの値|レコードの選択基準|例|  
|------------------------------------|----------------------------------------|-------------|  
|**NULL**|`GetDefaultSQL` の返す文字列。||  
|SQL テーブル名|`DoFieldExchange` または `DoBulkFieldExchange` のテーブル リストのすべての列。|`"Customer"`|  
|定義済みクエリ (ストアド プロシージャ) の名前|返すためにクエリが定義された列。|`"{call OverDueAccts}"`|  
|**選択**列リスト**FROM**テーブル リスト|指定したテーブルの指定した列。|`"SELECT CustId, CustName FROM`<br /><br /> `Customer"`|  
  
> [!CAUTION]
>  SQL 文字列に余分な空白を挿入しないでください。 たとえば、中かっこの間にスペースを挿入する場合、**を呼び出す**キーワード、MFC は、テーブル名として、SQL 文字列を誤って解釈およびに組み込むため、**選択**ステートメントでは、原因となる、例外がスローされます。 同様に、定義済みクエリは、出力パラメーターを使用する場合は空白を挿入しないで中かっこの間および ' 記号です。 中かっこの前に空白を挿入する最後に、必要があります、**呼び出し**ステートメントまたは前に、**選択**キーワード、**選択**ステートメント。  
  
 通常のプロシージャでは**NULL**に`Open`です。 この場合、`Open`呼び出し[GetDefaultSQL](#getdefaultsql)です。 派生を使用している場合`CRecordset`クラス、 **GetDefaultSQL** ClassWizard で指定したテーブル名を提供します。 代わりに、その他の情報を `lpszSQL` パラメーターに指定できます。  
  
 何を渡した`Open`クエリの最終的な SQL 文字列を構築 (SQL も**場所**と**ORDER BY**に句が追加されます、`lpszSQL`渡された文字列) しを実行クエリ。 呼び出すことによって構築された文字列を調べることができます[GetSQL](#getsql)呼び出した後に *`Open`です。 レコード セットの SQL ステートメントを作成して、レコードを選択する詳細については、記事を参照してください[レコード セット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)です。  
  
 レコードセット クラスのフィールド データ メンバーは、選択したデータの列に結び付けられています。 いくつかのレコードが返された場合、最初のレコードが現在のレコードになります。  
  
 フィルターや並べ替えなど、レコード セットのオプションを設定する場合を指定してこれらを呼び出す前に、レコード セット オブジェクトを構築した後、`Open`です。 レコード セットは既に開いてレコード セット内のレコードを更新する場合は、呼び出す[Requery](#requery)です。  
  
 詳細については、その他の例を含む、記事をご覧ください[レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)、[レコード セット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)、および[レコード セット: の生成と破棄。レコード セット (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)です。  
  
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
 *wRow*  
 1 から始まる位置の行の現在の行セット。 この値の範囲は、行セットのサイズに 0 です。  
  
 *wLockType*  
 更新された後に行をロックする方法を示す値です。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>Remarks  
 ゼロの値を渡す場合*wRow*、行セット内のすべての行が更新されます。  
  
 使用する`RefreshRowset`、する必要がありますバルク行フェッチを実装を指定して、 **CRecordset::useMulitRowFetch**オプション、[開く](#open)メンバー関数。  
  
 `RefreshRowset` ODBC API 関数を呼び出す**SQLSetPos**です。 *WLockType*パラメーターを指定した後の行のロック状態**SQLSetPos**が実行されます。 次の表に、可能な値*wLockType*です。  
  
|wLockType|説明|  
|---------------|-----------------|  
|`SQL_LOCK_NO_CHANGE` (既定値)|ドライバーまたはデータ ソースにより、行が同じロックまたはロック解除状態で前に、と`RefreshRowset`が呼び出されました。|  
|`SQL_LOCK_EXCLUSIVE`|ドライバーまたはデータ ソースでは、行が排他的ロックします。 すべてのデータ ソースは、この種類のロックをサポートします。|  
|`SQL_LOCK_UNLOCK`|ドライバーまたはデータ ソースには、行がロック解除します。 すべてのデータ ソースは、この種類のロックをサポートします。|  
  
 詳細については**SQLSetPos**、Windows SDK を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
##  <a name="requery"></a>  :Requery  
 (更新) を再構築、レコード セット。  
  
```  
virtual BOOL Requery();
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットが正常に再構築された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 いくつかのレコードが返された場合、最初のレコードが現在のレコードになります。  
  
 レコード セットを反映して追加および削除するか、他のユーザーがデータ ソースに対して実行するためには、呼び出すことによってレコード セットをリビルドする必要があります`Requery`です。 レコード セットがダイナセットの場合は、または他のユーザーがその既存のレコード (ただし、追加機能ではない) を構成する更新プログラムを自動的に反映します。 レコード セットがスナップショットの場合は、呼び出す必要があります`Requery`編集内容を他のユーザーだけでなく追加および削除を反映するようにします。  
  
 ダイナセットまたはスナップショットのいずれかを呼び出す`Requery`いつでも新しいフィルターや並べ替え、または新しいパラメーター値を使用して、レコード セットを再構築します。 新しいフィルターまたは並べ替えプロパティを設定する新しい値を割り当てるを**か**と`m_strSort`呼び出す前に`Requery`です。 新しい値を呼び出す前にパラメーター データ メンバーに割り当てることによって新しいパラメーターの設定`Requery`です。 フィルターと並べ替え文字列が変更されていない場合は、パフォーマンスを向上させると、クエリが再利用できます。  
  
 レコード セットを再構築する試行が失敗した場合、レコード セットは閉じられます。 呼び出す前に`Requery`、呼び出すことによって、レコード セットを表示できるかどうかを決定できます、`CanRestart`メンバー関数。 `CanRestart` 限りませんを`Requery`は成功します。  
  
> [!CAUTION]
>  呼び出す`Requery`を呼び出した後にのみ[開く](#open)です。  
  
### <a name="example"></a>例  
 この例では、別の並べ替え順序を適用するレコード セットが再構築します。  
  
 [!code-cpp[NVC_MFCDatabase#29](../../mfc/codesnippet/cpp/crecordset-class_16.cpp)]  
  
##  <a name="setabsoluteposition"></a>  CRecordset::SetAbsolutePosition  
 指定されたレコード番号に対応するレコードのレコード セットを配置します。  
  
```  
void SetAbsolutePosition(long nRows);
```  
  
### <a name="parameters"></a>パラメーター  
 *nRows*  
 1 から始まる序数位置、現在のレコードのレコード セット。  
  
### <a name="remarks"></a>Remarks  
 `SetAbsolutePosition` この位置を表す序数に基づく現在のレコード ポインターを移動します。  
  
> [!NOTE]
>  このメンバー関数は前方スクロール専用レコードでは無効です。  
  
 ODBC レコード セットの絶対位置は 1 に設定は、レコード セットの最初のレコードを指します0 に設定は、ファイルの先頭 (BOF) の位置を指します。  
  
 負の値を渡すこともできます`SetAbsolutePosition`です。 ここでは、レコード セットの位置は、レコード セットの末尾から評価されます。 たとえば、`SetAbsolutePosition( -1 )`レコード セットの最後のレコードを現在のレコード ポインターを移動します。  
  
> [!NOTE]
>  絶対位置は、レコード番号の代わりとして使用するものではありません。 ブックマークは、まだ保持して、レコードの位置変更前のレコードが削除されたとき以降を指定された位置を返すための推奨される方法です。 さらに、することはできません確実に実行する場合は、レコード セットを再作成、を使用してSQLステートメントを使用して作成された場合を除き、レコードセット内の各レコードの順序が保証されないために、特定のレコードが同じ絶対位置を持つこと**ORDER BY**句。  
  
 レコード セットの移動とブックマークの詳細については、記事を参照してください。[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)と[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)です。  
  
##  <a name="setbookmark"></a>  CRecordset::SetBookmark  
 指定されたブックマークを含むレコードをレコード セットに配置します。  
  
```  
void SetBookmark(const CDBVariant& varBookmark);
```  
  
### <a name="parameters"></a>パラメーター  
 *varBookmark*  
 参照、 [CDBVariant](../../mfc/reference/cdbvariant-class.md)特定のレコードのブックマークの値を含むオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 調べるには、レコード セットで、ブックマークがサポートされているかどうか、呼び出す[調べる](#canbookmark)です。 ブックマークを使用できるようにサポートされている場合に設定する必要があります、 **crecordset::usebookmarks**オプション、 *dwOptions*のパラメーター、[開く](#open)メンバー関数。  
  
> [!NOTE]
>  ブックマークはサポートされていないか使用できない場合、呼び出す`SetBookmark`例外がスローされます。 順方向専用レコード セットでは、ブックマークはサポートされていません。  
  
 現在のレコードのブックマークを最初に取得するを呼び出す[GetBookmark](#getbookmark)、するブックマークの値を保存、`CDBVariant`オブジェクト。 呼び出してそのレコードを返すことができます、後で`SetBookmark`保存されているブックマークの値を使用します。  
  
> [!NOTE]
>  レコード セットの特定の操作後に、呼び出す前に、ブックマークの永続性をチェックする必要があります`SetBookmark`です。 持つブックマークを取得する場合など、`GetBookmark`およびを呼び出す`Requery`ブックマークは有効でなくなる可能性があります。 呼び出す[CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence)を安全に呼び出すことができるかどうかを確認する`SetBookmark`です。  
  
 ブックマークとレコード セットの移動の詳細については、記事を参照してください。[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)と[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)です。  
  
##  <a name="setfielddirty"></a>  CRecordset::SetFieldDirty  
 フィールド データ メンバーを変更なしまたは変更されると、レコード セットのフラグを設定します。  
  
```  
void SetFieldDirty(void* pv, BOOL bDirty = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *pv*  
 レコード セットのフィールド データ メンバーのアドレスを格納または**NULL**です。 場合**NULL**、レコード セット内のすべてのフィールド データ メンバーのフラグが付けられます。 (C++ **NULL**は Null の場合と同じデータベース用語では、「値を持たない」を意味する)。  
  
 *bDirty*  
 **TRUE**かどうか、フィールド データ メンバーは「ダーティ」(変更されている) としてマークされます。 それ以外の場合**FALSE**かどうか、フィールド データ メンバーは「クリーンアップ」(変更なし) としてフラグが付けられます。  
  
### <a name="remarks"></a>Remarks  
 フィールドを変更されないとしてマークすることにより、フィールドが更新されていないと、結果、SQL トラフィックも少なくて済みます。  
  
> [!NOTE]
>  このメンバー関数では、バルク行フェッチを使用しているレコード セットに適用されません。 実装した場合、バルク行フェッチし、`SetFieldDirty`アサーションは失敗が発生します。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
 フレームワークは、レコード フィールド エクス (チェンジ RFX) メカニズムによって、データ ソースのレコードに書き込まが確認するためのフィールド データ メンバーを変更します。 フィールドの値を変更すると、通常、フィールド ダーティは自動的に設定を呼び出すことはほとんどありません必要がありますので`SetFieldDirty`ユーザー自身が場合がありますようにすることも、列が明示的に更新または挿入するフィールドのデータでは、どのような値に関係なくメンバー。  
  
> [!CAUTION]
>  このメンバー関数を呼び出した後にのみ[編集](#edit)または[AddNew](#addnew)です。  
  
 使用して**NULL**関数の最初の引数が関数にのみ適用されますの**outputColumn**フィールドいない**param**フィールドです。 インスタンスの呼び出し  
  
 [!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 セットのみが**outputColumn**フィールドを**NULL**です。**param**フィールドには影響ありません。  
  
 作業する**param**フィールドで、個々 の実際のアドレスを指定する必要があります**param**など、作業します。  
  
 [!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 つまり、すべて設定することはできません**param**フィールドを**NULL**と同様、 **outputColumn**フィールドです。  
  
##  <a name="setfieldnull"></a>  CRecordset::SetFieldNull  
 レコード セットのフィールド データ メンバー (具体的には値を持たない) Null または null 以外のフラグを設定します。  
  
```  
void SetFieldNull(void* pv, BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *pv*  
 レコード セットのフィールド データ メンバーのアドレスを格納または**NULL**です。 場合**NULL**、レコード セット内のすべてのフィールド データ メンバーのフラグが付けられます。 (C++ **NULL**は Null の場合と同じデータベース用語では、「値を持たない」を意味する)。  
  
 *特別*  
 以外の場合は、フィールド データ メンバーが値 (Null) がないものとしてフラグが付けられます。 それ以外の場合は 0 場合は、フィールド データ メンバーは Null としてフラグが付けられます。  
  
### <a name="remarks"></a>Remarks  
 レコード セットに新しいレコードを追加するときにすべてのフィールド データ メンバーが最初に Null 値に設定され「ダーティ」(変更されている) フラグが付けられます。 データ ソースからレコードを取得するときにその列既に値があるかが Null です。  
  
> [!NOTE]
>  バルク行フェッチを使用しているレコード セットでこのメンバー関数を呼び出さないでください。 バルク行フェッチを実装した場合は、呼び出す`SetFieldNull`結果アサーションは失敗します。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
 具体的には呼び出し、値を持っていないと、現在のレコードのフィールドを指定する場合`SetFieldNull`で*特別*'éý' **TRUE**に Null としてフラグを設定します。 フィールドが以前に設定された場合 Null とするようになりましたする値を単にその新しい値を設定します。 Null フラグを削除する必要はありません`SetFieldNull`です。 フィールドが Null を指定できるかどうかを確認するのには、呼び出す`IsFieldNullable`です。  
  
> [!CAUTION]
>  このメンバー関数を呼び出した後にのみ[編集](#edit)または[AddNew](#addnew)です。  
  
 使用して**NULL**関数の最初の引数が関数にのみ適用されますの**outputColumn**フィールドいない**param**フィールドです。 インスタンスの呼び出し  
  
 [!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 セットのみが**outputColumn**フィールドを**NULL**です。**param**フィールドには影響ありません。  
  
 作業する**param**フィールドで、個々 の実際のアドレスを指定する必要があります**param**など、作業します。  
  
 [!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 つまり、すべて設定することはできません**param**フィールドを**NULL**と同様、 **outputColumn**フィールドです。  
  
> [!NOTE]
>  Null の場合への呼び出しにパラメーターを設定するときに`SetFieldNull`レコード セットが開かれている結果アサーションで前にします。 この例では、呼び出す[SetParamNull](#setparamnull)です。  
  
 `SetFieldNull` によって実装され[DoFieldExchange](#dofieldexchange)です。  
  
##  <a name="setlockingmode"></a>  CRecordset::SetLockingMode  
 ロック (既定)「オプティミスティック」または「ペシミスティック」をロックするロック モードを設定します。 更新プログラムのレコードをロックする方法を決定します。  
  
```  
void SetLockingMode(UINT nMode);
```  
  
### <a name="parameters"></a>パラメーター  
 *nMode*  
 次の値のいずれかが含まれています、 **enum LockMode**:  
  
- **オプティミスティック**ロックへの呼び出し中にのみ更新されるレコード`Update`です。  
  
- **ペシミスティック**レコードをロックして排他ロックとすぐに`Edit`が呼び出され、までロック状態に保ちます、`Update`呼び出しが完了するか、新しいレコードに移動します。  
  
### <a name="remarks"></a>Remarks  
 レコード セットが更新プログラムを使用して、2 つのレコードのロック方法を指定する必要がある場合は、このメンバー関数を呼び出します。 レコード セットのロック モードは、既定では、**オプティミスティック**です。 慎重に変更することできます**ペシミスティック**戦略をロックします。 呼び出す`SetLockingMode`を呼び出す前に、構築して、レコード セット オブジェクトを開いた後`Edit`です。  
  
##  <a name="setparamnull"></a>  CRecordset::SetParamNull  
 (具体的には値を持たない) Null または null 以外のパラメーターのフラグを設定します。  
  
```  
void SetParamNull(
    int nIndex,  
    BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 パラメーターの 0 から始まるインデックス。  
  
 *特別*  
 場合**TRUE** (既定値) の場合は、パラメーターが Null としてフラグが付けられます。 それ以外の場合、パラメーターは Null としてフラグが設定されます。  
  
### <a name="remarks"></a>Remarks  
 異なり[な](#setfieldnull)、呼び出すことができます`SetParamNull`レコード セットを開く前にします。  
  
 `SetParamNull` 通常、定義済みクエリ (ストアド プロシージャ) と一緒に使用します。  
  
##  <a name="setrowsetcursorposition"></a>  CRecordset::SetRowsetCursorPosition  
 現在の行セット内の行にカーソルを移動します。  
  
```  
void SetRowsetCursorPosition(WORD wRow, WORD wLockType = SQL_LOCK_NO_CHANGE);
```  
  
### <a name="parameters"></a>パラメーター  
 *wRow*  
 1 から始まる位置の行の現在の行セット。 この値の範囲は 1、行セットのサイズにします。  
  
 *wLockType*  
 更新された後に行をロックする方法を示す値です。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>Remarks  
 バルク行フェッチを実装する場合は、レコードが現在のレコードをフェッチした行セットの最初のレコードがここでは、行セットによって取得されます。 行セット内の別のレコードを現在のレコードにするには、するために呼び出す`SetRowsetCursorPosition`です。 たとえば、結合`SetRowsetCursorPosition`で、 [GetFieldValue](#getfieldvalue)レコード セットの任意のレコードからデータを動的に取得するメンバー関数。  
  
 使用する`SetRowsetCursorPosition`、する必要がありますバルク行フェッチを実装を指定して、`CRecordset::useMultiRowFetch`のオプション、 *dwOptions*内のパラメーター、[開く](#open)メンバー関数。  
  
 `SetRowsetCursorPosition` ODBC API 関数を呼び出す**SQLSetPos**です。 *WLockType*パラメーターを指定した後の行のロック状態**SQLSetPos**が実行されます。 次の表に、可能な値*wLockType*です。  
  
|wLockType|説明|  
|---------------|-----------------|  
|`SQL_LOCK_NO_CHANGE` (既定値)|ドライバーまたはデータ ソースにより、行が同じロックまたはロック解除状態で前に、と`SetRowsetCursorPosition`が呼び出されました。|  
|`SQL_LOCK_EXCLUSIVE`|ドライバーまたはデータ ソースでは、行が排他的ロックします。 すべてのデータ ソースは、この種類のロックをサポートします。|  
|`SQL_LOCK_UNLOCK`|ドライバーまたはデータ ソースには、行がロック解除します。 すべてのデータ ソースは、この種類のロックをサポートします。|  
  
 詳細については**SQLSetPos**、Windows SDK を参照してください。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
##  <a name="setrowsetsize"></a>  CRecordset::SetRowsetSize  
 フェッチ中に取得するレコードの数を指定します。  
  
```  
virtual void SetRowsetSize(DWORD dwNewRowsetSize);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwNewRowsetSize*  
 回のフェッチ中に取得する行の数。  
  
### <a name="remarks"></a>Remarks  
 この仮想メンバー関数は、バルク行フェッチを使用する場合は、1 回のフェッチ中に取得する行の数を指定します。 バルク行フェッチを実装するのに設定する必要があります、`CRecordset::useMultiRowFetch`オプション、 *dwOptions*のパラメーター、[開く](#open)メンバー関数。  
  
> [!NOTE]
>  呼び出す`SetRowsetSize`一括を実装することがなく、失敗したアサーションの行フェッチが発生します。  
  
 呼び出す`SetRowsetSize`呼び出す前に`Open`を最初に、レコード セットの行セットのサイズを設定します。 バルク行フェッチを実装する場合は、既定行セットのサイズは 25 です。  
  
> [!NOTE]
>  呼び出すときに警告を使用して`SetRowsetSize`です。 場合は、データの記憶域を手動で割り当てている場合 (指定に従って、 **crecordset::userallocmultirowbuffers** dwOptions のパラメーターのオプション`Open`)、これらの記憶域を再割り当てが必要かどうかを確認する必要があります呼び出した後のバッファー`SetRowsetSize`カーソルのナビゲーション操作を実行する前にします。  
  
 行セットのサイズの現在の設定を取得する呼び出し[GetRowsetSize](#getrowsetsize)です。  
  
 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
##  <a name="update"></a>  CRecordset::Update  
 完了、`AddNew`または`Edit`データ ソースで新しいまたは更新されたデータを保存することで操作します。  
  
```  
virtual BOOL Update();
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は 1 つのレコードが正常に更新されました。列が変更されていない場合それ以外の場合 0 を返します。 レコードが更新されない、または 1 つのレコードが更新された数より多い場合、例外がスローされます。 例外は、データ ソース上の他のエラーもスローされます。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数を呼び出した後、 [AddNew](#addnew)または[編集](#edit)メンバー関数。 この呼び出しが完了するために必要な`AddNew`または`Edit`操作します。  
  
> [!NOTE]
>  バルク行フェッチを実装した場合を呼び出すことはできません`Update`です。 これにより、失敗したアサーションが発生します。 クラス`CRecordset`メカニズムが用意されていないデータの一括行を更新するには、ODBC API 関数を使用して、独自の関数を記述することができます**SQLSetPos**です。 バルク行フェッチの詳細については、「 [レコードセット: バルク行フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。  
  
 両方`AddNew`と`Edit`データ ソースに保存するため、追加または編集されたデータが置かれている編集バッファーを準備します。 `Update` データを保存します。 マークまたは変更されたものとして検出されたフィールドのみ更新されます。  
  
 データ ソースは、トランザクションをサポートする場合は、`Update`呼び出し (とその対応する`AddNew`または`Edit`呼び出し)、トランザクションの一部です。 トランザクションの詳細については、記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)です。  
  
> [!CAUTION]
>  呼び出す場合`Update`最初に呼び出して、`AddNew`または`Edit`、`Update`スロー、`CDBException`です。 呼び出す場合`AddNew`または`Edit`、呼び出す必要があります`Update`を呼び出す前に、`Move`操作、またはレコード セットまたはデータ ソース接続を閉じる前にします。 それ以外の場合、変更は、通知することがなく失われます。  
  
 処理の詳細`Update`の障害は、記事を参照して[レコード セット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)です。  
  
### <a name="example"></a>例  
 記事を参照して[トランザクション: レコード セット (ODBC) でのトランザクションを実行する](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDatabase クラス](../../mfc/reference/cdatabase-class.md)   
 [CRecordView クラス](../../mfc/reference/crecordview-class.md)
