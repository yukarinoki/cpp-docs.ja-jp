---
title: CDaoRecordset クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0c7090940699894e6b868c246d90a9c85a8b2795
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956038"
---
# <a name="cdaorecordset-class"></a>CDaoRecordset クラス
データ ソースから選択された 1 組のレコードセットを表現します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDaoRecordset : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoRecordset::CDaoRecordset](#cdaorecordset)|`CDaoRecordset` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoRecordset::AddNew](#addnew)|新しいレコードを追加する準備をします。 呼び出す[更新](#update)追加を完了します。|  
|[CDaoRecordset::CanAppend](#canappend)|使用して、レコード セットに新しいレコードを追加する場合は 0 以外を返します、 [AddNew](#addnew)メンバー関数。|  
|[CDaoRecordset::CanBookmark](#canbookmark)|レコード セットは、ブックマークをサポートする場合は 0 以外を返します。|  
|[CDaoRecordset::CancelUpdate](#cancelupdate)|キャンセルの理由のため、保留中の更新プログラム、[編集](#edit)または[AddNew](#addnew)操作します。|  
|[CDaoRecordset::CanRestart](#canrestart)|場合は 0 以外を返します[Requery](#requery)レコード セットのクエリを再実行を呼び出すことができます。|  
|[CDaoRecordset::CanScroll](#canscroll)|レコード間をスクロールできる場合は 0 以外を返します。|  
|[CDaoRecordset::CanTransact](#cantransact)|データ ソースには、トランザクションがサポートしている場合は 0 以外を返します。|  
|[CDaoRecordset::CanUpdate](#canupdate)|レコード セットを更新する場合は 0 以外を返します (することができますを追加、更新、またはレコードを削除) します。|  
|[CDaoRecordset::Close](#close)|レコード セットを閉じます。|  
|[CDaoRecordset::Delete](#delete)|レコード セットから現在のレコードを削除します。 削除された後は、別のレコードに明示的にスクロールする必要があります。|  
|[CDaoRecordset::DoFieldExchange](#dofieldexchange)|レコード セットのフィールド データ メンバーと、データ ソースに対応するレコードの間で (双方向) のデータを交換するには、呼び出されます。 レコード フィールド エクス (チェンジ DFX) を実装 DAO です。|  
|[CDaoRecordset::Edit](#edit)|現在のレコードへの変更を準備します。 呼び出す`Update`編集を完了します。|  
|[CDaoRecordset::FillCache](#fillcache)|すべての塗りつぶしまたは ODBC データ ソースからデータを含むレコード セット オブジェクトのローカル キャッシュの一部です。|  
|[CDaoRecordset::Find](#find)|最初に、[次へ] を検索し、特定の文字列を指定された条件と、そのレコードを現在のレコードを満たすダイナセット タイプのレコード セット内の前、または最後の位置。|  
|[CDaoRecordset::FindFirst](#findfirst)|ダイナセット型またはレコードを指定された条件と、そのレコードを現在のレコードを満たす最初のレコードを検索します。|  
|[CDaoRecordset::FindLast](#findlast)|ダイナセットの種類またはスナップショットの種類のレコード セット、指定された条件と、そのレコードを現在のレコード内の最後のレコードを検索します。|  
|[CDaoRecordset::FindNext](#findnext)|ダイナセットの種類またはスナップショットの種類のレコード セット、指定された条件と、そのレコードを現在のレコード内の次のレコードを検索します。|  
|[CDaoRecordset::FindPrev](#findprev)|ダイナセット型またはレコードを指定された条件と、そのレコードを現在のレコードを満たすには、前のレコードを検索します。|  
|[CDaoRecordset::GetAbsolutePosition](#getabsoluteposition)|レコード セット オブジェクトの現在のレコードのレコード数を返します。|  
|[CDaoRecordset::GetBookmark](#getbookmark)|レコードのブックマークを表す値を返します。|  
|[CDaoRecordset::GetCacheSize](#getcachesize)|ODBC データ ソースからローカルにキャッシュされたデータを含むダイナセット タイプのレコード セット内のレコードの数を示す値を返します。|  
|[CDaoRecordset::GetCacheStart](#getcachestart)|キャッシュするレコード セットの最初のレコード、ブックマークを示す値を返します。|  
|[CDaoRecordset::GetCurrentIndex](#getcurrentindex)|返します、`CString`最近にインデックスの名前を含むインデックスが設定されたテーブル タイプで使用される`CDaoRecordset`です。|  
|[CDaoRecordset::GetDateCreated](#getdatecreated)|基になるベース テーブルの日付と時刻を返します、`CDaoRecordset`オブジェクトが作成されました|  
|[CDaoRecordset::GetDateLastUpdated](#getdatelastupdated)|基になるベース テーブルのデザインに加えられた最近の変更日時を返します、`CDaoRecordset`オブジェクト。|  
|[CDaoRecordset::GetDefaultDBName](#getdefaultdbname)|既定のデータ ソースの名前を返します。|  
|[CDaoRecordset::GetDefaultSQL](#getdefaultsql)|実行する既定の SQL 文字列を取得するには、呼び出されます。|  
|[CDaoRecordset::GetEditMode](#geteditmode)|現在のレコードの編集状態を示す値を返します。|  
|[CDaoRecordset::GetFieldCount](#getfieldcount)|レコード セット内のフィールドの数を表す値を返します。|  
|[CDaoRecordset::GetFieldInfo](#getfieldinfo)|レコード セットの特定の種類のフィールドに関する情報を返します。|  
|[CDaoRecordset::GetFieldValue](#getfieldvalue)|レコード セット内のフィールドの値を返します。|  
|[CDaoRecordset::GetIndexCount](#getindexcount)|レコード セットを基になるテーブル内のインデックスの数を取得します。|  
|[CDaoRecordset::GetIndexInfo](#getindexinfo)|さまざまな種類のインデックスについての情報を返します。|  
|[CDaoRecordset::GetLastModifiedBookmark](#getlastmodifiedbookmark)|最後に追加またはレコードの更新を判断するために使用します。|  
|[CDaoRecordset::GetLockingMode](#getlockingmode)|編集中に有効になっているロックの種類を示す値を返します。|  
|[CDaoRecordset::GetName](#getname)|返します、`CString`レコード セットの名前を含むです。|  
|[CDaoRecordset::GetParamValue](#getparamvalue)|基になる DAOParameter オブジェクトに格納されている指定されたパラメーターの現在の値を取得します。|  
|[CDaoRecordset::GetPercentPosition](#getpercentposition)|現在のレコードのレコードの総数の割合としての位置を返します。|  
|[CDaoRecordset::GetRecordCount](#getrecordcount)|レコード セット オブジェクトにアクセスするレコードの数を返します。|  
|[CDaoRecordset::GetSQL](#getsql)|レコード セットのレコードを選択するために使用する SQL 文字列を取得します。|  
|[CDaoRecordset::GetType](#gettype)|レコード セットの種類を決定するために呼び出さ: テーブルの種類、ダイナセット型、またはスナップショットの種類。|  
|[CDaoRecordset::GetValidationRule](#getvalidationrule)|返します、`CString`フィールドに入力されたデータを検証する値を格納します。|  
|[CDaoRecordset::GetValidationText](#getvalidationtext)|検証規則が満たされていない場合に表示されるテキストを取得します。|  
|[CDaoRecordset::IsBOF](#isbof)|レコード セットは、最初のレコードの前に位置付けられている場合は 0 以外を返します。 現在のレコードがありません。|  
|[CDaoRecordset::IsDeleted](#isdeleted)|レコード セットが削除されたレコードに配置されている場合は 0 以外を返します。|  
|[CDaoRecordset::IsEOF](#iseof)|レコード セットは、後の最後のレコードに位置付けられている場合は 0 以外を返します。 現在のレコードがありません。|  
|[CDaoRecordset::IsFieldDirty](#isfielddirty)|現在のレコードで指定されたフィールドが変更された場合は 0 以外を返します。|  
|[CDaoRecordset::IsFieldNull](#isfieldnull)|現在のレコードで指定されたフィールドが Null (には、値がない) 場合は 0 以外を返します。|  
|[CDaoRecordset::IsFieldNullable](#isfieldnullable)|現在のレコードで指定したフィールドを Null に設定する (値がない) 場合は 0 以外を返します。|  
|[CDaoRecordset::IsOpen](#isopen)|場合は 0 以外を返します[開く](#open)既に呼び出されています。|  
|[CDaoRecordset::Move](#move)|どちらの方向に現在のレコードから指定した数のレコードに、レコード セットを配置します。|  
|[CDaoRecordset::MoveFirst](#movefirst)|レコード セットの最初のレコードの現在のレコードを配置します。|  
|[CDaoRecordset::MoveLast](#movelast)|レコード セットの最後のレコードの現在のレコードを配置します。|  
|[CDaoRecordset::MoveNext](#movenext)|レコード セットの次のレコードの現在のレコードを配置します。|  
|[CDaoRecordset::MovePrev](#moveprev)|レコード セットの前のレコードの現在のレコードを配置します。|  
|[Cdaorecordset::open](#open)|テーブル、ダイナセット、またはスナップショットから新しいレコード セットを作成します。|  
|[CDaoRecordset::Requery](#requery)|選択したレコードを更新するには、もう一度、レコード セットのクエリを実行します。|  
|[CDaoRecordset::Seek](#seek)|現在のインデックスと、そのレコードを現在のレコードの指定した条件を満たすインデックス付きのテーブル型のレコード セット オブジェクト内のレコードを検索します。|  
|[CDaoRecordset::SetAbsolutePosition](#setabsoluteposition)|レコード セット オブジェクトの現在のレコードのレコード数を設定します。|  
|[CDaoRecordset::SetBookmark](#setbookmark)|指定されたブックマークを含むレコードをレコード セットに配置します。|  
|[CDaoRecordset::SetCacheSize](#setcachesize)|ODBC データ ソースからローカルにキャッシュされたデータを含むダイナセット タイプのレコード セット内のレコードの数を示す値を設定します。|  
|[CDaoRecordset::SetCacheStart](#setcachestart)|キャッシュするレコード セット内の最初のレコード、ブックマークを示す値を設定します。|  
|[CDaoRecordset::SetCurrentIndex](#setcurrentindex)|テーブル型のレコード セットのインデックスを設定すると呼ばれます。|  
|[CDaoRecordset::SetFieldDirty](#setfielddirty)|変更されると、現在のレコードで指定したフィールドをマークします。|  
|[CDaoRecordset::SetFieldNull](#setfieldnull)|Null (値を持たない) を現在のレコードで指定されたフィールドの値を設定します。|  
|[たび](#setfieldvalue)|レコード セットのフィールドの値を設定します。|  
|[CDaoRecordset::SetFieldValueNull](#setfieldvaluenull)|Null をレコード セット内のフィールドの値を設定します。 (値を持たない)。|  
|[CDaoRecordset::SetLockingMode](#setlockingmode)|編集中に有効にするロックの種類を示す値を設定します。|  
|[CDaoRecordset::SetParamValue](#setparamvalue)|基になる DAOParameter オブジェクトに格納されている指定されたパラメーターの現在の値を設定します。|  
|[CDaoRecordset::SetParamValueNull](#setparamvaluenull)|Null (値を持たない) を指定されたパラメーターの現在の値を設定します。|  
|[CDaoRecordset::SetPercentPosition](#setpercentposition)|レコード セット内のレコードの合計数の割合に対応する位置を現在のレコードの位置を設定します。|  
|[CDaoRecordset::Update](#update)|完了、`AddNew`または`Edit`データ ソースで新しいまたは更新されたデータを保存することで操作します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoRecordset::m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)|フィールドの変更は自動的にマークするかどうかを示すフラグが含まれています。|  
|[CDaoRecordset::m_nFields](#m_nfields)|レコード セット クラスのフィールド データ メンバーの数と、データ ソースからレコード セットが選択した列の数が含まれています。|  
|[CDaoRecordset::m_nParams](#m_nparams)|レコード セット クラスのパラメーター データ メンバーの数が含まれています: レコード セットのクエリで渡されるパラメーターの数|  
|[CDaoRecordset::m_pDAORecordset](#m_pdaorecordset)|レコード セット オブジェクトを基になる DAO インターフェイスへのポインター。|  
|[CDaoRecordset::m_pDatabase](#m_pdatabase)|この結果セットのソース データベースです。 ポインターが含まれています、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクト。|  
|[CDaoRecordset::m_strFilter](#m_strfilter)|SQL を構築するために使用される文字列を含む**場所**ステートメントです。|  
|[CDaoRecordset::m_strSort](#m_strsort)|SQL を構築するために使用される文字列を含む**ORDER BY**ステートメントです。|  
  
## <a name="remarks"></a>Remarks  
 「レコード セット」と呼ばれる`CDaoRecordset`オブジェクトは、次の 3 つの形式で使用できます。  
  
-   テーブル型のレコード セットは、ベース テーブルを調べる、追加、変更、または単一のデータベース テーブルからレコードを削除に使用できるを表します。  
  
-   ダイナセット タイプは、更新可能なレコードを持つことができるクエリの結果です。 これらのレコード セットは、調べる、追加、変更、または、基になるデータベース テーブルまたはテーブルからレコードを削除に使用できるレコードのセットです。 ダイナセット タイプは、データベース内の 1 つまたは複数のテーブルのフィールドを含めることができます。  
  
-   スナップショットの種類のレコード セットは、一連のデータの検索や、レポートの生成に使用できるレコードの静的なコピーです。 これらのレコード セットは、データベース内の 1 つまたは複数のテーブルのフィールドを含めることができますが、更新することはできません。  
  
 レコード セットの各フォームは、レコード セットを開いた時点で固定されたレコードのセットを表します。 テーブル型のレコード セットまたはダイナセット タイプのレコード セット内のレコードをスクロールすると、レコード セットが開かれた後に、他のユーザーまたはアプリケーションで他のレコード セットのいずれかのレコードに加えられた変更を反映します。 (スナップショットの種類のレコード セットを更新できません。)使用することができます`CDaoRecordset`直接、アプリケーション固有のレコード セット クラスから派生または`CDaoRecordset`です。 ことができます。  
  
-   レコード間をスクロールします。  
  
-   インデックスを設定し、レコードを使用してすばやく探し[シーク](#seek)(テーブル型のレコード セットのみ)。  
  
-   文字列比較に基づいてレコードを検索:"<「、」\<="、「=」、"> ="、または">"(ダイナセットの型とスナップショットの種類のレコード セット)。  
  
-   レコードを更新し、(スナップショットの種類のレコード セット) を除くロック モードを指定します。  
  
-   データ ソースで使用できるものからを選択するレコードを制限するレコード セットをフィルター処理します。  
  
-   レコード セットを並べ替えます。  
  
-   実行時まで不明情報で、選択範囲をカスタマイズするレコード セットをパラメーター化します。  
  
 クラス`CDaoRecordset`のクラスに似たインターフェイスを提供`CRecordset`です。 主な違いは、そのクラス`CDaoRecordset`OLE に基づくデータ アクセス オブジェクト (DAO) を介してデータにアクセスします。 クラス`CRecordset`DBMS のオープン データベース コネクティビティ (ODBC) と ODBC ドライバーを介して、DBMS にアクセスします。  
  
> [!NOTE]
>  DAO データベース クラスは、MFC データベース クラス ODBC Open Database Connectivity () をベースとは異なります。 DAO データベース クラスの名前では、"CDao"プレフィックスがあります。 DAO クラス; で ODBC データ ソースのアクセスをできます。Microsoft Jet データベース エンジンに固有であるために、DAO クラスは通常、優れた機能を提供します。  
  
 使用するか`CDaoRecordset`直接からクラスを派生または`CDaoRecordset`です。 どちらの場合、レコード セット クラスを使用するデータベースを開くオブジェクトを構築、レコード セットへのポインターをコンス トラクターに渡して、`CDaoDatabase`オブジェクト。 構築することも、`CDaoRecordset`オブジェクトし、MFC、一時パスワードが作成できるように`CDaoDatabase`オブジェクト。 レコード セットを呼び出す[開く](#open)かを指定するかどうか、オブジェクト タイプのレコード、ダイナセット タイプのレコード セットでは、スナップショットの種類のレコード セットのメンバー関数。 呼び出す`Open`データベースからデータを選択し、最初のレコードを取得します。  
  
 レコード間をスクロールし、それらを操作するには、オブジェクトのメンバー関数とデータ メンバーを使用します。 使用できる操作は、オブジェクトは、テーブル型のレコード セット、ダイナセット タイプのレコード セット、または、スナップショットの種類のレコード セットかどうかと、更新可能なと読み取り専用であるかによって異なります-これは、データベースまたはオープン データベース コネクティビティ (ODBC) の機能に依存。データ ソースです。 されている変更されたか、後に追加するレコードを更新する、`Open`呼び出し、オブジェクトの[Requery](#requery)メンバー関数。 オブジェクトの`Close`メンバー関数を関連付けが完了したら、オブジェクトを破棄します。  
  
 `CDaoRecordset` タイプ セーフな C++ のメンバーの読み取りとレコード フィールドの更新をサポートするために DAO レコード フィールド エクス (チェンジ DFX) を使用して、`CDaoRecordset`または`CDaoRecordset`-クラスを派生します。 DFX のメカニズムを使用して、使用せず、データベース内の列の動的バインドを実装することも[GetFieldValue](#getfieldvalue)と[いる](#setfieldvalue)です。  
  
 関連情報については、「Recordset オブジェクト」DAO ヘルプのトピックを参照してください。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoRecordset`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdao.h  
  
##  <a name="addnew"></a>  CDaoRecordset::AddNew  
 テーブル型またはダイナセット タイプのレコード セットに新しいレコードを追加するには、このメンバー関数を呼び出します。  
  
```  
virtual void AddNew();
```  
  
### <a name="remarks"></a>Remarks  
 レコードのフィールドは、最初に null 値がします。 (データベース用語では、「値を持たない」手段を Null に設定と同じではありませんし**NULL** c++)。完了するには、操作を呼び出す必要があります、[更新](#update)メンバー関数。 `Update` データ ソースに変更を保存します。  
  
> [!CAUTION]
>  レコードを編集し、スクロールと別のレコードを呼び出さずに`Update`、変更内容は警告なしに失われます。  
  
 呼び出して、ダイナセット タイプのレコード セットにレコードを追加するかどうかは[AddNew](#addnew)、レコードはレコード セットの可視性およびがあれば表示新規基になるテーブルに含まれている`CDaoRecordset`オブジェクト。  
  
 新しいレコードの位置は、レコード セットの種類によって異なります。  
  
-   ダイナセット タイプでは、新しいレコードが挿入されるレコード セットは保証されません。 この動作は、パフォーマンス、および同時実行のため Microsoft Jet 3.0 に変更します。 目標は、新しく追加されたレコードを現在のレコードには、最後に変更されたレコードのブックマークを取得し、そのブックマークに移動します。  
  
 [!code-cpp[NVC_MFCDatabase#1](../../mfc/codesnippet/cpp/cdaorecordset-class_1.cpp)]  
  
-   インデックスが指定されているテーブル型レコード セットの並べ替え順序での適切な場所でレコードが返されます。 インデックスが指定されていない場合は、レコード セットの末尾に新しいレコードが返されます。  
  
 レコードは、使用する前に現在`AddNew`のままです。 現在、新しいレコードを作成して、レコード セットは、ブックマーク、呼び出しをサポートしている場合[SetBookmark](#setbookmark) LastModified プロパティの設定によって、基になる DAO レコード セット オブジェクトの識別のブックマークにします。 これは、追加したレコード内のカウンター (自動インクリメント) フィールドの値を決定するために役立ちます。 詳細については、次を参照してください。 [GetLastModifiedBookmark](#getlastmodifiedbookmark)です。  
  
 データベースがトランザクションをサポートすることができます、`AddNew`呼び出し、トランザクションの一部です。 トランザクションの詳細については、クラスを参照してください。 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)です。 呼び出す必要があります[CDaoWorkspace::BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans)呼び出す前に`AddNew`です。  
  
 呼び出すことはできません`AddNew`レコード セットの持つ[開く](#open)メンバー関数が呼び出されていません。 A`CDaoException`を呼び出す場合にスローされる`AddNew`のレコード セットに追加することはできません。 呼び出すことによって、レコード セットは更新可能かどうかを判断できます[CanAppend](#canappend)です。  
  
 フレームワークは、DAO レコード フィールド エクス (チェンジ DFX) メカニズムによって、データ ソースのレコードに書き込まが確認するためのフィールド データ メンバーを変更します。 フィールドの値を変更すると、通常、フィールド ダーティは自動的に設定を呼び出すことはほとんどありません必要がありますので[き](#setfielddirty)ユーザー自身が場合がありますようにすることも、列が明示的に更新または挿入するかに関係なくどのような値のフィールド データ メンバーです。 DFX 機構は、の使用も採用されています。**擬似 NULL**です。 詳細については、次を参照してください。 [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)です。  
  
 ダブル バッファリング機構が使用されていない場合、フィールドの値を変更して自動的に設定しませんフィールド ダーティとして。 この例では、ダーティ フィールドを明示的に設定する必要があります。 格納されているフラグ[m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)このフィールドの自動チェックを制御します。  
  
> [!NOTE]
>  レコードがダブル バッファリングされた場合 (つまり、フィールドの自動チェックが有効)、呼び出す`CancelUpdate`メンバー変数を前の値に復元されます`AddNew`または`Edit`が呼び出されました。  
  
 関連情報については、"AddNew Method"、"ただし Method"、"LastModified Property"、および DAO ヘルプの「EditMode プロパティ」のトピックを参照してください。  
  
##  <a name="canappend"></a>  CDaoRecordset::CanAppend  
 以前に開いたレコード セットが呼び出すことによって新しいレコードを追加することができるかどうかを決定するには、このメンバー関数を呼び出す、 [AddNew](#addnew)メンバー関数。  
  
```  
BOOL CanAppend() const;  
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、レコード セットは、新しいレコードを追加できます。それ以外の場合 0 を返します。 `CanAppend` 読み取り専用とレコード セットを開いた場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 関連情報については、「DAO ヘルプの「メソッドの追加」」を参照してください。  
  
##  <a name="canbookmark"></a>  CDaoRecordset::CanBookmark  
 以前に開いたレコード セットが個別にブックマークを使用してレコードを指定することができるかどうかを決定するには、このメンバー関数を呼び出します。  
  
```  
BOOL CanBookmark();
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、レコード セットは、ブックマーク、それ以外の場合 0 をサポートしています。  
  
### <a name="remarks"></a>Remarks  
 Microsoft Jet データベース エンジンのテーブルで完全に基づくレコード セットを使用している場合、スクロール順方向専用レコード セットとしてフラグが設定されたスナップショットの種類のレコード セットで、ブックマークを除く使用できます。 その他のデータベース製品 (外部の ODBC データ ソース) が、ブックマークをサポートしていません。  
  
 関連情報については、DAO のヘルプで「ブックマークを設定プロパティ」を参照してください。  
  
##  <a name="cancelupdate"></a>  CDaoRecordset::CancelUpdate  
 `CancelUpdate`を取り消すために、保留中の更新プログラムのメンバー関数、[編集](#edit)または[AddNew](#addnew)操作します。  
  
```  
virtual void CancelUpdate();
```  
  
### <a name="remarks"></a>Remarks  
 たとえば、アプリケーションを呼び出す場合、`Edit`または`AddNew`メンバー関数が呼び出されると[更新](#update)、`CancelUpdate`後に加えられた変更をキャンセル`Edit`または`AddNew`が呼び出されました。  
  
> [!NOTE]
>  レコードがダブル バッファリングされた場合 (つまり、フィールドの自動チェックが有効)、呼び出す`CancelUpdate`メンバー変数を前の値に復元されます`AddNew`または`Edit`が呼び出されました。  
  
 ある場合ありません`Edit`または`AddNew`操作が保留中、 `CancelUpdate` MFC 例外をスローすると、します。 呼び出す、 [GetEditMode](#geteditmode)キャンセルできる保留中の操作があるかどうかを判断するメンバー関数。  
  
 関連情報については、DAO ヘルプの「ただしメソッド」を参照してください。  
  
##  <a name="canrestart"></a>  CDaoRecordset::CanRestart  
 レコード セットでは、呼び出すことによって、クエリを (そのレコードの更新) を再起動できるかどうかを決定するには、このメンバー関数を呼び出す、`Requery`メンバー関数。  
  
```  
BOOL CanRestart();
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値`Requery`レコード セットのクエリをもう一度、それ以外の場合 0 を実行すると呼ばれることができます。  
  
### <a name="remarks"></a>Remarks  
 テーブル型のレコード セットをサポートしていない`Requery`です。  
  
 場合`Requery`は呼び出しがサポートされていない[閉じる](#close)し[開く](#open)データを更新します。 呼び出すことができます`Requery`オブジェクトを更新するレコード セットの基になるパラメーター クエリ パラメーターの値が変更された後にします。  
  
 関連情報については、DAO のヘルプで「再開可能なプロパティ」を参照してください。  
  
##  <a name="canscroll"></a>  CDaoRecordset::CanScroll  
 レコード セットでは、スクロールできるかどうかを決定するには、このメンバー関数を呼び出します。  
  
```  
BOOL CanScroll() const;  
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は 0 それ以外の場合、レコードをスクロールすることができます。  
  
### <a name="remarks"></a>Remarks  
 呼び出す場合[開く](#open)で**dbForwardOnly**、レコード セットは前方スクロールのみできます。  
  
 関連情報については、"配置、現在のレコード ポインターと DAO"DAO ヘルプのトピックを参照してください。  
  
##  <a name="cantransact"></a>  CDaoRecordset::CanTransact  
 レコード セットがトランザクションを許可するかどうかを決定するには、このメンバー関数を呼び出します。  
  
```  
BOOL CanTransact();
```  
  
### <a name="return-value"></a>戻り値  
 基になるデータ ソースは 0 それ以外の場合、トランザクションをサポートする場合は 0 以外の値。  
  
### <a name="remarks"></a>Remarks  
 関連情報については、DAO ヘルプの「トランザクション プロパティ」を参照してください。  
  
##  <a name="canupdate"></a>  CDaoRecordset::CanUpdate  
 レコード セットを更新できるかどうかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットを更新する場合は 0 以外 (追加、更新、およびレコードの削除)、それ以外の場合に 0 です。  
  
### <a name="remarks"></a>Remarks  
 基になるデータ ソースが読み取り専用の場合、または指定した場合、レコード セットを読み取り専用可能性があります**dbReadOnly**の*nOptions*呼び出されたとき[開く](#open)レコード セットのです。  
  
 関連情報については、"AddNew Method"、「メソッドの編集」、「メソッドの削除」、「更新メソッド」、および DAO ヘルプの「更新可能なプロパティ」のトピックを参照してください。  
  
##  <a name="cdaorecordset"></a>  CDaoRecordset::CDaoRecordset  
 `CDaoRecordset` オブジェクトを構築します。  
  
```  
CDaoRecordset(CDaoDatabase* pDatabase = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDatabase*  
 ポインターが含まれています、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトまたは値**NULL**です。 ない場合**NULL**と`CDaoDatabase`オブジェクトの`Open`データ ソースに接続するメンバー関数が呼び出されていない、レコード セットが、ファイルを開いて、それ自体の中にしようとしています。[開く](#open)を呼び出します。 渡す場合**NULL**、`CDaoDatabase`オブジェクトが構築されからレコード セット クラスを派生するかどうかに指定したデータ ソースの情報を使用して接続されている`CDaoRecordset`です。  
  
### <a name="remarks"></a>Remarks  
 使用するか`CDaoRecordset`直接からアプリケーションに固有のクラスを派生または`CDaoRecordset`です。 ClassWizard を使用するには、レコード セット クラスを派生します。  
  
> [!NOTE]
>  派生した場合、`CDaoRecordset`クラス、派生クラスは、独自のコンス トラクターを指定する必要があります。 派生クラスのコンス トラクターで、コンス トラクターを呼び出します`CDaoRecordset::CDaoRecordset`、に沿って、適切なパラメーターを渡します。  
  
 渡す**NULL**がレコード セット コンス トラクターに、`CDaoDatabase`オブジェクトが構築され、自動的に結合します。 これは便利なショートカットを構築し、接続を必要としない、`CDaoDatabase`レコード セットを構築する前にオブジェクト。 場合、`CDaoDatabase`オブジェクトが開いていない、 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)オブジェクトは、既定のワークスペースを使用するのも作成されます。 詳細については、次を参照してください。 [CDaoDatabase::CDaoDatabase](../../mfc/reference/cdaodatabase-class.md#cdaodatabase)です。  
  
##  <a name="close"></a>  CDaoRecordset::Close  
 閉じる、`CDaoRecordset`オブジェクトが関連付けられているデータベースで開いているレコード セットのコレクションから削除します。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Remarks  
 **閉じる**を破棄しません、`CDaoRecordset`オブジェクトを呼び出すことによって、オブジェクトを再利用できる`Open`同じデータ ソースまたは別のデータ ソースにします。  
  
 保留中のすべて[AddNew](#addnew)または[編集](#edit)ステートメントはキャンセルされ、すべて保留中のトランザクションはロールバックされます。 保留中の追加や変更を保持する場合は、呼び出す[更新](#update)を呼び出す前に`Close`の各レコード セット。  
  
 呼び出すことができます`Open`呼び出した後にもう一度`Close`です。 これにより、レコード セット オブジェクトを再利用できます。 呼び出すことがより優れた代替です[Requery](#requery)可能であれば、します。  
  
 関連情報については、「Close メソッド」DAO ヘルプのトピックを参照してください。  
  
##  <a name="delete"></a>  CDaoRecordset::Delete  
 開いているダイナセット型またはテーブル型のレコード セット オブジェクトの現在のレコードを削除するには、このメンバー関数を呼び出します。  
  
```  
virtual void Delete();
```  
  
### <a name="remarks"></a>Remarks  
 削除が成功した後、レコード セットのフィールド データ メンバーは、Null 値に設定され、レコード セットのナビゲーションのメンバー関数のいずれかを明示的に呼び出す必要があります ([移動](#move)、[シーク](#seek)、 [SetBookmark](#setbookmark)など)、削除したレコードから移動するためにします。 レコード セットからレコードを削除するときに必要があります、現在のレコード、レコード セット内を呼び出す前に`Delete`以外の場合、例外がスローされます。  
  
 `Delete` 現在のレコードを削除し、アクセスできなくなります。 編集または削除されたレコードを使用することはできませんが、現在残っています。 別のレコードに移動するとすることはできません、削除したレコード現在もう一度です。  
  
> [!CAUTION]
>  レコード セットは更新可能である必要があり、ありますの有効なレコードの現在のレコード セットを呼び出すとき`Delete`です。 たとえば、レコードを削除してを呼び出す前に、新しいレコードをスクロールしません`Delete`もう一度、`Delete`スロー、 [CDaoException](../../mfc/reference/cdaoexception-class.md)です。  
  
 トランザクションを使用してを呼び出す場合は、レコードを復元できます、 [CDaoWorkspace::Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback)メンバー関数。 基底のテーブルがプライマリ場合は、連鎖的にリレーションシップを削除、現在のレコードを削除すると、外部テーブル内の 1 つまたは複数のレコードも削除可能性があります。 詳細については、DAO のヘルプで、定義「連鎖削除」を参照してください。  
  
 異なり`AddNew`と`Edit`への呼び出し`Delete`への呼び出しが続かない`Update`です。  
  
 関連情報については、"AddNew Method"、「メソッドの編集」、「メソッドの削除」、「更新メソッド」、および DAO ヘルプの「更新可能なプロパティ」のトピックを参照してください。  
  
##  <a name="dofieldexchange"></a>  CDaoRecordset::DoFieldExchange  
 フレームワークは、レコード セット オブジェクトのフィールド データ メンバーと、データ ソースの現在のレコードの対応する列の間でデータを自動的に交換するには、このメンバー関数を呼び出します。  
  
```  
virtual void DoFieldExchange(CDaoFieldExchange* pFX);
```  
  
### <a name="parameters"></a>パラメーター  
 *pFX*  
 ポインターが含まれています、`CDaoFieldExchange`オブジェクト。 フレームワークは、フィールド交換操作のコンテキストを指定する、このオブジェクトは、既に設定しました。  
  
### <a name="remarks"></a>Remarks  
 また、レコード セットの選択用の SQL ステートメント文字列内のパラメーターのプレース ホルダーに存在する場合、パラメーターのデータ メンバーをバインドします。 DAO レコード フィールド エクス チェンジ (DFX) と呼ばれる、フィールドのデータの交換の両方向の動作: データ ソースのレコードのフィールドにレコード セット オブジェクトのフィールド データ メンバーと、レコード セット オブジェクトにデータ ソースのレコードからです。 列を動的にバインドする場合は、実装する必要はありません`DoFieldExchange`です。  
  
 唯一の操作を実装する通常実行する必要があります`DoFieldExchange`クラスは、派生したレコード セットを ClassWizard でクラスを作成し、フィールド データ メンバーの名前とデータ型を指定します。 ClassWizard が記述するパラメーターのデータ メンバーを指定するには、さらにコードを追加する可能性があります。 すべてのフィールドを動的にバインドされている場合は、この関数は非アクティブでパラメーター データ メンバーを指定していない限り。  
  
 ClassWizard で派生したレコード セット クラスを宣言するときのオーバーライドが書き込まれます`DoFieldExchange`次の例のようを。  
  
 [!code-cpp[NVC_MFCDatabase#2](../../mfc/codesnippet/cpp/cdaorecordset-class_2.cpp)]  
  
##  <a name="edit"></a>  CDaoRecordset::Edit  
 現在のレコードを変更できるようにするには、このメンバー関数を呼び出します。  
  
```  
virtual void Edit();
```  
  
### <a name="remarks"></a>Remarks  
 呼び出すと、`Edit`メンバー関数は、現在のレコードのフィールドに加えられた変更は、コピー バッファーにコピーされます。 レコードに必要な変更を加えた後呼び出す`Update`して変更を保存します。 `Edit` レコード セットのデータ メンバーの値を保存します。 呼び出す場合`Edit`、変更では、まず、`Edit`元に 1 つ目の前に、レコードの値を復元する、もう一度`Edit`呼び出します。  
  
> [!CAUTION]
>  レコードを編集して、最初の呼び出さずに別のレコードに移動する操作を実行して場合`Update`、変更内容は警告なしに失われます。 さらに、レコード セットまたは親データベースを閉じる場合は、警告なし、編集されたレコードが破棄されます。  
  
 場合によっては、(データを含まない) を Null にすることで、列を更新することがあります。 これを行うには、呼び出す`SetFieldNull`のパラメーターを持つ**TRUE** Null です。 このフィールドをマークするこれもにより、更新する列。 場合は、フィールドの値が変更されていない場合でも、データ ソースに書き込まれ、呼び出しを`SetFieldDirty`のパラメーターを持つ**TRUE**です。 これは、フィールド値の Null であった場合でも機能します。  
  
 フレームワークは、DAO レコード フィールド エクス (チェンジ DFX) メカニズムによって、データ ソースのレコードに書き込まが確認するためのフィールド データ メンバーを変更します。 フィールドの値を変更すると、通常、フィールド ダーティは自動的に設定を呼び出すことはほとんどありません必要がありますので[き](#setfielddirty)ユーザー自身が場合がありますようにすることも、列が明示的に更新または挿入するかに関係なくどのような値のフィールド データ メンバーです。 DFX 機構は、の使用も採用されています。**擬似 NULL**です。 詳細については、次を参照してください。 [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)です。  
  
 ダブル バッファリング機構が使用されていない場合、フィールドの値を変更して自動的に設定しませんフィールド ダーティとして。 この例では、ダーティ フィールドを明示的に設定する必要があります。 格納されているフラグ[m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)このフィールドの自動チェックを制御します。  
  
 レコード セット オブジェクトがマルチ ユーザー環境で排他ロックされると、レコードにはロックが時間から`Edit`更新が完了するまでに使用します。 レコード セットがやロックされている場合、レコードがロックされているし、データベースで更新される直前に、編集前のレコードと比較 呼び出されるため、レコードが変更された場合`Edit`、`Update`操作は失敗し、MFC は、例外をスローします。 ロック モードを変更する`SetLockingMode`です。  
  
> [!NOTE]
>  ODBC やインストール可能な ISAM など、外部データベース形式では、オプティミスティック ロックは使用が常にします。  
  
 現在のレコードを呼び出した後`Edit`です。 呼び出す`Edit`、現在のレコードである必要があります。 現在のレコードがない場合、またはレコード セットがオープン テーブル型またはダイナセット タイプのレコード セット オブジェクトを参照していない場合は、例外が発生します。 呼び出す`Edit`により、`CDaoException`が次の条件下でスローされます。  
  
-   現在のレコードがありません。  
  
-   データベースまたはレコード セットは読み取り専用です。  
  
-   レコードのフィールドは、更新可能ではありません。  
  
-   データベースまたはレコード セットは、別のユーザーによって排他的に開かれました。  
  
-   別のユーザーは、レコードを含むページをロックされています。  
  
 データ ソースは、トランザクションをサポートすることができます、`Edit`呼び出し、トランザクションの一部です。 呼び出す必要があります`CDaoWorkspace::BeginTrans`呼び出す前に`Edit`とレコード セットが開かれた後。 その呼び出し元にも注意してください`CDaoWorkspace::CommitTrans`呼び出しに代わるものではありません`Update`を完了する、`Edit`操作します。 トランザクションの詳細については、クラスを参照してください。`CDaoWorkspace`です。  
  
 関連情報については、"AddNew Method"、「メソッドの編集」、「メソッドの削除」、「更新メソッド」、および DAO ヘルプの「更新可能なプロパティ」のトピックを参照してください。  
  
##  <a name="fillcache"></a>  CDaoRecordset::FillCache  
 指定された数のレコード セットからレコードをキャッシュするには、このメンバー関数を呼び出します。  
  
```  
void FillCache(
    long* pSize = NULL,  
    COleVariant* pBookmark = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pSize*  
 キャッシュを埋めるために行の数を指定します。 このパラメーターを省略した場合、値は、基になる DAO オブジェクトの CacheSize プロパティ設定によって決まります。  
  
 *pBookmark*  
 A [COleVariant](../../mfc/reference/colevariant-class.md)ブックマークを指定します。 キャッシュはこのブックマークで示されたレコードから開始されます。 このパラメーターを省略した場合、キャッシュは、基になる DAO オブジェクトの CacheStart プロパティで示されたレコードから開始されます。  
  
### <a name="remarks"></a>Remarks  
 キャッシュすると、取得、またはリモート サーバーからデータをフェッチします。 アプリケーションのパフォーマンスが向上します。 キャッシュは、前提としているデータは再度要求されるアプリケーションの実行中に最後にフェッチ、サーバーからデータを保持するローカル メモリの領域が。 データが要求されると、Microsoft Jet データベース エンジンのキャッシュ データをまずチェック時間がかかると、サーバーからのフェッチではなくです。 非 ODBC データ ソースにデータ キャッシュを使用しても何も起こりませんようにデータがキャッシュに保存されません。  
  
 フェッチされるレコードを格納するキャッシュを待機しているのではなく入力することを明示的にキャッシュいつでも呼び出すことによって、`FillCache`メンバー関数。 これは、キャッシュの充てんために高速な方法`FillCache`同時ではなく 1 つずつの複数のレコードをフェッチします。 たとえば、画面にレコードが表示されているときに、アプリケーション呼び出しを持つことができます`FillCache`を [次へ] 画面にレコードをフェッチします。  
  
 レコード セット オブジェクトでアクセスされる任意の ODBC データベースには、ローカル キャッシュを持つことができます。 キャッシュを作成するにリモート データ ソースからレコード セット オブジェクトを開くし、呼び出し、`SetCacheSize`と`SetCacheStart`レコード セットのメンバー関数。 場合*lSize*と*lBookmark*部分的または完全に指定した範囲外の範囲を作成する`SetCacheSize`と`SetCacheStart`、この範囲外のレコード セットの部分は無視されはありませんキャッシュに読み込まれます。 場合`FillCache`よりも多くのレコードが、リモート データ ソースに残ります、残りのレコードのみがフェッチされ例外はスローされませんを要求します。  
  
 キャッシュからフェッチされたレコードでは、他のユーザーがデータ ソースに同時に行われた変更は反映されません。  
  
 `FillCache` キャッシュされていないレコードだけをフェッチします。 すべてのキャッシュされたデータの更新を強制するを呼び出す、`SetCacheSize`メンバー関数が、 *lSize*パラメーターを 0、呼び出し`SetCacheSize`を使用して、 *lSize*パラメーターは、キャッシュのサイズに等しい最初に要求を実行し、呼び出して`FillCache`です。  
  
 関連情報については、DAO ヘルプの「FillCache メソッド」を参照してください。  
  
##  <a name="find"></a>  CDaoRecordset::Find  
 比較演算子を使用してダイナセットまたはスナップショット タイプのレコード セット内で特定の文字列を検索するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL Find(
    long lFindType,  
    LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>パラメーター  
 *lFindType*  
 必要な検索操作の種類を示す値です。 次の値を指定できます。  
  
- **AFX_DAO_NEXT**一致する文字列の次の場所を検索します。  
  
- **AFX_DAO_PREV**一致する文字列の前の場所を検索します。  
  
- **AFX_DAO_FIRST**一致する文字列の最初の位置を検索します。  
  
- **AFX_DAO_LAST**一致する文字列の最後の場所を検索します。  
  
 *lpszFilter*  
 文字列式 (と同様に、**場所**語を除く SQL ステートメントの句**場所**) レコードを検索するために使用します。 例えば:  
  
 [!code-cpp[NVC_MFCDatabase#3](../../mfc/codesnippet/cpp/cdaorecordset-class_3.cpp)]  
  
### <a name="return-value"></a>戻り値  
 一致するレコードが見つかった場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>Remarks  
 最初に、[次へ] を検索する文字列の前、または最後のインスタンス。 `Find` 仮想関数の場合、このメソッドをオーバーライドし、独自の実装を追加することができます。 `FindFirst`、 `FindLast`、 `FindNext`、および`FindPrev`メンバー関数の呼び出し、`Find`メンバー関数を使用できるように`Find`すべての検索操作の動作を制御します。  
  
 テーブル型のレコード セット内のレコードを検索、呼び出し、[シーク](#seek)メンバー関数。  
  
> [!TIP]
>  レコードがある場合より効果的な一連の小さい`Find`になります。 一般と、ODBC データで特に必要なレコードだけを取得する新しいクエリを作成することをお勧めします。  
  
 関連情報については、トピックを参照して、"FindFirst、FindLast、FindNext、FindPrevious メソッド"DAO のヘルプ。  
  
##  <a name="findfirst"></a>  CDaoRecordset::FindFirst  
 指定した条件に一致する最初のレコードを検索するには、このメンバー関数を呼び出します。  
  
```  
BOOL FindFirst(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszFilter*  
 文字列式 (と同様に、**場所**語を除く SQL ステートメントの句**場所**) レコードを検索するために使用します。  
  
### <a name="return-value"></a>戻り値  
 一致するレコードが見つかった場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>Remarks  
 `FindFirst`メンバー関数は、レコード セットの先頭から検索し、レコード セットの末尾に検索を開始します。  
  
 含めるすべてのレコードを検索 (だけでなく、特定の条件を満たすもの) を使用して、移動操作のいずれかのレコードから移動する場合は。 テーブル型のレコード セット内のレコードを検索、呼び出し、`Seek`メンバー関数。  
  
 条件に一致するレコードが見つからない場合、現在のレコードのポインターが不明、および`FindFirst`は 0 を返します。 レコード セットには、条件を満たす 1 つ以上のレコードが含まれている場合`FindFirst`、最初に見つかった位置を検索し`FindNext`と次の出現箇所を検索します。  
  
> [!CAUTION]
>  現在のレコードを編集する場合は必ずを呼び出して、変更を保存する、`Update`メンバー関数は、別のレコードに移動する前にします。 更新することがなく別のレコードに移動すると、変更内容が警告なしに失われます。  
  
 `Find`メンバー関数は、次の表で指定された、双方向での場所から検索します。  
  
|検索操作|開始|検索の方向|  
|---------------------|-----------|----------------------|  
|`FindFirst`|レコード セットの先頭|レコード セットの末尾|  
|`FindLast`|レコード セットの末尾|レコード セットの先頭|  
|`FindNext`|現在のレコード|レコード セットの末尾|  
|`FindPrevious`|現在のレコード|レコード セットの先頭|  
  
> [!NOTE]
>  呼び出すと`FindLast`、Microsoft Jet データベース エンジンがこのが既に行われていない場合、検索を開始する前に、レコード セットが完全に設定します。 最初の検索は、以後の検索よりも長くかかる可能性があります。  
  
 検索操作のいずれかの方法が呼び出した場合と同じ`MoveFirst`または`MoveNext`、ただし、これだけで、先頭または [次へ] のレコード現在しなくても、条件を指定します。 移動操作で、検索操作を行うことができます。  
  
 検索操作を使用する場合は、次に注意してください。  
  
-   場合`Find`、現在のレコードが定義されていない 0 以外を返します。 この例では、有効なレコードには、現在のレコード ポインターを配置する必要があります。  
  
-   検索操作は、前方スクロール スナップショットの種類のレコード セットを使用できません。  
  
-   米国の日付形式 (月-日-年) を使用する必要があります、Microsoft Jet データベース エンジンの; 米国バージョンを使用していない場合でも、日付を持つフィールドを検索するときそれ以外の場合、一致するレコードが見つからない可能性があります。  
  
-   ODBC データベースで大きなダイナセットを処理するとき、検索操作が遅く、大きなレコード セットを使用する場合に特にが見つかることもあります。 SQL クエリを使用してパフォーマンスを向上させることができますとカスタマイズ**ORDERBY**または**場所**句、パラメーター クエリまたは`CDaoQuerydef`インデックス付きの特定のレコードを取得するオブジェクト。  
  
 関連情報については、トピックを参照して、"FindFirst、FindLast、FindNext、FindPrevious メソッド"DAO のヘルプ。  
  
##  <a name="findlast"></a>  CDaoRecordset::FindLast  
 指定した条件に一致する最後のレコードを検索するには、このメンバー関数を呼び出します。  
  
```  
BOOL FindLast(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszFilter*  
 文字列式 (と同様に、**場所**語を除く SQL ステートメントの句**場所**) レコードを検索するために使用します。  
  
### <a name="return-value"></a>戻り値  
 一致するレコードが見つかった場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>Remarks  
 `FindLast`メンバー関数は、レコード セットの末尾に検索し、レコード セットの先頭に向かって後方へ検索を開始します。  
  
 含めるすべてのレコードを検索 (だけでなく、特定の条件を満たすもの) を使用して、移動操作のいずれかのレコードから移動する場合は。 テーブル型のレコード セット内のレコードを検索、呼び出し、`Seek`メンバー関数。  
  
 条件に一致するレコードが見つからない場合、現在のレコードのポインターが不明、および`FindLast`は 0 を返します。 レコード セットには、条件を満たす 1 つ以上のレコードが含まれている場合`FindFirst`、最初に見つかった位置を検索し`FindNext`と、最初に見つかった位置の後に次の出現箇所を検索します。  
  
> [!CAUTION]
>  現在のレコードを編集する場合を呼び出して、変更を保存することを確認する、`Update`メンバー関数は、別のレコードに移動する前にします。 更新することがなく別のレコードに移動すると、変更内容が警告なしに失われます。  
  
 検索操作のいずれかの方法が呼び出した場合と同じ`MoveFirst`または`MoveNext`、ただし、これだけで、先頭または [次へ] のレコード現在しなくても、条件を指定します。 移動操作で、検索操作を行うことができます。  
  
 検索操作を使用する場合は、次に注意してください。  
  
-   場合`Find`、現在のレコードが定義されていない 0 以外を返します。 この例では、有効なレコードには、現在のレコード ポインターを配置する必要があります。  
  
-   検索操作は、前方スクロール スナップショットの種類のレコード セットを使用できません。  
  
-   米国の日付形式 (月-日-年) を使用する必要があります、Microsoft Jet データベース エンジンの; 米国バージョンを使用していない場合でも、日付を持つフィールドを検索するときそれ以外の場合、一致するレコードが見つからない可能性があります。  
  
-   ODBC データベースで大きなダイナセットを処理するとき、検索操作が遅く、大きなレコード セットを使用する場合に特にが見つかることもあります。 SQL クエリを使用してパフォーマンスを向上させることができますとカスタマイズ**ORDERBY**または**場所**句、パラメーター クエリまたは`CDaoQuerydef`インデックス付きの特定のレコードを取得するオブジェクト。  
  
 関連情報については、トピックを参照して、"FindFirst、FindLast、FindNext、FindPrevious メソッド"DAO のヘルプ。  
  
##  <a name="findnext"></a>  CDaoRecordset::FindNext  
 指定した条件に一致する次のレコードを検索するには、このメンバー関数を呼び出します。  
  
```  
BOOL FindNext(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszFilter*  
 文字列式 (と同様に、**場所**語を除く SQL ステートメントの句**場所**) レコードを検索するために使用します。  
  
### <a name="return-value"></a>戻り値  
 一致するレコードが見つかった場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>Remarks  
 `FindNext`メンバー関数は、現在のレコードには、その検索を開始し、レコード セットの末尾に検索します。  
  
 含めるすべてのレコードを検索 (だけでなく、特定の条件を満たすもの) を使用して、移動操作のいずれかのレコードから移動する場合は。 テーブル型のレコード セット内のレコードを検索、呼び出し、`Seek`メンバー関数。  
  
 条件に一致するレコードが見つからない場合、現在のレコードのポインターが不明、および`FindNext`は 0 を返します。 レコード セットには、条件を満たす 1 つ以上のレコードが含まれている場合`FindFirst`、最初に見つかった位置を検索し`FindNext`と次の出現箇所を検索します。  
  
> [!CAUTION]
>  現在のレコードを編集する場合を呼び出して、変更を保存することを確認する、`Update`メンバー関数は、別のレコードに移動する前にします。 更新することがなく別のレコードに移動すると、変更内容が警告なしに失われます。  
  
 検索操作のいずれかの方法が呼び出した場合と同じ`MoveFirst`または`MoveNext`、ただし、これだけで、先頭または [次へ] のレコード現在しなくても、条件を指定します。 移動操作で、検索操作を行うことができます。  
  
 検索操作を使用する場合は、次に注意してください。  
  
-   場合`Find`、現在のレコードが定義されていない 0 以外を返します。 この例では、有効なレコードには、現在のレコード ポインターを配置する必要があります。  
  
-   検索操作は、前方スクロール スナップショットの種類のレコード セットを使用できません。  
  
-   米国の日付形式 (月-日-年) を使用する必要があります、Microsoft Jet データベース エンジンの; 米国バージョンを使用していない場合でも、日付を持つフィールドを検索するときそれ以外の場合、一致するレコードが見つからない可能性があります。  
  
-   ODBC データベースで大きなダイナセットを処理するとき、検索操作が遅く、大きなレコード セットを使用する場合に特にが見つかることもあります。 SQL クエリを使用してパフォーマンスを向上させることができますとカスタマイズ**ORDERBY**または**場所**句、パラメーター クエリまたは`CDaoQuerydef`インデックス付きの特定のレコードを取得するオブジェクト。  
  
 関連情報については、トピックを参照して、"FindFirst、FindLast、FindNext、FindPrevious メソッド"DAO のヘルプ。  
  
##  <a name="findprev"></a>  CDaoRecordset::FindPrev  
 指定した条件に一致する前のレコードを検索するには、このメンバー関数を呼び出します。  
  
```  
BOOL FindPrev(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszFilter*  
 文字列式 (と同様に、**場所**語を除く SQL ステートメントの句**場所**) レコードを検索するために使用します。  
  
### <a name="return-value"></a>戻り値  
 一致するレコードが見つかった場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>Remarks  
 `FindPrev`メンバー関数は、現在のレコードには、その検索を開始し、レコード セットの先頭に向かって逆方向に検索します。  
  
 含めるすべてのレコードを検索 (だけでなく、特定の条件を満たすもの) を使用して、移動操作のいずれかのレコードから移動する場合は。 テーブル型のレコード セット内のレコードを検索、呼び出し、`Seek`メンバー関数。  
  
 条件に一致するレコードが見つからない場合、現在のレコードのポインターが不明、および`FindPrev`は 0 を返します。 レコード セットには、条件を満たす 1 つ以上のレコードが含まれている場合`FindFirst`、最初に見つかった位置を検索し`FindNext`と次の出現箇所を検索します。  
  
> [!CAUTION]
>  現在のレコードを編集する場合を呼び出して、変更を保存することを確認する、`Update`メンバー関数は、別のレコードに移動する前にします。 更新することがなく別のレコードに移動すると、変更内容が警告なしに失われます。  
  
 検索操作のいずれかの方法が呼び出した場合と同じ`MoveFirst`または`MoveNext`、ただし、これだけで、先頭または [次へ] のレコード現在しなくても、条件を指定します。 移動操作で、検索操作を行うことができます。  
  
 検索操作を使用する場合は、次に注意してください。  
  
-   場合`Find`、現在のレコードが定義されていない 0 以外を返します。 この例では、有効なレコードには、現在のレコード ポインターを配置する必要があります。  
  
-   検索操作は、前方スクロール スナップショットの種類のレコード セットを使用できません。  
  
-   米国の日付形式 (月-日-年) を使用する必要があります、Microsoft Jet データベース エンジンの; 米国バージョンを使用していない場合でも、日付を持つフィールドを検索するときそれ以外の場合、一致するレコードが見つからない可能性があります。  
  
-   ODBC データベースで大きなダイナセットを処理するとき、検索操作が遅く、大きなレコード セットを使用する場合に特にが見つかることもあります。 SQL クエリを使用してパフォーマンスを向上させることができますとカスタマイズ**ORDERBY**または**場所**句、パラメーター クエリまたは`CDaoQuerydef`インデックス付きの特定のレコードを取得するオブジェクト。  
  
 関連情報については、トピックを参照して、"FindFirst、FindLast、FindNext、FindPrevious メソッド"DAO のヘルプ。  
  
##  <a name="getabsoluteposition"></a>  CDaoRecordset::GetAbsolutePosition  
 レコード セット オブジェクトの現在のレコードのレコード数を返します。  
  
```  
long GetAbsolutePosition();
```  
  
### <a name="return-value"></a>戻り値  
 レコード セット内のレコードの数を 0 から整数。 レコード セット内の現在のレコードの序数位置に対応します。  
  
### <a name="remarks"></a>Remarks  
 基になる DAO オブジェクトの AbsolutePosition プロパティの値は 0 から始まります。0 に設定は、レコード セットの最初のレコードを参照します。 呼び出すことによって、レコード セット内のデータが設定されたレコードの数を指定できます[GetRecordCount](#getrecordcount)です。 呼び出す`GetRecordCount`数を確認して、すべてのレコードにアクセスする必要がありますので時間がかかる場合があります。  
  
 場合は、現在のレコードとして、レコード セット内のレコードがない場合 - 1 が返されます。 現在のレコードを削除すると、AbsolutePosition プロパティの値が定義されていませんし、MFC は、参照されている場合に例外をスローします。 ダイナセットの種類のレコード セットに対して新しいレコードは、シーケンスの末尾に追加されます。  
  
> [!NOTE]
>  このプロパティは、レコード番号の代わりとして使用するものではありません。 ブックマークはいるデータを保持し、指定した位置に返すことをお勧めであり、すべての種類のレコード セット オブジェクトで、現在のレコードを配置する唯一の方法です。 具体的には、前のレコードが削除されたときに指定されたレコードの位置を変更します。 また、レコード セットが再作成された SQL ステートメントを使用して、使用して作成された場合を除き、レコード セット内の各レコードの順序が保証されないため場合、特定のレコードが同じ絶対位置を持つことの保証はありません、 **ORDERBY**句。  
  
> [!NOTE]
>  このメンバー関数は、ダイナセット タイプとスナップショットの種類のレコード セットに対してのみ有効です。  
  
 関連情報については、DAO ヘルプの「AbsolutePosition プロパティ」を参照してください。  
  
##  <a name="getbookmark"></a>  CDaoRecordset::GetBookmark  
 特定のレコードのブックマークの値を取得するには、このメンバー関数を呼び出します。  
  
```  
COleVariant GetBookmark();
```  
  
### <a name="return-value"></a>戻り値  
 現在のレコードにブックマークを表す値を返します。  
  
### <a name="remarks"></a>Remarks  
 レコード セット オブジェクトを作成または開くときに各レコードは既に一意のブックマーク サポートしている場合。 呼び出す`CanBookmark`をレコード セットでブックマークをサポートするかどうかを判断します。  
  
 現在のレコードのブックマークを保存するには、ブックマークがの値を割り当てることによって、`COleVariant`オブジェクト。 戻るにはすぐにそのレコードにいつでも別のレコードに移動した後、呼び出す`SetBookmark`の値に対応するパラメーターを持つ`COleVariant`オブジェクト。  
  
> [!NOTE]
>  呼び出す[Requery](#requery) DAO ブックマークを変更します。  
  
 関連情報については、DAO のヘルプで「ブックマーク プロパティ」を参照してください。  
  
##  <a name="getcachesize"></a>  CDaoRecordset::GetCacheSize  
 キャッシュされたレコードの数を取得するには、このメンバー関数を呼び出します。  
  
```  
long GetCacheSize();
```  
  
### <a name="return-value"></a>戻り値  
 ODBC データ ソースからローカルにキャッシュされたデータを含むダイナセット タイプのレコード セット内のレコードの数を指定する値。  
  
### <a name="remarks"></a>Remarks  
 データ キャッシュには、ダイナセット タイプのレコード セット オブジェクト経由でリモート サーバーからデータを取得するアプリケーションのパフォーマンスが向上します。 キャッシュは、最後に取得したサーバーから、アプリケーションの実行中にデータを再要求は、データを保持するローカル メモリ内のスペースです。 データが要求されると、Microsoft Jet データベース エンジンのキャッシュ要求されたデータをまずチェック時間がかかると、サーバーから取得するのではなくです。 ODBC データ ソースから発生しないデータがキャッシュに保存されません。  
  
 アタッチのテーブルなど、任意の ODBC データ ソースには、ローカル キャッシュを持つことができます。  
  
 関連情報については、DAO ヘルプのトピック「CacheSize、CacheStart プロパティ」を参照してください。  
  
##  <a name="getcachestart"></a>  CDaoRecordset::GetCacheStart  
 最初のレコードをキャッシュするレコード セット内のブックマークの値を取得するには、このメンバー関数を呼び出します。  
  
```  
COleVariant GetCacheStart();
```  
  
### <a name="return-value"></a>戻り値  
 A`COleVariant`キャッシュに保存するレコード セットの最初のレコード、ブックマークを指定します。  
  
### <a name="remarks"></a>Remarks  
 Microsoft Jet データベース エンジンが、キャッシュからキャッシュの範囲内のレコードを要求し、サーバーからキャッシュ範囲外のレコードを要求します。  
  
> [!NOTE]
>  キャッシュから取得したレコードでは、他のユーザーがデータ ソースに同時に行われた変更は反映されません。  
  
 関連情報については、DAO ヘルプのトピック「CacheSize、CacheStart プロパティ」を参照してください。  
  
##  <a name="getcurrentindex"></a>  CDaoRecordset::GetCurrentIndex  
 インデックス付きのテーブル型で使用されているインデックスを確認するには、このメンバー関数を呼び出す`CDaoRecordset`オブジェクト。  
  
```  
CString GetCurrentIndex();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`テーブル型のレコード セットで使用されているインデックスの名前を含むです。 インデックスが設定されていない場合は、空の文字列を返します。  
  
### <a name="remarks"></a>Remarks  
 このインデックスは、テーブル型のレコード セット内のレコードの順序の基準であり、によって使用される、[シーク](#seek)レコードを検索するメンバー関数。  
  
 A`CDaoRecordset`オブジェクトは、1 つ以上のインデックスを持つことができますが、一度に 1 つだけのインデックスを使用することができます (ただし、[どちら](../../mfc/reference/cdaotabledef-class.md)オブジェクトに定義されているいくつかのインデックスがあります)。  
  
 関連情報については、トピック「インデックス オブジェクト」および DAO のヘルプでは、"現在のインデックス"の定義を参照してください。  
  
##  <a name="getdatecreated"></a>  CDaoRecordset::GetDateCreated  
 ベース テーブルが作成された日時を取得するには、このメンバー関数を呼び出します。  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>戻り値  
 A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)ベース テーブルが作成された日時を含むオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 日付と時刻の設定は、ベース テーブルが作成されているコンピューターから派生します。  
  
 関連情報については、DAO ヘルプのトピックの「作成日時、LastUpdated プロパティ」を参照してください。  
  
##  <a name="getdatelastupdated"></a>  CDaoRecordset::GetDateLastUpdated  
 スキーマが最後に更新された日時を取得するには、このメンバー関数を呼び出します。  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>戻り値  
 A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)ベース テーブルの構造 (スキーマ) が最後に更新された日時を含むオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 日付と時刻の設定は、ベース テーブルの構造 (スキーマ) が最後に更新されたコンピューターから派生します。  
  
 関連情報については、DAO ヘルプのトピックの「作成日時、LastUpdated プロパティ」を参照してください。  
  
##  <a name="getdefaultdbname"></a>  CDaoRecordset::GetDefaultDBName  
 このレコード セットに対して、データベースの名前を特定するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetDefaultDBName();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`このレコード セットの派生元のデータベースの名前とパスを格納しています。  
  
### <a name="remarks"></a>Remarks  
 レコード セットへのポインターなしで作成された場合、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)を開くには、既定のデータベースのレコード セットがこのパスが使用されます。 既定では、この関数は、空の文字列を返します。 ClassWizard がから新しいレコード セットを派生して`CDaoRecordset`のこの関数が作成されます。  
  
 次の例では、二重の円記号の使用 (\\\\)、文字列としての必須では、文字列を正しく解釈されるためです。  
  
 [!code-cpp[NVC_MFCDatabase#4](../../mfc/codesnippet/cpp/cdaorecordset-class_4.cpp)]  
  
##  <a name="getdefaultsql"></a>  CDaoRecordset::GetDefaultSQL  
 フレームワークは、レコード セットの基になる既定の SQL ステートメントを取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetDefaultSQL();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`を既定の SQL ステートメントが含まれています。  
  
### <a name="remarks"></a>Remarks  
 これは、テーブル名または SQL**選択**ステートメントです。  
  
 直接定義していない既定の SQL ステートメントで ClassWizard、レコード セット クラスを宣言することによってと ClassWizard では、このタスクを実行します。  
  
 Null SQL 文字列を渡す場合[開く](#open)、この関数は、レコード セットのテーブル名または SQL に確認し、します。  
  
##  <a name="geteditmode"></a>  CDaoRecordset::GetEditMode  
 このメンバー関数の編集、状態を調べるには、次の値の 1 つを呼び出します。  
  
```  
short GetEditMode();
```  
  
### <a name="return-value"></a>戻り値  
 現在のレコードの編集状態を示す値を返します。  
  
### <a name="remarks"></a>Remarks  
  
|[値]|説明|  
|-----------|-----------------|  
|**dbEditNone**|編集操作が進行中ではありません。|  
|**dbEditInProgress**|`Edit` 呼び出されました。|  
|**dbEditAdd**|`AddNew` 呼び出されました。|  
  
 関連情報については、DAO ヘルプの「EditMode プロパティ」を参照してください。  
  
##  <a name="getfieldcount"></a>  CDaoRecordset::GetFieldCount  
 レコード セットで定義されたフィールド (列) の数を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットのフィールドの数。  
  
### <a name="remarks"></a>Remarks  
 関連情報については、「Count プロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="getfieldinfo"></a>  CDaoRecordset::GetFieldInfo  
 レコード セット内のフィールドに関する情報を取得するには、このメンバー関数を呼び出します。  
  
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
 *nIndex*  
 インデックスで検索する場合、レコード セットのフィールド コレクションで定義済みフィールドの 0 から始まるインデックス。  
  
 *fieldinfo*  
 参照、 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体。  
  
 *dwInfoOptions*  
 取得するレコード セットに関する情報を指定するオプション。 使用可能なオプションは、それらの原因を返す関数もここで表示されます。 最適なパフォーマンスを必要な情報のレベルのみを取得します。  
  
- `AFX_DAO_PRIMARY_INFO` (既定値)名前、種類、サイズ、属性  
  
- `AFX_DAO_SECONDARY_INFO` プライマリについては、プラス: 必要に応じて、序数位置 0 長、照合順序、外部名、ソース フィールド、ソース テーブルを許可します。  
  
- `AFX_DAO_ALL_INFO` プライマリとセカンダリの情報と: 既定値、検証規則、検証テキスト  
  
 *lpszName*  
 フィールドの名前。  
  
### <a name="remarks"></a>Remarks  
 関数の 1 つのバージョンでは、インデックスを使用してフィールドを検索することができます。 その他のバージョンでは、名前、フィールドを検索することができます。  
  
 返される情報については、次を参照してください。、 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報項目に対応するは*dwInfoOptions*です。 1 つのレベルの情報を要求するときに、同様に、以前のレベルの情報を取得します。  
  
 関連情報については、DAO ヘルプの「属性プロパティ」を参照してください。  
  
##  <a name="getfieldvalue"></a>  CDaoRecordset::GetFieldValue  
 レコード セット内のデータを取得するには、このメンバー関数を呼び出します。  
  
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
 *lpszName*  
 フィールドの名前を表す文字列へのポインター。  
  
 *varValue*  
 参照、`COleVariant`フィールドの値を格納するオブジェクト。  
  
 *nIndex*  
 インデックスで検索する場合、レコード セットのフィールド コレクション内のフィールドの 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 2 つのバージョンの`GetFieldValue`値の戻り値を返す、 [COleVariant](../../mfc/reference/colevariant-class.md)フィールドの値を含むオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 名前または序数位置によって、フィールドを参照することができます。  
  
> [!NOTE]
>  呼び出しを取るメンバー関数のバージョンのいずれかをより効率的である、`COleVariant`オブジェクトを返すバージョンの呼び出しではなく、パラメーターとして参照、`COleVariant`オブジェクト。 この関数の以前のバージョンは、旧バージョンとの互換性のために保持されます。  
  
 使用して`GetFieldValue`と[いる](#setfieldvalue)実行時ではなく静的を使用してバインド列にフィールドに動的にバインドする、 [DoFieldExchange](#dofieldexchange)メカニズムです。  
  
 `GetFieldValue` および`DoFieldExchange`メカニズムは、パフォーマンスを向上させるために結合できます。 たとえば、使用して`GetFieldValue`、要求時にのみ必要な値を取得し、その呼び出しをインターフェイスで [詳細情報] ボタンを割り当てます。  
  
 関連情報については、「フィールド オブジェクト」と「Value プロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="getindexcount"></a>  CDaoRecordset::GetIndexCount  
 テーブル型のレコード セットで使用できるインデックスの数を決定するには、このメンバー関数を呼び出します。  
  
```  
short GetIndexCount();
```  
  
### <a name="return-value"></a>戻り値  
 テーブル型のレコード セット内のインデックスの数。  
  
### <a name="remarks"></a>Remarks  
 `GetIndexCount` レコード セット内のすべてのインデックスをループに役立ちます。 そのためを使用して`GetIndexCount`と共に[GetIndexInfo](#getindexinfo)です。 ダイナセットの種類またはスナップショットの種類のレコード セットでこのメンバー関数を呼び出すと、MFC は、例外をスローします。  
  
 関連情報については、DAO ヘルプの「属性プロパティ」を参照してください。  
  
##  <a name="getindexinfo"></a>  CDaoRecordset::GetIndexInfo  
 さまざまな種類のレコード セットを基になるベース テーブルで定義されているインデックスについての情報を取得するには、このメンバー関数を呼び出します。  
  
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
 *nIndex*  
 数値の位置で検索する場合、テーブルのインデックス コレクション内の 0 から始まるインデックス。  
  
 *indexinfo*  
 参照、 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)構造体。  
  
 *dwInfoOptions*  
 取得するインデックスに関する情報を指定するオプション。 使用可能なオプションは、それらの原因を返す関数もここで表示されます。 最適なパフォーマンスを必要な情報のレベルのみを取得します。  
  
- `AFX_DAO_PRIMARY_INFO` (既定値)名前、フィールドの情報、フィールド  
  
- `AFX_DAO_SECONDARY_INFO` プライマリについては、プラス: プライマリ、Unique、クラスター化された、IgnoreNulls、必要に応じて、異形式  
  
- `AFX_DAO_ALL_INFO` プライマリとセカンダリの情報と: 個別のカウント  
  
 *lpszName*  
 名前で検索のインデックス オブジェクトの名前へのポインター。  
  
### <a name="remarks"></a>Remarks  
 関数の 1 つのバージョンでは、コレクション内の位置でインデックスを検索することができます。 その他のバージョンでは、名前、インデックスを検索することができます。  
  
 返される情報については、次を参照してください。、 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報項目に対応するは*dwInfoOptions*です。 1 つのレベルの情報を要求するときに、同様に、以前のレベルの情報を取得します。  
  
 関連情報については、DAO ヘルプの「属性プロパティ」を参照してください。  
  
##  <a name="getlastmodifiedbookmark"></a>  CDaoRecordset::GetLastModifiedBookmark  
 最も最近追加または更新されたレコードのブックマークを取得するには、このメンバー関数を呼び出します。  
  
```  
COleVariant GetLastModifiedBookmark();
```  
  
### <a name="return-value"></a>戻り値  
 A`COleVariant`最後を示すブックマークを含む、追加またはレコードを変更します。  
  
### <a name="remarks"></a>Remarks  
 レコード セット オブジェクトを作成または開くときに各レコードは既に一意のブックマーク サポートしている場合。 呼び出す[GetBookmark](#getbookmark)をレコード セットにブックマークがサポートしているかを判断します。 レコード セットは、ブックマークをサポートしていない場合、`CDaoException`がスローされます。  
  
 レコードを追加するときに、レコード セットの最後に表示され、現在のレコードではありません。 新しいレコードを現在させるには、呼び出す`GetLastModifiedBookmark`およびを呼び出す`SetBookmark`を新しく追加したレコードを返します。  
  
 関連情報については、DAO ヘルプの「LastModified プロパティ」を参照してください。  
  
##  <a name="getlockingmode"></a>  CDaoRecordset::GetLockingMode  
 レコード セットに対して有効でロックの種類を確認するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetLockingMode();
```  
  
### <a name="return-value"></a>戻り値  
 ロックの種類は、ペシミスティック場合 0 以外。 ロックの場合は 0 です。  
  
### <a name="remarks"></a>Remarks  
 呼び出すと、すぐにロックされているときに排他ロックが有効で、編集しているレコードを含むデータ ページ、[編集](#edit)メンバー関数。 ページのロックが解除されてを呼び出すとき、[更新](#update)または[閉じる](#close)メンバー関数または移動または検索操作のいずれか。  
  
 レコードの更新中にのみレコードを含むデータ ページがロックされている共有ロックが有効で、ときに、`Update`メンバー関数。  
  
 ODBC データ ソースを使用するときにロック モードはオプティミスティック常にします。  
  
 関連情報については、「LockEdits プロパティ」と"ロック動作マルチ ユーザー アプリケーションで"DAO ヘルプ トピックを参照してください。  
  
##  <a name="getname"></a>  CDaoRecordset::GetName  
 レコード セットの名前を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`レコード セットの名前を含むです。  
  
### <a name="remarks"></a>Remarks  
 レコード セットの名前は文字で始める必要があり、最大 40 文字を含めることができます。 数字を含めることができ、アンダー スコア文字ですが、区切り記号やスペースを含めることはできません。  
  
 関連情報については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
##  <a name="getparamvalue"></a>  CDaoRecordset::GetParamValue  
 基になる DAOParameter オブジェクトに格納されている指定されたパラメーターの現在の値を取得するには、このメンバー関数を呼び出します。  
  
```  
virtual COleVariant GetParamValue(int nIndex);  
virtual COleVariant GetParamValue(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 基になる DAOParameter オブジェクトで、パラメーターの数値の位置。  
  
 *lpszName*  
 値を取得するパラメーターの名前。  
  
### <a name="return-value"></a>戻り値  
 クラスのオブジェクト[COleVariant](../../mfc/reference/colevariant-class.md)パラメーターの値を格納します。  
  
### <a name="remarks"></a>Remarks  
 パラメーターは、名前またはコレクション内の位置のいずれかにアクセスすることができます。  
  
 関連情報については、「パラメーター オブジェクトが」DAO ヘルプのトピックを参照してください。  
  
##  <a name="getpercentposition"></a>  CDaoRecordset::GetPercentPosition  
 呼び出すダイナセットの種類またはスナップショットの種類のレコード セットを使用しているときに`GetPercentPosition`移動量は、呼び出すことによって示されるアクセスできるレコードの数に対して、レコード セットを完全に設定するには、する前に[GetRecordCount](#getrecordcount).  
  
```  
float GetPercentPosition();
```  
  
### <a name="return-value"></a>戻り値  
 0 ~ 100 の数値では、レコード セット内のレコードの比率に基づいて、レコード セット オブジェクトの現在のレコードのおおよその場所を示します。  
  
### <a name="remarks"></a>Remarks  
 行うことができます、最後のレコードを呼び出して[MoveLast](#movelast)に完全なすべてのレコード セットが、これの母集団かかる場合がありますかなりの時間。  
  
 呼び出すことができます`GetPercentPosition`レコード セット オブジェクトの次の 3 つの種類でインデックスなしテーブルを含むです。 ただし、呼び出すことはできません`GetPercentPosition`スクロール順方向専用のスナップショット、または外部データベースに対してパススルー クエリから開かれたレコード セット。 現在のレコードがないか、彼は現在のレコードが削除された場合、`CDaoException`がスローされます。  
  
 関連情報については、DAO ヘルプの「PercentPosition プロパティ」を参照してください。  
  
##  <a name="getrecordcount"></a>  CDaoRecordset::GetRecordCount  
 レコード セットのレコードの数がアクセスされていないを調べるには、このメンバー関数を呼び出します。  
  
```  
long GetRecordCount();
```  
  
### <a name="return-value"></a>戻り値  
 レコード セット オブジェクトにアクセスするレコードの数を返します。  
  
### <a name="remarks"></a>Remarks  
 `GetRecordCount` アクセスされていないすべてのレコードになるまで、レコードの数がダイナセット タイプまたはスナップショットの種類のレコード セットに含まれるは示しません。 このメンバー関数の呼び出しは、かなりの時間を完了にかかる場合があります。  
  
 最後のレコードがアクセスされた後、戻り値は、レコード セットで削除されていないレコードの合計数を示します。 最後のレコードにアクセスするのには、呼び出し、`MoveLast`または`FindLast`レコード セットのメンバー関数。 また、クエリが返すレコードのおおよその数を決定するのに SQL Count を使用することができます。  
  
 ダイナセット タイプ、レコード セットの戻り値のレコードの削除、アプリケーションと`GetRecordCount`が減少します。 ただし、他のユーザーによって削除されたレコードはによって反映されません`GetRecordCount`まで、現在のレコードが削除されたレコードに位置付けられます。 レコードの数に影響するトランザクションを実行し、その後、トランザクションをロールバックして`GetRecordCount`残りのレコードの実際の数は反映されません。  
  
 値`GetRecordCount`スナップショット タイプのレコード セットからは影響しません、基になるテーブルに変更します。  
  
 値`GetRecordCount`テーブル型からレコード セットが、テーブルのレコードの概算数を反映し、テーブルのレコードが追加または削除されるとすぐに影響を受けるはします。  
  
 レコードのないレコード セットは、0 の値を返します。 アタッチされているテーブルまたは ODBC データベースを使用するときに`GetRecordCount`常に - 1 を返します。 呼び出す、`Requery`のレコード セットのメンバー関数の値にリセット`GetRecordCount`クエリが再実行された場合と同様です。  
  
 関連情報については、DAO ヘルプの「RecordCount プロパティ」を参照してください。  
  
##  <a name="getsql"></a>  CDaoRecordset::GetSQL  
 開かれたときに、レコード セットのレコードを選択するために使用された SQL ステートメントを取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetSQL() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A `CString` SQL ステートメントを含むです。  
  
### <a name="remarks"></a>Remarks  
 これは一般に、SQL になります**選択**ステートメントです。  
  
 によって返される文字列`GetSQL`通常とは異なる任意の文字列でレコード セットに渡された可能性があります、 *lpszSQL*パラメーターを[開く](#open)メンバー関数。 これは、レコード セットに渡される内容に基づく完全な SQL ステートメントを作成するため`Open`ClassWizard で指定した、およびどのような場合がありますで指定した、[か](#m_strfilter)と[レコード](#m_strsort)データ メンバーです。  
  
> [!NOTE]
>  呼び出した後にのみ、このメンバー関数を呼び出す`Open`です。  
  
 関連情報については、DAO ヘルプの「SQL プロパティ」を参照してください。  
  
##  <a name="gettype"></a>  CDaoRecordset::GetType  
 レコード セット オブジェクトの種類を決定するレコード セットを開いた後に、このメンバー関数を呼び出します。  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットの種類を示す値は次のいずれかです。  
  
- **dbOpenTable**テーブル型のレコード セット  
  
- **dbOpenDynaset**ダイナセット タイプのレコード セット  
  
- **dbOpenSnapshot**スナップショット タイプのレコード セット  
  
### <a name="remarks"></a>Remarks  
 関連情報については、DAO ヘルプの「型プロパティ」を参照してください。  
  
##  <a name="getvalidationrule"></a>  CDaoRecordset::GetValidationRule  
 データの検証に使用されるルールを判断するには、このメンバー関数を呼び出します。  
  
```  
CString GetValidationRule();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`が変更またはテーブルに追加すると、レコード内のデータを検証する値を含むオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 このルールは、テキスト ベースでは、し、基になるテーブルが変更されるたびに適用します。 データが有効でない場合、MFC は、例外をスローします。 返されたエラー メッセージは、指定した場合は基になるフィールド オブジェクトのプロパティのテキストまたは基になるフィールド オブジェクトのプロパティで指定された式のテキストです。 呼び出すことができます[GetValidationText](#getvalidationtext)エラー メッセージのテキストを取得します。  
  
 たとえば、月の日を必要とするレコードのフィールドがあります、検証規則など"DAY BETWEEN 1 から 31 です"。  
  
 関連情報については、"Validationrule"DAO ヘルプのトピックを参照してください。  
  
##  <a name="getvalidationtext"></a>  CDaoRecordset::GetValidationText  
 基になるフィールド オブジェクトのプロパティのテキストを取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetValidationText();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`フィールドの値が、基になるフィールド オブジェクトの検証規則を満たしていない場合に表示されるメッセージのテキストを含むオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 関連情報については、「プロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="isbof"></a>  CDaoRecordset::IsBOF  
 レコード セットの最初のレコードの前に位置しているかどうかを学習するレコードにレコードをスクロールする前に、このメンバー関数を呼び出します。  
  
```  
BOOL IsBOF() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットにレコードが含まれていない場合、または最初のレコードの前にスクロールした場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 呼び出すこともできます`IsBOF`と共に`IsEOF`レコード セットがすべてのレコードが含まれていますか空かどうかを確認します。 呼び出した後すぐに`Open`レコード セットに、レコードが含まれていない場合、 `IsBOF` 0 以外を返します。 最初のレコードが現在のレコードには、少なくとも 1 つのレコードがレコード セットを開いたときと`IsBOF`0 を返します。  
  
 最初のレコードは、現在のレコードとを呼び出す場合`MovePrev`、`IsBOF`後以外を返します。 場合`IsBOF`呼び出す 0 以外を返しますと`MovePrev`例外がスローされます。 場合`IsBOF`0 以外を返します、現在のレコードが定義されていないと、現在のレコードを必要とする任意のアクション、例外が発生します。  
  
 特定のメソッドの効果`IsBOF`と`IsEOF`設定。  
  
-   呼び出す`Open*`内部的には、最初のレコード、レコード セットの現在のレコードを呼び出して`MoveFirst`です。 そのため、`Open`レコード原因の空のセットで`IsBOF`と`IsEOF`に 0 以外を返します。 (失敗したときの動作については、次の表を参照してください`MoveFirst`または`MoveLast`呼び出します)。  
  
-   レコードを正常に配置したすべての移動操作が発生する両方`IsBOF`と`IsEOF`0 を返します。  
  
-   `AddNew`呼び出しが続いて、`Update`呼び出しが正常に新しいレコードを挿入すると、`IsBOF`を返す場合に限り、0、`IsEOF`が既に 0 以外。 状態`IsEOF`は常に変更されません。 定義されている Microsoft Jet データベース エンジンは、現在のレコードの後に、新しいレコードが挿入されるため、空のレコード セットの現在のレコード ポインターは、ファイルの最後にします。  
  
-   どの`Delete`の呼び出しで、レコードから残っている唯一のレコードを削除する場合でも、値を変更しないの`IsBOF`または`IsEOF`です。  
  
 この表では、移動操作のさまざまな組み合わせで使用できる`IsBOF` / `IsEOF`です。  
  
||MoveFirst、MoveLast|MovePrev、<br /><br /> < 0 を移動します。|0 を移動します。|MoveNext、<br /><br /> > 0 を移動します。|  
|------|-------------------------|-----------------------------|------------|-----------------------------|  
|`IsBOF`= 0 以外の場合<br /><br /> `IsEOF`=0|Allowed|例外|例外|Allowed|  
|`IsBOF`=0,<br /><br /> `IsEOF`0 以外の値 =|Allowed|Allowed|例外|例外|  
|0 以外の両方|例外|例外|例外|例外|  
|どちらも 0|Allowed|Allowed|Allowed|Allowed|  
  
 移動操作を許可してもの操作が正常にレコードを見つけるとは限りません。 だけでことを示します、指定した移動操作を実行しようとは許可されて例外は生成されません。 値、`IsBOF`と`IsEOF`動いておらず、実行しようとしたメンバー関数を変更することがあります。  
  
 移動操作の値には、レコードを特定できない場合の効果`IsBOF`と`IsEOF`設定が次の表に示すようにします。  
  
||IsBOF|IsEOF|  
|------|-----------|-----------|  
|`MoveFirst`, `MoveLast`|0 以外の値|0 以外の値|  
|`Move` 0|変更はありません。|変更はありません。|  
|`MovePrev`、 `Move` < 0|0 以外の値|変更はありません。|  
|`MoveNext`、 `Move` > 0|変更はありません。|0 以外の値|  
  
 関連情報については、トピックを参照してください。"BOF, EOF プロパティ"DAO のヘルプ。  
  
##  <a name="isdeleted"></a>  CDaoRecordset::IsDeleted  
 現在のレコードが削除されたかどうかを決定するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsDeleted() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットが削除されたレコードに配置されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 レコードをスクロールする場合と`IsDeleted`返します**TRUE** (0 以外)、スクロールして別のレコードに他のレコード セットの操作を実行する前にします。  
  
> [!NOTE]
>  スナップショット パブリケーションまたはテーブル型のレコード セット内のレコードの削除済みの状態を確認する必要はありません。 呼び出す必要はありませんレコードは、スナップショットから削除されることはできません、ため`IsDeleted`です。 テーブル型のレコード セットの削除されたレコードはレコード セットから実際に削除します。 レコードが削除されたして別のユーザーまたは別のレコード セット内のいずれかと、そのレコードにスクロールすることはできません。 したがってを呼び出す必要はありません`IsDeleted`です。  
  
 ダイナセットからレコードを削除して、レコード セットから削除されますそのレコードにスクロールすることはできません。 ただし場合内のレコード ダイナセットは削除別のユーザーによってまたは同じテーブルに基づく別のレコード セット内のいずれか`IsDeleted`戻ります**TRUE**そのレコードに後でスクロールしたとき。  
  
 関連情報については、「メソッドの削除」、「LastModified プロパティ」と「EditMode プロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="iseof"></a>  CDaoRecordset::IsEOF  
 レコードからレコード セットの最後のレコードを越えているかどうかを説明するレコードをスクロールするときに、このメンバー関数を呼び出します。  
  
```  
BOOL IsEOF() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットにレコードが含まれていない場合、または最後のレコードより後にスクロールする場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 呼び出すこともできます`IsEOF`レコード セットがすべてのレコードが含まれていますか空かどうかを確認します。 呼び出した後すぐに`Open`レコード セットに、レコードが含まれていない場合、 `IsEOF` 0 以外を返します。 最初のレコードが現在のレコードには、少なくとも 1 つのレコードがレコード セットを開いたときと`IsEOF`0 を返します。  
  
 呼び出すときに、最後のレコードが現在のレコードがかどうか`MoveNext`、`IsEOF`後以外を返します。 場合`IsEOF`呼び出す 0 以外を返しますと`MoveNext`例外がスローされます。 場合`IsEOF`0 以外を返します、現在のレコードが定義されていないと、現在のレコードを必要とする任意のアクション、例外が発生します。  
  
 特定のメソッドの効果`IsBOF`と`IsEOF`設定。  
  
-   呼び出す`Open`内部的には、最初のレコード、レコード セットの現在のレコードを呼び出して`MoveFirst`です。 そのため、`Open`レコード原因の空のセットで`IsBOF`と`IsEOF`に 0 以外を返します。 (失敗したときの動作については、次の表を参照してください`MoveFirst`呼び出します)。  
  
-   レコードを正常に配置したすべての移動操作が発生する両方`IsBOF`と`IsEOF`0 を返します。  
  
-   `AddNew`呼び出しが続いて、`Update`呼び出しが正常に新しいレコードを挿入すると、`IsBOF`を返す場合に限り、0、`IsEOF`が既に 0 以外。 状態`IsEOF`は常に変更されません。 定義されている Microsoft Jet データベース エンジンは、現在のレコードの後に、新しいレコードが挿入されるため、空のレコード セットの現在のレコード ポインターは、ファイルの最後にします。  
  
-   どの`Delete`の呼び出しで、レコードから残っている唯一のレコードを削除する場合でも、値を変更しないの`IsBOF`または`IsEOF`です。  
  
 この表では、移動操作のさまざまな組み合わせで使用できる`IsBOF` / `IsEOF`です。  
  
||MoveFirst、MoveLast|MovePrev、<br /><br /> < 0 を移動します。|0 を移動します。|MoveNext、<br /><br /> > 0 を移動します。|  
|------|-------------------------|-----------------------------|------------|-----------------------------|  
|`IsBOF`= 0 以外の場合<br /><br /> `IsEOF`=0|Allowed|例外|例外|Allowed|  
|`IsBOF`=0,<br /><br /> `IsEOF`0 以外の値 =|Allowed|Allowed|例外|例外|  
|0 以外の両方|例外|例外|例外|例外|  
|どちらも 0|Allowed|Allowed|Allowed|Allowed|  
  
 移動操作を許可してもの操作が正常にレコードを見つけるとは限りません。 だけでことを示します、指定した移動操作を実行しようとは許可されて例外は生成されません。 値、`IsBOF`と`IsEOF`動いておらず、実行しようとしたメンバー関数を変更することがあります。  
  
 移動操作の値には、レコードを特定できない場合の効果`IsBOF`と`IsEOF`設定が次の表に示すようにします。  
  
||IsBOF|IsEOF|  
|------|-----------|-----------|  
|`MoveFirst`, `MoveLast`|0 以外の値|0 以外の値|  
|`Move` 0|変更はありません。|変更はありません。|  
|`MovePrev`、 `Move` < 0|0 以外の値|変更はありません。|  
|`MoveNext`、 `Move` > 0|変更はありません。|0 以外の値|  
  
 関連情報については、トピックを参照してください。"BOF, EOF プロパティ"DAO のヘルプ。  
  
##  <a name="isfielddirty"></a>  CDaoRecordset::IsFieldDirty  
 ダイナセットの指定したフィールド データ メンバーを「ダーティ」としてマークされているかどうかを決定する (変更)。 このメンバー関数を呼び出します。  
  
```  
BOOL IsFieldDirty(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 *pv*  
 状態を確認するにはフィールド データ メンバーへのポインターまたは**NULL**をフィールドのいずれがダーティかどうかを判断します。  
  
### <a name="return-value"></a>戻り値  
 指定されたフィールド データ メンバーがダーティ; としてフラグが設定された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 すべてのダーティ フィールド データ メンバー内のデータは上を転送レコード、データ ソースへの呼び出しによって、現在のレコードが更新されたときに、`Update`のメンバー関数`CDaoRecordset`(の呼び出しに続く`Edit`または`AddNew`)。 このナレッジをさらに手順を実行できますなど、フラグ、フィールド データ メンバーをデータ ソースに書き込まれませんので、列をマークします。  
  
 `IsFieldDirty` によって実装され`DoFieldExchange`です。  
  
##  <a name="isfieldnull"></a>  CDaoRecordset::IsFieldNull  
 レコード セットの指定したフィールド データ メンバーを Null としてマークされているかどうかを決定するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsFieldNull(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 *pv*  
 状態を確認するにはフィールド データ メンバーへのポインターまたは**NULL**をフィールドのいずれかが Null であるかどうかを判断します。  
  
### <a name="return-value"></a>戻り値  
 指定されたフィールド データ メンバーが Null です。 としてフラグが設定された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 (データベース用語では、「値を持たない」手段を Null に設定と同じではありませんし**NULL** c++)。フィールド データ メンバーが Null としてフラグが設定した場合は、対象の値はありません、現在のレコードの列として解釈されます。  
  
> [!NOTE]
>  使用して、特定の状況で`IsFieldNull`できる効率的な場合は、次のコード例に示すようにします。  
  
 [!code-cpp[NVC_MFCDatabase#5](../../mfc/codesnippet/cpp/cdaorecordset-class_5.cpp)]  
  
> [!NOTE]
>  派生することがなく動的レコード バインドを使用しているかどうかは`CDaoRecordset`を使用してください**VT_** の例で示すようにします。  
  
##  <a name="isfieldnullable"></a>  CDaoRecordset::IsFieldNullable  
 このメンバー関数、指定されたフィールド データ メンバーが"null 値を許容"するかどうかを判断する (できます; に Null 値に設定C++ **NULL** Null の場合、つまり、データベース用語と同じではありません「値を持たない」) です。  
  
```  
BOOL IsFieldNullable(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 *pv*  
 状態を確認するにはフィールド データ メンバーへのポインターまたは**NULL**をフィールドのいずれかが Null であるかどうかを判断します。  
  
### <a name="return-value"></a>戻り値  
 以外の場合、指定されたフィールド データ メンバーにできる Null です。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 Null 値は、フィールド値が必要です。 このようなフィールドを追加またはレコードを更新する場合は Null に設定しようとすると、データ ソースは追加または更新プログラムを拒否し、`Update`例外がスローされます。 呼び出すときに例外が発生した`Update`を呼び出すときではなく、`SetFieldNull`です。  
  
##  <a name="isopen"></a>  CDaoRecordset::IsOpen  
 レコード セットが開いているかどうかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、レコード セット オブジェクトの`Open`または`Requery`メンバー関数が呼び出されていたため、レコード セットが閉じられましたできません; 0 それ以外の場合。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="m_bcheckcachefordirtyfields"></a>  CDaoRecordset::m_bCheckCacheForDirtyFields  
 かどうかキャッシュされているフィールドは自動的にマーク ダーティとして (変更) を示すフラグを格納および Null です。  
  
### <a name="remarks"></a>Remarks  
 フラグの既定値**TRUE**です。 このデータ メンバーの設定は、全体のダブル バッファリングの機構を制御します。 フラグを設定する場合**TRUE**、DFX メカニズムを使用してフィールドの単位でキャッシュを無効にできます。 フラグを設定する場合**FALSE**、呼び出す必要があります`SetFieldDirty`と`SetFieldNull`自分でします。  
  
 呼び出しの前にこのデータ メンバーをセット`Open`です。 このメカニズムは、主に、使いやすさです。 パフォーマンスは、変更に合わせてフィールドのダブル バッファリングにより低下する可能性があります。  
  
##  <a name="m_nfields"></a>  CDaoRecordset::m_nFields  
 レコード セット クラスのフィールド データ メンバーの数と、データ ソースからレコード セットが選択した列の数が含まれています。  
  
### <a name="remarks"></a>Remarks  
 レコード セット クラスのコンス トラクターを初期化する必要があります`m_nFields`と静的にバインドされたフィールドの正しい数。 ClassWizard は、レコード セット クラスの宣言を使用するときに、この初期化を書き込みます。 手動で記述することもできます。  
  
 フレームワークは、フィールド データ メンバーと、データ ソースの現在のレコードの対応する列間の相互作用を管理するのに、この番号を使用します。  
  
> [!NOTE]
>  この数に登録されている出力列の数に対応する必要があります`DoFieldExchange`への呼び出し後`SetFieldType`パラメーターを使用して**CDaoFieldExchange::outputColumn**です。  
  
 ようで動的に列をバインドする`CDaoRecordset::GetFieldValue`と`CDaoRecordset::SetFieldValue`です。 これを行う場合はでカウントをインクリメントする必要はありません`m_nFields`呼び出し DFX 関数の数を反映するように、`DoFieldExchange`メンバー関数。  
  
##  <a name="m_nparams"></a>  CDaoRecordset::m_nParams  
 レコード セット クラスのパラメーター データ メンバーの数が含まれています: レコード セットのクエリで渡されるパラメーターの数。  
  
### <a name="remarks"></a>Remarks  
 クラスのコンス トラクターを初期化する必要があります、レコード セット クラスにパラメーター データ メンバーがある場合は、 *m_nParams*を正しい値にします。 値*m_nParams*既定値は 0 です。 パラメーター データ メンバーを追加する場合、手動で行うことができます: パラメーターの数を反映するように、クラス コンス トラクターで初期化を手動で追加する必要があります (の数とサイズ以上である必要がありますが ' 内のプレース ホルダー、*か*または*レコード*文字列)。  
  
 フレームワークは、レコード セットのクエリをパラメーター化するときに、この番号を使用します。  
  
> [!NOTE]
>  この数は、「パラメーター」に登録されている数に対応する必要があります`DoFieldExchange`への呼び出し後`SetFieldType`パラメーターを使用して**CFieldExchange::param**です。  
  
 関連情報については、「パラメーター オブジェクトが」DAO ヘルプのトピックを参照してください。  
  
##  <a name="m_pdaorecordset"></a>  CDaoRecordset::m_pDAORecordset  
 DAO レコード セット オブジェクト基になるの OLE インターフェイスへのポインターが含まれています、`CDaoRecordset`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 DAO インターフェイスに直接アクセスする必要がある場合は、このポインターを使用します。  
  
 関連情報については、「Recordset オブジェクト」DAO ヘルプのトピックを参照してください。  
  
##  <a name="m_pdatabase"></a>  CDaoRecordset::m_pDatabase  
 ポインターが含まれています、`CDaoDatabase`データ ソースに使用されるレコード セットが接続されているオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 この変数は、2 つの方法で設定されます。 通常、ポインターを渡して、既に開かれている`CDaoDatabase`オブジェクトのレコード セット オブジェクトを構築するときにします。 渡す場合**NULL**代わりに、`CDaoRecordset`を作成、`CDaoDatabase`オブジェクトを開きます。 どちらの場合、`CDaoRecordset`この変数にポインターを格納します。  
  
 通常は直接不要に格納されているポインターを使用する**m_pDatabase**です。 独自の拡張機能を記述する場合`CDaoRecordset`、ただし、ポインターを使用する必要があります。 たとえば、する必要があります、ポインターをスローする場合、独自`CDaoException`(秒)。  
  
 関連情報については、「データベースのオブジェクト」DAO ヘルプのトピックを参照してください。  
  
##  <a name="m_strfilter"></a>  CDaoRecordset::m_strFilter  
 構築するために使用する文字列を含む、**場所**SQL ステートメントの句。  
  
### <a name="remarks"></a>Remarks  
 予約語を含まない**場所**をレコード セットをフィルター処理します。 このデータ メンバーの使用は、テーブル型のレコード セットを適用できません。 使用**か**も何も起こりませんを使用して、レコード セットを開くときに、`CDaoQueryDef`ポインター。  
  
 米国の日付形式 (月-日-年) を使用して、Microsoft Jet データベース エンジンの; 米国バージョンを使用していない場合でも、日付を持つフィールドをフィルター処理する場合それ以外の場合、データは、期待どおりにいないフィルター可能性があります。  
  
 関連情報については、DAO ヘルプの「フィルター プロパティ」を参照してください。  
  
##  <a name="m_strsort"></a>  CDaoRecordset::m_strSort  
 含む文字列が含まれています、 **ORDERBY**予約語を含まない SQL ステートメントの句**ORDERBY**です。  
  
### <a name="remarks"></a>Remarks  
 ダイナセットのスナップショットの種類のレコード セット オブジェクトを並べ替えることができます。  
  
 テーブル型のレコード セット オブジェクトを並べ替えることはできません。 テーブル型のレコード セットの並べ替え順序を特定するのには、呼び出す[SetCurrentIndex](#setcurrentindex)です。  
  
 使用*レコード*も何も起こりませんを使用して、レコード セットを開くときに、`CDaoQueryDef`ポインター。  
  
 関連情報については、DAO ヘルプの「並べ替えプロパティ」を参照してください。  
  
##  <a name="move"></a>  CDaoRecordset::Move  
 レコード セットに移動するには、このメンバー関数を呼び出す*lRows*現在のレコードからのレコードです。  
  
```  
virtual void Move(long lRows);
```  
  
### <a name="parameters"></a>パラメーター  
 *lRows*  
 前方または後方に移動するレコードの数。 正の値は、レコード セットの末尾に向かって前方移動します。 負の値は、先頭に向かって後方移動します。  
  
### <a name="remarks"></a>Remarks  
 前方または後方に移動することができます。 `Move( 1 )` 等価`MoveNext`、および`Move( -1 )`は等価`MovePrev`です。  
  
> [!CAUTION]
>  いずれかを呼び出して、`Move`レコード セットにレコードが存在しない場合、関数が例外をスローします。 一般に、両方を呼び出す`IsBOF`と`IsEOF`移動操作をいくつかのレコードをレコード セットが存在するかどうかを判断する前にします。 呼び出した後`Open`または`Requery`、いずれかを呼び出す`IsBOF`または`IsEOF`です。  
  
> [!NOTE]
>  先頭またはレコード セットの末尾を越えてスクロールした場合 (`IsBOF`または`IsEOF`0 以外を返します) への呼び出し`Move`スロー、`CDaoException`です。  
  
> [!NOTE]
>  呼び出す場合、`Move`関数を現在のレコードがされている間に更新または追加、更新プログラムは警告なしに失われます。  
  
 呼び出すと`Move`前方スクロールのスナップショットで、`lRows`パラメーターは正の整数を指定する必要がありますに移動できるように前方のみ、ブックマークは使用できません。  
  
 First、last、次に、以前レコードまたはレコード セットから、現在のレコードを呼び出し、 `MoveFirst`、 `MoveLast`、 `MoveNext`、または`MovePrev`メンバー関数。  
  
 関連情報については、トピックを参照して、「Move メソッド」と"MoveFirst、MoveLast、MoveNext、MovePrevious メソッド"DAO のヘルプ。  
  
##  <a name="movefirst"></a>  CDaoRecordset::MoveFirst  
 (存在する場合)、レコード セットの最初のレコードを作成するには、このメンバー関数を呼び出して、現在のレコードです。  
  
```  
void MoveFirst();
```  
  
### <a name="remarks"></a>Remarks  
 呼び出していない`MoveFirst`レコード セットを開いた直後後。 その時点では、最初のレコード (存在する場合) と、現在のレコードでは自動的にします。  
  
> [!CAUTION]
>  いずれかを呼び出して、`Move`レコード セットにレコードが存在しない場合、関数が例外をスローします。 一般に、両方を呼び出す`IsBOF`と`IsEOF`移動操作をいくつかのレコードをレコード セットが存在するかどうかを判断する前にします。 呼び出した後`Open`または`Requery`、いずれかを呼び出す`IsBOF`または`IsEOF`です。  
  
> [!NOTE]
>  呼び出す場合、`Move`関数を現在のレコードがされている間に更新または追加、更新プログラムは警告なしに失われます。  
  
 使用して、`Move`条件を適用することがなくレコード間を移動する関数。 ダイナセット タイプまたは特定の条件に適合するスナップショットの種類のレコード セット オブジェクト内でレコードを検索するのにには、検索操作を使用します。 テーブル型のレコード セット オブジェクトでレコードを検索、呼び出す`Seek`です。  
  
 レコード セットは、テーブル型のレコード セットを参照している場合、移動は、テーブルの現在のインデックスをたどります。 現在のインデックスを設定するには、基になる DAO オブジェクトのインデックス プロパティを使用します。 場合は、現在のインデックスを設定しないと、返されたレコードの順序は定義されません。  
  
 呼び出す場合`MoveLast`SQL クエリまたはクエリに基づいて、レコード セット オブジェクトは、クエリが完了するまで強制実行され、レコード セット オブジェクトが完全に設定されます。  
  
 呼び出すことはできません、`MoveFirst`または`MovePrev`前方スクロール スナップショットを使用してメンバー関数。  
  
 個のレコードを前方または後方の固有の仕様、レコード セット オブジェクトで、現在の位置を記録するには、呼び出す`Move`です。  
  
 関連情報については、トピックを参照して、「Move メソッド」と"MoveFirst、MoveLast、MoveNext、MovePrevious メソッド"DAO のヘルプ。  
  
##  <a name="movelast"></a>  CDaoRecordset::MoveLast  
 レコード セットの現在のレコード内 (存在する場合) は、最後のレコードを作成するには、このメンバー関数を呼び出します。  
  
```  
void MoveLast();
```  
  
### <a name="remarks"></a>Remarks  
  
> [!CAUTION]
>  いずれかを呼び出して、`Move`レコード セットにレコードが存在しない場合、関数が例外をスローします。 一般に、両方を呼び出す`IsBOF`と`IsEOF`移動操作をいくつかのレコードをレコード セットが存在するかどうかを判断する前にします。 呼び出した後`Open`または`Requery`、いずれかを呼び出す`IsBOF`または`IsEOF`です。  
  
> [!NOTE]
>  呼び出す場合、`Move`関数を現在のレコードがされている間に更新または追加、更新プログラムは警告なしに失われます。  
  
 使用して、`Move`条件を適用することがなくレコード間を移動する関数。 ダイナセット タイプまたは特定の条件に適合するスナップショットの種類のレコード セット オブジェクト内でレコードを検索するのにには、検索操作を使用します。 テーブル型のレコード セット オブジェクトでレコードを検索、呼び出す`Seek`です。  
  
 レコード セットは、テーブル型のレコード セットを参照している場合、移動は、テーブルの現在のインデックスをたどります。 現在のインデックスを設定するには、基になる DAO オブジェクトのインデックス プロパティを使用します。 場合は、現在のインデックスを設定しないと、返されたレコードの順序は定義されません。  
  
 呼び出す場合`MoveLast`SQL クエリまたはクエリに基づいて、レコード セット オブジェクトは、クエリが完了するまで強制実行され、レコード セット オブジェクトが完全に設定されます。  
  
 個のレコードを前方または後方の固有の仕様、レコード セット オブジェクトで、現在の位置を記録するには、呼び出す`Move`です。  
  
 関連情報については、トピックを参照して、「Move メソッド」と"MoveFirst、MoveLast、MoveNext、MovePrevious メソッド"DAO のヘルプ。  
  
##  <a name="movenext"></a>  CDaoRecordset::MoveNext  
 現在のレコードのレコード セット内の次のレコードを作成するには、このメンバー関数を呼び出します。  
  
```  
void MoveNext();
```  
  
### <a name="remarks"></a>Remarks  
 呼び出すことをお勧め`IsBOF`前のレコードに移動しようとする前にします。 呼び出し`MovePrev`がスローされます、`CDaoException`場合`IsBOF`、既にスクロールした最初のレコードの前に、またはレコード セットによってレコードが選択されていないことを示す 0 以外を返します。  
  
> [!CAUTION]
>  いずれかを呼び出して、`Move`レコード セットにレコードが存在しない場合、関数が例外をスローします。 一般に、両方を呼び出す`IsBOF`と`IsEOF`移動操作をいくつかのレコードをレコード セットが存在するかどうかを判断する前にします。 呼び出した後`Open`または`Requery`、いずれかを呼び出す`IsBOF`または`IsEOF`です。  
  
> [!NOTE]
>  呼び出す場合、`Move`関数を現在のレコードがされている間に更新または追加、更新プログラムは警告なしに失われます。  
  
 使用して、`Move`条件を適用することがなくレコード間を移動する関数。 ダイナセット タイプまたは特定の条件に適合するスナップショットの種類のレコード セット オブジェクト内でレコードを検索するのにには、検索操作を使用します。 テーブル型のレコード セット オブジェクトでレコードを検索、呼び出す`Seek`です。  
  
 レコード セットは、テーブル型のレコード セットを参照している場合、移動は、テーブルの現在のインデックスをたどります。 現在のインデックスを設定するには、基になる DAO オブジェクトのインデックス プロパティを使用します。 場合は、現在のインデックスを設定しないと、返されたレコードの順序は定義されません。  
  
 個のレコードを前方または後方の固有の仕様、レコード セット オブジェクトで、現在の位置を記録するには、呼び出す`Move`です。  
  
 関連情報については、トピックを参照して、「Move メソッド」と"MoveFirst、MoveLast、MoveNext、MovePrevious メソッド"DAO のヘルプ。  
  
##  <a name="moveprev"></a>  CDaoRecordset::MovePrev  
 現在のレコードのレコード セットの前のレコードを作成するには、このメンバー関数を呼び出します。  
  
```  
void MovePrev();
```  
  
### <a name="remarks"></a>Remarks  
 呼び出すことをお勧め`IsBOF`前のレコードに移動しようとする前にします。 呼び出し`MovePrev`がスローされます、`CDaoException`場合`IsBOF`、既にスクロールした最初のレコードの前に、またはレコード セットによってレコードが選択されていないことを示す 0 以外を返します。  
  
> [!CAUTION]
>  いずれかを呼び出して、`Move`レコード セットにレコードが存在しない場合、関数が例外をスローします。 一般に、両方を呼び出す`IsBOF`と`IsEOF`移動操作をいくつかのレコードをレコード セットが存在するかどうかを判断する前にします。 呼び出した後`Open`または`Requery`、いずれかを呼び出す`IsBOF`または`IsEOF`です。  
  
> [!NOTE]
>  呼び出す場合、`Move`関数を現在のレコードがされている間に更新または追加、更新プログラムは警告なしに失われます。  
  
 使用して、`Move`条件を適用することがなくレコード間を移動する関数。 ダイナセット タイプまたは特定の条件に適合するスナップショットの種類のレコード セット オブジェクト内でレコードを検索するのにには、検索操作を使用します。 テーブル型のレコード セット オブジェクトでレコードを検索、呼び出す`Seek`です。  
  
 レコード セットは、テーブル型のレコード セットを参照している場合、移動は、テーブルの現在のインデックスをたどります。 現在のインデックスを設定するには、基になる DAO オブジェクトのインデックス プロパティを使用します。 場合は、現在のインデックスを設定しないと、返されたレコードの順序は定義されません。  
  
 呼び出すことはできません、`MoveFirst`または`MovePrev`前方スクロール スナップショットを使用してメンバー関数。  
  
 個のレコードを前方または後方の固有の仕様、レコード セット オブジェクトで、現在の位置を記録するには、呼び出す`Move`です。  
  
 関連情報については、トピックを参照して、「Move メソッド」と"MoveFirst、MoveLast、MoveNext、MovePrevious メソッド"DAO のヘルプ。  
  
##  <a name="open"></a>  Cdaorecordset::open  
 レコード セットのレコードを取得するには、このメンバー関数を呼び出す必要があります。  
  
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
 *できるかどうか*  
 次のいずれかの値です。  
  
- **dbOpenDynaset**双方向にスクロールできるダイナセット タイプのレコード セット。 既定値です。  
  
- **dbOpenTable**双方向にスクロールできるタイプのレコードです。  
  
- **dbOpenSnapshot**双方向にスクロールできるスナップショットの種類のレコード セット。  
  
 *lpszSQL*  
 次のいずれかを含む文字列ポインター:  
  
-   A **NULL**ポインター。  
  
-   1 つまたは複数のテーブル定義および querydefs (コンマ区切り) の名前。  
  
-   SQL**選択**ステートメント (SQL オプションで**場所**または**ORDERBY**句)。  
  
-   パススルー クエリ。  
  
 *nOptions*  
 1 つ以上の以下のオプションです。 既定値は 0 です。 次の値を指定できます。  
  
- **dbAppendOnly**のみ (ダイナセット タイプのレコード セットのみ) の新しいレコードを追加することができます。 このオプションは、あるレコードのみ追加することにリテラルを意味します。 MFC ODBC データベース クラスには、レコードの取得し、追加可能追加専用オプションが用意されています。  
  
- **dbForwardOnly**レコード セットは、順方向専用のスナップショットがスクロールします。  
  
- **dbSeeChanges**別のユーザーが編集してデータを変更する場合に例外を生成します。  
  
- **dbDenyWrite**他のユーザーを変更またはレコードを追加できません。  
  
- **dbDenyRead**他のユーザーがレコード (テーブル型のレコード セットのみ) を表示できません。  
  
- **dbReadOnly**レコードのみを表示できます。 他のユーザーが変更できます。  
  
- **組み合わせて**一貫性のない更新が許可される (ダイナセット タイプのレコード セットのみ)。  
  
- **指定できます**のみ一貫性のある更新プログラムが (ダイナセット タイプのレコード セットのみ) を使用できます。  
  
> [!NOTE]
>  定数**指定できます**と**組み合わせて**は相互に排他的です。 いずれかを使用するか、一方の特定のインスタンスの両方ではなく`Open`です。  
  
 *pTableDef*  
 ポインター、[どちら](../../mfc/reference/cdaotabledef-class.md)オブジェクト。 このバージョンは、テーブル型のレコード セットに対してのみ有効です。 このオプションを使用する場合、`CDaoDatabase`ポインターを構築するために使用、`CDaoRecordset`は使用されません。 代わりに、テーブル定義が存在するデータベースが使用されます。  
  
 *pQueryDef*  
 ポインター、 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)オブジェクト。 このバージョンでは、ダイナセット タイプとスナップショットの種類のレコード セットに対してのみ有効です。 このオプションを使用する場合、`CDaoDatabase`ポインターを構築するために使用、`CDaoRecordset`は使用されません。 代わりに、クエリ定義が存在するデータベースが使用されます。  
  
### <a name="remarks"></a>Remarks  
 呼び出しの前に`Open`、レコード セット オブジェクトを構築する必要があります。 これにはいくつかの方法があります。  
  
-   レコード セット オブジェクトを構築するときにへのポインターを渡す、`CDaoDatabase`既に開かれているオブジェクト。  
  
-   レコード セット オブジェクトを構築するときにへのポインターを渡す、`CDaoDatabase`が開かれていないオブジェクトです。 レコード セットが開く、`CDaoDatabase`オブジェクトが、レコード セット オブジェクトを閉じるときに、その閉じられません。  
  
-   レコード セット オブジェクトを構築するときに渡す、 **NULL**ポインター。 レコード セット オブジェクトの呼び出し`GetDefaultDBName`Microsoft Access の名前を取得します。MDB ファイルを開きます。 レコード セットが、開く、`CDaoDatabase`レコード セットが開かれている限りを開くことが保持しておくオブジェクトです。 呼び出すと`Close`、レコード セットで、`CDaoDatabase`オブジェクトが閉じられてもいます。  
  
    > [!NOTE]
    >  レコード セットを開くと、`CDaoDatabase`オブジェクト、非排他アクセス権を持つデータ ソースを開きます。  
  
 バージョンの`Open`を使用して、 *lpszSQL*パラメーター、いくつかの方法の 1 つのレコードを取得するには、レコード セットが開く。 DFX 関数に 1 つ目は、`DoFieldExchange`です。 2 番目のオプションは、呼び出すことによって動的バインドを使用する、`GetFieldValue`メンバー関数。 これらのオプションは、個別にまたは組み合わせで実装できます。 それらが結合され、ならを渡す SQL ステートメントで自分自身への呼び出しで`Open`です。  
  
 2 番目のバージョンを使用すると`Open`に渡せば、`CDaoTableDef`オブジェクトを結果として得られる列を使用してバインドできるようになります`DoFieldExchange`と DFX メカニズムや経由で動的にバインド`GetFieldValue`です。  
  
> [!NOTE]
>  のみ呼び出せます`Open`を使用して、`CDaoTableDef`テーブル型のレコード セットのオブジェクト。  
  
 3 番目のバージョンを使用すると`Open`に渡せば、`CDaoQueryDef`オブジェクト、クエリが実行され、結果として得られる列があるを使用してバインドするための使用可能な`DoFieldExchange`と DFX メカニズムや経由で動的にバインド`GetFieldValue`です。  
  
> [!NOTE]
>  呼び出すことができますのみ`Open`を使用して、`CDaoQueryDef`ダイナセットの型とスナップショットの種類のレコード セット オブジェクトです。  
  
 最初のバージョンの`Open`を使用して、`lpszSQL`パラメーター、レコードは、次の表に示すようにに基づいて条件を選択します。  
  
|パラメーター `lpszSQL` の値。|レコードの選択基準|例|  
|--------------------------------------|----------------------------------------|-------------|  
|**NULL**|`GetDefaultSQL` の返す文字列。||  
|1 つまたは複数のテーブル定義やクエリ定義名のコンマ区切りの一覧です。|表されるすべての列、`DoFieldExchange`です。|`"Customer"`|  
|**選択**列リスト**FROM**テーブル リスト|指定されたテーブルまたはクエリ定義から指定された列です。|`"SELECT CustId, CustName`<br /><br /> `FROM Customer"`|  
  
 通常のプロシージャでは**NULL**に`Open`以外の場合は、`Open`呼び出し`GetDefaultSQL`、ClassWizard が作成するときに生成するオーバーライド可能なメンバー関数、 `CDaoRecordset`-クラスを派生します。 この値は、ClassWizard で指定したテーブルまたはクエリ定義の名前を示します。 他の情報を指定できます、 *lpszSQL*パラメーター。  
  
 何を渡した`Open`クエリの最終的な SQL 文字列を構築 (SQL も**場所**と**ORDERBY**に句が追加されます、 *lpszSQL*文字列渡されたする) と、そのクエリを実行します。 呼び出すことによって構築された文字列を調べることができます`GetSQL`呼び出した後`Open`です。  
  
 レコードセット クラスのフィールド データ メンバーは、選択したデータの列に結び付けられています。 いくつかのレコードが返された場合、最初のレコードが現在のレコードになります。  
  
 レコード セットは、フィルターや並べ替えなどのオプションを設定する場合は、設定**レコード**または**か**を呼び出す前に、レコード セット オブジェクトを構築した後、`Open`です。 レコード セットは既に開いてレコード セット内のレコードを更新する場合は、呼び出す`Requery`です。  
  
 呼び出す場合`Open`ダイナセット型またはスナップショットの種類のレコード セットに使用することはできません、データ ソースを指す場合、SQL ステートメントまたはアタッチ テーブルを表すテーブル定義、または**dbOpenTable**型引数ですこの場合、MFC の。例外をスローします。 テーブル定義オブジェクトが接続されているテーブルを表すかどうかを確認するのには、作成、[どちら](../../mfc/reference/cdaotabledef-class.md)オブジェクトと呼び出しの[GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect)メンバー関数。  
  
 使用して、 **dbSeeChanges**を編集または同じのレコードを削除するときに、別のユーザーまたはコンピューターに別のプログラムによって行われた変更をトラップする場合にフラグを設定します。 たとえば、2 人のユーザーが、同じレコードを呼び出して最初のユーザーの編集を開始、`Update`メンバー関数は成功します。 ときに`Update`2 番目のユーザーによって呼び出される、`CDaoException`がスローされます。 同様に、2 番目のユーザーが呼び出すしようとすると`Delete`、レコードおよびそれを削除するが既に変更されて、最初のユーザーによって、`CDaoException`に発生します。  
  
 通常、ユーザーがこの場合`CDaoException`の更新中に、コード必要があります、フィールドの内容を更新し、新しく変更された値を取得します。 削除する処理を行って、例外が発生した場合、コードは、データが最近変更されたことを示すメッセージをユーザーに、新しいレコードのデータを表示する可能性があります。 この時点では、コードでは、ユーザーがレコードを削除してもよいことの確認を要求できます。  
  
> [!TIP]
>  順方向専用のスクロール オプションを使用して ( **dbForwardOnly**) アプリケーションがレコード セットを 1 つのパススルーを行うときに、パフォーマンスを向上させるために、ODBC データ ソースから開きます。  
  
 関連情報については、DAO ヘルプの「何らかメソッド」を参照してください。  
  
##  <a name="requery"></a>  CDaoRecordset::Requery  
 レコード セットを (更新) を再構築するには、このメンバー関数を呼び出します。  
  
```  
virtual void Requery();
```  
  
### <a name="remarks"></a>Remarks  
 いくつかのレコードが返された場合、最初のレコードが現在のレコードになります。  
  
 レコード セットを反映して追加および削除するか、他のユーザーがデータ ソースに対して実行するためには、呼び出すことによってレコード セットをリビルドする必要があります`Requery`です。 レコード セットがダイナセットの場合は、または他のユーザーがその既存のレコード (ただし、追加機能ではない) を構成する更新プログラムを自動的に反映します。 レコード セットがスナップショットの場合は、呼び出す必要があります`Requery`編集内容を他のユーザーだけでなく追加および削除を反映するようにします。  
  
 ダイナセットまたはスナップショットのいずれかを呼び出す`Requery`パラメーター値を使用して、レコード セットを再構築する任意の時間。 設定して、新しいフィルターまたは並べ替えを設定[か](#m_strfilter)と[レコード](#m_strsort)呼び出す前に`Requery`です。 新しい値を呼び出す前にパラメーター データ メンバーに割り当てることによって新しいパラメーターの設定`Requery`です。  
  
 レコード セットを再構築する試行が失敗した場合、レコード セットは閉じられます。 呼び出す前に`Requery`、呼び出すことによって、レコード セットを表示できるかどうかを決定できます、 [CanRestart](#canrestart)メンバー関数。 `CanRestart` 限りませんを`Requery`は成功します。  
  
> [!CAUTION]
>  呼び出す`Requery`を呼び出した後にのみ`Open`です。  
  
> [!NOTE]
>  呼び出す[Requery](#requery) DAO ブックマークを変更します。  
  
 呼び出すことはできません`Requery`ダイナセット型またはスナップショットの種類のレコード セットを呼び出す場合に`CanRestart`0 を返しますまたすることも、テーブル型のレコードです。  
  
 両方`IsBOF`と`IsEOF`呼び出し後に 0 以外を返します`Requery`、いくつかのレコードと、レコード セットはデータを含まないクエリが返されませんでした。  
  
 関連情報については、「Requery メソッド」DAO ヘルプのトピックを参照してください。  
  
##  <a name="seek"></a>  CDaoRecordset::Seek  
 指定された条件を現在のインデックスを作成し、そのレコードを現在のレコードに適合するインデックス付きのテーブル型のレコード セット オブジェクト内でレコードを検索するには、このメンバー関数を呼び出します。  
  
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
 *lpszComparison*  
 次の文字列式のいずれかの:"<「、」\<="、「=」、"> ="、または">"です。  
  
 *pKey1*  
 ポインター、 [COleVariant](../../mfc/reference/colevariant-class.md)値を持つが、インデックスの最初のフィールドに対応しています。 必須。  
  
 *pKey2*  
 ポインター、`COleVariant`存在する場合、インデックスで、2 番目のフィールドに値が対応しています。 既定値は**NULL**です。  
  
 *pKey3*  
 ポインター、`COleVariant`存在する場合、インデックスで、3 番目のフィールドに値が対応しています。 既定値は**NULL**です。  
  
 *pKeyArray*  
 バリアント型の配列へのポインター。 配列のサイズは、インデックス内のフィールドの数に対応します。  
  
 *nKeys*  
 これは、インデックス内のフィールドの数と、配列のサイズに対応する整数。  
  
> [!NOTE]
>  キーには、ワイルドカードを指定しません。 ワイルドカードがにより`Seek`から一致するレコードが返されない。  
  
### <a name="return-value"></a>戻り値  
 一致するレコードが見つかった場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>Remarks  
 2 つ目の (配列) の形式を使用して`Seek`以上の 4 つのフィールドのインデックスを処理します。  
  
 `Seek` 高パフォーマンス インデックスをテーブル型のレコード セットで検索を有効にします。 呼び出して、現在のインデックスを設定する必要があります`SetCurrentIndex`呼び出す前に`Seek`です。 インデックスが一意のキー フィールドまたはフィールドを場合`Seek`条件を満たす最初のレコードを検索します。 インデックスを設定しないと、例外がスローされます。  
  
 UNICODE のレコード セットを作成していない場合、`COleVariant`オブジェクト必要があります明示的に宣言する ANSI です。 This can be done by using the [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc***,** *vtSrc* **)** form of constructor with *vtSrc* set to `VT_BSTRT` (ANSI) or by using the **COleVariant** function [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc***,** *vtSrc* **)** with *vtSrc* set to `VT_BSTRT`.  
  
 呼び出すと`Seek`、渡す 1 つまたは複数のキー値と比較演算子 ("<「、」\<="、「=」、"> ="、または">") です。 `Seek` 指定されたキー フィールドを検索してで指定された条件を満たす最初のレコードを見つけます*lpszComparison*と*pKey1*です。 見つかったら、 `Seek` 、0 以外を返すし、そのレコードは現在、します。 場合`Seek`、一致の検索に失敗`Seek`0 が返されます、および現在のレコードが定義されていません。 DAO の直接を使用する場合は、NoMatch プロパティを明示的にチェックする必要があります。  
  
 場合`lpszComparison`は「=」、"> ="、または">"、`Seek`インデックスの先頭から開始します。 場合*lpszComparison*は"<"または"< ="、`Seek`インデックスの最後に起動し、最後に重複するインデックス エントリがある場合を除き、逆方向に検索します。 この場合、`Seek`インデックスの最後に重複するインデックス エントリの中で任意のエントリから開始します。  
  
 なくても使用すると、現在のレコードである`Seek`です。  
  
 ダイナセット タイプまたは特定の条件を満たすスナップショット タイプのレコード セットのレコードを検索するには、検索操作を使用します。 特定の条件を満たすものだけでなく、すべてのレコードを含めるには、レコード間を移動する移動操作を使用します。  
  
 呼び出すことはできません`Seek`アタッチ テーブルのいずれかでダイナセット タイプまたはスナップショットの種類のレコード セットとしてアタッチされているテーブルを開く必要があるために、入力します。 ただし、呼び出した場合`CDaoDatabase::Open`インストール可能な ISAM データベースを直接開くを呼び出すことができます`Seek`、そのデータベース内のテーブルにありますが、パフォーマンスが低下します。  
  
 関連情報については、「Seek メソッド」DAO ヘルプのトピックを参照してください。  
  
##  <a name="setabsoluteposition"></a>  CDaoRecordset::SetAbsolutePosition  
 レコード セット オブジェクトの現在のレコードの相対レコード数を設定します。  
  
```  
void SetAbsolutePosition(long lPosition);
```  
  
### <a name="parameters"></a>パラメーター  
 *lPosition*  
 レコード セット内の現在のレコードの序数位置に対応します。  
  
### <a name="remarks"></a>Remarks  
 呼び出す`SetAbsolutePosition`ダイナセット タイプまたはスナップショットの種類のレコード セットの序数位置に基づいて特定のレコードを現在のレコード ポインターを配置することができます。 呼び出して、現在のレコード数を確認することも[GetAbsolutePosition](#getabsoluteposition)です。  
  
> [!NOTE]
>  このメンバー関数は、ダイナセット タイプとスナップショットの種類のレコード セットに対してのみ有効です。  
  
 基になる DAO オブジェクトの AbsolutePosition プロパティの値は 0 から始まります。0 に設定は、レコード セットの最初のレコードを参照します。 格納済みのレコードと、例外をスローする MFC の数より大きい値を設定します。 呼び出すことによって、レコード セット内のデータが設定されたレコードの数を指定できます、`GetRecordCount`メンバー関数。  
  
 現在のレコードを削除すると、AbsolutePosition プロパティの値が定義されていませんし、MFC は、参照されている場合に例外をスローします。 新しいレコードは、シーケンスの末尾に追加されます。  
  
> [!NOTE]
>  このプロパティは、レコード番号の代わりとして使用するものではありません。 ブックマークはまだ保持して、指定された位置を返すための推奨される方法であり、ブックマークをサポートしているレコード セット オブジェクトのすべての型経由で現在のレコードを配置する唯一の方法です。 具体的には、前のレコードが削除されたときに指定されたレコードの位置を変更します。 また、レコード セットが再作成された SQL ステートメントを使用して、使用して作成された場合を除き、レコード セット内の各レコードの順序が保証されないため場合、特定のレコードが同じ絶対位置を持つことの保証はありません、 **ORDERBY**句。  
  
 関連情報については、DAO ヘルプの「AbsolutePosition プロパティ」を参照してください。  
  
##  <a name="setbookmark"></a>  CDaoRecordset::SetBookmark  
 レコード セットを指定されたブックマークを含むレコードに移動するには、このメンバー関数を呼び出します。  
  
```  
void SetBookmark(COleVariant varBookmark);
```  
  
### <a name="parameters"></a>パラメーター  
 *varBookmark*  
 A [COleVariant](../../mfc/reference/colevariant-class.md)特定のレコードのブックマークの値を含むオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 レコード セット オブジェクトを作成したり開いたりすると、各レコードは既に一意のブックマークを持っています。 呼び出して、現在のレコードのブックマークを取得する`GetBookmark`する値を保存し、`COleVariant`オブジェクト。 後で呼び出すことでそのレコードに戻すことができます`SetBookmark`保存されているブックマークの値を使用します。  
  
> [!NOTE]
>  呼び出す[Requery](#requery) DAO ブックマークを変更します。  
  
 UNICODE のレコード セットを作成していない場合、`COleVariant`オブジェクト必要があります明示的に宣言する ANSI です。 This can be done by using the [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc***,** *vtSrc* **)** form of constructor with *vtSrc* set to `VT_BSTRT` (ANSI) or by using the `COleVariant` function [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc***,** *vtSrc* **)** with *vtSrc* set to `VT_BSTRT`.  
  
 関連情報については、トピックを参照して、「Bookmark プロパティ」とブックマークを設定のプロパティ"DAO のヘルプ。  
  
##  <a name="setcachesize"></a>  CDaoRecordset::SetCacheSize  
 キャッシュするレコードの数を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetCacheSize(long lSize);
```  
  
### <a name="parameters"></a>パラメーター  
 *lSize*  
 レコードの数を指定します。 一般的な値は 100 です。 0 に設定は、キャッシュをオフにします。 設定は、5 ~ 1200 レコード間でなければなりません。 キャッシュは、相当量のメモリを使用する可能性があります。  
  
### <a name="remarks"></a>Remarks  
 キャッシュは、最後に取得したサーバーから、アプリケーションの実行中にデータを再要求は、データを保持するローカル メモリ内のスペースです。 データ キャッシュには、ダイナセット タイプのレコード セット オブジェクト経由でリモート サーバーからデータを取得するアプリケーションのパフォーマンスが向上します。 データが要求されると、Microsoft Jet データベース エンジンのキャッシュ要求されたデータをまずチェック時間がかかると、サーバーから取得するのではなくです。 ODBC データ ソースから発生しないデータがキャッシュに保存されません。  
  
 アタッチのテーブルなど、任意の ODBC データ ソースには、ローカル キャッシュを持つことができます。 キャッシュを作成するには、リモート データ ソース、呼び出しから recordset オブジェクトを開く、`SetCacheSize`と`SetCacheStart`メンバー関数と、呼び出し、`FillCache`メンバー関数または移動操作のいずれかを使用して、レコード間のステップします。 *LSize*のパラメーター、`SetCacheSize`メンバー関数は、アプリケーションが同時に使用できるレコードの数に基づくことができます。 たとえば、レコード セットは、画面に表示されるデータのソースとして使用されている場合を渡せる、 `SetCacheSize` *lSize*パラメーターとして 20 ~ 20 のレコードを同時に表示します。  
  
 関連情報については、DAO ヘルプのトピック「CacheSize、CacheStart プロパティ」を参照してください。  
  
##  <a name="setcachestart"></a>  CDaoRecordset::SetCacheStart  
 キャッシュするレコード セットの最初のレコード、ブックマークを指定するには、このメンバー関数を呼び出します。  
  
```  
void SetCacheStart(COleVariant varBookmark);
```  
  
### <a name="parameters"></a>パラメーター  
 *varBookmark*  
 A [COleVariant](../../mfc/reference/colevariant-class.md)キャッシュに保存するレコード セットの最初のレコード、ブックマークを指定します。  
  
### <a name="remarks"></a>Remarks  
 任意のレコードのブックマークの値を使用することができます、 *varBookmark*のパラメーター、`SetCacheStart`メンバー関数。 現在のレコードにキャッシュを開始、そのレコードを使用するためのブックマークを確立するレコード[SetBookmark](#setbookmark)、ブックマーク値のパラメーターとして渡す、`SetCacheStart`メンバー関数。  
  
 Microsoft Jet データベース エンジンが、キャッシュからキャッシュの範囲内のレコードを要求し、サーバーからキャッシュ範囲外のレコードを要求します。  
  
 キャッシュから取得したレコードでは、他のユーザーがデータ ソースに同時に行われた変更は反映されません。  
  
 強制的にすべてのキャッシュされたデータの更新を渡す、 *lSize*のパラメーター `SetCacheSize` 0 として呼び出す`SetCacheSize`再度でキャッシュのサイズを最初に要求しを呼び出す、`FillCache`メンバー関数。  
  
 UNICODE のレコード セットを作成していない場合、`COleVariant`オブジェクト必要があります明示的に宣言する ANSI です。 This can be done by using the [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc***,** *vtSrc* **)** form of constructor with *vtSrc* set to `VT_BSTRT` (ANSI) or by using the `COleVariant` function [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc***,** *vtSrc* **)** with *vtSrc* set to `VT_BSTRT`.  
  
 関連情報については、トピックを参照して、CacheSize、CacheStart プロパティ"DAO のヘルプ。  
  
##  <a name="setcurrentindex"></a>  CDaoRecordset::SetCurrentIndex  
 テーブル型のレコード セットのインデックスを設定するには、このメンバー関数を呼び出します。  
  
```  
void SetCurrentIndex(LPCTSTR lpszIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszIndex*  
 設定するインデックスの名前を含むポインター。  
  
### <a name="remarks"></a>Remarks  
 ベース テーブルのレコードは、特定の順序では格納されません。 インデックスを設定すると、データベースから返されるレコードの順序変更には、レコードが格納される順序は影響しません。 指定されたインデックスは、既に定義されている必要があります。 存在しないインデックス オブジェクトを使用しようとする場合、または呼び出す場合は、インデックスが設定されていない場合[シーク](#seek)MFC は、例外をスローします。  
  
 呼び出して、テーブルの新しいインデックスを作成した[CDaoTableDef::CreateIndex](../../mfc/reference/cdaotabledef-class.md#createindex)および基になるテーブルのインデックス コレクションに呼び出すことによって、新しいインデックスを付加[CDaoTableDef::Append](../../mfc/reference/cdaotabledef-class.md#append)、およびレコード セットを閉じてください。  
  
 テーブル型のレコード セットから返されるレコードの順序には基になるテーブル定義に対して定義されているインデックスでのみを指定できます。 その他の順序でレコードを並べ替えるには、ダイナセット型または SQL を使用して、スナップショットの種類のレコード セットを開くことができます**ORDERBY**に格納されている句[CDaoRecordset::m_strSort](#m_strsort)です。  
  
 関連情報については、トピック「インデックス オブジェクト」および DAO のヘルプでは、"現在のインデックス"の定義を参照してください。  
  
##  <a name="setfielddirty"></a>  CDaoRecordset::SetFieldDirty  
 このメンバー関数として、変更の有無、レコード セットのフィールド データ メンバーにフラグを設定します。  
  
```  
void SetFieldDirty(
    void* pv,  
    BOOL bDirty = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *pv*  
 レコード セットのフィールド データ メンバーのアドレスを格納または**NULL**です。 場合**NULL**、レコード セット内のすべてのフィールド データ メンバーのフラグが付けられます。 (C++ **NULL**は Null の場合と同じデータベース用語では、「値を持たない」を意味する)。  
  
 *bDirty*  
 **TRUE**かどうか、フィールド データ メンバーは「ダーティ」(変更されている) としてマークされます。 それ以外の場合**FALSE**かどうか、フィールド データ メンバーは「クリーンアップ」(変更なし) としてフラグが付けられます。  
  
### <a name="remarks"></a>Remarks  
 フィールドを変更されないとしてマークすることにより、フィールドは更新されません。  
  
 フレームワークは、DAO レコード フィールド エクス (チェンジ DFX) メカニズムによって、データ ソースのレコードに書き込まが確認するためのフィールド データ メンバーを変更します。 フィールドの値を変更すると、通常、フィールド ダーティは自動的に設定を呼び出すことはほとんどありません必要がありますので`SetFieldDirty`ユーザー自身が場合がありますようにすることも、列が明示的に更新または挿入するフィールドのデータでは、どのような値に関係なくメンバー。 DFX 機構は、の使用も採用されています。 **PSEUDONULL**です。 詳細については、次を参照してください。 [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)です。  
  
 ダブル バッファリング機構が使用されていない場合、フィールドの値を変更して自動的に設定しませんフィールド ダーティとして。 この場合、フィールドをダーティとして明示的に設定する必要があります。 格納されているフラグ[m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)このフィールドの自動チェックを制御します。  
  
> [!NOTE]
>  このメンバー関数を呼び出した後にのみ[編集](#edit)または[AddNew](#addnew)です。  
  
 使用して**NULL**すべてに、関数を適用する関数の最初の引数の**outputColumn**フィールドいない**param**フィールド`CDaoFieldExchange`です。 インスタンスの呼び出し  
  
 [!code-cpp[NVC_MFCDatabase#6](../../mfc/codesnippet/cpp/cdaorecordset-class_6.cpp)]  
  
 セットのみが**outputColumn**フィールドを**NULL**です。**param**フィールドには影響ありません。  
  
 動作する、 **param**、個々 の実際のアドレスを指定する必要があります**param**など、作業します。  
  
 [!code-cpp[NVC_MFCDatabase#7](../../mfc/codesnippet/cpp/cdaorecordset-class_7.cpp)]  
  
 つまり、すべて設定することはできません**param**フィールドを**NULL**と同様、 **outputColumn**フィールドです。  
  
 `SetFieldDirty` によって実装され`DoFieldExchange`です。  
  
##  <a name="setfieldnull"></a>  CDaoRecordset::SetFieldNull  
 レコード セット (具体的には値を持たない) Null または null 以外のフィールド データ メンバーにフラグを設定するには、このメンバー関数を呼び出します。  
  
```  
void SetFieldNull(
    void* pv,  
    BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *pv*  
 レコード セットのフィールド データ メンバーのアドレスを格納または**NULL**です。 場合**NULL**、レコード セット内のすべてのフィールド データ メンバーのフラグが付けられます。 (C++ **NULL**は Null の場合と同じデータベース用語では、「値を持たない」を意味する)。  
  
 *特別*  
 以外の場合は、フィールド データ メンバーが値 (Null) がないものとしてフラグが付けられます。 それ以外の場合は 0 場合は、フィールド データ メンバーは Null としてフラグが付けられます。  
  
### <a name="remarks"></a>Remarks  
 `SetFieldNull` フィールドにバインドされているため、`DoFieldExchange`メカニズムです。  
  
 レコード セットに新しいレコードを追加するときにすべてのフィールド データ メンバーが最初に Null 値に設定され「ダーティ」(変更されている) フラグが付けられます。 データ ソースからレコードを取得するときにその列既に値があるかが Null です。 Null の場合、フィールドを設定が適切ではない場合、 [CDaoException](../../mfc/reference/cdaoexception-class.md)がスローされます。  
  
 たとえば、具体的には呼び出し、値を持っていないと、現在のレコードのフィールドを指定する場合、ダブル バッファリング メカニズムを使用する場合`SetFieldNull`で*特別*'éý' **TRUE**フラグにNull として。 フィールドが以前に設定された場合 Null とするようになりましたする値を単にその新しい値を設定します。 Null フラグを削除する必要はありません`SetFieldNull`です。 フィールドが Null を指定できるかどうかを確認するのには、呼び出す[調べる](#isfieldnullable)です。  
  
 ダブル バッファリング機構を使用していない場合、フィールドの値を変更して自動的に設定しませんフィールドとしてダーティと Null 以外。 フィールドは、ダーティと Null 以外に明示的に設定する必要があります。 格納されているフラグ[m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)このフィールドの自動チェックを制御します。  
  
 DFX 機構の使用を採用する**PSEUDONULL**です。 詳細については、次を参照してください。 [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)です。  
  
> [!NOTE]
>  このメンバー関数を呼び出した後にのみ[編集](#edit)または[AddNew](#addnew)です。  
  
 使用して**NULL**関数の最初の引数が関数にのみ適用されますの**outputColumn**フィールドいない**param**フィールドで`CDaoFieldExchange`です。 インスタンスの呼び出し  
  
 [!code-cpp[NVC_MFCDatabase#8](../../mfc/codesnippet/cpp/cdaorecordset-class_8.cpp)]  
  
 セットのみが**outputColumn**フィールドを**NULL**です。**param**フィールドには影響ありません。  
  
##  <a name="setfieldvalue"></a>  たび  
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
 *lpszName*  
 フィールドの名前を含む文字列へのポインター。  
  
 *varValue*  
 参照、 [COleVariant](../../mfc/reference/colevariant-class.md)フィールドの内容の値を含むオブジェクト。  
  
 *nIndex*  
 レコード セットのフィールド コレクションの (0 から始まる) 内のフィールドの序数位置を表す整数。  
  
 *lpszValue*  
 フィールドの内容の値を含む文字列へのポインター。  
  
### <a name="remarks"></a>Remarks  
 使用して`SetFieldValue`と[GetFieldValue](#getfieldvalue)実行時ではなく静的を使用してバインド列にフィールドに動的にバインドする、 [DoFieldExchange](#dofieldexchange)メカニズムです。  
  
 UNICODE のレコード セットを作成するので、いずれかの形式を使用する必要がありますに注意してください`SetFieldValue`を含まない、`COleVariant`パラメーター、または`COleVariant`オブジェクト必要があります明示的に宣言する ANSI です。 This can be done by using the [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc***,** *vtSrc* **)** form of constructor with *vtSrc* set to `VT_BSTRT` (ANSI) or by using the `COleVariant` function [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc***,** *vtSrc* **)** with *vtSrc* set to `VT_BSTRT`.  
  
 関連情報については、「フィールド オブジェクト」と「Value プロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="setfieldvaluenull"></a>  CDaoRecordset::SetFieldValueNull  
 フィールドを Null 値に設定するには、このメンバー関数を呼び出します。  
  
```  
void SetFieldValueNull(int nIndex);  
void SetFieldValueNull(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 0 から始まるインデックスで検索する場合、レコード セット内のフィールドのインデックス。  
  
 *lpszName*  
 名前で検索する場合、レコード セット内のフィールドの名前。  
  
### <a name="remarks"></a>Remarks  
 C++ **NULL** Null の場合、つまり、データベース用語と同じではありません「値を持たない」。  
  
 関連情報については、「フィールド オブジェクト」と「Value プロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="setlockingmode"></a>  CDaoRecordset::SetLockingMode  
 レコード セットに対するロックの種類を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetLockingMode(BOOL bPessimistic);
```  
  
### <a name="parameters"></a>パラメーター  
 *bPessimistic*  
 ロックの種類を示すフラグです。  
  
### <a name="remarks"></a>Remarks  
 呼び出すと、すぐにロックされているときに排他ロックが有効で、編集しているレコードを含む 2 K ページ、`Edit`メンバー関数。 ページのロックが解除されてを呼び出すとき、`Update`または`Close`メンバー関数または移動または検索操作のいずれか。  
  
 レコードの更新中にのみレコードを含む 2 K ページがロックされている共有ロックが有効で、ときに、`Update`メンバー関数。  
  
 ページがロックされている場合は、その他のユーザー レコードを編集できませんは同じページ上。 呼び出す場合`SetLockingMode`とは、0 以外の値を渡す、および別のユーザーには既にロックされているページを呼び出すときに、例外がスローされます`Edit`です。 他のユーザーは、ロックされたページからデータを読み取ることができます。  
  
 呼び出す場合`SetLockingMode`ゼロ値以降を呼び出す`Update`ページが別のユーザーによってロックされている間、例外が発生します。 別のユーザーによって、レコードに行われた変更を参照してください (し、変更内容が失われる) を呼び出します、`SetBookmark`ブックマーク値は、現在のレコードのメンバー関数。  
  
 ODBC データ ソースを使用するときにロック モードはオプティミスティック常にします。  
  
##  <a name="setparamvalue"></a>  CDaoRecordset::SetParamValue  
 実行時に、レコード セット内のパラメーターの値を設定するには、このメンバー関数を呼び出します。  
  
```  
virtual void SetParamValue(
    int nIndex,  
    const COleVariant& varValue);

 
virtual void SetParamValue(
    LPCTSTR lpszName,  
    const COleVariant& varValue);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 クエリ定義のパラメーター コレクション内のパラメーターの数値の位置。  
  
 *var*  
 に設定する値「解説」を参照してください。  
  
 *lpszName*  
 値を設定するパラメーターの名前。  
  
### <a name="remarks"></a>Remarks  
 パラメーター既に、レコード セットの SQL 文字列の一部として設定されていなければなりません。 パラメーターは、名前またはコレクションのインデックス位置のいずれかにアクセスすることができます。  
  
 として設定する値を指定して、`COleVariant`オブジェクト。 目的の値と型に設定については、`COleVariant`オブジェクト、クラスを参照して[COleVariant](../../mfc/reference/colevariant-class.md)です。 UNICODE のレコード セットを作成していない場合、`COleVariant`オブジェクト必要があります明示的に宣言する ANSI です。 This can be done by using the [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc***,** *vtSrc* **)** form of constructor with *vtSrc* set to `VT_BSTRT` (ANSI) or by using the `COleVariant` function [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc***,** *vtSrc* **)** with *vtSrc* set to `VT_BSTRT`.  
  
##  <a name="setparamvaluenull"></a>  CDaoRecordset::SetParamValueNull  
 パラメーターに Null 値を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetParamValueNull(int nIndex);  
void SetParamValueNull(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 0 から始まるインデックスで検索する場合、レコード セット内のフィールドのインデックス。  
  
 *lpszName*  
 名前で検索する場合、レコード セット内のフィールドの名前。  
  
### <a name="remarks"></a>Remarks  
 C++ **NULL** Null の場合、つまり、データベース用語と同じではありません「値を持たない」。  
  
##  <a name="setpercentposition"></a>  CDaoRecordset::SetPercentPosition  
 レコード セット内のレコードの比率に基づいて、レコード セット オブジェクトの現在のレコードのおおよその場所を変更する値を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetPercentPosition(float fPosition);
```  
  
### <a name="parameters"></a>パラメーター  
 *fPosition*  
 0 ～ 100 の値。  
  
### <a name="remarks"></a>Remarks  
 ダイナセットの種類またはスナップショットの種類のレコード セットを扱うときにまず recordset 移したら最後のレコードを呼び出す前に`SetPercentPosition`です。 呼び出す場合`SetPercentPosition`、アクセスされたレコード数の値によって示される相対移動量は、レコード セットを完全に設定するには、する前に[GetRecordCount](#getrecordcount)です。 行うことができます、最後のレコードを呼び出して`MoveLast`です。  
  
 呼び出す`SetPercentPosition`、その値に対応するおおよその位置にあるレコードが最新になった。  
  
> [!NOTE]
>  呼び出す`SetPercentPosition`を移動、レコード セット内の特定のレコードを現在のレコードはお勧めしません。 呼び出す、 [SetBookmark](#setbookmark)メンバー関数を使用します。  
  
 関連情報については、DAO ヘルプの「PercentPosition プロパティ」を参照してください。  
  
##  <a name="update"></a>  CDaoRecordset::Update  
 このメンバー関数を呼び出した後、`AddNew`または`Edit`メンバー関数。  
  
```  
virtual void Update();
```  
  
### <a name="remarks"></a>Remarks  
 この呼び出しが完了するために必要な`AddNew`または`Edit`操作します。  
  
 両方`AddNew`と`Edit`データ ソースに保存するため、追加または編集されたデータが置かれている編集バッファーを準備します。 `Update` データを保存します。 マークまたは変更されたものとして検出されたフィールドのみ更新されます。  
  
 データ ソースは、トランザクションをサポートする場合は、`Update`呼び出し (とその対応する`AddNew`または`Edit`呼び出し)、トランザクションの一部です。  
  
> [!CAUTION]
>  呼び出す場合`Update`最初に呼び出して、`AddNew`または`Edit`、`Update`スロー、`CDaoException`です。 呼び出す場合`AddNew`または`Edit`、呼び出す必要があります`Update`を呼び出す前に[MoveNext](#movenext)またはレコード セットまたはデータ ソース接続を終了します。 それ以外の場合、変更は、通知することがなく失われます。  
  
 レコード セット オブジェクトがマルチ ユーザー環境で排他ロックされると、レコードにはロックが時間から`Edit`更新が完了するまでに使用します。 レコード セットがやロックされている場合、レコードがロックされているし、データベースで更新される直前に、編集前のレコードと比較 呼び出されるため、レコードが変更された場合`Edit`、`Update`操作は失敗し、MFC は、例外をスローします。 ロック モードを変更する`SetLockingMode`です。  
  
> [!NOTE]
>  ODBC やインストール可能な ISAM など、外部データベース形式では、オプティミスティック ロックは使用が常にします。  
  
 関連情報については、"AddNew Method"、"ただし Method"、「メソッドの削除」、"LastModified Property"、「更新メソッド」、および「EditMode プロパティ」DAO ヘルプのトピックを参照してください。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [どちらのクラス](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoWorkspace クラス](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)
