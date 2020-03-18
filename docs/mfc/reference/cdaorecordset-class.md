---
title: CDaoRecordset クラス
ms.date: 08/27/2018
f1_keywords:
- CDaoRecordset
- AFXDAO/CDaoRecordset
- AFXDAO/CDaoRecordset::CDaoRecordset
- AFXDAO/CDaoRecordset::AddNew
- AFXDAO/CDaoRecordset::CanAppend
- AFXDAO/CDaoRecordset::CanBookmark
- AFXDAO/CDaoRecordset::CancelUpdate
- AFXDAO/CDaoRecordset::CanRestart
- AFXDAO/CDaoRecordset::CanScroll
- AFXDAO/CDaoRecordset::CanTransact
- AFXDAO/CDaoRecordset::CanUpdate
- AFXDAO/CDaoRecordset::Close
- AFXDAO/CDaoRecordset::Delete
- AFXDAO/CDaoRecordset::DoFieldExchange
- AFXDAO/CDaoRecordset::Edit
- AFXDAO/CDaoRecordset::FillCache
- AFXDAO/CDaoRecordset::Find
- AFXDAO/CDaoRecordset::FindFirst
- AFXDAO/CDaoRecordset::FindLast
- AFXDAO/CDaoRecordset::FindNext
- AFXDAO/CDaoRecordset::FindPrev
- AFXDAO/CDaoRecordset::GetAbsolutePosition
- AFXDAO/CDaoRecordset::GetBookmark
- AFXDAO/CDaoRecordset::GetCacheSize
- AFXDAO/CDaoRecordset::GetCacheStart
- AFXDAO/CDaoRecordset::GetCurrentIndex
- AFXDAO/CDaoRecordset::GetDateCreated
- AFXDAO/CDaoRecordset::GetDateLastUpdated
- AFXDAO/CDaoRecordset::GetDefaultDBName
- AFXDAO/CDaoRecordset::GetDefaultSQL
- AFXDAO/CDaoRecordset::GetEditMode
- AFXDAO/CDaoRecordset::GetFieldCount
- AFXDAO/CDaoRecordset::GetFieldInfo
- AFXDAO/CDaoRecordset::GetFieldValue
- AFXDAO/CDaoRecordset::GetIndexCount
- AFXDAO/CDaoRecordset::GetIndexInfo
- AFXDAO/CDaoRecordset::GetLastModifiedBookmark
- AFXDAO/CDaoRecordset::GetLockingMode
- AFXDAO/CDaoRecordset::GetName
- AFXDAO/CDaoRecordset::GetParamValue
- AFXDAO/CDaoRecordset::GetPercentPosition
- AFXDAO/CDaoRecordset::GetRecordCount
- AFXDAO/CDaoRecordset::GetSQL
- AFXDAO/CDaoRecordset::GetType
- AFXDAO/CDaoRecordset::GetValidationRule
- AFXDAO/CDaoRecordset::GetValidationText
- AFXDAO/CDaoRecordset::IsBOF
- AFXDAO/CDaoRecordset::IsDeleted
- AFXDAO/CDaoRecordset::IsEOF
- AFXDAO/CDaoRecordset::IsFieldDirty
- AFXDAO/CDaoRecordset::IsFieldNull
- AFXDAO/CDaoRecordset::IsFieldNullable
- AFXDAO/CDaoRecordset::IsOpen
- AFXDAO/CDaoRecordset::Move
- AFXDAO/CDaoRecordset::MoveFirst
- AFXDAO/CDaoRecordset::MoveLast
- AFXDAO/CDaoRecordset::MoveNext
- AFXDAO/CDaoRecordset::MovePrev
- AFXDAO/CDaoRecordset::Open
- AFXDAO/CDaoRecordset::Requery
- AFXDAO/CDaoRecordset::Seek
- AFXDAO/CDaoRecordset::SetAbsolutePosition
- AFXDAO/CDaoRecordset::SetBookmark
- AFXDAO/CDaoRecordset::SetCacheSize
- AFXDAO/CDaoRecordset::SetCacheStart
- AFXDAO/CDaoRecordset::SetCurrentIndex
- AFXDAO/CDaoRecordset::SetFieldDirty
- AFXDAO/CDaoRecordset::SetFieldNull
- AFXDAO/CDaoRecordset::SetFieldValue
- AFXDAO/CDaoRecordset::SetFieldValueNull
- AFXDAO/CDaoRecordset::SetLockingMode
- AFXDAO/CDaoRecordset::SetParamValue
- AFXDAO/CDaoRecordset::SetParamValueNull
- AFXDAO/CDaoRecordset::SetPercentPosition
- AFXDAO/CDaoRecordset::Update
- AFXDAO/CDaoRecordset::m_bCheckCacheForDirtyFields
- AFXDAO/CDaoRecordset::m_nFields
- AFXDAO/CDaoRecordset::m_nParams
- AFXDAO/CDaoRecordset::m_pDAORecordset
- AFXDAO/CDaoRecordset::m_pDatabase
- AFXDAO/CDaoRecordset::m_strFilter
- AFXDAO/CDaoRecordset::m_strSort
helpviewer_keywords:
- CDaoRecordset [MFC], CDaoRecordset
- CDaoRecordset [MFC], AddNew
- CDaoRecordset [MFC], CanAppend
- CDaoRecordset [MFC], CanBookmark
- CDaoRecordset [MFC], CancelUpdate
- CDaoRecordset [MFC], CanRestart
- CDaoRecordset [MFC], CanScroll
- CDaoRecordset [MFC], CanTransact
- CDaoRecordset [MFC], CanUpdate
- CDaoRecordset [MFC], Close
- CDaoRecordset [MFC], Delete
- CDaoRecordset [MFC], DoFieldExchange
- CDaoRecordset [MFC], Edit
- CDaoRecordset [MFC], FillCache
- CDaoRecordset [MFC], Find
- CDaoRecordset [MFC], FindFirst
- CDaoRecordset [MFC], FindLast
- CDaoRecordset [MFC], FindNext
- CDaoRecordset [MFC], FindPrev
- CDaoRecordset [MFC], GetAbsolutePosition
- CDaoRecordset [MFC], GetBookmark
- CDaoRecordset [MFC], GetCacheSize
- CDaoRecordset [MFC], GetCacheStart
- CDaoRecordset [MFC], GetCurrentIndex
- CDaoRecordset [MFC], GetDateCreated
- CDaoRecordset [MFC], GetDateLastUpdated
- CDaoRecordset [MFC], GetDefaultDBName
- CDaoRecordset [MFC], GetDefaultSQL
- CDaoRecordset [MFC], GetEditMode
- CDaoRecordset [MFC], GetFieldCount
- CDaoRecordset [MFC], GetFieldInfo
- CDaoRecordset [MFC], GetFieldValue
- CDaoRecordset [MFC], GetIndexCount
- CDaoRecordset [MFC], GetIndexInfo
- CDaoRecordset [MFC], GetLastModifiedBookmark
- CDaoRecordset [MFC], GetLockingMode
- CDaoRecordset [MFC], GetName
- CDaoRecordset [MFC], GetParamValue
- CDaoRecordset [MFC], GetPercentPosition
- CDaoRecordset [MFC], GetRecordCount
- CDaoRecordset [MFC], GetSQL
- CDaoRecordset [MFC], GetType
- CDaoRecordset [MFC], GetValidationRule
- CDaoRecordset [MFC], GetValidationText
- CDaoRecordset [MFC], IsBOF
- CDaoRecordset [MFC], IsDeleted
- CDaoRecordset [MFC], IsEOF
- CDaoRecordset [MFC], IsFieldDirty
- CDaoRecordset [MFC], IsFieldNull
- CDaoRecordset [MFC], IsFieldNullable
- CDaoRecordset [MFC], IsOpen
- CDaoRecordset [MFC], Move
- CDaoRecordset [MFC], MoveFirst
- CDaoRecordset [MFC], MoveLast
- CDaoRecordset [MFC], MoveNext
- CDaoRecordset [MFC], MovePrev
- CDaoRecordset [MFC], Open
- CDaoRecordset [MFC], Requery
- CDaoRecordset [MFC], Seek
- CDaoRecordset [MFC], SetAbsolutePosition
- CDaoRecordset [MFC], SetBookmark
- CDaoRecordset [MFC], SetCacheSize
- CDaoRecordset [MFC], SetCacheStart
- CDaoRecordset [MFC], SetCurrentIndex
- CDaoRecordset [MFC], SetFieldDirty
- CDaoRecordset [MFC], SetFieldNull
- CDaoRecordset [MFC], SetFieldValue
- CDaoRecordset [MFC], SetFieldValueNull
- CDaoRecordset [MFC], SetLockingMode
- CDaoRecordset [MFC], SetParamValue
- CDaoRecordset [MFC], SetParamValueNull
- CDaoRecordset [MFC], SetPercentPosition
- CDaoRecordset [MFC], Update
- CDaoRecordset [MFC], m_bCheckCacheForDirtyFields
- CDaoRecordset [MFC], m_nFields
- CDaoRecordset [MFC], m_nParams
- CDaoRecordset [MFC], m_pDAORecordset
- CDaoRecordset [MFC], m_pDatabase
- CDaoRecordset [MFC], m_strFilter
- CDaoRecordset [MFC], m_strSort
ms.assetid: 2322067f-1027-4662-a5d7-aa2fc7488630
ms.openlocfilehash: 96118645aa656e97fcb93a0fd223045208ab03a3
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424537"
---
# <a name="cdaorecordset-class"></a>CDaoRecordset クラス

データ ソースから選択された 1 組のレコードセットを表現します。

## <a name="syntax"></a>構文

```
class CDaoRecordset : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|Description|
|----------|-----------------|
|[CDaoRecordset:: CDaoRecordset](#cdaorecordset)|`CDaoRecordset` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[CDaoRecordset:: AddNew](#addnew)|新しいレコードを追加するための準備をします。 [Update](#update)を呼び出して、追加を完了します。|
|[CDaoRecordset:: CanAppend](#canappend)|[AddNew](#addnew)メンバー関数を使用してレコードセットに新しいレコードを追加できる場合は、0以外の値を返します。|
|[CDaoRecordset:: CanBookmark](#canbookmark)|レコードセットがブックマークをサポートしている場合は0以外の値を返します。|
|[CDaoRecordset:: CancelUpdate](#cancelupdate)|[編集](#edit)または[AddNew](#addnew)操作によって保留中の更新をキャンセルします。|
|[CDaoRecordset:: CanRestart](#canrestart)|[Requery](#requery)を呼び出してレコードセットのクエリを再実行できる場合は、0以外の値を返します。|
|[CDaoRecordset:: CanScroll](#canscroll)|レコードをスクロールできる場合は0以外の値を返します。|
|[CDaoRecordset:: CanTransact](#cantransact)|データソースがトランザクションをサポートしている場合は0以外の値を返します。|
|[CDaoRecordset:: CanUpdate](#canupdate)|レコードセットを更新できる場合は0以外の値を返します (レコードを追加、更新、または削除できます)。|
|[CDaoRecordset:: Close](#close)|レコードセットを閉じます。|
|[CDaoRecordset::D e)](#delete)|レコードセットから現在のレコードを削除します。 削除後は、明示的に別のレコードにスクロールする必要があります。|
|[CDaoRecordset::D oFieldExchange](#dofieldexchange)|レコードセットのフィールドデータメンバーとデータソースの対応するレコードとの間で、双方向のデータ交換を行うために呼び出されます。 DAO レコードフィールドエクスチェンジ (DFX) を実装します。|
|[CDaoRecordset:: Edit](#edit)|現在のレコードへの変更を準備します。 `Update` を呼び出して、編集を完了します。|
|[CDaoRecordset:: FillCache](#fillcache)|ODBC データソースのデータを含むレコードセットオブジェクトのすべてまたは一部をローカルキャッシュに格納します。|
|[CDaoRecordset:: Find](#find)|指定された条件を満たす、ダイナセット型のレコードセット内の特定の文字列の最初、次、前、または最後の位置を検索し、そのレコードを現在のレコードにします。|
|[CDaoRecordset:: FindFirst](#findfirst)|指定された条件を満たす、ダイナセット型またはスナップショット型のレコードセット内の最初のレコードを検索し、そのレコードを現在のレコードにします。|
|[CDaoRecordset:: FindLast](#findlast)|指定された条件を満たす、ダイナセット型またはスナップショット型のレコードセット内の最後のレコードを検索し、そのレコードを現在のレコードにします。|
|[CDaoRecordset:: FindNext](#findnext)|指定された条件を満たす、ダイナセット型またはスナップショット型のレコードセット内の次のレコードを検索し、そのレコードを現在のレコードにします。|
|[CDaoRecordset:: FindPrev](#findprev)|指定された条件を満たす、ダイナセット型またはスナップショット型のレコードセット内の前のレコードを検索し、そのレコードを現在のレコードにします。|
|[CDaoRecordset:: GetAbsolutePosition](#getabsoluteposition)|レコードセットオブジェクトの現在のレコードのレコード番号を返します。|
|[CDaoRecordset:: GetBookmark](#getbookmark)|レコードのブックマークを表す値を返します。|
|[CDaoRecordset:: GetCacheSize](#getcachesize)|ODBC データソースからローカルにキャッシュされるデータを含む、ダイナセット型のレコードセット内のレコードの数を示す値を返します。|
|[CDaoRecordset:: GetCacheStart](#getcachestart)|キャッシュされるレコードセット内の最初のレコードのブックマークを示す値を返します。|
|[CDaoRecordset:: GetCurrentIndex](#getcurrentindex)|インデックス付きのテーブル型 `CDaoRecordset`で最近使用されたインデックスの名前を含む `CString` を返します。|
|[CDaoRecordset:: GetDateCreated](#getdatecreated)|`CDaoRecordset` オブジェクトの基になるベーステーブルが作成された日付と時刻を返します。|
|[CDaoRecordset:: GetDateLastUpdated](#getdatelastupdated)|`CDaoRecordset` オブジェクトの基になるベーステーブルのデザインに対して行われた最新の変更の日付と時刻を返します。|
|[CDaoRecordset:: GetDefaultDBName](#getdefaultdbname)|既定のデータソースの名前を返します。|
|[CDaoRecordset:: GetDefaultSQL](#getdefaultsql)|実行する既定の SQL 文字列を取得するために呼び出されます。|
|[CDaoRecordset:: GetEditMode](#geteditmode)|現在のレコードの編集の状態を示す値を返します。|
|[CDaoRecordset:: GetFieldCount](#getfieldcount)|レコードセット内のフィールドの数を表す値を返します。|
|[CDaoRecordset:: GetFieldInfo](#getfieldinfo)|レコードセット内のフィールドに関する特定の種類の情報を返します。|
|[CDaoRecordset:: GetFieldValue](#getfieldvalue)|レコードセット内のフィールドの値を返します。|
|[CDaoRecordset:: GetIndexCount](#getindexcount)|レコードセットの基になるテーブル内のインデックスの数を取得します。|
|[CDaoRecordset:: GetIndexInfo](#getindexinfo)|インデックスに関するさまざまな種類の情報を返します。|
|[CDaoRecordset:: GetLastModifiedBookmark](#getlastmodifiedbookmark)|最近追加または更新されたレコードを特定するために使用します。|
|[CDaoRecordset:: Getロックモード](#getlockingmode)|編集中に有効なロックの種類を示す値を返します。|
|[CDaoRecordset:: GetName](#getname)|レコードセットの名前を含む `CString` を返します。|
|[CDaoRecordset:: GetParamValue](#getparamvalue)|基になる DAOParameter オブジェクトに格納されている、指定したパラメーターの現在の値を取得します。|
|[CDaoRecordset:: GetPercentPosition](#getpercentposition)|現在のレコードの位置を、レコードの合計数に対する割合として返します。|
|[CDaoRecordset:: GetRecordCount](#getrecordcount)|レコードセットオブジェクト内でアクセスされたレコードの数を返します。|
|[CDaoRecordset:: GetSQL](#getsql)|レコードセットのレコードを選択するために使用する SQL 文字列を取得します。|
|[CDaoRecordset:: GetType](#gettype)|レコードセットの型 (テーブル型、ダイナセット型、またはスナップショット型) を決定するために呼び出されます。|
|[CDaoRecordset:: GetValidationRule](#getvalidationrule)|フィールドに入力されたデータを検証する値を含む `CString` を返します。|
|[CDaoRecordset:: GetValidationText](#getvalidationtext)|検証規則が満たされていない場合に表示されるテキストを取得します。|
|[CDaoRecordset:: IsBOF](#isbof)|レコードセットが最初のレコードの前に配置されている場合は、0以外の値を返します。 現在のレコードがありません。|
|[CDaoRecordset:: IsDeleted](#isdeleted)|レコードセットが削除されたレコードに配置されている場合は、0以外の値を返します。|
|[CDaoRecordset:: IsEOF](#iseof)|レコードセットが最後のレコードの後に配置されている場合は0以外の値を返します。 現在のレコードがありません。|
|[CDaoRecordset:: IsFieldDirty](#isfielddirty)|現在のレコード内の指定されたフィールドが変更されている場合は、0以外の値を返します。|
|[CDaoRecordset:: IsFieldNull](#isfieldnull)|現在のレコード内の指定されたフィールドが Null である (値がない) 場合は、0以外の値を返します。|
|[CDaoRecordset:: IsFieldNullable](#isfieldnullable)|現在のレコード内の指定されたフィールドを Null に設定できる場合 (値がない場合) は0以外の値を返します。|
|[CDaoRecordset:: IsOpen](#isopen)|[Open](#open)が既に呼び出されている場合は0以外の値を返します。|
|[CDaoRecordset:: Move](#move)|現在のレコードから指定された数のレコードに、いずれかの方向でレコードセットを配置します。|
|[CDaoRecordset:: MoveFirst](#movefirst)|レコードセット内の最初のレコードに現在のレコードを配置します。|
|[CDaoRecordset:: MoveLast](#movelast)|レコードセットの最後のレコードに現在のレコードを配置します。|
|[CDaoRecordset:: MoveNext](#movenext)|レコードセット内の次のレコードに現在のレコードを配置します。|
|[CDaoRecordset:: MovePrev](#moveprev)|レコードセット内の前のレコードの現在のレコードを配置します。|
|[CDaoRecordset:: Open](#open)|テーブル、ダイナセット、またはスナップショットから新しいレコードセットを作成します。|
|[CDaoRecordset:: Requery](#requery)|レコードセットのクエリを再実行して、選択したレコードを更新します。|
|[CDaoRecordset:: Seek](#seek)|現在のインデックスに対して指定された条件を満たす、インデックス付きテーブル型のレコードセットオブジェクト内のレコードを検索し、そのレコードを現在のレコードにします。|
|[CDaoRecordset:: SetAbsolutePosition](#setabsoluteposition)|レコードセットオブジェクトの現在のレコードのレコード番号を設定します。|
|[CDaoRecordset:: SetBookmark](#setbookmark)|指定されたブックマークを含むレコードにレコードセットを配置します。|
|[CDaoRecordset:: SetCacheSize](#setcachesize)|ODBC データソースからローカルにキャッシュされるデータを含む、ダイナセット型のレコードセット内のレコードの数を指定する値を設定します。|
|[CDaoRecordset:: SetCacheStart](#setcachestart)|キャッシュされるレコードセット内の最初のレコードのブックマークを指定する値を設定します。|
|[CDaoRecordset:: SetCurrentIndex](#setcurrentindex)|テーブル型のレコードセットにインデックスを設定するために呼び出されます。|
|[CDaoRecordset:: SetFieldDirty](#setfielddirty)|現在のレコード内の指定されたフィールドを変更済みとしてマークします。|
|[CDaoRecordset:: SetFieldNull](#setfieldnull)|現在のレコード内の指定されたフィールドの値を Null に設定します (値はありません)。|
|[CDaoRecordset:: SetFieldValue](#setfieldvalue)|レコードセット内のフィールドの値を設定します。|
|[CDaoRecordset:: SetFieldValueNull](#setfieldvaluenull)|レコードセットのフィールドの値を Null に設定します。 (値がありません)。|
|[CDaoRecordset:: Setロックモード](#setlockingmode)|編集中に適用されるロックの種類を示す値を設定します。|
|[CDaoRecordset:: SetParamValue](#setparamvalue)|基になる DAOParameter オブジェクトに格納されている、指定したパラメーターの現在の値を設定します。|
|[CDaoRecordset:: SetParamValueNull](#setparamvaluenull)|指定されたパラメーターの現在の値を Null に設定します (値はありません)。|
|[CDaoRecordset:: SetPercentPosition](#setpercentposition)|現在のレコードの位置を、レコードセット内のレコードの合計数に対する割合に対応する位置に設定します。|
|[CDaoRecordset:: Update](#update)|新しいデータまたは編集されたデータをデータソースに保存することにより、`AddNew` または `Edit` 操作を完了します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|Name|Description|
|----------|-----------------|
|[CDaoRecordset:: m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)|フィールドが自動的に変更済みとしてマークされているかどうかを示すフラグが含まれています。|
|[CDaoRecordset:: m_nFields](#m_nfields)|レコードセットクラスのフィールドデータメンバーの数と、データソースからレコードセットによって選択された列の数を格納します。|
|[CDaoRecordset:: m_nParams](#m_nparams)|レコードセットクラスのパラメーターデータメンバーの数 (レコードセットのクエリで渡されるパラメーターの数) を格納します。|
|[CDaoRecordset:: m_pDAORecordset](#m_pdaorecordset)|レコードセットオブジェクトの基になる DAO インターフェイスへのポインター。|
|[CDaoRecordset:: m_pDatabase](#m_pdatabase)|この結果セットのソースデータベース。 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトへのポインターが含まれています。|
|[CDaoRecordset:: m_strFilter](#m_strfilter)|SQL **WHERE**ステートメントの作成に使用する文字列が含まれています。|
|[CDaoRecordset:: m_strSort](#m_strsort)|SQL **ORDER BY**ステートメントを構築するために使用する文字列が含まれています。|

## <a name="remarks"></a>解説

"レコードセット" と呼ばれる `CDaoRecordset` オブジェクトは、次の3つの形式で使用できます。

- テーブル型のレコードセットは、1つのデータベーステーブルのレコードを確認、追加、変更、または削除するために使用できるベーステーブルを表します。

- ダイナセット型のレコードセットは、更新可能なレコードを持つことができるクエリの結果です。 これらのレコードセットは、基になるデータベーステーブルまたはテーブルのレコードを確認、追加、変更、または削除するために使用できる一連のレコードです。 ダイナセット型のレコードセットには、データベース内の1つ以上のテーブルのフィールドを含めることができます。

- スナップショット型のレコードセットは、データの検索やレポートの生成に使用できる一連のレコードの静的なコピーです。 これらのレコードセットには、データベース内の1つ以上のテーブルのフィールドを含めることができますが、更新することはできません。

レコードセットの各形式は、レコードセットが開かれたときに固定されたレコードのセットを表します。 テーブル型のレコードセットまたはダイナセットタイプのレコードセット内のレコードにスクロールすると、他のユーザーまたはアプリケーション内の他のレコードセットによってレコードセットが開かれた後に、レコードに加えられた変更が反映されます。 (スナップショットの種類のレコードセットを更新することはできません)。`CDaoRecordset` を直接使用することも、`CDaoRecordset`からアプリケーション固有のレコードセットクラスを派生させることもできます。 この場合は、次のいずれかの操作を行うことができます。

- レコードをスクロールします。

- [シーク](#seek)を使用してインデックスを設定し、レコードをすばやく検索します (テーブル型のレコードセットのみ)。

- 文字列比較に基づいてレコードを検索します。 "<"、"\<="、"="、"> ="、または ">" (ダイナセット型およびスナップショット型のレコードセット)。

- レコードを更新し、ロックモードを指定します (スナップショットの種類のレコードセットを除く)。

- レコードセットをフィルター処理して、データソースで使用できるレコードのうち、どれを選択するかを制限します。

- レコードセットを並べ替えます。

- レコードセットをパラメーター化して、実行時まで知られていない情報で選択をカスタマイズします。

クラス `CDaoRecordset` には、クラス `CRecordset`と同様のインターフェイスが用意されています。 主な違いは、クラス `CDaoRecordset` は OLE に基づくデータアクセスオブジェクト (DAO) を介してデータにアクセスすることです。 クラス `CRecordset` は、Open Database Connectivity (ODBC) とその DBMS の ODBC ドライバーを使用して DBMS にアクセスします。

> [!NOTE]
> DAO データベースクラスは、Open Database Connectivity (ODBC) に基づく MFC データベースクラスとは異なります。 すべての DAO データベースクラス名には、"CDao" プレフィックスが付いています。 DAO クラスを使用して ODBC データソースにアクセスすることもできます。DAO クラスは、一般に、Microsoft Jet データベースエンジンに固有のものであるため、優れた機能を提供します。

`CDaoRecordset` を直接使用することも、`CDaoRecordset`からクラスを派生させることもできます。 どちらの場合でもレコードセットクラスを使用するには、データベースを開き、レコードセットオブジェクトを構築して、コンストラクターに `CDaoDatabase` オブジェクトへのポインターを渡します。 また、`CDaoRecordset` オブジェクトを構築して、MFC が一時的な `CDaoDatabase` オブジェクトを作成できるようにすることもできます。 次に、レコードセットの[Open](#open)メンバー関数を呼び出して、オブジェクトがテーブル型のレコードセットであるか、ダイナセット型のレコードセットであるか、またはスナップショットの種類のレコードセットであるかを指定します。 `Open` を呼び出すと、データベースからデータが選択され、最初のレコードが取得されます。

レコードをスクロールして操作するには、オブジェクトのメンバー関数とデータメンバーを使用します。 使用できる操作は、オブジェクトがテーブル型のレコードセットであるか、ダイナセット型のレコードセットであるか、またはスナップショットの種類のレコードセットであるか、および更新可能か読み取り専用かによって異なります。これは、データベースまたは Open Database Connectivity (ODBC) の機能に依存します。データソース。 `Open` の呼び出し以降に変更または追加された可能性があるレコードを更新するには、オブジェクトの[Requery](#requery)メンバー関数を呼び出します。 オブジェクトの `Close` メンバー関数を呼び出し、終了時にオブジェクトを破棄します。

`CDaoRecordset` は、DAO レコードフィールドエクスチェンジ (DFX) を使用して、`CDaoRecordset` または `CDaoRecordset`派生クラスC++のタイプセーフなメンバーによるレコードフィールドの読み取りと更新をサポートします。 また、 [GetFieldValue](#getfieldvalue)と[SetFieldValue](#setfieldvalue)を使用する DFX 機構を使用せずに、データベース内の列の動的バインドを実装することもできます。

関連情報については、DAO ヘルプの「レコードセットオブジェクト」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CDaoRecordset`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdao

##  <a name="addnew"></a>CDaoRecordset:: AddNew

テーブル型またはダイナセット型のレコードセットに新しいレコードを追加するには、このメンバー関数を呼び出します。

```
virtual void AddNew();
```

### <a name="remarks"></a>解説

レコードのフィールドは、最初は Null になります。 (データベース用語では、Null は "値がありません" を意味し、でC++は null と同じではありません)。操作を完了するには、 [Update](#update)メンバー関数を呼び出す必要があります。 `Update` によって、データソースへの変更が保存されます。

> [!CAUTION]
>  レコードを編集してから `Update`を呼び出さずに別のレコードにスクロールすると、警告が表示されずに変更内容が失われます。

[AddNew](#addnew)を呼び出して、ダイナセット型のレコードセットにレコードを追加すると、レコードはレコードセットに表示され、基になるテーブルに含まれ、新しい `CDaoRecordset` オブジェクトから参照できるようになります。

新しいレコードの位置は、レコードセットの種類によって異なります。

- 新しいレコードが挿入される場合、ダイナセット型のレコードセットでは保証されません。 この動作は、パフォーマンスと同時実行の理由により、Microsoft Jet 3.0 で変更されました。 新しく追加されたレコードを現在のレコードにすることが目的である場合は、最後に変更されたレコードのブックマークを取得し、そのブックマークに移動します。

[!code-cpp[NVC_MFCDatabase#1](../../mfc/codesnippet/cpp/cdaorecordset-class_1.cpp)]

- インデックスが指定されているテーブル型のレコードセットでは、レコードが並べ替え順序において適切な場所に返されます。 インデックスが指定されていない場合は、レコードセットの末尾に新しいレコードが返されます。

`AddNew` を使用する前に最新だったレコードは、現在のままです。 新しいレコードを現在作成し、レコードセットがブックマークをサポートする場合は、基になる DAO レコードセットオブジェクトの LastModified プロパティ設定で識別されるブックマークに[SetBookmark](#setbookmark)を呼び出します。 これは、追加されたレコードの counter (自動インクリメント) フィールドの値を判断するのに役立ちます。 詳細については、「 [GetLastModifiedBookmark](#getlastmodifiedbookmark)」を参照してください。

データベースでトランザクションがサポートされている場合は、`AddNew` トランザクションの一部を呼び出すことができます。 トランザクションの詳細については、「クラス[CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)」を参照してください。 `AddNew`を呼び出す前に、 [CDaoWorkspace:: BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans)を呼び出す必要があることに注意してください。

[Open](#open)メンバー関数が呼び出されていないレコードセットに対して `AddNew` を呼び出すことはできません。 追加できないレコードセットに対して `AddNew` を呼び出すと `CDaoException` がスローされます。 [CanAppend](#canappend)を呼び出すことで、レコードセットが更新可能かどうかを判断できます。

フレームワークは、変更されたフィールドデータメンバーを、DAO レコードフィールドエクスチェンジ (DFX) メカニズムによってデータソースのレコードに書き込まれるようにマークします。 フィールドの値を変更すると、通常はダーティフィールドが自動的にダーティに設定されるため、 [SetFieldDirty](#setfielddirty)を自分で呼び出す必要はほとんどありませんが、フィールドデータメンバー内の値に関係なく、明示的に列が更新または挿入されるようにすることが必要になる場合があります。 また、DFX のメカニズムでは、**擬似 NULL**の使用も使用されます。 詳細については、「 [CDaoFieldExchange:: m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)」を参照してください。

ダブルバッファリング機構が使用されていない場合は、フィールドの値を変更しても、フィールドがダーティとして自動的に設定されるわけではありません。 この場合は、フィールドをダーティに明示的に設定する必要があります。 [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)に含まれるフラグは、この自動フィールドチェックを制御します。

> [!NOTE]
> レコードがダブルバッファーされている場合 (つまり、自動フィールドチェックが有効になっている場合)、`CancelUpdate` を呼び出すと、`AddNew` または `Edit` が呼び出される前に保持されていた値にメンバー変数が復元されます。

関連情報については、DAO ヘルプの「AddNew メソッド」、「CancelUpdate メソッド」、「LastModified プロパティ」、および「EditMode プロパティ」を参照してください。

##  <a name="canappend"></a>CDaoRecordset:: CanAppend

このメンバー関数を呼び出して、既に開いているレコードセットで、 [AddNew](#addnew)メンバー関数を呼び出すことによって新しいレコードを追加できるかどうかを判断します。

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>戻り値

レコードセットで新しいレコードの追加が許可されている場合は0以外の。それ以外の場合は0です。 レコードセットを読み取り専用として開いた場合、`CanAppend` は0を返します。

### <a name="remarks"></a>解説

関連情報については、DAO ヘルプのトピック「Append メソッド」を参照してください。

##  <a name="canbookmark"></a>CDaoRecordset:: CanBookmark

このメンバー関数を呼び出して、既に開いているレコードセットがブックマークを使用してレコードを個別にマークできるかどうかを判断します。

```
BOOL CanBookmark();
```

### <a name="return-value"></a>戻り値

レコードセットがブックマークをサポートしている場合は0以外。それ以外の場合は0。

### <a name="remarks"></a>解説

Microsoft Jet データベースエンジンのすべてのテーブルに基づいてレコードセットを使用している場合は、前方参照専用のスクロールレコードとしてフラグが設定されたスナップショット型のレコードセットを除き、ブックマークを使用できます。 その他のデータベース製品 (外部 ODBC データソース) はブックマークをサポートしていない可能性があります。

関連情報については、DAO ヘルプの「Bookmarkable プロパティ」を参照してください。

##  <a name="cancelupdate"></a>CDaoRecordset:: CancelUpdate

`CancelUpdate` メンバー関数は、[編集](#edit)または[AddNew](#addnew)操作によって保留中の更新をキャンセルします。

```
virtual void CancelUpdate();
```

### <a name="remarks"></a>解説

たとえば、アプリケーションが `Edit` または `AddNew` のメンバー関数を呼び出し、 [Update](#update)を呼び出さない場合、`CancelUpdate` は `Edit` または `AddNew` が呼び出された後に行われたすべての変更を取り消します。

> [!NOTE]
>  レコードがダブルバッファーされている場合 (つまり、自動フィールドチェックが有効になっている場合)、`CancelUpdate` を呼び出すと、`AddNew` または `Edit` が呼び出される前に保持されていた値にメンバー変数が復元されます。

`Edit` または `AddNew` 操作が保留されていない場合、`CancelUpdate` は MFC が例外をスローします。 [GetEditMode](#geteditmode)メンバー関数を呼び出して、取り消すことができる保留中の操作があるかどうかを確認します。

関連情報については、DAO ヘルプの「CancelUpdate メソッド」を参照してください。

##  <a name="canrestart"></a>CDaoRecordset:: CanRestart

このメンバー関数を呼び出して、レコードセットで `Requery` メンバー関数を呼び出すことによってクエリを再起動できるかどうかを判断します (レコードを更新する場合)。

```
BOOL CanRestart();
```

### <a name="return-value"></a>戻り値

レコードセットのクエリを再実行するために `Requery` を呼び出すことができる場合は0以外。それ以外の場合は0。

### <a name="remarks"></a>解説

テーブル型のレコードセットは、`Requery`をサポートしていません。

`Requery` がサポートされていない場合は、 [Close](#close)を呼び出し、を[開い](#open)てデータを更新します。 パラメーター値が変更された後、`Requery` を呼び出して、レコードセットオブジェクトの基になるパラメータークエリを更新することができます。

関連情報については、DAO ヘルプの「再開可能なプロパティ」を参照してください。

##  <a name="canscroll"></a>CDaoRecordset:: CanScroll

このメンバー関数を呼び出して、レコードセットでスクロールが許可されているかどうかを確認します。

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>戻り値

レコードをスクロールできる場合は0以外。それ以外の場合は0。

### <a name="remarks"></a>解説

`dbForwardOnly`で[Open](#open)を呼び出すと、レコードセットは前方にのみスクロールできます。

関連情報については、DAO ヘルプの「DAO を使用した現在のレコードポインターの配置」を参照してください。

##  <a name="cantransact"></a>CDaoRecordset:: CanTransact

このメンバー関数を呼び出して、レコードセットでトランザクションが許可されているかどうかを確認します。

```
BOOL CanTransact();
```

### <a name="return-value"></a>戻り値

基になるデータソースがトランザクションをサポートしている場合は0以外。それ以外の場合は0。

### <a name="remarks"></a>解説

関連情報については、DAO ヘルプのトピック「トランザクションのプロパティ」を参照してください。

##  <a name="canupdate"></a>CDaoRecordset:: CanUpdate

レコードセットを更新できるかどうかを判断するには、このメンバー関数を呼び出します。

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>戻り値

レコードセットを更新 (レコードの追加、更新、削除) することができる場合は0以外。それ以外の場合は0。

### <a name="remarks"></a>解説

基になるデータソースが読み取り専用の場合、またはレコードセットに[Open](#open)を呼び出したときに*nOptions*に `dbReadOnly` を指定した場合は、レコードセットが読み取り専用になることがあります。

関連情報については、DAO ヘルプの「AddNew メソッド」、「Edit メソッド」、「Delete メソッド」、「Update メソッド」、「更新可能なプロパティ」の各トピックを参照してください。

##  <a name="cdaorecordset"></a>CDaoRecordset:: CDaoRecordset

`CDaoRecordset` オブジェクトを構築します。

```
CDaoRecordset(CDaoDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>パラメーター

*pDatabase*<br/>
には、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトへのポインターまたは NULL 値が含まれます。 NULL ではなく、`CDaoDatabase` オブジェクトの `Open` メンバー関数が呼び出されていない場合は、それをデータソースに接続するために、レコードセットは、独自の[open](#open)呼び出しの間にその関数を開こうとします。 NULL を渡すと、レコードセットクラスを `CDaoRecordset`から派生した場合に指定したデータソース情報を使用して、`CDaoDatabase` オブジェクトが構築され、接続されます。

### <a name="remarks"></a>解説

`CDaoRecordset` を直接使用することも、`CDaoRecordset`からアプリケーション固有のクラスを派生させることもできます。 ClassWizard を使用して、レコードセットクラスを派生させることができます。

> [!NOTE]
>  `CDaoRecordset` クラスを派生させる場合は、派生クラスで独自のコンストラクターを指定する必要があります。 派生クラスのコンストラクターで `CDaoRecordset::CDaoRecordset`コンストラクターを呼び出し、適切なパラメーターを渡します。

レコードセットコンストラクターに NULL を渡して、`CDaoDatabase` オブジェクトを自動的に構築および接続するようにします。 これは、レコードセットを構築する前に、`CDaoDatabase` オブジェクトを構築して接続する必要がない便利なショートカットです。 `CDaoDatabase` オブジェクトが開いていない場合は、既定のワークスペースを使用する[CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)オブジェクトも作成されます。 詳細については、「 [cdaodatabase:: cdaodatabase](../../mfc/reference/cdaodatabase-class.md#cdaodatabase)」を参照してください。

##  <a name="close"></a>CDaoRecordset:: Close

`CDaoRecordset` オブジェクトを閉じると、関連付けられているデータベース内の開いているレコードセットからオブジェクトが削除されます。

```
virtual void Close();
```

### <a name="remarks"></a>解説

`Close` によって `CDaoRecordset` オブジェクトが破棄されないため、同じデータソースまたは別のデータソースで `Open` を呼び出すことによって、オブジェクトを再利用できます。

すべての保留中の[AddNew](#addnew)ステートメントまたは[編集](#edit)ステートメントが取り消され、すべての保留中のトランザクションがロールバックされます。 保留中の追加または編集を保持する場合は、レコードセットごとに `Close` を呼び出す前に[Update](#update)を呼び出します。

`Close`を呼び出した後、`Open` をもう一度呼び出すことができます。 これにより、レコードセットオブジェクトを再利用できます。 可能な場合は、 [Requery](#requery)を呼び出すことをお勧めします。

関連情報については、DAO ヘルプの「Close メソッド」を参照してください。

##  <a name="delete"></a>CDaoRecordset::D e)

開いているダイナセット型またはテーブル型のレコードセットオブジェクトの現在のレコードを削除するには、このメンバー関数を呼び出します。

```
virtual void Delete();
```

### <a name="remarks"></a>解説

削除が正常に完了すると、レコードセットのフィールドデータメンバーが Null 値に設定されます。また、レコードセットナビゲーションメンバー関数 ( [move](#move)、 [Seek](#seek)、 [SetBookmark](#setbookmark)など) の1つを明示的に呼び出して、削除されたレコードから移動する必要があります。 レコードセットからレコードを削除する場合は、`Delete`を呼び出す前にレコードセットに現在のレコードが存在している必要があります。それ以外の場合、MFC は例外をスローします。

現在のレコードを削除し、アクセスできないように `Delete` します。 削除されたレコードを編集または使用することはできませんが、最新の状態のままです。 ただし、別のレコードに移動した場合は、削除されたレコードを再び現在使用することはできません。

> [!CAUTION]
>  レコードセットは更新可能である必要があります。また、`Delete`を呼び出すときは、レコードセットの現在のレコードが有効である必要があります。 たとえば、レコードを削除しても、`Delete` を再度呼び出す前に新しいレコードにスクロールしない場合、`Delete` は[CDaoException](../../mfc/reference/cdaoexception-class.md)をスローします。

トランザクションを使用し、 [CDaoWorkspace:: Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback)メンバー関数を呼び出すと、レコードの削除を取り消すことができます。 ベーステーブルが連鎖削除リレーションシップの主テーブルである場合、現在のレコードを削除すると、外部テーブル内の1つ以上のレコードが削除されることがあります。 詳細については、DAO ヘルプの「連鎖削除」の定義を参照してください。

`AddNew` と `Edit`とは異なり、`Delete` の呼び出しの後に `Update`を呼び出すことはできません。

関連情報については、DAO ヘルプの「AddNew メソッド」、「Edit メソッド」、「Delete メソッド」、「Update メソッド」、「更新可能なプロパティ」の各トピックを参照してください。

##  <a name="dofieldexchange"></a>CDaoRecordset::D oFieldExchange

フレームワークは、このメンバー関数を呼び出して、レコードセットオブジェクトのフィールドデータメンバーと、データソースの現在のレコードの対応する列との間でデータを自動的に交換します。

```
virtual void DoFieldExchange(CDaoFieldExchange* pFX);
```

### <a name="parameters"></a>パラメーター

*.Cer*<br/>
`CDaoFieldExchange` オブジェクトへのポインターを格納します。 フレームワークでは、フィールド交換操作のコンテキストを指定するために、このオブジェクトが既に設定されています。

### <a name="remarks"></a>解説

また、パラメーターのデータメンバー (存在する場合) を、レコードセットの選択に使用する SQL ステートメント文字列のパラメータープレースホルダーにバインドします。 DAO レコードフィールドエクスチェンジ (DFX) と呼ばれるフィールドデータの交換は、レコードセットオブジェクトのフィールドデータメンバーからデータソース上のレコードのフィールドへの変換と、データソースのレコードからレコードセットオブジェクトへの双方向で機能します。 列を動的にバインドする場合は、`DoFieldExchange`を実装する必要はありません。

派生レコードセットクラスの `DoFieldExchange` を実装するために通常必要な操作は、ClassWizard でクラスを作成し、フィールドデータメンバーの名前とデータ型を指定することです。 また、ClassWizard によってパラメーターデータメンバーを指定するために書き込まれるコードを追加することもできます。 すべてのフィールドが動的にバインドされる場合、パラメーターデータメンバーを指定しない限り、この関数は非アクティブになります。

ClassWizard で派生したレコードセットクラスを宣言すると、ウィザードによって `DoFieldExchange` のオーバーライドが書き込まれます。これは、次の例のようになります。

[!code-cpp[NVC_MFCDatabase#2](../../mfc/codesnippet/cpp/cdaorecordset-class_2.cpp)]

##  <a name="edit"></a>CDaoRecordset:: Edit

現在のレコードを変更できるようにするには、このメンバー関数を呼び出します。

```
virtual void Edit();
```

### <a name="remarks"></a>解説

`Edit` メンバー関数を呼び出すと、現在のレコードのフィールドに加えられた変更がコピーバッファーにコピーされます。 レコードに必要な変更を加えたら、`Update` を呼び出して変更を保存します。 `Edit` では、レコードセットのデータメンバーの値が保存されます。 `Edit`を呼び出して変更を加え、`Edit` を再度呼び出すと、レコードの値は最初の `Edit` 呼び出しの前の値に復元されます。

> [!CAUTION]
>  レコードを編集してから `Update`を呼び出さずに別のレコードに移動する操作を実行した場合、変更は警告なしに失われます。 さらに、レコードセットまたは親データベースを閉じた場合、編集したレコードは警告なしで破棄されます。

場合によっては、Null (データを含まない) によって列を更新することが必要になることがあります。 これを行うには、パラメーターを TRUE に設定して `SetFieldNull` を呼び出して、フィールドを Null に設定します。これにより、列も更新されます。 値が変更されていないにもかかわらず、データソースにフィールドを書き出す場合は、パラメーターを TRUE に設定して `SetFieldDirty` を呼び出します。 これは、フィールドの値が Null の場合でも機能します。

フレームワークは、変更されたフィールドデータメンバーを、DAO レコードフィールドエクスチェンジ (DFX) メカニズムによってデータソースのレコードに書き込まれるようにマークします。 フィールドの値を変更すると、通常はダーティフィールドが自動的にダーティに設定されるため、 [SetFieldDirty](#setfielddirty)を自分で呼び出す必要はほとんどありませんが、フィールドデータメンバー内の値に関係なく、明示的に列が更新または挿入されるようにすることが必要になる場合があります。 また、DFX のメカニズムでは、**擬似 NULL**の使用も使用されます。 詳細については、「 [CDaoFieldExchange:: m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)」を参照してください。

ダブルバッファリング機構が使用されていない場合は、フィールドの値を変更しても、フィールドがダーティとして自動的に設定されるわけではありません。 この場合は、フィールドをダーティに明示的に設定する必要があります。 [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)に含まれるフラグは、この自動フィールドチェックを制御します。

マルチユーザー環境でレコードセットオブジェクトが pessimistically にロックされている場合、レコードは、更新が完了するまで `Edit` が使用された時点からロックされたままになります。 レコードセットがオプティミスティックでロックされている場合、レコードはロックされ、データベース内で更新される直前に、編集前のレコードと比較されます。 `Edit`を呼び出した後にレコードが変更された場合、`Update` 操作は失敗し、MFC は例外をスローします。 ロックモードは、`SetLockingMode`で変更できます。

> [!NOTE]
>  オプティミスティックロックは、ODBC やインストール可能な ISAM などの外部データベース形式で常に使用されます。

`Edit`を呼び出した後、現在のレコードは最新のままです。 `Edit`を呼び出すには、現在のレコードが存在する必要があります。 現在のレコードが存在しない場合、またはレコードセットが開いているテーブル型またはダイナセット型の recordset オブジェクトを参照していない場合は、例外が発生します。 `Edit` を呼び出すと、次の条件で `CDaoException` がスローされます。

- 現在のレコードがありません。

- データベースまたはレコードセットは読み取り専用です。

- レコードのフィールドが更新可能ではありません。

- 他のユーザーが排他的に使用するために、データベースまたはレコードセットが開かれました。

- 別のユーザーがレコードを含むページをロックしました。

データソースでトランザクションがサポートされている場合は、トランザクションの一部 `Edit` 呼び出しを行うことができます。 `Edit` を呼び出す前と、レコードセットを開いた後に `CDaoWorkspace::BeginTrans` を呼び出す必要があることに注意してください。 `CDaoWorkspace::CommitTrans` の呼び出しは、`Update` を呼び出して `Edit` 操作を完了するための代替ではないことにも注意してください。 トランザクションの詳細については、「クラス `CDaoWorkspace`」を参照してください。

関連情報については、DAO ヘルプの「AddNew メソッド」、「Edit メソッド」、「Delete メソッド」、「Update メソッド」、「更新可能なプロパティ」の各トピックを参照してください。

##  <a name="fillcache"></a>CDaoRecordset:: FillCache

このメンバー関数を呼び出して、レコードセットから指定された数のレコードをキャッシュします。

```
void FillCache(
    long* pSize = NULL,
    COleVariant* pBookmark = NULL);
```

### <a name="parameters"></a>パラメーター

*pSize*<br/>
キャッシュに格納する行の数を指定します。 このパラメーターを省略した場合、値は基になる DAO オブジェクトの CacheSize プロパティの設定によって決まります。

*pBookmark*<br/>
ブックマークを指定する[COleVariant](../../mfc/reference/colevariant-class.md)です。 キャッシュは、このブックマークによって示されるレコードから開始されます。 このパラメーターを省略した場合、キャッシュは、基になる DAO オブジェクトの CacheStart プロパティによって示されるレコードから開始されます。

### <a name="remarks"></a>解説

キャッシュを行うと、リモートサーバーからデータを取得またはフェッチするアプリケーションのパフォーマンスが向上します。 キャッシュは、アプリケーションの実行中にデータが再要求される可能性があると想定して、サーバーから最後にフェッチされたデータを保持するローカルメモリ内の領域です。 データが要求されると、Microsoft Jet データベースエンジンは、サーバーからデータをフェッチするのではなく、最初にキャッシュを確認します。これには時間がかかります。 データがキャッシュに保存されないため、非 ODBC データソースでデータキャッシュを使用しても効果はありません。

キャッシュには、フェッチ時にレコードが格納されるのを待機するのではなく、`FillCache` メンバー関数を呼び出すことによって、いつでも明示的にキャッシュを入力できます。 `FillCache` は一度に1つずつではなく、一度に複数のレコードをフェッチするため、これにより、キャッシュを短時間で読み込むことができます。 たとえば、レコードの各画面が表示されている間に、アプリケーションが `FillCache` を呼び出して、次の1番目のレコードをフェッチすることができます。

レコードセットオブジェクトを使用してアクセスされるすべての ODBC データベースは、ローカルキャッシュを持つことができます。 キャッシュを作成するには、リモートデータソースからレコードセットオブジェクトを開き、レコードセットの `SetCacheSize` および `SetCacheStart` メンバー関数を呼び出します。 *Lsize*と*lsize*が、`SetCacheSize` と `SetCacheStart`で指定された範囲外の範囲を作成した場合、この範囲外のレコードセットの部分は無視され、キャッシュに読み込まれません。 `FillCache` がリモートデータソースに残っているよりも多くのレコードを要求した場合、残りのレコードのみがフェッチされ、例外はスローされません。

キャッシュからフェッチされたレコードには、他のユーザーによってソースデータに同時に加えられた変更は反映されません。

`FillCache` は、まだキャッシュされていないレコードのみをフェッチします。 キャッシュされたすべてのデータを強制的に更新するには、 *Lsize*パラメーターが0に等しい `SetCacheSize` メンバー関数を呼び出し、最初に要求したキャッシュのサイズと等しい*lsize*パラメーターを使用して `SetCacheSize` を呼び出してから、`FillCache`を呼び出します。

関連情報については、DAO ヘルプの「FillCache メソッド」を参照してください。

##  <a name="find"></a>CDaoRecordset:: Find

比較演算子を使用して、ダイナセットまたはスナップショット型のレコードセット内の特定の文字列を検索するには、このメンバー関数を呼び出します。

```
virtual BOOL Find(
    long lFindType,
    LPCTSTR lpszFilter);
```

### <a name="parameters"></a>パラメーター

*lFindType*<br/>
目的の検索操作の種類を示す値。 指定できる値は、

- 一致する文字列の次の位置を検索 AFX_DAO_NEXT ます。

- 一致する文字列の前の場所を検索 AFX_DAO_PREV ます。

- 一致する文字列の最初の位置を検索 AFX_DAO_FIRST ます。

- 一致する文字列の最後の位置を検索 AFX_DAO_LAST ます。

*lpszFilter*<br/>
レコードを検索するために使用される文字列式 (where 句を含まない SQL ステートメント内の**where**句と**同様)。** 次に例を示します。

[!code-cpp[NVC_MFCDatabase#3](../../mfc/codesnippet/cpp/cdaorecordset-class_3.cpp)]

### <a name="return-value"></a>戻り値

一致するレコードが見つかった場合は0以外。それ以外の場合は0。

### <a name="remarks"></a>解説

文字列の最初、次、前、または最後のインスタンスを見つけることができます。 `Find` は仮想関数であるため、オーバーライドして独自の実装を追加することができます。 `FindFirst`、`FindLast`、`FindNext`、および `FindPrev` の各メンバー関数は、`Find` のメンバー関数を呼び出します。そのため、`Find` を使用してすべての検索操作の動作を制御できます。

テーブル型のレコードセット内のレコードを検索するには、 [Seek](#seek)メンバー関数を呼び出します。

> [!TIP]
>  レコードの数が少ないほど、より効果的な `Find` になります。 一般に、特に ODBC データの場合は、必要なレコードだけを取得する新しいクエリを作成することをお勧めします。

関連情報については、DAO ヘルプの「FindFirst、FindLast、FindNext、FindPrevious メソッド」を参照してください。

##  <a name="findfirst"></a>CDaoRecordset:: FindFirst

このメンバー関数を呼び出して、指定した条件に一致する最初のレコードを検索します。

```
BOOL FindFirst(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>パラメーター

*lpszFilter*<br/>
レコードを検索するために使用される文字列式 (where 句を含まない SQL ステートメント内の**where**句と**同様)。**

### <a name="return-value"></a>戻り値

一致するレコードが見つかった場合は0以外。それ以外の場合は0。

### <a name="remarks"></a>解説

`FindFirst` メンバー関数は、レコードセットの先頭から検索を開始し、レコードセットの末尾まで検索します。

(特定の条件を満たすものだけでなく) 検索にすべてのレコードを含める場合は、移動操作のいずれかを使用して、レコードからレコードに移動します。 テーブル型のレコードセット内のレコードを検索するには、`Seek` メンバー関数を呼び出します。

条件に一致するレコードが見つからない場合、現在のレコードポインターは不定になり、`FindFirst` は0を返します。 条件を満たすレコードがレコードセットに1つ以上含まれている場合、`FindFirst` は最初の出現箇所を検索し、`FindNext` 次の出現箇所を検索します。

> [!CAUTION]
>  現在のレコードを編集する場合は、別のレコードに移動する前に `Update` メンバー関数を呼び出して変更を保存してください。 更新せずに別のレコードに移動した場合、変更は警告なしに失われます。

`Find` メンバー関数は、場所と、次の表で指定されている方向を検索します。

|検索操作|Begin|検索方向|
|---------------------|-----------|----------------------|
|`FindFirst`|レコードセットの先頭|レコードセットの最後|
|`FindLast`|レコードセットの最後|レコードセットの先頭|
|`FindNext`|現在のレコード|レコードセットの最後|
|`FindPrevious`|現在のレコード|レコードセットの先頭|

> [!NOTE]
>  `FindLast`を呼び出すと、検索を開始する前に、Microsoft Jet データベースエンジンによってレコードセットが完全に設定されます (これがまだ完了していない場合)。 最初の検索では、後続の検索よりも長い時間がかかることがあります。

ただし、検索操作の1つを使用することは `MoveFirst` または `MoveNext`の呼び出しと同じではありませんが、単に条件を指定せずに最初または次のレコードを最新の状態にします。 移動操作では、検索操作に従うことができます。

検索操作を使用する場合は、次の点に注意してください。

- `Find` が0以外の値を返した場合、現在のレコードは定義されません。 この場合は、現在のレコードポインターを有効なレコードに戻す必要があります。

- 前方スクロール専用のスナップショット型のレコードセットでは、検索操作を使用できません。

- 米国バージョンの Microsoft Jet データベースエンジンを使用していない場合でも、日付を含むフィールドを検索するときには、米国の日付形式 (月-日-年) を使用する必要があります。それ以外の場合は、一致するレコードが見つからない可能性があります。

- ODBC データベースや大きなダイナセットを操作する場合は、特に大規模なレコードセットを操作するときに、検索操作の使用が低速であることがわかります。 カスタマイズされた**ORDERBY**句、 **WHERE**句、パラメータークエリ、または特定のインデックス付きレコードを取得する `CDaoQuerydef` オブジェクトを使用して、SQL クエリを使用することにより、パフォーマンスを向上させることができます。

関連情報については、DAO ヘルプの「FindFirst、FindLast、FindNext、FindPrevious メソッド」を参照してください。

##  <a name="findlast"></a>CDaoRecordset:: FindLast

指定した条件に一致する最後のレコードを検索するには、このメンバー関数を呼び出します。

```
BOOL FindLast(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>パラメーター

*lpszFilter*<br/>
レコードを検索するために使用される文字列式 (where 句を含まない SQL ステートメント内の**where**句と**同様)。**

### <a name="return-value"></a>戻り値

一致するレコードが見つかった場合は0以外。それ以外の場合は0。

### <a name="remarks"></a>解説

`FindLast` メンバー関数は、レコードセットの末尾から検索を開始し、レコードセットの先頭に向かって後方に検索します。

(特定の条件を満たすものだけでなく) 検索にすべてのレコードを含める場合は、移動操作のいずれかを使用して、レコードからレコードに移動します。 テーブル型のレコードセット内のレコードを検索するには、`Seek` メンバー関数を呼び出します。

条件に一致するレコードが見つからない場合、現在のレコードポインターは不定になり、`FindLast` は0を返します。 条件を満たすレコードがレコードセットに1つ以上含まれている場合、`FindFirst` は、最初の出現箇所を検索し、最初の出現後の次の出現箇所を検索 `FindNext` ます。

> [!CAUTION]
>  現在のレコードを編集する場合は、別のレコードに移動する前に `Update` メンバー関数を呼び出して変更を保存してください。 更新せずに別のレコードに移動した場合、変更は警告なしに失われます。

ただし、検索操作の1つを使用することは `MoveFirst` または `MoveNext`の呼び出しと同じではありませんが、単に条件を指定せずに最初または次のレコードを最新の状態にします。 移動操作では、検索操作に従うことができます。

検索操作を使用する場合は、次の点に注意してください。

- `Find` が0以外の値を返した場合、現在のレコードは定義されません。 この場合は、現在のレコードポインターを有効なレコードに戻す必要があります。

- 前方スクロール専用のスナップショット型のレコードセットでは、検索操作を使用できません。

- 米国バージョンの Microsoft Jet データベースエンジンを使用していない場合でも、日付を含むフィールドを検索するときには、米国の日付形式 (月-日-年) を使用する必要があります。それ以外の場合は、一致するレコードが見つからない可能性があります。

- ODBC データベースや大きなダイナセットを操作する場合は、特に大規模なレコードセットを操作するときに、検索操作の使用が低速であることがわかります。 カスタマイズされた**ORDERBY**句、 **WHERE**句、パラメータークエリ、または特定のインデックス付きレコードを取得する `CDaoQuerydef` オブジェクトを使用して、SQL クエリを使用することにより、パフォーマンスを向上させることができます。

関連情報については、DAO ヘルプの「FindFirst、FindLast、FindNext、FindPrevious メソッド」を参照してください。

##  <a name="findnext"></a>CDaoRecordset:: FindNext

指定した条件に一致する次のレコードを検索するには、このメンバー関数を呼び出します。

```
BOOL FindNext(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>パラメーター

*lpszFilter*<br/>
レコードを検索するために使用される文字列式 (where 句を含まない SQL ステートメント内の**where**句と**同様)。**

### <a name="return-value"></a>戻り値

一致するレコードが見つかった場合は0以外。それ以外の場合は0。

### <a name="remarks"></a>解説

`FindNext` メンバー関数は、現在のレコードから検索を開始し、レコードセットの末尾を検索します。

(特定の条件を満たすものだけでなく) 検索にすべてのレコードを含める場合は、移動操作のいずれかを使用して、レコードからレコードに移動します。 テーブル型のレコードセット内のレコードを検索するには、`Seek` メンバー関数を呼び出します。

条件に一致するレコードが見つからない場合、現在のレコードポインターは不定になり、`FindNext` は0を返します。 条件を満たすレコードがレコードセットに1つ以上含まれている場合、`FindFirst` は最初の出現箇所を検索し、`FindNext` 次の出現箇所を検索します。

> [!CAUTION]
>  現在のレコードを編集する場合は、別のレコードに移動する前に `Update` メンバー関数を呼び出して変更を保存してください。 更新せずに別のレコードに移動した場合、変更は警告なしに失われます。

ただし、検索操作の1つを使用することは `MoveFirst` または `MoveNext`の呼び出しと同じではありませんが、単に条件を指定せずに最初または次のレコードを最新の状態にします。 移動操作では、検索操作に従うことができます。

検索操作を使用する場合は、次の点に注意してください。

- `Find` が0以外の値を返した場合、現在のレコードは定義されません。 この場合は、現在のレコードポインターを有効なレコードに戻す必要があります。

- 前方スクロール専用のスナップショット型のレコードセットでは、検索操作を使用できません。

- 米国バージョンの Microsoft Jet データベースエンジンを使用していない場合でも、日付を含むフィールドを検索するときには、米国の日付形式 (月-日-年) を使用する必要があります。それ以外の場合は、一致するレコードが見つからない可能性があります。

- ODBC データベースや大きなダイナセットを操作する場合は、特に大規模なレコードセットを操作するときに、検索操作の使用が低速であることがわかります。 カスタマイズされた**ORDERBY**句、 **WHERE**句、パラメータークエリ、または特定のインデックス付きレコードを取得する `CDaoQuerydef` オブジェクトを使用して、SQL クエリを使用することにより、パフォーマンスを向上させることができます。

関連情報については、DAO ヘルプの「FindFirst、FindLast、FindNext、FindPrevious メソッド」を参照してください。

##  <a name="findprev"></a>CDaoRecordset:: FindPrev

指定した条件に一致する前のレコードを検索するには、このメンバー関数を呼び出します。

```
BOOL FindPrev(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>パラメーター

*lpszFilter*<br/>
レコードを検索するために使用される文字列式 (where 句を含まない SQL ステートメント内の**where**句と**同様)。**

### <a name="return-value"></a>戻り値

一致するレコードが見つかった場合は0以外。それ以外の場合は0。

### <a name="remarks"></a>解説

`FindPrev` メンバー関数は、現在のレコードから検索を開始し、レコードセットの先頭に向かって後方に検索します。

(特定の条件を満たすものだけでなく) 検索にすべてのレコードを含める場合は、移動操作のいずれかを使用して、レコードからレコードに移動します。 テーブル型のレコードセット内のレコードを検索するには、`Seek` メンバー関数を呼び出します。

条件に一致するレコードが見つからない場合、現在のレコードポインターは不定になり、`FindPrev` は0を返します。 条件を満たすレコードがレコードセットに1つ以上含まれている場合、`FindFirst` は最初の出現箇所を検索し、`FindNext` 次の出現箇所を検索します。

> [!CAUTION]
>  現在のレコードを編集する場合は、別のレコードに移動する前に `Update` メンバー関数を呼び出して変更を保存してください。 更新せずに別のレコードに移動した場合、変更は警告なしに失われます。

ただし、検索操作の1つを使用することは `MoveFirst` または `MoveNext`の呼び出しと同じではありませんが、単に条件を指定せずに最初または次のレコードを最新の状態にします。 移動操作では、検索操作に従うことができます。

検索操作を使用する場合は、次の点に注意してください。

- `Find` が0以外の値を返した場合、現在のレコードは定義されません。 この場合は、現在のレコードポインターを有効なレコードに戻す必要があります。

- 前方スクロール専用のスナップショット型のレコードセットでは、検索操作を使用できません。

- 米国バージョンの Microsoft Jet データベースエンジンを使用していない場合でも、日付を含むフィールドを検索するときには、米国の日付形式 (月-日-年) を使用する必要があります。それ以外の場合は、一致するレコードが見つからない可能性があります。

- ODBC データベースや大きなダイナセットを操作する場合は、特に大規模なレコードセットを操作するときに、検索操作の使用が低速であることがわかります。 カスタマイズされた**ORDERBY**句、 **WHERE**句、パラメータークエリ、または特定のインデックス付きレコードを取得する `CDaoQuerydef` オブジェクトを使用して、SQL クエリを使用することにより、パフォーマンスを向上させることができます。

関連情報については、DAO ヘルプの「FindFirst、FindLast、FindNext、FindPrevious メソッド」を参照してください。

##  <a name="getabsoluteposition"></a>CDaoRecordset:: GetAbsolutePosition

レコードセットオブジェクトの現在のレコードのレコード番号を返します。

```
long GetAbsolutePosition();
```

### <a name="return-value"></a>戻り値

0からレコードセット内のレコード数までの整数。 レコードセット内の現在のレコードの序数位置に対応します。

### <a name="remarks"></a>解説

基になる DAO オブジェクトの AbsolutePosition プロパティの値は0から始まります。0に設定すると、レコードセットの最初のレコードが参照されます。 [GetRecordCount](#getrecordcount)を呼び出すことによって、レコードセット内の設定されたレコードの数を確認できます。 `GetRecordCount` を呼び出すと、カウントを決定するためにすべてのレコードにアクセスする必要があるため、時間がかかることがあります。

レコードセットにレコードが存在しない場合のように、現在のレコードが存在しない場合は、-1 が返されます。 現在のレコードが削除されると、AbsolutePosition プロパティの値が定義されず、MFC が参照されている場合は例外がスローされます。 ダイナセット型のレコードセットの場合、新しいレコードがシーケンスの最後に追加されます。

> [!NOTE]
>  このプロパティは、サロゲートレコード番号として使用するためのものではありません。 ブックマークは、特定の位置を保持して返すための推奨される方法であり、すべての種類のレコードセットオブジェクトに対して現在のレコードを配置する唯一の方法です。 特に、指定されたレコードの位置は、先行するレコードが削除されると変更されます。 また、 **ORDERBY**句を使用して SQL ステートメントで作成された場合を除き、レコードセット内の個々のレコードの順序は保証されないため、レコードセットを再作成した場合、特定のレコードの絶対位置が同じであることは保証されません。

> [!NOTE]
>  このメンバー関数は、ダイナセット型およびスナップショット型のレコードセットに対してのみ有効です。

関連情報については、DAO ヘルプの「AbsolutePosition プロパティ」を参照してください。

##  <a name="getbookmark"></a>CDaoRecordset:: GetBookmark

特定のレコードのブックマーク値を取得するには、このメンバー関数を呼び出します。

```
COleVariant GetBookmark();
```

### <a name="return-value"></a>戻り値

現在のレコードのブックマークを表す値を返します。

### <a name="remarks"></a>解説

レコードセットオブジェクトを作成または開くと、そのレコードがサポートされている場合、そのレコードには一意のブックマークが既に存在します。 `CanBookmark` を呼び出して、レコードセットがブックマークをサポートするかどうかを判断します。

ブックマークの値を `COleVariant` オブジェクトに割り当てることにより、現在のレコードのブックマークを保存できます。 別のレコードに移動した後、いつでもそのレコードにすばやく戻るには、その `COleVariant` オブジェクトの値に対応するパラメーターを指定して `SetBookmark` を呼び出します。

> [!NOTE]
>  [Requery](#requery)を呼び出すと、DAO ブックマークが変更します。

関連情報については、DAO ヘルプのトピック「Bookmark プロパティ」を参照してください。

##  <a name="getcachesize"></a>CDaoRecordset:: GetCacheSize

キャッシュされたレコードの数を取得するには、このメンバー関数を呼び出します。

```
long GetCacheSize();
```

### <a name="return-value"></a>戻り値

ODBC データソースからローカルにキャッシュされるデータを含む、ダイナセット型のレコードセット内のレコードの数を示す値です。

### <a name="remarks"></a>解説

データキャッシュを使用すると、ダイナセット型のレコードセットオブジェクトを介してリモートサーバーからデータを取得するアプリケーションのパフォーマンスが向上します。 キャッシュとは、アプリケーションの実行中にデータが再度要求される場合に、サーバーから最後に取得されたデータを保持するローカルメモリ内の領域です。 データが要求されると、Microsoft Jet データベースエンジンは、要求されたデータをサーバーから取得するのではなく、最初にキャッシュを確認します。これには時間がかかります。 ODBC データソースから取得されていないデータはキャッシュに保存されません。

アタッチされたテーブルなどの ODBC データソースは、ローカルキャッシュを持つことができます。

関連情報については、DAO ヘルプの「CacheSize、CacheStart プロパティ」を参照してください。

##  <a name="getcachestart"></a>CDaoRecordset:: GetCacheStart

キャッシュされるレコードセット内の最初のレコードのブックマーク値を取得するには、このメンバー関数を呼び出します。

```
COleVariant GetCacheStart();
```

### <a name="return-value"></a>戻り値

キャッシュされるレコードセット内の最初のレコードのブックマークを指定する `COleVariant`。

### <a name="remarks"></a>解説

Microsoft Jet データベースエンジンはキャッシュからキャッシュ範囲内のレコードを要求し、サーバーからキャッシュ範囲外のレコードを要求します。

> [!NOTE]
>  キャッシュから取得されたレコードには、他のユーザーによってソースデータに同時に加えられた変更は反映されません。

関連情報については、DAO ヘルプの「CacheSize、CacheStart プロパティ」を参照してください。

##  <a name="getcurrentindex"></a>CDaoRecordset:: GetCurrentIndex

このメンバー関数を呼び出して、インデックス付きテーブル型 `CDaoRecordset` オブジェクトで現在使用されているインデックスを確認します。

```
CString GetCurrentIndex();
```

### <a name="return-value"></a>戻り値

現在テーブル型のレコードセットで使用されているインデックスの名前を含む `CString`。 インデックスが設定されていない場合は、空の文字列を返します。

### <a name="remarks"></a>解説

このインデックスは、レコードをテーブル型のレコードセットで並べ替えるための基礎であり、 [Seek](#seek)メンバー関数でレコードを検索するために使用されます。

`CDaoRecordset` オブジェクトは複数のインデックスを持つことができますが、一度に1つのインデックスのみを使用できます (ただし、 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)オブジェクトには複数のインデックスが定義されている場合があります)。

関連情報については、DAO ヘルプの「Index オブジェクト」と「現在のインデックス」を参照してください。

##  <a name="getdatecreated"></a>CDaoRecordset:: GetDateCreated

ベーステーブルが作成された日付と時刻を取得するには、このメンバー関数を呼び出します。

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>戻り値

ベーステーブルが作成された日付と時刻を含む[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクト。

### <a name="remarks"></a>解説

日付と時刻の設定は、ベーステーブルが作成されたコンピューターから派生します。

関連情報については、DAO ヘルプの「DateCreated、LastUpdated Properties」を参照してください。

##  <a name="getdatelastupdated"></a>CDaoRecordset:: GetDateLastUpdated

スキーマが最後に更新された日付と時刻を取得するには、このメンバー関数を呼び出します。

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>戻り値

ベーステーブル構造 (スキーマ) が最後に更新された日付と時刻を含む[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクト。

### <a name="remarks"></a>解説

日付と時刻の設定は、ベーステーブル構造 (スキーマ) が最後に更新されたコンピューターから派生します。

関連情報については、DAO ヘルプの「DateCreated、LastUpdated Properties」を参照してください。

##  <a name="getdefaultdbname"></a>CDaoRecordset:: GetDefaultDBName

このレコードセットのデータベースの名前を確認するには、このメンバー関数を呼び出します。

```
virtual CString GetDefaultDBName();
```

### <a name="return-value"></a>戻り値

このレコードセットの派生元であるデータベースのパスと名前を含む `CString` です。

### <a name="remarks"></a>解説

レコードセットを作成するとき[に、この](../../mfc/reference/cdaodatabase-class.md)パスを使用して、レコードセットが、既定のデータベースを開くために、レコードセットによって使用されます。 既定では、この関数は空の文字列を返します。 ClassWizard が `CDaoRecordset`から新しいレコードセットを派生すると、この関数が作成されます。

文字列が正しく解釈されるために必要な2つの円記号 (\\\\) の使用例を次に示します。

[!code-cpp[NVC_MFCDatabase#4](../../mfc/codesnippet/cpp/cdaorecordset-class_4.cpp)]

##  <a name="getdefaultsql"></a>CDaoRecordset:: GetDefaultSQL

フレームワークは、このメンバー関数を呼び出して、レコードセットの基になる既定の SQL ステートメントを取得します。

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>戻り値

既定の SQL ステートメントを含む `CString` です。

### <a name="remarks"></a>解説

テーブル名または SQL **SELECT**ステートメントを指定できます。

ClassWizard でレコードセットクラスを宣言することで、既定の SQL ステートメントを間接的に定義すると、ClassWizard がこのタスクを実行します。

Null の SQL 文字列を渡してを[開く](#open)場合は、この関数を呼び出して、レコードセットのテーブル名または SQL を決定します。

##  <a name="geteditmode"></a>CDaoRecordset:: GetEditMode

このメンバー関数を呼び出して、編集の状態を確認します。これは次のいずれかの値です。

```
short GetEditMode();
```

### <a name="return-value"></a>戻り値

現在のレコードの編集の状態を示す値を返します。

### <a name="remarks"></a>解説

|値|Description|
|-----------|-----------------|
|`dbEditNone`|編集操作は実行されていません。|
|`dbEditInProgress`|`Edit` が呼び出されました。|
|`dbEditAdd`|`AddNew` が呼び出されました。|

関連情報については、DAO ヘルプの「EditMode プロパティ」を参照してください。

##  <a name="getfieldcount"></a>CDaoRecordset:: GetFieldCount

このメンバー関数を呼び出して、レコードセットで定義されているフィールド (列) の数を取得します。

```
short GetFieldCount();
```

### <a name="return-value"></a>戻り値

レコードセット内のフィールドの数。

### <a name="remarks"></a>解説

関連情報については、DAO ヘルプのトピック「Count プロパティ」を参照してください。

##  <a name="getfieldinfo"></a>CDaoRecordset:: GetFieldInfo

レコードセット内のフィールドに関する情報を取得するには、このメンバー関数を呼び出します。

```
void GetFieldInfo(
    int nIndex,
    CDaoFieldInfo& fieldinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetFieldInfo(
    LPCTSTR lpszName,
    CDaoFieldInfo& fieldinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
インデックスによる検索のために、レコードセットの Fields コレクション内の定義済みフィールドの0から始まるインデックス。

*fieldinfo*<br/>
[CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体への参照。

*オプション*<br/>
取得するレコードセットに関する情報を指定するオプション。 使用可能なオプションは、関数が返す原因と共にここに表示されます。 最適なパフォーマンスを得るには、必要な情報のレベルのみを取得します。

- `AFX_DAO_PRIMARY_INFO` (既定) 名前、種類、サイズ、属性

- 主要な情報に加えて、序数の位置、必須、長さ0、照合順序、外部名、ソースフィールド、ソーステーブルを指定します。 `AFX_DAO_SECONDARY_INFO`

- プライマリとセカンダリの情報に加え、既定値、検証規則、検証テキストを `AFX_DAO_ALL_INFO` します。

*lpszName*<br/>
フィールドの名前。

### <a name="remarks"></a>解説

関数の1つのバージョンでは、インデックスを使用してフィールドを検索できます。 もう1つのバージョンでは、名前でフィールドを検索できます。

返される情報の説明については、「 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体」を参照してください。 この構造体には、前に説明した情報の項目に対応するメンバーが含まれ*ています。* 1つのレベルで情報を要求すると、以前のレベルについても情報が得られます。

関連情報については、DAO ヘルプの「Attributes プロパティ」を参照してください。

##  <a name="getfieldvalue"></a>CDaoRecordset:: GetFieldValue

レコードセット内のデータを取得するには、このメンバー関数を呼び出します。

```
virtual void GetFieldValue(
    LPCTSTR lpszName,
    COleVariant& varValue);

virtual void GetFieldValue(
    int nIndex,
    COleVariant& varValue);

virtual COleVariant GetFieldValue(LPCTSTR lpszName);
virtual COleVariant GetFieldValue(int nIndex);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
フィールドの名前を格納している文字列へのポインター。

*varValue*<br/>
フィールドの値を格納する `COleVariant` オブジェクトへの参照。

*nIndex*<br/>
インデックスによる検索のために、レコードセットの Fields コレクション内のフィールドの0から始まるインデックス。

### <a name="return-value"></a>戻り値

値を返す `GetFieldValue` の2つのバージョンでは、フィールドの値を含む[COleVariant](../../mfc/reference/colevariant-class.md)オブジェクトが返されます。

### <a name="remarks"></a>解説

フィールドは、名前または序数で検索できます。

> [!NOTE]
>  `COleVariant` オブジェクトを返すバージョンを呼び出すのではなく、`COleVariant` オブジェクト参照をパラメーターとして受け取る、このメンバー関数のいずれかのバージョンを呼び出す方が効率的です。 この関数の後者のバージョンは、旧バージョンとの互換性のために残されています。

`GetFieldValue` と[SetFieldValue](#setfieldvalue)を使用して、 [DoFieldExchange](#dofieldexchange)メカニズムを使用して静的に列をバインドするのではなく、実行時にフィールドを動的にバインドします。

`GetFieldValue` と `DoFieldExchange` メカニズムを組み合わせることにより、パフォーマンスを向上させることができます。 たとえば、必要に応じて必要な値を取得し、その呼び出しをインターフェイスの "More Information" ボタンに割り当てるには、`GetFieldValue` を使用します。

関連情報については、DAO ヘルプの「フィールドオブジェクト」と「値プロパティ」を参照してください。

##  <a name="getindexcount"></a>CDaoRecordset:: GetIndexCount

このメンバー関数を呼び出して、テーブル型のレコードセットで使用可能なインデックスの数を確認します。

```
short GetIndexCount();
```

### <a name="return-value"></a>戻り値

テーブル型のレコードセット内のインデックスの数。

### <a name="remarks"></a>解説

`GetIndexCount` は、レコードセット内のすべてのインデックスをループ処理する場合に便利です。 そのためには、 [Getindexinfo](#getindexinfo)と共に `GetIndexCount` を使用します。 このメンバー関数を、ダイナセット型またはスナップショット型のレコードセットに対して呼び出した場合、MFC は例外をスローします。

関連情報については、DAO ヘルプの「Attributes プロパティ」を参照してください。

##  <a name="getindexinfo"></a>CDaoRecordset:: GetIndexInfo

このメンバー関数を呼び出して、レコードセットの基になるベーステーブルで定義されているインデックスに関するさまざまな種類の情報を取得します。

```
void GetIndexInfo(
    int nIndex,
    CDaoIndexInfo& indexinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetIndexInfo(
    LPCTSTR lpszName,
    CDaoIndexInfo& indexinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
数値位置による検索のための、テーブルの Indexes コレクション内の0から始まるインデックス。

*indexinfo*<br/>
[CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)構造体への参照。

*オプション*<br/>
取得するインデックスに関する情報を指定するオプション。 使用可能なオプションは、関数が返す原因と共にここに表示されます。 最適なパフォーマンスを得るには、必要な情報のレベルのみを取得します。

- `AFX_DAO_PRIMARY_INFO` (既定) 名前、フィールド情報、フィールド

- 主な情報に加え、プライマリ、Unique、Clustered、IgnoreNulls、Required、Foreign `AFX_DAO_SECONDARY_INFO`

- プライマリとセカンダリの情報に加え、個別のカウントを `AFX_DAO_ALL_INFO` します。

*lpszName*<br/>
名前で検索するための、インデックスオブジェクトの名前へのポインター。

### <a name="remarks"></a>解説

関数の1つのバージョンでは、インデックスをコレクション内の位置で検索できます。 もう1つのバージョンでは、インデックスを名前で検索できます。

返される情報の説明については、「 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)構造体」を参照してください。 この構造体には、前に説明した情報の項目に対応するメンバーが含まれ*ています。* 1つのレベルで情報を要求すると、以前のレベルについても情報が得られます。

関連情報については、DAO ヘルプの「Attributes プロパティ」を参照してください。

##  <a name="getlastmodifiedbookmark"></a>CDaoRecordset:: GetLastModifiedBookmark

最後に追加または更新されたレコードのブックマークを取得するには、このメンバー関数を呼び出します。

```
COleVariant GetLastModifiedBookmark();
```

### <a name="return-value"></a>戻り値

最後に追加または変更されたレコードを示すブックマークを含む `COleVariant`。

### <a name="remarks"></a>解説

レコードセットオブジェクトを作成または開くと、そのレコードがサポートされている場合、そのレコードには一意のブックマークが既に存在します。 [GetBookmark](#getbookmark)を呼び出して、レコードセットがブックマークをサポートしているかどうかを確認します。 レコードセットでブックマークがサポートされていない場合は、`CDaoException` がスローされます。

レコードを追加すると、レコードはレコードセットの末尾に表示され、現在のレコードではなくなります。 新しいレコードを現在のレコードにするには、`GetLastModifiedBookmark` を呼び出し、`SetBookmark` を呼び出して新しく追加されたレコードに戻ります。

関連情報については、DAO ヘルプの「LastModified プロパティ」を参照してください。

##  <a name="getlockingmode"></a>CDaoRecordset:: Getロックモード

レコードセットに対して有効なロックの種類を決定するには、このメンバー関数を呼び出します。

```
BOOL GetLockingMode();
```

### <a name="return-value"></a>戻り値

ロックの種類がペシミスティックの場合は0以外。それ以外の場合は、オプティミスティックレコードロックの場合は0。

### <a name="remarks"></a>解説

ペシミスティックロックが有効になっている場合、編集するレコードを含むデータページは、 [Edit](#edit)メンバー関数を呼び出すとすぐにロックされます。 [Update](#update)または[Close](#close)メンバー関数、または Move または Find 操作のいずれかを呼び出すと、ページのロックが解除されます。

オプティミスティックロックが有効になっている場合、レコードを含むデータページは、`Update` メンバー関数でレコードが更新されている間だけロックされます。

ODBC データソースを使用する場合、ロックモードは常にオプティミスティックです。

関連情報については、DAO ヘルプの「LockEdits プロパティ」と「マルチユーザーアプリケーションでのロック動作」を参照してください。

##  <a name="getname"></a>CDaoRecordset:: GetName

このメンバー関数を呼び出して、レコードセットの名前を取得します。

```
CString GetName();
```

### <a name="return-value"></a>戻り値

レコードセットの名前を含む `CString` です。

### <a name="remarks"></a>解説

レコードセットの名前は、文字で始まる必要があり、最大40文字まで含めることができます。 数字とアンダースコア文字を含めることができますが、句読点やスペースを含めることはできません。

関連情報については、DAO ヘルプの「Name プロパティ」を参照してください。

##  <a name="getparamvalue"></a>CDaoRecordset:: GetParamValue

このメンバー関数を呼び出して、基になる DAOParameter オブジェクトに格納されている、指定したパラメーターの現在の値を取得します。

```
virtual COleVariant GetParamValue(int nIndex);
virtual COleVariant GetParamValue(LPCTSTR lpszName);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
基になる DAOParameter オブジェクト内のパラメーターの数値位置。

*lpszName*<br/>
値を設定するパラメーターの名前。

### <a name="return-value"></a>戻り値

パラメーターの値を格納している[COleVariant](../../mfc/reference/colevariant-class.md)クラスのオブジェクト。

### <a name="remarks"></a>解説

パラメーターには、名前またはコレクション内の数値の位置を使用してアクセスできます。

関連情報については、DAO ヘルプの「Parameter オブジェクト」を参照してください。

##  <a name="getpercentposition"></a>CDaoRecordset:: GetPercentPosition

ダイナセット型またはスナップショット型のレコードセットを使用する場合、レコードセットに完全に値を設定する前に `GetPercentPosition` を呼び出すと、移動の量は、 [GetRecordCount](#getrecordcount)を呼び出すことによって示されるようにアクセスされたレコードの数に対して相対的になります。

```
float GetPercentPosition();
```

### <a name="return-value"></a>戻り値

レコードセット内のレコードの割合に基づく、レコードセットオブジェクト内の現在のレコードのおおよその位置を示す 0 ~ 100 の数値。

### <a name="remarks"></a>解説

すべてのレコードセットの作成を完了するには、 [MoveLast](#movelast)を呼び出して最後のレコードに移動しますが、これにはかなりの時間がかかることがあります。

インデックスなしのテーブルを含め、3種類のレコードセットオブジェクトのすべてに対して `GetPercentPosition` を呼び出すことができます。 ただし、順方向専用スクロールスナップショット、または外部データベースに対するパススルークエリから開かれたレコードセットに対して `GetPercentPosition` を呼び出すことはできません。 現在のレコードが存在しない場合、または現在のレコードが削除されている場合は、`CDaoException` がスローされます。

関連情報については、DAO ヘルプの「PercentPosition プロパティ」を参照してください。

##  <a name="getrecordcount"></a>CDaoRecordset:: GetRecordCount

このメンバー関数を呼び出して、レコードセット内のアクセスされたレコードの数を確認します。

```
long GetRecordCount();
```

### <a name="return-value"></a>戻り値

レコードセットオブジェクト内でアクセスされたレコードの数を返します。

### <a name="remarks"></a>解説

`GetRecordCount` は、すべてのレコードがアクセスされるまで、ダイナセット型またはスナップショット型のレコードセットに含まれるレコード数を示しません。 このメンバー関数の呼び出しは、完了までにかなりの時間がかかる場合があります。

最後のレコードがアクセスされると、戻り値は、レコードセット内の未完了のレコードの合計数を示します。 最後のレコードへのアクセスを強制するには、レコードセットの `MoveLast` または `FindLast` メンバー関数を呼び出します。 また、SQL カウントを使用して、クエリが返すレコードの概数を指定することもできます。

アプリケーションがダイナセット型のレコードセット内のレコードを削除すると、`GetRecordCount` の戻り値が減少します。 ただし、他のユーザーによって削除されたレコードは、現在のレコードが削除されたレコードに配置されるまで、`GetRecordCount` によって反映されません。 レコード数に影響を与えるトランザクションを実行し、その後トランザクションをロールバックした場合、`GetRecordCount` には残りのレコードの実際の数は反映されません。

スナップショット型のレコードセットからの `GetRecordCount` の値は、基になるテーブルの変更の影響を受けません。

テーブル型のレコードセットの `GetRecordCount` の値は、テーブル内のレコードの概数を反映し、テーブルレコードが追加および削除されるとすぐに影響を受けます。

レコードのないレコードセットでは、値0が返されます。 アタッチされたテーブルまたは ODBC データベースを使用する場合、`GetRecordCount` は常に-1 を返します。 レコードセットの `Requery` メンバー関数を呼び出すと、クエリを再実行した場合と同じように `GetRecordCount` の値がリセットされます。

関連情報については、DAO ヘルプの「RecordCount プロパティ」を参照してください。

##  <a name="getsql"></a>CDaoRecordset:: GetSQL

レコードセットのレコードを開いたときにそのレコードを選択するために使用された SQL ステートメントを取得するには、このメンバー関数を呼び出します。

```
CString GetSQL() const;
```

### <a name="return-value"></a>戻り値

SQL ステートメントを含む `CString` です。

### <a name="remarks"></a>解説

通常、これは SQL **SELECT**ステートメントです。

`GetSQL` によって返される文字列は、通常、 [Open](#open)メンバー関数の*lpszSQL*パラメーターのレコードセットに渡された文字列とは異なります。 これは、`Open`に渡された内容に基づいて完全な SQL ステートメントが作成され、ClassWizard で指定したものと、 [m_strFilter](#m_strfilter)データメンバーと[m_strSort](#m_strsort)データメンバーで指定した内容に基づいて作成されるためです。

> [!NOTE]
>  `Open`を呼び出した後にのみ、このメンバー関数を呼び出します。

関連情報については、DAO ヘルプの「SQL プロパティ」を参照してください。

##  <a name="gettype"></a>CDaoRecordset:: GetType

レコードセットを開いた後、このメンバー関数を呼び出して、レコードセットオブジェクトの型を決定します。

```
short GetType();
```

### <a name="return-value"></a>戻り値

レコードセットの種類を示す次のいずれかの値です。

- `dbOpenTable` テーブル型のレコードセット

- `dbOpenDynaset` ダイナセット型のレコードセット

- `dbOpenSnapshot` スナップショット型のレコードセット

### <a name="remarks"></a>解説

関連情報については、DAO ヘルプの「Type プロパティ」を参照してください。

##  <a name="getvalidationrule"></a>CDaoRecordset:: GetValidationRule

データの検証に使用するルールを決定するには、このメンバー関数を呼び出します。

```
CString GetValidationRule();
```

### <a name="return-value"></a>戻り値

レコードが変更されたとき、またはテーブルに追加されたときに、レコード内のデータを検証する値を格納している `CString` オブジェクト。

### <a name="remarks"></a>解説

このルールはテキストベースで、基になるテーブルが変更されるたびに適用されます。 データが有効でない場合、MFC は例外をスローします。 返されるエラーメッセージは、基になるフィールドオブジェクトの "ValidationText" プロパティ、指定されている場合は、基になるフィールドオブジェクトの ValidationRule プロパティで指定された式のテキストです。 [Getvalidationtext](#getvalidationtext)を呼び出して、エラーメッセージのテキストを取得できます。

たとえば、月の日付を必要とするレコード内のフィールドには、"DAY BETWEEN 1 AND 31" などの検証ルールがある場合があります。

関連情報については、DAO ヘルプのトピック「ValidationRule プロパティ」を参照してください。

##  <a name="getvalidationtext"></a>CDaoRecordset:: GetValidationText

このメンバー関数を呼び出して、基になるフィールドオブジェクトの "ValidationText" プロパティのテキストを取得します。

```
CString GetValidationText();
```

### <a name="return-value"></a>戻り値

フィールドの値が基になるフィールドオブジェクトの検証規則を満たしていない場合に表示されるメッセージのテキストを格納している `CString` オブジェクト。

### <a name="remarks"></a>解説

関連情報については、DAO ヘルプのトピック「ValidationText プロパティ」を参照してください。

##  <a name="isbof"></a>CDaoRecordset:: IsBOF

レコードごとにスクロールしてレコードセットの最初のレコードの前に移動したかどうかを調べるには、このメンバー関数を呼び出します。

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>戻り値

レコードセットにレコードが含まれていない場合、または最初のレコードの前に後方にスクロールした場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

また、`IsEOF` と共に `IsBOF` を呼び出して、レコードセットにレコードが含まれているか、空であるかを確認することもできます。 `Open`を呼び出した直後、レコードセットにレコードが含まれていない場合、`IsBOF` は0以外の値を返します。 少なくとも1つのレコードを含むレコードセットを開くと、最初のレコードが現在のレコードになり、`IsBOF` 0 が返されます。

最初のレコードが現在のレコードで、`MovePrev`を呼び出すと、`IsBOF` は0以外の値を返します。 `IsBOF` が0以外の値を返し、`MovePrev`を呼び出すと、例外がスローされます。 `IsBOF` が0以外の値を返した場合、現在のレコードは未定義であり、現在のレコードを必要とするすべてのアクションで例外が発生します。

`IsBOF` および `IsEOF` 設定に対する特定のメソッドの影響:

- `Open*` を呼び出すと、`MoveFirst`を呼び出すことによってレコードセットの最初のレコードが現在のレコードになります。 したがって、空のレコードセットに対して `Open` を呼び出すと、`IsBOF` と `IsEOF` が0以外の値を返します。 (失敗した `MoveFirst` または `MoveLast` の呼び出しの動作については、次の表を参照してください。)

- レコードが正常に検索されたすべての移動操作では、`IsBOF` と `IsEOF` の両方が0を返します。

- `AddNew` の呼び出しの後に、新しいレコードを正常に挿入する `Update` 呼び出しがあると、`IsBOF` は0を返しますが、`IsEOF` が既に0以外の場合にのみ返されます。 `IsEOF` の状態は常に変更されません。 Microsoft Jet データベースエンジンで定義されているように、空のレコードセットの現在のレコードポインターはファイルの末尾にあるため、現在のレコードの後に新しいレコードが挿入されます。

- レコードセットから唯一のレコードを削除しても、`Delete` の呼び出しでは、`IsBOF` または `IsEOF`の値は変更されません。

次の表は、`IsBOF`/ `IsEOF`のさまざまな組み合わせで許可される移動操作を示しています。

||MoveFirst、MoveLast|MovePrev<br /><br /> < 0 に移動|0の移動|MoveNext<br /><br /> > 0 に移動|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`= 0 以外、<br /><br /> `IsEOF`=0|許可|例外|例外|許可|
|`IsBOF`=0,<br /><br /> `IsEOF`= 0 以外|許可|許可|例外|例外|
|両方0以外|例外|例外|例外|例外|
|両方0|許可|許可|許可|許可|

移動操作を許可しても、操作によってレコードが正常に検索されるとは限りません。 これは、指定された移動操作の実行が許可され、例外が生成されないことを示しているだけです。 `IsBOF` および `IsEOF` のメンバー関数の値は、移動しようとした結果として変更される可能性があります。

次の表に、`IsBOF` の値と `IsEOF` 設定の値についてレコードが見つからない移動操作の効果を示します。

||IsBOF|IsEOF|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|なら|なら|
|`Move` 0|変更なし|変更なし|
|`MovePrev`、`Move` < 0|なら|変更なし|
|`MoveNext`、`Move` > 0|変更なし|なら|

関連情報については、DAO ヘルプの「BOF、EOF プロパティ」を参照してください。

##  <a name="isdeleted"></a>CDaoRecordset:: IsDeleted

現在のレコードが削除されているかどうかを判断するには、このメンバー関数を呼び出します。

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>戻り値

レコードセットが削除されたレコードに配置されている場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

レコードまでスクロールし、`IsDeleted` が TRUE (0 以外) を返した場合は、他のレコードセット操作を実行する前に、別のレコードまでスクロールする必要があります。

> [!NOTE]
>  スナップショットまたはテーブル型のレコードセット内のレコードの削除された状態を確認する必要はありません。 レコードをスナップショットから削除することはできないため、`IsDeleted`を呼び出す必要はありません。 テーブル型のレコードセットの場合、削除されたレコードは実際にレコードセットから削除されます。 レコードが削除されると、ユーザー、別のユーザー、または別のレコードセットでレコードをスクロールできなくなります。 そのため、`IsDeleted`を呼び出す必要はありません。

ダイナセットからレコードを削除すると、レコードはレコードセットから削除され、そのレコードにスクロールすることはできません。 ただし、ダイナセット内のレコードが、別のユーザーまたは同じテーブルに基づく別のレコードセットによって削除された場合、`IsDeleted` は、後でそのレコードをスクロールするときに TRUE を返します。

関連情報については、DAO ヘルプの「Delete メソッド」、「LastModified プロパティ」、および「EditMode プロパティ」を参照してください。

##  <a name="iseof"></a>CDaoRecordset:: IsEOF

レコードごとにスクロールしてレコードセットの最後のレコードを超えたかどうかを確認するには、このメンバー関数を呼び出します。

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>戻り値

レコードセットにレコードが含まれていない場合、または最後のレコードを超えてスクロールした場合は0以外。それ以外の場合は0です。

### <a name="remarks"></a>解説

また、`IsEOF` を呼び出して、レコードセットにレコードが含まれているか、空であるかを確認することもできます。 `Open`を呼び出した直後、レコードセットにレコードが含まれていない場合、`IsEOF` は0以外の値を返します。 少なくとも1つのレコードを含むレコードセットを開くと、最初のレコードが現在のレコードになり、`IsEOF` 0 が返されます。

`MoveNext`を呼び出すと最後のレコードが現在のレコードの場合、`IsEOF` は0以外の値を返します。 `IsEOF` が0以外の値を返し、`MoveNext`を呼び出すと、例外がスローされます。 `IsEOF` が0以外の値を返した場合、現在のレコードは未定義であり、現在のレコードを必要とするすべてのアクションで例外が発生します。

`IsBOF` および `IsEOF` 設定に対する特定のメソッドの影響:

- `Open` を呼び出すと、`MoveFirst`を呼び出すことによってレコードセットの最初のレコードが現在のレコードになります。 したがって、空のレコードセットに対して `Open` を呼び出すと、`IsBOF` と `IsEOF` が0以外の値を返します。 (失敗した `MoveFirst` 呼び出しの動作については、次の表を参照してください。)

- レコードが正常に検索されたすべての移動操作では、`IsBOF` と `IsEOF` の両方が0を返します。

- `AddNew` の呼び出しの後に、新しいレコードを正常に挿入する `Update` 呼び出しがあると、`IsBOF` は0を返しますが、`IsEOF` が既に0以外の場合にのみ返されます。 `IsEOF` の状態は常に変更されません。 Microsoft Jet データベースエンジンで定義されているように、空のレコードセットの現在のレコードポインターはファイルの末尾にあるため、現在のレコードの後に新しいレコードが挿入されます。

- レコードセットから唯一のレコードを削除しても、`Delete` の呼び出しでは、`IsBOF` または `IsEOF`の値は変更されません。

次の表は、`IsBOF`/ `IsEOF`のさまざまな組み合わせで許可される移動操作を示しています。

||MoveFirst、MoveLast|MovePrev<br /><br /> < 0 に移動|0の移動|MoveNext<br /><br /> > 0 に移動|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`= 0 以外、<br /><br /> `IsEOF`=0|許可|例外|例外|許可|
|`IsBOF`=0,<br /><br /> `IsEOF`= 0 以外|許可|許可|例外|例外|
|両方0以外|例外|例外|例外|例外|
|両方0|許可|許可|許可|許可|

移動操作を許可しても、操作によってレコードが正常に検索されるとは限りません。 これは、指定された移動操作の実行が許可され、例外が生成されないことを示しているだけです。 `IsBOF` および `IsEOF` のメンバー関数の値は、移動しようとした結果として変更される可能性があります。

次の表に、`IsBOF` の値と `IsEOF` 設定の値についてレコードが見つからない移動操作の効果を示します。

||IsBOF|IsEOF|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|なら|なら|
|`Move` 0|変更なし|変更なし|
|`MovePrev`、`Move` < 0|なら|変更なし|
|`MoveNext`、`Move` > 0|変更なし|なら|

関連情報については、DAO ヘルプの「BOF、EOF プロパティ」を参照してください。

##  <a name="isfielddirty"></a>CDaoRecordset:: IsFieldDirty

このメンバー関数を呼び出して、指定したダイナセットのフィールドデータメンバーに "ダーティ" (変更) のフラグが設定されているかどうかを確認します。

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
状態を確認するフィールドデータメンバーへのポインター。または、いずれかのフィールドがダーティかどうかを判断する場合は NULL。

### <a name="return-value"></a>戻り値

指定されたフィールドデータメンバーにダーティのフラグが設定されている場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

すべてのダーティフィールドデータメンバーのデータは、現在のレコードが、`CDaoRecordset` の `Update` メンバー関数 (`Edit` または `AddNew`への呼び出しに従って) の呼び出しによって更新されたときに、データソースのレコードに転送されます。 この知識があれば、データソースに書き込まれないように列をマークするために、フィールドデータメンバーのフラグを解除するなど、さらに手順を実行できます。

`IsFieldDirty` は `DoFieldExchange`を通じて実装されます。

##  <a name="isfieldnull"></a>CDaoRecordset:: IsFieldNull

このメンバー関数を呼び出して、レコードセットの指定したフィールドデータメンバーに Null としてフラグが設定されているかどうかを確認します。

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
状態を確認するフィールドデータメンバーへのポインター。または、いずれかのフィールドが Null かどうかを判断する場合は NULL。

### <a name="return-value"></a>戻り値

指定されたフィールドデータメンバーに Null のフラグが設定されている場合は0以外の値。それ以外の場合は0です。

### <a name="remarks"></a>解説

(データベース用語では、Null は "値がありません" を意味し、でC++は null と同じではありません)。フィールドデータメンバーに Null のフラグが設定されている場合、そのメンバーは、値がない現在のレコードの列として解釈されます。

> [!NOTE]
>  特定の状況では、次のコード例に示すように、`IsFieldNull` を使用することは効率的ではありません。

[!code-cpp[NVC_MFCDatabase#5](../../mfc/codesnippet/cpp/cdaorecordset-class_5.cpp)]

> [!NOTE]
>  `CDaoRecordset`から派生せずに動的レコードバインディングを使用する場合は、例に示すように VT_NULL を使用するようにしてください。

##  <a name="isfieldnullable"></a>CDaoRecordset:: IsFieldNullable

このメンバー関数を呼び出して、指定されたフィールドデータメンバーが "nullable" である (Null 値に設定できる) かどうかを確認します。C++ Null は null と同じではありません。これは、データベース用語では、"値がない" ことを意味します。

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
状態を確認するフィールドデータメンバーへのポインター。または、いずれかのフィールドが Null かどうかを判断する場合は NULL。

### <a name="return-value"></a>戻り値

指定されたフィールドデータメンバーを Null にできる場合は0以外の値。それ以外の場合は0です。

### <a name="remarks"></a>解説

Null にできないフィールドには値が必要です。 レコードを追加または更新するときに、このようなフィールドを Null に設定しようとすると、データソースは追加または更新を拒否し、`Update` は例外をスローします。 この例外は、`SetFieldNull`を呼び出したときではなく `Update`を呼び出すと発生します。

##  <a name="isopen"></a>CDaoRecordset:: IsOpen

レコードセットが開いているかどうかを判断するには、このメンバー関数を呼び出します。

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>戻り値

レコードセットオブジェクトの `Open` または `Requery` メンバー関数が既に呼び出されていて、レコードセットが閉じられていない場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

##  <a name="m_bcheckcachefordirtyfields"></a>CDaoRecordset:: m_bCheckCacheForDirtyFields

キャッシュされたフィールドを自動的にダーティ (変更) と Null としてマークするかどうかを示すフラグを格納します。

### <a name="remarks"></a>解説

フラグの既定値は TRUE です。 このデータメンバーの設定は、ダブルバッファリング機構全体を制御します。 フラグを TRUE に設定した場合は、DFX 機構を使用して、フィールドごとにキャッシュを無効にすることができます。 フラグを FALSE に設定した場合は、`SetFieldDirty` を呼び出して自分で `SetFieldNull` する必要があります。

`Open`を呼び出す前に、このデータメンバーを設定してください。 このメカニズムは、主に使いやすさを目的としています。 フィールドのダブルバッファリングによって変更が行われるため、パフォーマンスが低下する可能性があります。

##  <a name="m_nfields"></a>CDaoRecordset:: m_nFields

レコードセットクラスのフィールドデータメンバーの数と、データソースからレコードセットによって選択された列の数を格納します。

### <a name="remarks"></a>解説

レコードセットクラスのコンストラクターは、静的にバインドされたフィールドの正しい数を使用して `m_nFields` を初期化する必要があります。 この初期化は、レコードセットクラスを宣言するために使用するときに ClassWizard によって書き込まれます。 また、手動で書き込むこともできます。

フレームワークは、この数値を使用して、フィールドデータメンバーと、データソースの現在のレコードの対応する列との間の対話を管理します。

> [!NOTE]
>  この数値は、パラメーター `CDaoFieldExchange::outputColumn`で `SetFieldType` を呼び出した後に `DoFieldExchange` に登録されている出力列の数に対応している必要があります。

`CDaoRecordset::GetFieldValue` と `CDaoRecordset::SetFieldValue`の方法によって、列を動的にバインドできます。 この場合、`DoFieldExchange` メンバー関数内の DFX 関数呼び出しの数を反映するために `m_nFields` のカウントをインクリメントする必要はありません。

##  <a name="m_nparams"></a>CDaoRecordset:: m_nParams

レコードセットクラスのパラメーターデータメンバーの数 (レコードセットのクエリで渡されるパラメーターの数) を格納します。

### <a name="remarks"></a>解説

レコードセットクラスにパラメーターデータメンバーが含まれている場合、クラスのコンストラクターは、正しい数値を使用して*m_nParams*を初期化する必要があります。 *M_nParams*の値の既定値は0です。 手動で行う必要があるパラメーターデータメンバーを追加する場合は、パラメーターの数を反映するために、クラスコンストラクターに初期化を手動で追加する必要もあります (これは、 *m_strFilter*または*m_strSort*文字列の ' ' プレースホルダーの数と少なくとも同じである必要があります)。

フレームワークは、レコードセットのクエリをパラメーター化するときに、この数値を使用します。

> [!NOTE]
>  この数値は、パラメーター `CFieldExchange::param`で `SetFieldType` を呼び出した後に `DoFieldExchange` に登録された "params" の数に対応している必要があります。

関連情報については、DAO ヘルプの「Parameter オブジェクト」を参照してください。

##  <a name="m_pdaorecordset"></a>CDaoRecordset:: m_pDAORecordset

`CDaoRecordset` オブジェクトの基になる DAO レコードセットオブジェクトの OLE インターフェイスへのポインターを格納します。

### <a name="remarks"></a>解説

DAO インターフェイスに直接アクセスする必要がある場合は、このポインターを使用します。

関連情報については、DAO ヘルプの「レコードセットオブジェクト」を参照してください。

##  <a name="m_pdatabase"></a>CDaoRecordset:: m_pDatabase

レコードセットをデータソースに接続するために使用する `CDaoDatabase` オブジェクトへのポインターを格納します。

### <a name="remarks"></a>解説

この変数は2つの方法で設定されます。 通常は、レコードセットオブジェクトを構築するときに、既に開いている `CDaoDatabase` オブジェクトへのポインターを渡します。 代わりに NULL を渡すと、`CDaoRecordset` によって `CDaoDatabase` オブジェクトが作成されて開きます。 どちらの場合も、`CDaoRecordset` によってこの変数にポインターが格納されます。

通常は、`m_pDatabase`に格納されているポインターを直接使用する必要はありません。 ただし、独自の拡張機能を `CDaoRecordset`に記述する場合は、ポインターを使用する必要がある場合があります。 たとえば、独自の `CDaoException`をスローする場合は、ポインターが必要になることがあります。

関連情報については、DAO ヘルプの「データベースオブジェクト」を参照してください。

##  <a name="m_strfilter"></a>CDaoRecordset:: m_strFilter

SQL ステートメントの**where**句を構築するために使用される文字列が含まれています。

### <a name="remarks"></a>解説

これには、レコードセットをフィルター**選択するための予約**語は含まれません。 このデータメンバーの使用は、テーブル型のレコードセットには適用されません。 `m_strFilter` の使用は、`CDaoQueryDef` ポインターを使用してレコードセットを開くときには効果がありません。

米国の Microsoft Jet データベースエンジンを使用していない場合でも、日付が含まれているフィールドにフィルターを適用するときは、米国の日付形式 (月-日-年) を使用します。そうしないと、意図したとおりにデータがフィルター処理されない可能性があります。

関連情報については、DAO ヘルプの「Filter プロパティ」を参照してください。

##  <a name="m_strsort"></a>CDaoRecordset:: m_strSort

予約語の**orderby**を使用せずに、SQL ステートメントの**orderby**句を含む文字列を格納します。

### <a name="remarks"></a>解説

ダイナセットおよびスナップショット型のレコードセットオブジェクトを基準にして並べ替えることができます。

テーブル型のレコードセットオブジェクトを並べ替えることはできません。 テーブル型のレコードセットの並べ替え順序を決定するには、 [SetCurrentIndex](#setcurrentindex)を呼び出します。

*M_strSort*の使用は、`CDaoQueryDef` ポインターを使用してレコードセットを開くときには効果がありません。

関連情報については、DAO ヘルプの「Sort プロパティ」を参照してください。

##  <a name="move"></a>CDaoRecordset:: Move

現在のレコードからレコードセットの*Lrows*レコードを配置するには、このメンバー関数を呼び出します。

```
virtual void Move(long lRows);
```

### <a name="parameters"></a>パラメーター

*lRows*<br/>
前方または後方に移動するレコードの数。 正の値は、レコードセットの末尾に向かって前方に移動します。 負の値は、先頭に向かって後方に移動します。

### <a name="remarks"></a>解説

前方または後方に移動できます。 `Move( 1 )` は `MoveNext`に相当し、`Move( -1 )` は `MovePrev`に相当します。

> [!CAUTION]
>  レコードセットにレコードがない場合は、`Move` 関数のいずれかを呼び出すと例外がスローされます。 一般に、移動操作の前に `IsBOF` と `IsEOF` の両方を呼び出して、レコードセットにレコードがあるかどうかを確認します。 `Open` または `Requery`を呼び出した後、`IsBOF` または `IsEOF`を呼び出します。

> [!NOTE]
>  レコードセットの先頭または末尾を超えてスクロールした場合 (`IsBOF` または `IsEOF` が0以外の値を返した場合)、`Move` を呼び出すと `CDaoException`がスローされます。

> [!NOTE]
>  現在のレコードを更新または追加しているときに `Move` 関数のいずれかを呼び出すと、警告なしに更新が失われます。

順方向専用スクロールスナップショットで `Move` を呼び出す場合、 *Lrows*パラメーターは正の整数である必要があります。ブックマークは許可されないため、先に進むことができます。

レコードセット内の最初、最後、次のレコード、または前のレコードを現在のレコードにするには、`MoveFirst`、`MoveLast`、`MoveNext`、または `MovePrev` のメンバー関数を呼び出します。

関連情報については、DAO ヘルプの「Move メソッド」と「MoveFirst、MoveLast、MoveNext、MovePrevious メソッド」を参照してください。

##  <a name="movefirst"></a>CDaoRecordset:: MoveFirst

このメンバー関数を呼び出して、レコードセット内の最初のレコード (存在する場合) を現在のレコードにします。

```
void MoveFirst();
```

### <a name="remarks"></a>解説

レコードセットを開いた直後に `MoveFirst` を呼び出す必要はありません。 その時点で、最初のレコード (存在する場合) が自動的に現在のレコードになります。

> [!CAUTION]
>  レコードセットにレコードがない場合は、`Move` 関数のいずれかを呼び出すと例外がスローされます。 一般に、移動操作の前に `IsBOF` と `IsEOF` の両方を呼び出して、レコードセットにレコードがあるかどうかを確認します。 `Open` または `Requery`を呼び出した後、`IsBOF` または `IsEOF`を呼び出します。

> [!NOTE]
>  現在のレコードを更新または追加しているときに `Move` 関数のいずれかを呼び出すと、警告なしに更新が失われます。

`Move` 関数を使用すると、条件を適用せずにレコード間を移動できます。 特定の条件を満たす、ダイナセット型またはスナップショット型のレコードセットオブジェクト内のレコードを検索するには、検索操作を使用します。 テーブル型の recordset オブジェクト内のレコードを検索するには、`Seek`を呼び出します。

レコードセットがテーブル型のレコードセットを参照する場合、移動はテーブルの現在のインデックスに従います。 現在のインデックスを設定するには、基になる DAO オブジェクトの Index プロパティを使用します。 現在のインデックスを設定しない場合、返されるレコードの順序は定義されません。

SQL クエリまたはクエリ定義に基づいてレコードセットオブジェクトの `MoveLast` を呼び出すと、クエリが強制的に完了し、レコードセットオブジェクトに完全に値が設定されます。

前方参照専用のスクロールスナップショットを使用して `MoveFirst` または `MovePrev` メンバー関数を呼び出すことはできません。

レコードセットオブジェクトの現在のレコードの位置を、特定の数のレコードを前方または後方に移動するには、`Move`を呼び出します。

関連情報については、DAO ヘルプの「Move メソッド」と「MoveFirst、MoveLast、MoveNext、MovePrevious メソッド」を参照してください。

##  <a name="movelast"></a>CDaoRecordset:: MoveLast

このメンバー関数を呼び出して、レコードセット内の最後のレコード (存在する場合) を現在のレコードにします。

```
void MoveLast();
```

### <a name="remarks"></a>解説

> [!CAUTION]
>  レコードセットにレコードがない場合は、`Move` 関数のいずれかを呼び出すと例外がスローされます。 一般に、移動操作の前に `IsBOF` と `IsEOF` の両方を呼び出して、レコードセットにレコードがあるかどうかを確認します。 `Open` または `Requery`を呼び出した後、`IsBOF` または `IsEOF`を呼び出します。

> [!NOTE]
>  現在のレコードを更新または追加しているときに `Move` 関数のいずれかを呼び出すと、警告なしに更新が失われます。

`Move` 関数を使用すると、条件を適用せずにレコード間を移動できます。 特定の条件を満たす、ダイナセット型またはスナップショット型のレコードセットオブジェクト内のレコードを検索するには、検索操作を使用します。 テーブル型の recordset オブジェクト内のレコードを検索するには、`Seek`を呼び出します。

レコードセットがテーブル型のレコードセットを参照する場合、移動はテーブルの現在のインデックスに従います。 現在のインデックスを設定するには、基になる DAO オブジェクトの Index プロパティを使用します。 現在のインデックスを設定しない場合、返されるレコードの順序は定義されません。

SQL クエリまたはクエリ定義に基づいてレコードセットオブジェクトの `MoveLast` を呼び出すと、クエリが強制的に完了し、レコードセットオブジェクトに完全に値が設定されます。

レコードセットオブジェクトの現在のレコードの位置を、特定の数のレコードを前方または後方に移動するには、`Move`を呼び出します。

関連情報については、DAO ヘルプの「Move メソッド」と「MoveFirst、MoveLast、MoveNext、MovePrevious メソッド」を参照してください。

##  <a name="movenext"></a>CDaoRecordset:: MoveNext

このメンバー関数を呼び出して、レコードセット内の次のレコードを現在のレコードにします。

```
void MoveNext();
```

### <a name="remarks"></a>解説

前のレコードに移動する前に、`IsBOF` を呼び出すことをお勧めします。 `IsBOF` が0以外の値を返した場合、`MovePrev` を呼び出すと、`CDaoException` がスローされます。これは、最初のレコードの前に既にスクロールしているか、レコードセットによってレコードが選択されていないかを示します。

> [!CAUTION]
>  レコードセットにレコードがない場合は、`Move` 関数のいずれかを呼び出すと例外がスローされます。 一般に、移動操作の前に `IsBOF` と `IsEOF` の両方を呼び出して、レコードセットにレコードがあるかどうかを確認します。 `Open` または `Requery`を呼び出した後、`IsBOF` または `IsEOF`を呼び出します。

> [!NOTE]
>  現在のレコードを更新または追加しているときに `Move` 関数のいずれかを呼び出すと、警告なしに更新が失われます。

`Move` 関数を使用すると、条件を適用せずにレコード間を移動できます。 特定の条件を満たす、ダイナセット型またはスナップショット型のレコードセットオブジェクト内のレコードを検索するには、検索操作を使用します。 テーブル型の recordset オブジェクト内のレコードを検索するには、`Seek`を呼び出します。

レコードセットがテーブル型のレコードセットを参照する場合、移動はテーブルの現在のインデックスに従います。 現在のインデックスを設定するには、基になる DAO オブジェクトの Index プロパティを使用します。 現在のインデックスを設定しない場合、返されるレコードの順序は定義されません。

レコードセットオブジェクトの現在のレコードの位置を、特定の数のレコードを前方または後方に移動するには、`Move`を呼び出します。

関連情報については、DAO ヘルプの「Move メソッド」と「MoveFirst、MoveLast、MoveNext、MovePrevious メソッド」を参照してください。

##  <a name="moveprev"></a>CDaoRecordset:: MovePrev

このメンバー関数を呼び出して、レコードセット内の前のレコードを現在のレコードにします。

```
void MovePrev();
```

### <a name="remarks"></a>解説

前のレコードに移動する前に、`IsBOF` を呼び出すことをお勧めします。 `IsBOF` が0以外の値を返した場合、`MovePrev` を呼び出すと、`CDaoException` がスローされます。これは、最初のレコードの前に既にスクロールしているか、レコードセットによってレコードが選択されていないかを示します。

> [!CAUTION]
>  レコードセットにレコードがない場合は、`Move` 関数のいずれかを呼び出すと例外がスローされます。 一般に、移動操作の前に `IsBOF` と `IsEOF` の両方を呼び出して、レコードセットにレコードがあるかどうかを確認します。 `Open` または `Requery`を呼び出した後、`IsBOF` または `IsEOF`を呼び出します。

> [!NOTE]
>  現在のレコードを更新または追加しているときに `Move` 関数のいずれかを呼び出すと、警告なしに更新が失われます。

`Move` 関数を使用すると、条件を適用せずにレコード間を移動できます。 特定の条件を満たす、ダイナセット型またはスナップショット型のレコードセットオブジェクト内のレコードを検索するには、検索操作を使用します。 テーブル型の recordset オブジェクト内のレコードを検索するには、`Seek`を呼び出します。

レコードセットがテーブル型のレコードセットを参照する場合、移動はテーブルの現在のインデックスに従います。 現在のインデックスを設定するには、基になる DAO オブジェクトの Index プロパティを使用します。 現在のインデックスを設定しない場合、返されるレコードの順序は定義されません。

前方参照専用のスクロールスナップショットを使用して `MoveFirst` または `MovePrev` メンバー関数を呼び出すことはできません。

レコードセットオブジェクトの現在のレコードの位置を、特定の数のレコードを前方または後方に移動するには、`Move`を呼び出します。

関連情報については、DAO ヘルプの「Move メソッド」と「MoveFirst、MoveLast、MoveNext、MovePrevious メソッド」を参照してください。

##  <a name="open"></a>CDaoRecordset:: Open

レコードセットのレコードを取得するには、このメンバー関数を呼び出す必要があります。

```
virtual void Open(
    int nOpenType = AFX_DAO_USE_DEFAULT_TYPE,
    LPCTSTR lpszSQL = NULL,
    int nOptions = 0);

virtual void Open(
    CDaoTableDef* pTableDef,
    int nOpenType = dbOpenTable,
    int nOptions = 0);

virtual void Open(
    CDaoQueryDef* pQueryDef,
    int nOpenType = dbOpenDynaset,
    int nOptions = 0);
```

### <a name="parameters"></a>パラメーター

*Noて Type*<br/>
次のいずれかの値:

- 双方向スクロールを使用して、ダイナセット型のレコードセットを `dbOpenDynaset` します。 これは既定値です。

- 双方向スクロールを使用してテーブル型のレコードセットを `dbOpenTable` します。

- 双方向スクロールを使用して、スナップショット型のレコードセットを `dbOpenSnapshot` します。

*lpszSQL*<br/>
次のいずれかを含む文字列ポインター:

- NULL ポインター。

- 1つ以上のテーブル名またはクエリ名 (コンマ区切り)。

- SQL **SELECT**ステートメント (必要に応じて、sql **WHERE**句または**ORDERBY**句を使用します)。

- パススルークエリ。

*nOptions*<br/>
以下に一覧表示されている1つ以上のオプション。 既定値は 0 です。 次の値を指定できます。

- `dbAppendOnly` 新しいレコードのみを追加できます (ダイナセット型のレコードセットのみ)。 このオプションは、レコードが追加されるだけであることを意味します。 MFC ODBC データベースクラスには追加専用のオプションがあり、レコードを取得して追加することができます。

- レコードセットは、順方向専用スクロールスナップショットで `dbForwardOnly` ます。

- 別のユーザーが編集中のデータを変更している場合は、`dbSeeChanges` によって例外が生成されます。

- `dbDenyWrite` 他のユーザーがレコードを変更または追加することはできません。

- 他のユーザー `dbDenyRead` レコードを表示することはできません (テーブル型のレコードセットのみ)。

- `dbReadOnly` レコードのみを表示できます。他のユーザーが変更できます。

- `dbInconsistent` の不整合な更新が許可されます (ダイナセット型のレコードセットのみ)。

- `dbConsistent` 一貫性のある更新プログラムのみが許可されます (ダイナセット型のレコードセットのみ)。

> [!NOTE]
>  定数 `dbConsistent` と `dbInconsistent` は相互に排他的です。 どちらか一方を使用できますが、`Open`の特定のインスタンスで両方を使用することはできません。

*pTableDef*<br/>
[CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)オブジェクトへのポインター。 このバージョンは、テーブル型のレコードセットに対してのみ有効です。 このオプションを使用する場合、`CDaoRecordset` の構築に使用される `CDaoDatabase` ポインターは使用されません。代わりに、tabledef が存在するデータベースが使用されます。

*pQueryDef*<br/>
[CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)オブジェクトへのポインター。 このバージョンは、ダイナセット型およびスナップショット型のレコードセットに対してのみ有効です。 このオプションを使用する場合、`CDaoRecordset` の構築に使用される `CDaoDatabase` ポインターは使用されません。代わりに、クエリ定義が存在するデータベースが使用されます。

### <a name="remarks"></a>解説

`Open`を呼び出す前に、レコードセットオブジェクトを作成する必要があります。 これにはいくつかの方法があります。

- レコードセットオブジェクトを構築する場合は、既に開いている `CDaoDatabase` オブジェクトへのポインターを渡します。

- レコードセットオブジェクトを構築するときに、開かれていない `CDaoDatabase` オブジェクトへのポインターを渡します。 レコードセットは `CDaoDatabase` オブジェクトを開きますが、レコードセットオブジェクトを閉じるときにはオブジェクトを閉じません。

- レコードセットオブジェクトを作成する場合は、NULL ポインターを渡します。 レコードセットオブジェクトは、`GetDefaultDBName` を呼び出して、Microsoft Access の名前を取得します。開く MDB ファイル。 その後、レコードセットは `CDaoDatabase` オブジェクトを開き、レコードセットが開いている間は開いたままにします。 レコードセットで `Close` を呼び出すと、`CDaoDatabase` オブジェクトも閉じられます。

    > [!NOTE]
    >  レコードセットによって `CDaoDatabase` オブジェクトが開かれると、非排他アクセスでデータソースが開かれます。

*LpszSQL*パラメーターを使用するバージョンの `Open` では、レコードセットが開かれると、いくつかの方法のいずれかでレコードを取得できます。 最初のオプションは、`DoFieldExchange`で DFX 関数を使用する方法です。 2つ目の方法は、`GetFieldValue` メンバー関数を呼び出すことによって動的バインドを使用することです。 これらのオプションは、個別に、または組み合わせて実装できます。 これらを組み合わせて使用する場合は、`Open`を呼び出すことによって、SQL ステートメントを自分で渡す必要があります。

`CDaoTableDef` オブジェクトを渡す `Open` の2番目のバージョンを使用すると、結果として得られる列は `DoFieldExchange` および DFX 機構を介してバインドしたり、`GetFieldValue`を使用して動的にバインドしたりすることができます。

> [!NOTE]
>  `Open` を呼び出すことができるのは、テーブル型のレコードセットに対して `CDaoTableDef` オブジェクトを使用する場合だけです。

`CDaoQueryDef` オブジェクトを渡す `Open` の3番目のバージョンを使用すると、そのクエリが実行され、`DoFieldExchange` および DFX のメカニズムを使用してバインドしたり、`GetFieldValue`を使用して動的にバインドしたりできるようになります。

> [!NOTE]
>  `Open` を呼び出すことができるのは、ダイナセット型とスナップショット型のレコードセットに対して `CDaoQueryDef` オブジェクトを使用する場合だけです。

`lpszSQL` パラメーターを使用する `Open` の最初のバージョンでは、次の表に示す条件に基づいてレコードが選択されます。

|パラメーター `lpszSQL` の値。|レコードの選択基準|例|
|--------------------------------------|----------------------------------------|-------------|
|NULL|`GetDefaultSQL` の返す文字列。||
|1つまたは複数のテーブル名またはその両方の名前のコンマ区切りのリスト。|`DoFieldExchange`で表されるすべての列。|`"Customer"`|
|テーブルリスト**から**列リストを**選択し**ます|指定された tabledef または querydef から指定された列。|`"SELECT CustId, CustName`<br /><br /> `FROM Customer"`|

通常の手順では、NULL を `Open`に渡します。この場合、`Open` は `GetDefaultSQL`を呼び出します。これは、ClassWizard が `CDaoRecordset`派生クラスを作成するときに生成するオーバーライド可能なメンバー関数です。 この値は、ClassWizard で指定したテーブル名またはクエリ名 (またはその両方) を示します。 代わりに、 *lpszSQL*パラメーターで他の情報を指定することもできます。

どのような場合でも、`Open` は、クエリの最終的な SQL 文字列を構築します (文字列には、渡された*lpszSQL*文字列に Sql の**WHERE**句と**ORDERBY**句が追加されている場合があります)。その後、クエリを実行します。 `Open`を呼び出した後に `GetSQL` を呼び出すことによって、構築された文字列を調べることができます。

レコードセット クラスのフィールド データ メンバーは、選択したデータの列に結び付けられています。 いくつかのレコードが返された場合、最初のレコードが現在のレコードになります。

フィルターや並べ替えなどのレコードセットのオプションを設定する場合は、レコードセットオブジェクトを作成した後、`Open`を呼び出す前に、`m_strSort` または `m_strFilter` を設定します。 レコードセットが既に開いた後でレコードセット内のレコードを更新する場合は、`Requery`を呼び出します。

ダイナセット型またはスナップショット型のレコードセットで `Open` を呼び出す場合、またはデータソースが、アタッチされたテーブルを表す SQL ステートメントまたはテーブルセットを参照している場合は、型引数に `dbOpenTable` を使用することはできません。この場合、MFC は例外をスローします。 Tabledef オブジェクトがアタッチされたテーブルを表すかどうかを確認するには、 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)オブジェクトを作成し、その[getconnect](../../mfc/reference/cdaotabledef-class.md#getconnect)メンバー関数を呼び出します。

同じレコードを編集または削除するときに、コンピューター上の別のユーザーまたは別のプログラムによって行われた変更をトラップする場合は、`dbSeeChanges` フラグを使用します。 たとえば、2人のユーザーが同じレコードの編集を開始した場合、最初のユーザーが `Update` メンバー関数を呼び出すと成功します。 2番目のユーザーによって `Update` が呼び出されると、`CDaoException` がスローされます。 同様に、2番目のユーザーが `Delete` を呼び出してレコードを削除しようとし、そのレコードが最初のユーザーによって既に変更されている場合、`CDaoException` が発生します。

通常、更新中にユーザーがこの `CDaoException` を取得した場合は、コードでフィールドの内容を更新し、新しく変更された値を取得する必要があります。 削除処理中に例外が発生した場合、コードによって、新しいレコードデータがユーザーに表示され、データが最近変更されたことを示すメッセージが表示されることがあります。 この時点で、コードは、ユーザーがレコードを削除しようとしていることを確認するメッセージを要求できます。

> [!TIP]
>  アプリケーションが ODBC データソースから開かれたレコードセットをパススルーするときにパフォーマンスを向上させるには、順方向専用スクロールオプション (`dbForwardOnly`) を使用します。

関連情報については、DAO ヘルプの「OpenRecordset メソッド」を参照してください。

##  <a name="requery"></a>CDaoRecordset:: Requery

このメンバー関数を呼び出して、レコードセットを再構築 (更新) します。

```
virtual void Requery();
```

### <a name="remarks"></a>解説

いくつかのレコードが返された場合、最初のレコードが現在のレコードになります。

ユーザーまたは他のユーザーがデータソースに対して行った追加や削除をレコードセットに反映させるには、`Requery`を呼び出してレコードセットを再構築する必要があります。 レコードセットがダイナセットである場合は、自分または他のユーザーが既存のレコードに対して行った更新が自動的に反映されます (ただし、追加することはできません)。 レコードセットがスナップショットの場合は、`Requery` を呼び出して、他のユーザーによる編集と、追加や削除を反映する必要があります。

ダイナセットまたはスナップショットの場合は、パラメーター値を使用してレコードセットを再構築するときに、いつでも `Requery` を呼び出します。 `Requery`を呼び出す前に[m_strFilter](#m_strfilter)と[m_strSort](#m_strsort)を設定して、新しいフィルターまたは並べ替えを設定します。 `Requery`を呼び出す前に、パラメーターデータメンバーに新しい値を割り当てることによって、新しいパラメーターを設定します。

レコードセットを再構築しようとして失敗した場合、レコードセットは閉じられます。 `Requery`を呼び出す前に、 [Canrestart](#canrestart)メンバー関数を呼び出して、レコードセットを再クエリできるかどうかを判断できます。 `CanRestart` では、`Requery` が成功するとは限りません。

> [!CAUTION]
>  `Open`を呼び出した後にのみ `Requery` を呼び出します。

> [!NOTE]
>  [Requery](#requery)を呼び出すと、DAO ブックマークが変更します。

`CanRestart` が0を返す場合、またはテーブル型のレコードセットで使用できない場合は、ダイナセット型またはスナップショット型のレコードセットで `Requery` を呼び出すことはできません。

`Requery`を呼び出した後に `IsBOF` と `IsEOF` の両方が0以外の値を返した場合、クエリはレコードを返さなかったため、レコードセットにはデータが含まれません。

関連情報については、DAO ヘルプの「Requery メソッド」を参照してください。

##  <a name="seek"></a>CDaoRecordset:: Seek

このメンバー関数を呼び出して、インデックス付きテーブル型 recordset オブジェクト内の、現在のインデックスに指定した条件を満たすレコードを検索し、そのレコードを現在のレコードにします。

```
BOOL Seek(
    LPCTSTR lpszComparison,
    COleVariant* pKey1,
    COleVariant* pKey2 = NULL,
    COleVariant* pKey3 = NULL);

BOOL Seek(
    LPCTSTR lpszComparison,
    COleVariant* pKeyArray,
    WORD nKeys);
```

### <a name="parameters"></a>パラメーター

*lpszComparison*<br/>
次のいずれかの文字列式: "<"、"\<="、"="、"> ="、または ">"。

*pKey1*<br/>
インデックスの最初のフィールドに値が対応する[COleVariant](../../mfc/reference/colevariant-class.md)へのポインター。 必須。

*pKey2*<br/>
インデックスの2番目のフィールド (存在する場合) に対応する値を持つ `COleVariant` へのポインター。 既定値は NULL です。

*pKey3*<br/>
インデックスの3番目のフィールド (存在する場合) に対応する値を持つ `COleVariant` へのポインター。 既定値は NULL です。

*pKeyArray*<br/>
バリアントの配列へのポインター。 配列のサイズは、インデックス内のフィールドの数に対応しています。

*nKeys*<br/>
配列のサイズに対応する整数。インデックス内のフィールド数です。

> [!NOTE]
>  キーにはワイルドカードを指定しないでください。 ワイルドカードを `Seek` すると、一致するレコードは返されません。

### <a name="return-value"></a>戻り値

一致するレコードが見つかった場合は0以外。それ以外の場合は0。

### <a name="remarks"></a>解説

2つ目の (配列) バージョンの `Seek` を使用して、4つ以上のフィールドのインデックスを処理します。

`Seek` を使用すると、テーブル型のレコードセットに対して高パフォーマンスのインデックス検索を実行できます。 `Seek`を呼び出す前に `SetCurrentIndex` を呼び出して、現在のインデックスを設定する必要があります。 インデックスが一意でないキーフィールドを識別する場合、`Seek` は条件を満たす最初のレコードを検索します。 インデックスを設定しないと、例外がスローされます。

UNICODE レコードセットを作成しない場合は、`COleVariant` オブジェクトを明示的に ANSI として宣言する必要があることに注意してください。 これを行うには、 *vtsrc*を `VT_BSTRT` (ANSI) に設定したコンストラクターの[COleVariant:: COleVariant](../../mfc/reference/colevariant-class.md#colevariant) **(** *lpszsrc* **,** *vtsrc* **)** 形式を使用するか、 *vtsrc*を `VT_BSTRT`に設定した `COleVariant` 関数[setstring](../../mfc/reference/colevariant-class.md#setstring) **(** *lpszsrc* **、** *vtsrc* **)** を使用します。

`Seek`を呼び出すときに、1つ以上のキー値と比較演算子 ("<"、"\<="、"="、"> ="、または ">") を渡します。 `Seek` は、指定されたキーフィールドを検索し、 *Lpszcomparison*および*pKey1*によって指定された条件を満たす最初のレコードを検索します。 見つかった場合、`Seek` は0以外の値を返し、そのレコードを現在のものにします。 `Seek` が一致の検索に失敗した場合、`Seek` は0を返し、現在のレコードは未定義になります。 DAO を直接使用する場合は、NoMatch プロパティを明示的に確認する必要があります。

`lpszComparison` が "="、"> ="、または ">" の場合、`Seek` はインデックスの先頭から開始されます。 *Lpszcomparison*が "<" または "< =" の場合、`Seek` はインデックスの末尾から開始し、最後に重複するインデックスエントリがない限り、後方に検索します。 この場合、`Seek` は、インデックスの末尾にある重複するインデックスエントリの中から任意のエントリから開始されます。

`Seek`を使用する場合、現在のレコードである必要はありません。

特定の条件を満たす、ダイナセット型またはスナップショット型のレコードセット内のレコードを検索するには、検索操作を使用します。 特定の条件を満たすレコードだけでなく、すべてのレコードを含めるには、移動操作を使用してレコード間を移動します。

アタッチされたテーブルは、ダイナセット型またはスナップショット型のレコードセットとして開く必要があるため、任意の型のアタッチされたテーブルで `Seek` を呼び出すことはできません。 ただし、インストール可能な ISAM データベースを直接開くために `CDaoDatabase::Open` を呼び出すと、そのデータベース内のテーブルに対して `Seek` を呼び出すことができますが、パフォーマンスは低下する可能性があります。

関連情報については、DAO ヘルプの「Seek メソッド」を参照してください。

##  <a name="setabsoluteposition"></a>CDaoRecordset:: SetAbsolutePosition

レコードセットオブジェクトの現在のレコードの相対レコード番号を設定します。

```
void SetAbsolutePosition(long lPosition);
```

### <a name="parameters"></a>パラメーター

*lPosition*<br/>
レコードセット内の現在のレコードの序数位置に対応します。

### <a name="remarks"></a>解説

`SetAbsolutePosition` を呼び出すと、ダイナセット型またはスナップショット型のレコードセット内の序数位置に基づいて、特定のレコードへの現在のレコードポインターを配置できます。 [GetAbsolutePosition](#getabsoluteposition)を呼び出すことによって、現在のレコード番号を確認することもできます。

> [!NOTE]
>  このメンバー関数は、ダイナセット型およびスナップショット型のレコードセットに対してのみ有効です。

基になる DAO オブジェクトの AbsolutePosition プロパティの値は0から始まります。0に設定すると、レコードセットの最初のレコードが参照されます。 設定されたレコードの数を超える値を設定すると、MFC は例外をスローします。 `GetRecordCount` メンバー関数を呼び出すことによって、レコードセット内の設定されたレコードの数を確認できます。

現在のレコードが削除されると、AbsolutePosition プロパティの値が定義されず、MFC が参照されている場合は例外がスローされます。 新しいレコードがシーケンスの最後に追加されます。

> [!NOTE]
>  このプロパティは、サロゲートレコード番号として使用するためのものではありません。 ブックマークは、指定された位置に保持して返すことをお勧めします。ブックマークをサポートするすべての種類のレコードセットオブジェクトに対して現在のレコードを配置する唯一の方法です。 特に、指定されたレコードの位置は、先行するレコードが削除されると変更されます。 また、 **ORDERBY**句を使用して SQL ステートメントで作成された場合を除き、レコードセット内の個々のレコードの順序は保証されないため、レコードセットを再作成した場合、特定のレコードの絶対位置が同じであることは保証されません。

関連情報については、DAO ヘルプの「AbsolutePosition プロパティ」を参照してください。

##  <a name="setbookmark"></a>CDaoRecordset:: SetBookmark

このメンバー関数を呼び出して、指定したブックマークを含むレコードにレコードセットを配置します。

```
void SetBookmark(COleVariant varBookmark);
```

### <a name="parameters"></a>パラメーター

*varBookmark*<br/>
特定のレコードのブックマーク値を格納している[COleVariant](../../mfc/reference/colevariant-class.md)オブジェクト。

### <a name="remarks"></a>解説

レコードセットオブジェクトを作成または開くと、そのレコードにはそれぞれ一意のブックマークが既に存在します。 `GetBookmark` を呼び出し、`COleVariant` オブジェクトに値を保存することにより、現在のレコードのブックマークを取得できます。 保存されているブックマーク値を使用して `SetBookmark` を呼び出すことにより、後でそのレコードに戻ることができます。

> [!NOTE]
>  [Requery](#requery)を呼び出すと、DAO ブックマークが変更します。

UNICODE レコードセットを作成しない場合は、`COleVariant` オブジェクトを明示的に ANSI として宣言する必要があることに注意してください。 これを行うには、 *vtsrc*を `VT_BSTRT` (ANSI) に設定したコンストラクターの[COleVariant:: COleVariant](../../mfc/reference/colevariant-class.md#colevariant) **(** *lpszsrc* **,** *vtsrc* **)** 形式を使用するか、 *vtsrc*を `VT_BSTRT`に設定した `COleVariant` 関数[setstring](../../mfc/reference/colevariant-class.md#setstring) **(** *lpszsrc* **、** *vtsrc* **)** を使用します。

関連情報については、DAO ヘルプの「Bookmark プロパティ」および「Bookmarkable プロパティ」を参照してください。

##  <a name="setcachesize"></a>CDaoRecordset:: SetCacheSize

キャッシュするレコードの数を設定するには、このメンバー関数を呼び出します。

```
void SetCacheSize(long lSize);
```

### <a name="parameters"></a>パラメーター

*lSize*<br/>
レコードの数を指定します。 一般的な値は100です。 0に設定すると、キャッシュは無効になります。 5 ~ 1200 のレコードを設定する必要があります。 キャッシュでは、大量のメモリを使用する場合があります。

### <a name="remarks"></a>解説

キャッシュとは、アプリケーションの実行中にデータが再度要求される場合に、サーバーから最後に取得されたデータを保持するローカルメモリ内の領域です。 データキャッシュを使用すると、ダイナセット型のレコードセットオブジェクトを介してリモートサーバーからデータを取得するアプリケーションのパフォーマンスが向上します。 データが要求されると、Microsoft Jet データベースエンジンは、要求されたデータをサーバーから取得するのではなく、最初にキャッシュを確認します。これには時間がかかります。 ODBC データソースから取得されていないデータはキャッシュに保存されません。

アタッチされたテーブルなどの ODBC データソースは、ローカルキャッシュを持つことができます。 キャッシュを作成するには、リモートデータソースからレコードセットオブジェクトを開き、`SetCacheSize` と `SetCacheStart` のメンバー関数を呼び出した後、`FillCache` のメンバー関数を呼び出すか、移動操作のいずれかを使用してレコードをステップ実行します。 `SetCacheSize` メンバー関数の*Lsize*パラメーターは、アプリケーションが同時に処理できるレコードの数に基づいている場合があります。 たとえば、画面に表示されるデータのソースとしてレコードセットを使用している場合、`SetCacheSize` *Lsize*パラメーターを20として渡すことで、一度に20個のレコードを表示できます。

関連情報については、DAO ヘルプの「CacheSize、CacheStart プロパティ」を参照してください。

##  <a name="setcachestart"></a>CDaoRecordset:: SetCacheStart

キャッシュされるレコードセット内の最初のレコードのブックマークを指定するには、このメンバー関数を呼び出します。

```
void SetCacheStart(COleVariant varBookmark);
```

### <a name="parameters"></a>パラメーター

*varBookmark*<br/>
キャッシュされるレコードセット内の最初のレコードのブックマークを指定する[COleVariant](../../mfc/reference/colevariant-class.md) 。

### <a name="remarks"></a>解説

`SetCacheStart` メンバー関数の*varbookmark*パラメーターには、任意のレコードの bookmark 値を使用できます。 現在のレコードでキャッシュを開始するレコードを作成し、 [SetBookmark](#setbookmark)を使用してそのレコードのブックマークを確立し、ブックマークの値を `SetCacheStart` メンバー関数のパラメーターとして渡します。

Microsoft Jet データベースエンジンはキャッシュからキャッシュ範囲内のレコードを要求し、サーバーからキャッシュ範囲外のレコードを要求します。

キャッシュから取得されたレコードには、他のユーザーによってソースデータに同時に加えられた変更は反映されません。

キャッシュされたすべてのデータを強制的に更新するには、`SetCacheSize` の*Lsize*パラメーターを0として渡し、最初に要求したキャッシュのサイズで `SetCacheSize` を再度呼び出してから、`FillCache` メンバー関数を呼び出します。

UNICODE レコードセットを作成しない場合は、`COleVariant` オブジェクトを明示的に ANSI として宣言する必要があることに注意してください。 これを行うには、 *vtsrc*を `VT_BSTRT` (ANSI) に設定したコンストラクターの[COleVariant:: COleVariant](../../mfc/reference/colevariant-class.md#colevariant) **(** *lpszsrc* **,** *vtsrc* **)** 形式を使用するか、 *vtsrc*を `VT_BSTRT`に設定した `COleVariant` 関数[setstring](../../mfc/reference/colevariant-class.md#setstring) **(** *lpszsrc* **、** *vtsrc* **)** を使用します。

関連情報については、DAO ヘルプの「CacheSize、CacheStart プロパティ」を参照してください。

##  <a name="setcurrentindex"></a>CDaoRecordset:: SetCurrentIndex

テーブル型のレコードセットにインデックスを設定するには、このメンバー関数を呼び出します。

```
void SetCurrentIndex(LPCTSTR lpszIndex);
```

### <a name="parameters"></a>パラメーター

*lpszIndex*<br/>
設定するインデックスの名前を格納しているポインター。

### <a name="remarks"></a>解説

ベーステーブル内のレコードは、特定の順序では保存されません。 インデックスを設定すると、データベースから返されるレコードの順序が変わりますが、レコードが格納される順序には影響しません。 指定されたインデックスは既に定義されている必要があります。 存在しないインデックスオブジェクトを使用しようとした場合、または[Seek](#seek)を呼び出したときにインデックスが設定されていない場合、MFC は例外をスローします。

[CDaoTableDef:: CreateIndex](../../mfc/reference/cdaotabledef-class.md#createindex)を呼び出し、基になるテーブルグループの Indexes コレクションに新しいインデックスを追加することによって、テーブルの新しいインデックスを作成できます。そのためには、 [CDaoTableDef:: Append](../../mfc/reference/cdaotabledef-class.md#append)を呼び出し、レコードセットを再度開きます。

テーブル型のレコードセットから返されるレコードは、基になるテーブルテーブルに対して定義されているインデックスによってのみ並べ替えることができます。 他の順序でレコードを並べ替えるには、 [CDaoRecordset:: m_strSort](#m_strsort)に格納されている SQL **ORDERBY**句を使用して、ダイナセット型またはスナップショット型のレコードセットを開くことができます。

関連情報については、DAO ヘルプの「Index オブジェクト」と「現在のインデックス」を参照してください。

##  <a name="setfielddirty"></a>CDaoRecordset:: SetFieldDirty

このメンバー関数を呼び出して、レコードセットのフィールドデータメンバーに、変更済みまたは変更なしとしてフラグを付けます。

```
void SetFieldDirty(
    void* pv,
    BOOL bDirty = TRUE);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
レコードセットのフィールドデータメンバーのアドレス、または NULL を格納します。 NULL の場合、レコードセット内のすべてのフィールドデータメンバーにフラグが設定されます。 (C++ Null はデータベース用語では null と同じではなく、"値がない" ことを意味します)。

*bDirty*<br/>
フィールドデータメンバーに "ダーティ" としてフラグを設定する場合は TRUE (変更された場合)。 それ以外の場合は、フィールドデータメンバーに "clean" (変更なし) のフラグを設定する場合は FALSE。

### <a name="remarks"></a>解説

フィールドを変更せずにマークすると、フィールドは更新されません。

フレームワークは、変更されたフィールドデータメンバーを、DAO レコードフィールドエクスチェンジ (DFX) メカニズムによってデータソースのレコードに書き込まれるようにマークします。 フィールドの値を変更すると、通常はダーティフィールドが自動的にダーティに設定されるため、`SetFieldDirty` を自分で呼び出す必要はほとんどありませんが、フィールドデータメンバー内の値に関係なく、明示的に列が更新または挿入されるようにすることが必要になる場合があります。 DFX のメカニズムでは、PSEUDONULL を使用することもできます。 詳細については、「 [CDaoFieldExchange:: m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)」を参照してください。

ダブルバッファリング機構が使用されていない場合は、フィールドの値を変更しても、フィールドがダーティとして自動的に設定されるわけではありません。 この場合は、フィールドをダーティとして明示的に設定する必要があります。 [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)に含まれるフラグは、この自動フィールドチェックを制御します。

> [!NOTE]
>  このメンバー関数は、 [Edit](#edit)または[AddNew](#addnew)を呼び出した後にのみ呼び出してください。

関数の最初の引数に NULL を使用すると、`CDaoFieldExchange`の**param**フィールドではなく、すべての `outputColumn` フィールドに関数が適用されます。 たとえば、

[!code-cpp[NVC_MFCDatabase#6](../../mfc/codesnippet/cpp/cdaorecordset-class_6.cpp)]

`outputColumn` フィールドのみを NULL に設定します。**param**フィールドは影響を受けません。

**パラメーター**を操作するには、次のように、使用する個々の**パラメーター**の実際のアドレスを指定する必要があります。

[!code-cpp[NVC_MFCDatabase#7](../../mfc/codesnippet/cpp/cdaorecordset-class_7.cpp)]

これは、`outputColumn` フィールドの場合と同様に、すべての**param**フィールドを NULL に設定することができないことを意味します。

`SetFieldDirty` は `DoFieldExchange`を通じて実装されます。

##  <a name="setfieldnull"></a>CDaoRecordset:: SetFieldNull

このメンバー関数を呼び出して、レコードセットのフィールドデータメンバーに Null (特に値がない) または非 Null としてフラグを付けます。

```
void SetFieldNull(
    void* pv,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>パラメーター

*pv*<br/>
レコードセットのフィールドデータメンバーのアドレス、または NULL を格納します。 NULL の場合、レコードセット内のすべてのフィールドデータメンバーにフラグが設定されます。 (C++ Null はデータベース用語では null と同じではなく、"値がない" ことを意味します)。

*bNull*<br/>
フィールドデータメンバーに値がないことを示すフラグが設定されている場合は0以外 (Null)。 それ以外の場合は、フィールドデータメンバーに Null 以外のフラグが設定されている場合は0になります。

### <a name="remarks"></a>解説

`SetFieldNull` は、`DoFieldExchange` メカニズムでバインドされたフィールドに使用されます。

レコードセットに新しいレコードを追加すると、すべてのフィールドデータメンバーは最初に Null 値に設定され、"ダーティ" (変更) としてフラグが設定されます。 データソースからレコードを取得する場合、その列には既に値があるか、または Null になります。 フィールドを Null にするのが適切でない場合は、 [CDaoException](../../mfc/reference/cdaoexception-class.md)がスローされます。

たとえば、ダブルバッファリング機構を使用している場合、たとえば、現在のレコードのフィールドに値を設定しないように指定する場合は、 *Bnull*を TRUE に設定して `SetFieldNull` を呼び出し、null としてフラグを設定します。 フィールドが以前は Null とマークされていて、値を指定する必要がある場合は、単に新しい値を設定します。 `SetFieldNull`で Null フラグを削除する必要はありません。 フィールドを Null にできるかどうかを判断するには、 [IsFieldNullable](#isfieldnullable)を呼び出します。

ダブルバッファリング機構を使用していない場合は、フィールドの値を変更しても、フィールドがダーティおよび Null 以外の値として自動的に設定されることはありません。 具体的には、フィールドをダーティおよび非 Null に設定する必要があります。 [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)に含まれるフラグは、この自動フィールドチェックを制御します。

DFX のメカニズムでは、PSEUDONULL を使用します。 詳細については、「 [CDaoFieldExchange:: m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)」を参照してください。

> [!NOTE]
>  このメンバー関数は、 [Edit](#edit)または[AddNew](#addnew)を呼び出した後にのみ呼び出してください。

関数の最初の引数に NULL を使用すると、関数が `CDaoFieldExchange`の**param**フィールドではなく `outputColumn` フィールドにのみ適用されます。 たとえば、

[!code-cpp[NVC_MFCDatabase#8](../../mfc/codesnippet/cpp/cdaorecordset-class_8.cpp)]

`outputColumn` フィールドのみを NULL に設定します。**param**フィールドは影響を受けません。

##  <a name="setfieldvalue"></a>CDaoRecordset:: SetFieldValue

序数位置によって、または文字列の値を変更することによって、フィールドの値を設定するには、このメンバー関数を呼び出します。

```
virtual void SetFieldValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);

virtual void SetFieldValue(
    int nIndex,
    const COleVariant& varValue);

void SetFieldValue(
    LPCTSTR lpszName,
    LPCTSTR lpszValue);

void SetFieldValue(
    int nIndex,
    LPCTSTR lpszValue);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
フィールドの名前を格納している文字列へのポインター。

*varValue*<br/>
フィールドの内容の値を格納している[COleVariant](../../mfc/reference/colevariant-class.md)オブジェクトへの参照。

*nIndex*<br/>
レコードセットの Fields コレクション内のフィールドの序数位置を表す整数 (0 から始まります)。

*lpszValue*<br/>
フィールドの内容の値を格納している文字列へのポインター。

### <a name="remarks"></a>解説

`SetFieldValue` と[GetFieldValue](#getfieldvalue)を使用して、 [DoFieldExchange](#dofieldexchange)メカニズムを使用して静的に列をバインドするのではなく、実行時にフィールドを動的にバインドします。

UNICODE レコードセットを作成していない場合は、`COleVariant` パラメーターを含まない形式の `SetFieldValue` を使用するか、`COleVariant` オブジェクトを明示的に ANSI として宣言する必要があることに注意してください。 これを行うには、 *vtsrc*を `VT_BSTRT` (ANSI) に設定したコンストラクターの[COleVariant:: COleVariant](../../mfc/reference/colevariant-class.md#colevariant) **(** *lpszsrc* **,** *vtsrc* **)** 形式を使用するか、 *vtsrc*を `VT_BSTRT`に設定した `COleVariant` 関数[setstring](../../mfc/reference/colevariant-class.md#setstring) **(** *lpszsrc* **、** *vtsrc* **)** を使用します。

関連情報については、DAO ヘルプの「フィールドオブジェクト」と「値プロパティ」を参照してください。

##  <a name="setfieldvaluenull"></a>CDaoRecordset:: SetFieldValueNull

このメンバー関数を呼び出して、フィールドを Null 値に設定します。

```
void SetFieldValueNull(int nIndex);
void SetFieldValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
レコードセット内のフィールドのインデックス。0から始まるインデックスによって検索されます。

*lpszName*<br/>
名前で検索するための、レコードセット内のフィールドの名前。

### <a name="remarks"></a>解説

C++NULL は Null と同じではありません。データベース用語では、"値がありません" という意味になります。

関連情報については、DAO ヘルプの「フィールドオブジェクト」と「値プロパティ」を参照してください。

##  <a name="setlockingmode"></a>CDaoRecordset:: Setロックモード

レコードセットのロックの種類を設定するには、このメンバー関数を呼び出します。

```
void SetLockingMode(BOOL bPessimistic);
```

### <a name="parameters"></a>パラメーター

*bPessimistic*<br/>
ロックの種類を示すフラグ。

### <a name="remarks"></a>解説

ペシミスティックロックが有効になっている場合、編集しようとしているレコードを含む2Kb ページは、`Edit` メンバー関数を呼び出すとすぐにロックされます。 `Update` または `Close` メンバー関数、または Move 操作または Find 操作のいずれかを呼び出すと、ページのロックが解除されます。

オプティミスティックロックが有効になっている場合、レコードを含む2Kb ページは、レコードが `Update` メンバー関数で更新されている間だけロックされます。

ページがロックされている場合、他のユーザーが同じページ上のレコードを編集することはできません。 `SetLockingMode` を呼び出し、0以外の値を渡すと、別のユーザーが既にページをロックしている場合、`Edit`を呼び出すと例外がスローされます。 他のユーザーは、ロックされたページからデータを読み取ることができます。

0の値を指定して `SetLockingMode` を呼び出した後に `Update` を呼び出したときに、別のユーザーによってページがロックされている場合、例外が発生します。 別のユーザーによってレコードに加えられた変更を表示する (および変更を破棄する) には、現在のレコードの bookmark 値を使用して `SetBookmark` メンバー関数を呼び出します。

ODBC データソースを使用する場合、ロックモードは常にオプティミスティックです。

##  <a name="setparamvalue"></a>CDaoRecordset:: SetParamValue

実行時にレコードセットのパラメーターの値を設定するには、このメンバー関数を呼び出します。

```
virtual void SetParamValue(
    int nIndex,
    const COleVariant& varValue);

virtual void SetParamValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
クエリ定義の Parameters コレクション内のパラメーターの数値位置。

*var*<br/>
設定する値。「解説」を参照してください。

*lpszName*<br/>
値を設定するパラメーターの名前。

### <a name="remarks"></a>解説

パラメーターは、レコードセットの SQL 文字列の一部として既に設定されている必要があります。 パラメーターには、名前またはコレクション内のインデックス位置によってアクセスできます。

`COleVariant` オブジェクトとして設定する値を指定します。 `COleVariant` オブジェクトでの必要な値と型の設定の詳細については、「クラス[COleVariant](../../mfc/reference/colevariant-class.md)」を参照してください。 UNICODE レコードセットを作成しない場合は、`COleVariant` オブジェクトを明示的に ANSI として宣言する必要があることに注意してください。 これを行うには、 *vtsrc*を `VT_BSTRT` (ANSI) に設定したコンストラクターの[COleVariant:: COleVariant](../../mfc/reference/colevariant-class.md#colevariant) **(** *lpszsrc* **,** *vtsrc* **)** 形式を使用するか、 *vtsrc*を `VT_BSTRT`に設定した `COleVariant` 関数[setstring](../../mfc/reference/colevariant-class.md#setstring) **(** *lpszsrc* **、** *vtsrc* **)** を使用します。

##  <a name="setparamvaluenull"></a>CDaoRecordset:: SetParamValueNull

パラメーターを Null 値に設定するには、このメンバー関数を呼び出します。

```
void SetParamValueNull(int nIndex);
void SetParamValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
レコードセット内のフィールドのインデックス。0から始まるインデックスによって検索されます。

*lpszName*<br/>
名前で検索するための、レコードセット内のフィールドの名前。

### <a name="remarks"></a>解説

C++NULL は Null と同じではありません。データベース用語では、"値がありません" という意味になります。

##  <a name="setpercentposition"></a>CDaoRecordset:: SetPercentPosition

レコードセット内のレコードの割合に基づいて、レコードセットオブジェクトの現在のレコードのおおよその位置を変更する値を設定するには、このメンバー関数を呼び出します。

```
void SetPercentPosition(float fPosition);
```

### <a name="parameters"></a>パラメーター

*fPosition*<br/>
0 ～ 100 の値。

### <a name="remarks"></a>解説

ダイナセット型またはスナップショット型のレコードセットを使用する場合は、最初に、`SetPercentPosition`を呼び出す前に最後のレコードに移動してレコードセットを設定します。 レコードセットを完全に作成する前に `SetPercentPosition` を呼び出した場合、移動の量は、 [GetRecordCount](#getrecordcount)の値によって示されているように、アクセスされたレコードの数に対して相対的になります。 `MoveLast`を呼び出すことによって、最後のレコードに移動できます。

`SetPercentPosition`を呼び出すと、その値に対応するおおよその位置にあるレコードが最新の状態になります。

> [!NOTE]
>  現在のレコードをレコードセット内の特定のレコードに移動するために `SetPercentPosition` を呼び出すことは推奨されません。 代わりに、 [SetBookmark](#setbookmark)メンバー関数を呼び出してください。

関連情報については、DAO ヘルプの「PercentPosition プロパティ」を参照してください。

##  <a name="update"></a>CDaoRecordset:: Update

`AddNew` または `Edit` メンバー関数の呼び出しの後に、このメンバー関数を呼び出します。

```
virtual void Update();
```

### <a name="remarks"></a>解説

この呼び出しは、`AddNew` または `Edit` 操作を完了するために必要です。

`AddNew` と `Edit` はどちらも、データソースに保存するために追加または編集されたデータを格納する編集バッファーを準備します。 `Update` によってデータが保存されます。 変更済みとしてマークまたは検出されたフィールドのみが更新されます。

データソースでトランザクションがサポートされている場合は、トランザクションの `Update` 呼び出し (およびそれに対応する `AddNew` または `Edit` 呼び出し) を行うことができます。

> [!CAUTION]
> 最初に `AddNew` または `Edit`を呼び出さずに `Update` を呼び出すと、`Update` は `CDaoException`をスローします。 `AddNew` または `Edit`を呼び出す場合は、 [MoveNext](#movenext)を呼び出す前、またはレコードセットまたはデータソース接続を閉じる前に `Update` を呼び出す必要があります。 そうしないと、変更内容が通知なしに失われます。

マルチユーザー環境でレコードセットオブジェクトが pessimistically にロックされている場合、レコードは、更新が完了するまで `Edit` が使用された時点からロックされたままになります。 レコードセットがオプティミスティックでロックされている場合、レコードはロックされ、データベース内で更新される直前に、編集前のレコードと比較されます。 `Edit`を呼び出した後にレコードが変更された場合、`Update` 操作は失敗し、MFC は例外をスローします。 ロックモードは、`SetLockingMode`で変更できます。

> [!NOTE]
> オプティミスティックロックは、ODBC やインストール可能な ISAM などの外部データベース形式で常に使用されます。

関連情報については、DAO ヘルプの「AddNew メソッド」、「CancelUpdate メソッド」、「Delete メソッド」、「LastModified プロパティ」、「Update メソッド」、および「EditMode プロパティ」を参照してください。

## <a name="see-also"></a>参照

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CDaoTableDef クラス](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoWorkspace クラス](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)<br/>
