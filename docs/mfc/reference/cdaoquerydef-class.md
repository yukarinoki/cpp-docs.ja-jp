---
title: CDaoQueryDef クラス
ms.date: 11/04/2016
f1_keywords:
- CDaoQueryDef
- AFXDAO/CDaoQueryDef
- AFXDAO/CDaoQueryDef::CDaoQueryDef
- AFXDAO/CDaoQueryDef::Append
- AFXDAO/CDaoQueryDef::CanUpdate
- AFXDAO/CDaoQueryDef::Close
- AFXDAO/CDaoQueryDef::Create
- AFXDAO/CDaoQueryDef::Execute
- AFXDAO/CDaoQueryDef::GetConnect
- AFXDAO/CDaoQueryDef::GetDateCreated
- AFXDAO/CDaoQueryDef::GetDateLastUpdated
- AFXDAO/CDaoQueryDef::GetFieldCount
- AFXDAO/CDaoQueryDef::GetFieldInfo
- AFXDAO/CDaoQueryDef::GetName
- AFXDAO/CDaoQueryDef::GetODBCTimeout
- AFXDAO/CDaoQueryDef::GetParameterCount
- AFXDAO/CDaoQueryDef::GetParameterInfo
- AFXDAO/CDaoQueryDef::GetParamValue
- AFXDAO/CDaoQueryDef::GetRecordsAffected
- AFXDAO/CDaoQueryDef::GetReturnsRecords
- AFXDAO/CDaoQueryDef::GetSQL
- AFXDAO/CDaoQueryDef::GetType
- AFXDAO/CDaoQueryDef::IsOpen
- AFXDAO/CDaoQueryDef::Open
- AFXDAO/CDaoQueryDef::SetConnect
- AFXDAO/CDaoQueryDef::SetName
- AFXDAO/CDaoQueryDef::SetODBCTimeout
- AFXDAO/CDaoQueryDef::SetParamValue
- AFXDAO/CDaoQueryDef::SetReturnsRecords
- AFXDAO/CDaoQueryDef::SetSQL
- AFXDAO/CDaoQueryDef::m_pDAOQueryDef
- AFXDAO/CDaoQueryDef::m_pDatabase
helpviewer_keywords:
- CDaoQueryDef [MFC], CDaoQueryDef
- CDaoQueryDef [MFC], Append
- CDaoQueryDef [MFC], CanUpdate
- CDaoQueryDef [MFC], Close
- CDaoQueryDef [MFC], Create
- CDaoQueryDef [MFC], Execute
- CDaoQueryDef [MFC], GetConnect
- CDaoQueryDef [MFC], GetDateCreated
- CDaoQueryDef [MFC], GetDateLastUpdated
- CDaoQueryDef [MFC], GetFieldCount
- CDaoQueryDef [MFC], GetFieldInfo
- CDaoQueryDef [MFC], GetName
- CDaoQueryDef [MFC], GetODBCTimeout
- CDaoQueryDef [MFC], GetParameterCount
- CDaoQueryDef [MFC], GetParameterInfo
- CDaoQueryDef [MFC], GetParamValue
- CDaoQueryDef [MFC], GetRecordsAffected
- CDaoQueryDef [MFC], GetReturnsRecords
- CDaoQueryDef [MFC], GetSQL
- CDaoQueryDef [MFC], GetType
- CDaoQueryDef [MFC], IsOpen
- CDaoQueryDef [MFC], Open
- CDaoQueryDef [MFC], SetConnect
- CDaoQueryDef [MFC], SetName
- CDaoQueryDef [MFC], SetODBCTimeout
- CDaoQueryDef [MFC], SetParamValue
- CDaoQueryDef [MFC], SetReturnsRecords
- CDaoQueryDef [MFC], SetSQL
- CDaoQueryDef [MFC], m_pDAOQueryDef
- CDaoQueryDef [MFC], m_pDatabase
ms.assetid: 9676a4a3-c712-44d4-8c5d-d1cc78288d3a
ms.openlocfilehash: fabb8e957ffaf8ab8d9d57bca8e7835d366ac390
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231820"
---
# <a name="cdaoquerydef-class"></a>CDaoQueryDef クラス

クエリ定義、つまり "querydef" を表し、通常はデータベースに保存されています。

## <a name="syntax"></a>構文

```
class CDaoQueryDef : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CDaoQueryDef::CDaoQueryDef](#cdaoquerydef)|`CDaoQueryDef` オブジェクトを構築します。 `Open` `Create` 必要に応じて、次のまたはを呼び出します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDaoQueryDef:: Append](#append)|データベースのクエリ定義コレクションに保存されたクエリとして、クエリを追加します。|
|[CDaoQueryDef:: CanUpdate](#canupdate)|クエリでデータベースを更新できる場合は0以外の値を返します。|
|[CDaoQueryDef:: Close](#close)|Querydef オブジェクトを閉じます。 終了時に C++ オブジェクトを破棄します。|
|[CDaoQueryDef:: Create](#create)|基になる DAO querydef オブジェクトを作成します。 クエリ定義を一時クエリとして使用するか、を呼び出して `Append` データベースに保存します。|
|[CDaoQueryDef:: Execute](#execute)|Querydef オブジェクトによって定義されたクエリを実行します。|
|[CDaoQueryDef:: GetConnect](#getconnect)|クエリ定義に関連付けられた接続文字列を返します。 接続文字列は、データソースを識別します。 (SQL パススルークエリのみの場合は、それ以外の場合は空の文字列)。|
|[CDaoQueryDef::GetDateCreated](#getdatecreated)|保存されたクエリが作成された日付を返します。|
|[CDaoQueryDef:: GetDateLastUpdated](#getdatelastupdated)|保存されたクエリが最後に更新された日付を返します。|
|[CDaoQueryDef:: GetFieldCount](#getfieldcount)|クエリ定義によって定義されたフィールドの数を返します。|
|[CDaoQueryDef::GetFieldInfo](#getfieldinfo)|クエリで定義されている、指定されたフィールドに関する情報を返します。|
|[CDaoQueryDef:: GetName](#getname)|クエリ定義の名前を返します。|
|[CDaoQueryDef:: GetODBCTimeout](#getodbctimeout)|クエリ実行時に ODBC (ODBC クエリの場合) で使用されるタイムアウト値を返します。 これにより、クエリのアクションが完了するまでの期間が決まります。|
|[CDaoQueryDef:: GetParameterCount](#getparametercount)|クエリに対して定義されているパラメーターの数を返します。|
|[CDaoQueryDef:: GetParameterInfo](#getparameterinfo)|指定されたパラメーターに関する情報をクエリに返します。|
|[CDaoQueryDef::GetParamValue](#getparamvalue)|クエリに対して指定されたパラメーターの値を返します。|
|[CDaoQueryDef::GetRecordsAffected](#getrecordsaffected)|アクションクエリの影響を受けたレコードの数を返します。|
|[CDaoQueryDef::GetReturnsRecords](#getreturnsrecords)|クエリ定義によって定義されたクエリがレコードを返す場合は、0以外の値を返します。|
|[CDaoQueryDef::GetSQL](#getsql)|クエリ定義によって定義されたクエリを指定する SQL 文字列を返します。|
|[CDaoQueryDef:: GetType](#gettype)|クエリの種類 (削除、更新、追加、テーブルの作成など) を返します。|
|[CDaoQueryDef:: IsOpen](#isopen)|クエリ定義が開いて実行できる場合は、0以外の値を返します。|
|[CDaoQueryDef:: Open](#open)|データベースのクエリ定義コレクションに格納されている既存のクエリ定義を開きます。|
|[CDaoQueryDef:: SetConnect](#setconnect)|ODBC データソースに対する SQL パススルークエリの接続文字列を設定します。|
|[CDaoQueryDef:: SetName](#setname)|クエリの作成時に使用した名前を置き換えて、保存されたクエリの名前を設定します。|
|[CDaoQueryDef:: SetODBCTimeout](#setodbctimeout)|クエリ実行時に ODBC によって使用されるタイムアウト値を設定します (ODBC クエリの場合)。|
|[CDaoQueryDef::SetParamValue](#setparamvalue)|指定されたパラメーターの値をクエリに設定します。|
|[CDaoQueryDef::SetReturnsRecords](#setreturnsrecords)|クエリ定義がレコードを返すかどうかを指定します。 この属性を TRUE に設定することは、SQL パススルークエリに対してのみ有効です。|
|[CDaoQueryDef::SetSQL](#setsql)|クエリ定義によって定義されたクエリを指定する SQL 文字列を設定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CDaoQueryDef:: m_pDAOQueryDef](#m_pdaoquerydef)|基になる DAO querydef オブジェクトの OLE インターフェイスへのポインター。|
|[CDaoQueryDef:: m_pDatabase](#m_pdatabase)|`CDaoDatabase`クエリ定義が関連付けられているオブジェクトへのポインター。 クエリがデータベースに保存されている可能性があります。|

## <a name="remarks"></a>解説

クエリ定義は、クエリを記述する SQL ステートメントとそのプロパティ ("作成日" や "ODBC タイムアウト" など) を含むデータアクセスオブジェクトです。 一時クエリオブジェクトを保存せずに作成することもできますが、データベースで頻繁に再利用されるクエリを保存することは便利で、はるかに効率的です。 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトは、クエリが保存されたクエリを含むコレクションを管理します。

> [!NOTE]
> DAO データベースクラスは、Open Database Connectivity (ODBC) に基づく MFC データベースクラスとは異なります。 すべての DAO データベースクラス名には、"CDao" プレフィックスが付いています。 DAO クラスを使用して ODBC データソースにアクセスすることもできます。 一般に、DAO に基づく MFC クラスは、ODBC に基づく MFC クラスよりも多くの機能を備えています。DAO ベースのクラスは、独自のデータベースエンジンを介して、ODBC ドライバーを介してデータにアクセスできます。 DAO ベースのクラスでは、データ定義言語 (DDL) 操作 (クラスを使用したテーブルの追加など) もサポートされています。 DAO を直接呼び出す必要はありません。

## <a name="usage"></a>使用法

既存の保存済みクエリを操作するか、新しい保存されたクエリまたは一時クエリを作成するには、クエリ定義オブジェクトを使用します。

1. 常に、最初にオブジェクトを構築し `CDaoQueryDef` て、クエリが属する[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトへのポインターを提供します。

1. 必要に応じて、次の操作を行います。

   - 既存の保存済みクエリを使用するには、保存されたクエリの名前を指定して、querydef オブジェクトの[Open](#open)メンバー関数を呼び出します。

   - 新しい保存されたクエリを作成するには、クエリの名前を指定して、querydef オブジェクトの[create](#create) member 関数を呼び出します。 次に、 [Append](#append)を呼び出して、クエリをデータベースのクエリ定義コレクションに追加して保存します。 `Create`を呼び出した後に、を呼び出さずに、クエリ定義を開いた状態にし `Create` `Open` ます。

   - 一時的なクエリを作成するには、を呼び出し `Create` ます。 クエリ名として空の文字列を渡します。 `Append` を呼び出さないでください。

Querydef オブジェクトの使用が終了したら、 [Close](#close)メンバー関数を呼び出します。次に、querydef オブジェクトを破棄します。

> [!TIP]
> 保存したクエリを作成する最も簡単な方法は、Microsoft Access を使用してそれらを作成し、データベースに保存することです。 次に、MFC コードでそれらを開いて使用できます。

## <a name="purposes"></a>おい

次のいずれかの目的で、querydef オブジェクトを使用できます。

- オブジェクトを作成するには `CDaoRecordset`

- `Execute`アクションクエリまたは SQL パススルークエリを直接実行するためにオブジェクトのメンバー関数を呼び出すには

選択、アクション、クロス集計、削除、更新、追加、テーブルの作成、データ定義、SQL パススルー、共用体、一括クエリなど、任意の種類のクエリに対して、querydef オブジェクトを使用できます。 クエリの種類は、指定した SQL ステートメントの内容によって決まります。 クエリの種類の詳細については、「」 `Execute` および「 [GetType](#gettype)メンバー関数」を参照してください。 レコードセットは、通常、行を返すクエリに使用され、通常は**SELECT...FROM**キーワード。 `Execute`は、一括操作で最も一般的に使用されます。 詳細については、「 [Execute](#execute)および[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)」を参照してください。

## <a name="querydefs-and-recordsets"></a>クエリ定義とレコードセット

オブジェクトを作成するために querydef オブジェクトを使用するには、 `CDaoRecordset` 通常、前述のように、クエリを作成または開きます。 次に、 [CDaoRecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open)を呼び出すときに、レコードセットオブジェクトへのポインターを渡して、レコードセットオブジェクトを構築します。 渡すクエリ定義は、open 状態である必要があります。 詳細については、「クラス[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)」を参照してください。

オープン状態でない限り、クエリを使用してレコードセットを作成することはできません (クエリ定義で最も一般的に使用されます)。 またはを呼び出して、クエリ定義をオープン状態にし `Open` `Create` ます。

## <a name="external-databases"></a>外部データベース

外部データベースエンジンのネイティブ SQL 言語を使用するには、クエリ定義オブジェクトを使用することをお勧めします。 たとえば、Microsoft SQL Server で使用されるように Transact SQL クエリを作成し、それを querydef オブジェクトに格納することができます。 Microsoft Jet データベースエンジンに基づいていない SQL クエリを使用する必要がある場合は、外部データソースを参照する接続文字列を指定する必要があります。 有効な接続文字列を持つクエリは、データベースエンジンをバイパスし、クエリを直接外部データベースサーバーに渡して処理します。

> [!TIP]
> ODBC テーブルを使用する場合は、Microsoft Jet () に接続することをお勧めします。MDB) データベース。

関連情報については、DAO SDK の「QueryDef オブジェクト」、「クエリコレクション」、および「CdbDatabase オブジェクト」のトピックを参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CDaoQueryDef`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdao

## <a name="cdaoquerydefappend"></a><a name="append"></a>CDaoQueryDef:: Append

[Create](#create)を呼び出して新しい querydef オブジェクトを作成した後に、このメンバー関数を呼び出します。

```
virtual void Append();
```

### <a name="remarks"></a>解説

`Append`データベースのクエリ定義コレクションにオブジェクトを追加することによって、データベースにクエリを保存します。 このクエリは追加せずに一時オブジェクトとして使用できますが、永続化する場合はを呼び出す必要があり `Append` ます。

一時的な querydef オブジェクトを追加しようとすると、MFC は[CDaoException](../../mfc/reference/cdaoexception-class.md)型の例外をスローします。

## <a name="cdaoquerydefcanupdate"></a><a name="canupdate"></a>CDaoQueryDef:: CanUpdate

このメンバー関数を呼び出して、名前や SQL 文字列を変更するなど、クエリ定義を変更できるかどうかを判断します。

```
BOOL CanUpdate();
```

### <a name="return-value"></a>戻り値

クエリ定義を変更することが許可されている場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

次の場合に、クエリ定義を変更できます。

- 読み取り専用で開かれているデータベースには基づいていません。

- データベースに対する更新権限があります。

   これは、セキュリティ機能が実装されているかどうかによって異なります。 MFC では、セキュリティがサポートされていません。直接、または Microsoft Access を使用して DAO を呼び出すことによって、独自に実装する必要があります。 DAO ヘルプの「Permissions プロパティ」を参照してください。

## <a name="cdaoquerydefcdaoquerydef"></a><a name="cdaoquerydef"></a>CDaoQueryDef::CDaoQueryDef

`CDaoQueryDef` オブジェクトを構築します。

```
CDaoQueryDef(CDaoDatabase* pDatabase);
```

### <a name="parameters"></a>パラメーター

*pDatabase*<br/>
開いている[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

オブジェクトは、データベースのクエリ定義コレクションに格納されている既存のクエリ定義、コレクションに格納される新しいクエリ、または格納されない一時的なクエリを表すことができます。 次の手順は、クエリの種類によって異なります。

- オブジェクトが既存のクエリ定義を表している場合は、オブジェクトの[Open](#open)メンバー関数を呼び出して初期化します。

- オブジェクトが、保存する新しいクエリを表す場合は、オブジェクトの[Create](#create) member 関数を呼び出します。 これにより、データベースのクエリ定義コレクションにオブジェクトが追加されます。 次 `CDaoQueryDef` に、メンバー関数を呼び出して、オブジェクトの属性を設定します。 最後に、 [Append](#append)を呼び出します。

- オブジェクトが (データベースに保存されるのではなく) 一時的なクエリを表す場合は、 `Create` を呼び出し、クエリの名前として空の文字列を渡します。 を呼び出した後 `Create` 、属性を直接設定して、クエリ定義を初期化します。 `Append` を呼び出さないでください。

クエリ定義の属性を設定するには、 [SetName](#setname)、 [SetSQL](#setsql)、 [setconnect](#setconnect)、 [Setodbctimeout](#setodbctimeout)、および[SetReturnsRecords](#setreturnsrecords)の各メンバー関数を使用します。

Querydef オブジェクトが完成したら、 [Close](#close)メンバー関数を呼び出します。 クエリ定義へのポインターがある場合は、演算子を使用して **`delete`** C++ オブジェクトを破棄します。

## <a name="cdaoquerydefclose"></a><a name="close"></a>CDaoQueryDef:: Close

このメンバー関数は、querydef オブジェクトの使用が終了したときに呼び出します。

```
virtual void Close();
```

### <a name="remarks"></a>解説

クエリを終了すると、基になる DAO オブジェクトが解放されますが、保存された DAO querydef オブジェクトまたは C++ オブジェクトは破棄されません `CDaoQueryDef` 。 これは、 [eletequerydef:D](../../mfc/reference/cdaodatabase-class.md#deletequerydef)と同じではありません。これは、DAO のデータベースのクエリコレクションコレクションからクエリを削除します (一時的なクエリを実行しない場合)。

## <a name="cdaoquerydefcreate"></a><a name="create"></a>CDaoQueryDef:: Create

このメンバー関数を呼び出して、新しい保存されたクエリまたは新しい一時クエリを作成します。

```
virtual void Create(
    LPCTSTR lpszName = NULL,
    LPCTSTR lpszSQL = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
データベースに保存されているクエリの一意の名前。 文字列の詳細については、DAO ヘルプの「CreateQueryDef メソッド」を参照してください。 既定値の空の文字列をそのまま使用すると、一時的なクエリが作成されます。 このようなクエリは、クエリ定義コレクションに保存されません。

*lpszSQL*<br/>
クエリを定義する SQL 文字列。 既定値の NULL をそのまま使用する場合は、後で[SetSQL](#setsql)を呼び出して文字列を設定する必要があります。 それまでは、クエリは定義されていません。 ただし、未定義のクエリを使用してレコードセットを開くことはできます。詳細については、「解説」を参照してください。 クエリ定義をクエリコレクションに追加する前に、SQL ステートメントを定義する必要があります。

### <a name="remarks"></a>解説

*Lpszname*に名前を渡すと、 [Append](#append)を呼び出して、データベースのクエリ定義コレクションにクエリを保存できます。 それ以外の場合、オブジェクトは一時的なクエリ定義であり、保存されません。 どちらの場合も、クエリ定義はオープン状態であり、それを使用して[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを作成するか、またはクエリ定義の[Execute](#execute)メンバー関数を呼び出すことができます。

*LpszSQL*で SQL ステートメントを指定しなかった場合、でクエリを実行することはできません `Execute` が、レコードセットを作成するために使用することはできます。 その場合、MFC では、レコードセットの既定の SQL ステートメントが使用されます。

## <a name="cdaoquerydefexecute"></a><a name="execute"></a>CDaoQueryDef:: Execute

このメンバー関数を呼び出して、querydef オブジェクトによって定義されたクエリを実行します。

```
virtual void Execute(int nOptions = dbFailOnError);
```

### <a name="parameters"></a>パラメーター

*nOptions*<br/>
クエリの特性を決定する整数。 関連情報については、DAO ヘルプの「Execute メソッド」を参照してください。 ビットごとの OR 演算子 ( **&#124;**) を使用して、この引数に次の定数を組み合わせることができます。

- `dbDenyWrite`他のユーザーに対する書き込み権限を拒否します。

- `dbInconsistent`一貫性のない更新プログラム。

- `dbConsistent`一貫した更新プログラム。

- `dbSQLPassThrough`SQL パススルー。 SQL ステートメントを ODBC データベースに渡して処理します。

- `dbFailOnError`既定値。 エラーが発生した場合は更新をロールバックし、エラーをユーザーに報告します。

- `dbSeeChanges`別のユーザーが編集中のデータを変更している場合は、実行時エラーを生成します。

> [!NOTE]
> 「一貫性のない」と「一貫性」という用語の説明については、DAO ヘルプの「Execute メソッド」を参照してください。

### <a name="remarks"></a>解説

この方法で実行するために使用される Querydef オブジェクトは、次のいずれかの種類のクエリのみを表すことができます。

- アクションクエリ

- SQL パススルークエリ

`Execute`select クエリなどのレコードを返すクエリでは機能しません。 `Execute`は、 **UPDATE**、 **INSERT**、 **SELECT INTO**、またはデータ定義言語 (DDL) 操作などの一括操作クエリでよく使用されます。

> [!TIP]
> ODBC データソースを操作するには、Microsoft Jet にテーブルをアタッチする方法をお勧めします (「」をお勧めします。MDB) データベース。 詳細については、DAO ヘルプの「DAO を使用した外部データベースへのアクセス」を参照してください。

最後の呼び出しによって影響を受けたレコードの数を判断するには、querydef オブジェクトの[GetRecordsAffected](#getrecordsaffected)メンバー関数を呼び出し `Execute` ます。 たとえば、は、 `GetRecordsAffected` アクションクエリの実行時に削除、更新、または挿入されたレコードの数に関する情報を返します。 返されるカウントには、連鎖更新または削除が有効になっている場合、関連テーブルの変更は反映されません。

との両方を含めた場合、 `dbInconsistent` `dbConsistent` またはを含まない場合、結果は既定値のになり `dbInconsistent` ます。

`Execute`では、レコードセットは返されません。 `Execute`レコードを選択するクエリでを使用すると、MFC は[CDaoException](../../mfc/reference/cdaoexception-class.md)型の例外をスローします。

## <a name="cdaoquerydefgetconnect"></a><a name="getconnect"></a>CDaoQueryDef:: GetConnect

このメンバー関数を呼び出して、クエリ定義のデータソースに関連付けられている接続文字列を取得します。

```
CString GetConnect();
```

### <a name="return-value"></a>戻り値

クエリ定義の接続文字列を格納している[CString](../../atl-mfc-shared/reference/cstringt-class.md) 。

### <a name="remarks"></a>解説

この関数は、ODBC データソースと特定の ISAM ドライバーでのみ使用されます。 Microsoft Jet () では使用されません。MDB) データベース。この場合、は `GetConnect` 空の文字列を返します。 詳細については、「 [Setconnect](#setconnect)」を参照してください。

> [!TIP]
> ODBC テーブルを使用する場合は、にアタッチすることをお勧めします。MDB データベース。 詳細については、DAO ヘルプの「DAO を使用した外部データベースへのアクセス」を参照してください。

接続文字列の詳細については、DAO ヘルプのトピック「Connect プロパティ」を参照してください。

## <a name="cdaoquerydefgetdatecreated"></a><a name="getdatecreated"></a>CDaoQueryDef::GetDateCreated

このメンバー関数を呼び出して、querydef オブジェクトが作成された日付を取得します。

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>戻り値

クエリ定義が作成された日付と時刻を格納している[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクト。

### <a name="remarks"></a>解説

関連情報については、DAO ヘルプの「DateCreated、LastUpdated Properties」を参照してください。

## <a name="cdaoquerydefgetdatelastupdated"></a><a name="getdatelastupdated"></a>CDaoQueryDef:: GetDateLastUpdated

このメンバー関数を呼び出して、クエリ定義オブジェクトが最後に更新された日付 (名前、SQL 文字列、接続文字列など) が変更された日時を取得します。

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>戻り値

クエリ定義が最後に更新された日付と時刻を含む[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクト。

### <a name="remarks"></a>解説

関連情報については、DAO ヘルプの「DateCreated、LastUpdated Properties」を参照してください。

## <a name="cdaoquerydefgetfieldcount"></a><a name="getfieldcount"></a>CDaoQueryDef:: GetFieldCount

クエリ内のフィールドの数を取得するには、このメンバー関数を呼び出します。

```
short GetFieldCount();
```

### <a name="return-value"></a>戻り値

クエリで定義されているフィールドの数。

### <a name="remarks"></a>解説

`GetFieldCount`は、クエリ定義内のすべてのフィールドをループ処理する場合に便利です。 そのためには、 `GetFieldCount` [getfieldinfo](#getfieldinfo)と共にを使用します。

## <a name="cdaoquerydefgetfieldinfo"></a><a name="getfieldinfo"></a>CDaoQueryDef:: GetFieldInfo

このメンバー関数を呼び出して、クエリ定義で定義されているフィールドに関するさまざまな種類の情報を取得します。

```cpp
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
インデックスによる検索のために、クエリ定義の Fields コレクション内の目的のフィールドの0から始まるインデックス。

*fieldinfo*<br/>
要求された `CDaoFieldInfo` 情報を返すオブジェクトへの参照。

*オプション*<br/>
取得するフィールドに関する情報を指定するオプション。 使用可能なオプションは、関数が返す原因と共にここに表示されます。

- AFX_DAO_PRIMARY_INFO (既定) 名前、種類、サイズ、属性

- 主要な情報に加えて、序数の位置、必須、長さ0の許可、ソースフィールド、外部名、ソーステーブル、照合順序を AFX_DAO_SECONDARY_INFO します。

- プライマリとセカンダリの情報に加え、既定値、検証テキスト、検証規則を AFX_DAO_ALL_INFO します。

*lpszName*<br/>
名前で検索する目的のフィールドの名前を格納している文字列。 [CString](../../atl-mfc-shared/reference/cstringt-class.md)を使用できます。

### <a name="remarks"></a>解説

*Fieldinfo*で返される情報の説明については、 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体を参照してください。 この構造体には、上の*Dwinのオプション*の説明情報に対応するメンバーが含まれています。 1レベルの情報を要求すると、以前のレベルの情報も取得されます。

## <a name="cdaoquerydefgetname"></a><a name="getname"></a>CDaoQueryDef:: GetName

このメンバー関数を呼び出して、クエリの実行によって表されるクエリの名前を取得します。

```
CString GetName();
```

### <a name="return-value"></a>戻り値

クエリ名を返します。

### <a name="remarks"></a>解説

クエリ定義名は、一意のユーザー定義名です。 クエリ定義名の詳細については、DAO ヘルプの「Name プロパティ」を参照してください。

## <a name="cdaoquerydefgetodbctimeout"></a><a name="getodbctimeout"></a>CDaoQueryDef:: GetODBCTimeout

このメンバー関数を呼び出して、ODBC データソースに対するクエリがタイムアウトになるまでの現在の制限を取得します。

```
short GetODBCTimeout();
```

### <a name="return-value"></a>戻り値

クエリがタイムアウトするまでの秒数。

### <a name="remarks"></a>解説

この制限時間の詳細については、DAO ヘルプの「ODBCTimeout プロパティ」を参照してください。

> [!TIP]
> ODBC テーブルを使用する場合は、Microsoft Jet () に接続することをお勧めします。MDB) データベース。 詳細については、DAO ヘルプの「DAO を使用した外部データベースへのアクセス」を参照してください。

## <a name="cdaoquerydefgetparametercount"></a><a name="getparametercount"></a>CDaoQueryDef:: GetParameterCount

このメンバー関数を呼び出して、保存されたクエリのパラメーターの数を取得します。

```
short GetParameterCount();
```

### <a name="return-value"></a>戻り値

クエリで定義されているパラメーターの数。

### <a name="remarks"></a>解説

`GetParameterCount`は、クエリ定義内のすべてのパラメーターをループ処理する場合に便利です。 そのためには、 `GetParameterCount` [getparameterinfo](#getparameterinfo)と組み合わせてを使用します。

関連情報については、DAO ヘルプの「Parameter オブジェクト」、「Parameters Collection」、「PARAMETERS 宣言 (SQL)」を参照してください。

## <a name="cdaoquerydefgetparameterinfo"></a><a name="getparameterinfo"></a>CDaoQueryDef:: GetParameterInfo

このメンバー関数を呼び出して、クエリ定義で定義されているパラメーターに関する情報を取得します。

```cpp
void GetParameterInfo(
    int nIndex,
    CDaoParameterInfo& paraminfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetParameterInfo(
    LPCTSTR lpszName,
    CDaoParameterInfo& paraminfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
インデックスによる検索のために、クエリ定義の Parameters コレクション内にある目的のパラメーターの0から始まるインデックス。

*パラメーター情報*<br/>
要求された情報を返す[CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md)オブジェクトへの参照。

*オプション*<br/>
取得するパラメーターに関する情報を指定するオプション。 使用可能なオプションは、関数が返す原因と共にここに表示されます。

- AFX_DAO_PRIMARY_INFO (既定) 名前、型

*lpszName*<br/>
名前で検索する目的のパラメーターの名前を格納している文字列。 [CString](../../atl-mfc-shared/reference/cstringt-class.md)を使用できます。

### <a name="remarks"></a>解説

*パラメーター情報*で返される情報の説明については、 [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md)構造体を参照してください。 この構造体には、上の*Dwinのオプション*の説明情報に対応するメンバーが含まれています。

関連情報については、DAO ヘルプの「PARAMETERS 宣言 (SQL)」を参照してください。

## <a name="cdaoquerydefgetparamvalue"></a><a name="getparamvalue"></a>CDaoQueryDef::GetParamValue

このメンバー関数を呼び出して、クエリ定義の Parameters コレクションに格納されている、指定したパラメーターの現在の値を取得します。

```
virtual COleVariant GetParamValue(LPCTSTR lpszName);
virtual COleVariant GetParamValue(int nIndex);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
名前によって検索するために必要な値を持つパラメーターの名前。

*nIndex*<br/>
インデックスによって検索するための、クエリ定義の Parameters コレクション内のパラメーターの0から始まるインデックス。 この値は、 [Getparametercount](#getparametercount)と[getparameterinfo](#getparameterinfo)の呼び出しを使用して取得できます。

### <a name="return-value"></a>戻り値

パラメーターの値を格納している[COleVariant](../../mfc/reference/colevariant-class.md)クラスのオブジェクト。

### <a name="remarks"></a>解説

パラメーターには、名前またはコレクション内の序数位置を使用してアクセスできます。

関連情報については、DAO ヘルプの「PARAMETERS 宣言 (SQL)」を参照してください。

## <a name="cdaoquerydefgetrecordsaffected"></a><a name="getrecordsaffected"></a>CDaoQueryDef::GetRecordsAffected

[Execute](#execute)の最後の呼び出しによって影響を受けたレコードの数を確認するには、このメンバー関数を呼び出します。

```
long GetRecordsAffected();
```

### <a name="return-value"></a>戻り値

影響を受けたレコード数です。

### <a name="remarks"></a>解説

返されるカウントには、連鎖更新または削除が有効になっている場合、関連テーブルの変更は反映されません。

関連情報については、DAO ヘルプの「RecordsAffected プロパティ」を参照してください。

## <a name="cdaoquerydefgetreturnsrecords"></a><a name="getreturnsrecords"></a>CDaoQueryDef::GetReturnsRecords

このメンバー関数を呼び出して、レコードを返すクエリに基づいてクエリを実行するかどうかを判断します。

```
BOOL GetReturnsRecords();
```

### <a name="return-value"></a>戻り値

レコードを返すクエリに基づいてクエリを実行する場合は0以外の値。それ以外の場合は0です。

### <a name="remarks"></a>解説

このメンバー関数は、SQL パススルークエリにのみ使用されます。 SQL クエリの詳細については、「 [Execute](#execute)メンバー関数」を参照してください。 SQL パススルークエリの操作の詳細については、「 [SetReturnsRecords](#setreturnsrecords)メンバー関数」を参照してください。

関連情報については、DAO ヘルプの「ReturnsRecords プロパティ」を参照してください。

## <a name="cdaoquerydefgetsql"></a><a name="getsql"></a>CDaoQueryDef::GetSQL

このメンバー関数を呼び出して、クエリ定義の基になるクエリを定義する SQL ステートメントを取得します。

```
CString GetSQL();
```

### <a name="return-value"></a>戻り値

クエリ定義の基になるクエリを定義する SQL ステートメント。

### <a name="remarks"></a>解説

次に、キーワードやテーブル名などの文字列を解析します。

関連情報については、DAO ヘルプの「SQL プロパティ」、「Microsoft Jet データベースエンジン SQL と ANSI SQL の比較」、および「コード内の SQL を使用したデータベースのクエリ」を参照してください。

## <a name="cdaoquerydefgettype"></a><a name="gettype"></a>CDaoQueryDef:: GetType

このメンバー関数を呼び出して、クエリの種類を決定します。

```
short GetType();
```

### <a name="return-value"></a>戻り値

クエリ定義によって定義されたクエリの型。 値については、「解説」を参照してください。

### <a name="remarks"></a>解説

クエリの種類は、クエリ定義を作成するときに、querydef の SQL 文字列で指定したものによって設定されるか、既存の querydef の[SetSQL](#setsql)メンバー関数を呼び出します。 この関数によって返されるクエリの種類は、次のいずれかの値になります。

- `dbQSelect`クリック

- `dbQAction` 動作

- `dbQCrosstab`集計

- `dbQDelete` Del

- `dbQUpdate` Update

- `dbQAppend`追記

- `dbQMakeTable`テーブルの作成

- `dbQDDL`データ定義

- `dbQSQLPassThrough`パススルー

- `dbQSetOperation`組合

- `dbQSPTBulk`レコードを `dbQSQLPassThrough` 返さないクエリを指定するために、と共に使用します。

> [!NOTE]
> SQL パススルークエリを作成するには、定数を設定しないで `dbSQLPassThrough` ください。 これは、Microsoft Jet データベースエンジンによって、querydef オブジェクトを作成し、接続文字列を設定するときに自動的に設定されます。

SQL 文字列の詳細については、「 [GetSQL](#getsql)」を参照してください。 クエリの種類の詳細については、「 [Execute](#execute)」を参照してください。

## <a name="cdaoquerydefisopen"></a><a name="isopen"></a>CDaoQueryDef:: IsOpen

オブジェクトが現在開いているかどうかを判断するには、このメンバー関数を呼び出し `CDaoQueryDef` ます。

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>戻り値

オブジェクトが現在開いている場合は0以外 `CDaoQueryDef` 。それ以外の場合は0。

### <a name="remarks"></a>解説

[Execute](#execute)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを作成するために使用する前に、クエリ定義をオープン状態にする必要があります。 オープン状態の呼び出しにクエリを配置するには、 [Create](#create) (新しい querydef の場合) または[open](#open) (既存のクエリの場合) を呼び出します。

## <a name="cdaoquerydefm_pdatabase"></a><a name="m_pdatabase"></a>CDaoQueryDef:: m_pDatabase

Querydef オブジェクトに関連付けられた[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトへのポインターを格納します。

### <a name="remarks"></a>解説

データベースに直接アクセスする必要がある場合は、このポインターを使用します。たとえば、データベースのコレクション内の他のクエリ定義またはレコードセットオブジェクトへのポインターを取得します。

## <a name="cdaoquerydefm_pdaoquerydef"></a><a name="m_pdaoquerydef"></a>CDaoQueryDef:: m_pDAOQueryDef

基になる DAO querydef オブジェクトの OLE インターフェイスへのポインターを格納します。

### <a name="remarks"></a>解説

このポインターは、他のクラスとの一貫性を保つために用意されています。 ただし、MFC では DAO のクエリ定義が完全にカプセル化されるため、必要になる可能性はほとんどありません。 使用する場合は慎重に行う必要があります。特に、何を行っているかわからない場合は、ポインターの値を変更しないでください。

## <a name="cdaoquerydefopen"></a><a name="open"></a>CDaoQueryDef:: Open

このメンバー関数を呼び出して、データベースのクエリ定義コレクションに保存されている定義済みのクエリを開きます。

```
virtual void Open(LPCTSTR lpszName = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
開く、保存されたクエリの名前を含む文字列。 [CString](../../atl-mfc-shared/reference/cstringt-class.md)を使用できます。

### <a name="remarks"></a>解説

クエリ定義が開いたら、その[Execute](#execute)メンバー関数を呼び出すか、またはクエリを使用して、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを作成できます。

## <a name="cdaoquerydefsetconnect"></a><a name="setconnect"></a>CDaoQueryDef:: SetConnect

このメンバー関数を呼び出して、querydef オブジェクトの接続文字列を設定します。

```cpp
void SetConnect(LPCTSTR lpszConnect);
```

### <a name="parameters"></a>パラメーター

*lpszConnect*<br/>
関連付けられた[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトの接続文字列を含む文字列。

### <a name="remarks"></a>解説

接続文字列は、必要に応じて ODBC および特定の ISAM ドライバーに追加情報を渡すために使用されます。 Microsoft Jet () では使用されません。MDB) データベース。

> [!TIP]
> ODBC テーブルを使用する場合は、にアタッチすることをお勧めします。MDB データベース。

SQL パススルークエリを表すクエリを ODBC データソースに対して実行する前に、接続文字列をに設定 `SetConnect` し、 [SetReturnsRecords](#setreturnsrecords)を呼び出して、クエリがレコードを返すかどうかを指定します。

接続文字列の構造と接続文字列コンポーネントの例の詳細については、DAO ヘルプの「Connect プロパティ」を参照してください。

## <a name="cdaoquerydefsetname"></a><a name="setname"></a>CDaoQueryDef:: SetName

一時的ではないクエリの名前を変更する場合は、このメンバー関数を呼び出します。

```cpp
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
関連付けられた[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトの非一時クエリの新しい名前を含む文字列。

### <a name="remarks"></a>解説

クエリ定義名は、一意のユーザー定義名です。 を呼び出すと、 `SetName` querydef オブジェクトがクエリコレクションコレクションに追加されます。

## <a name="cdaoquerydefsetodbctimeout"></a><a name="setodbctimeout"></a>CDaoQueryDef:: SetODBCTimeout

ODBC データソースに対するクエリがタイムアウトするまでの制限時間を設定するには、このメンバー関数を呼び出します。

```cpp
void SetODBCTimeout(short nODBCTimeout);
```

### <a name="parameters"></a>パラメーター

*nODBCTimeout*<br/>
クエリがタイムアウトするまでの秒数。

### <a name="remarks"></a>解説

このメンバー関数を使用すると、接続されたデータソースに対する後続の操作の "タイムアウト" までの既定の秒数をオーバーライドできます。 操作は、ネットワークアクセスの問題、クエリ処理時間の超過などによってタイムアウトする場合があります。 `SetODBCTimeout`クエリのタイムアウト値を変更する場合は、このクエリを使用してクエリを実行する前に、を呼び出します。 (ODBC で接続を再利用する場合、タイムアウト値は、同じ接続上のすべてのクライアントで同じになります)。

クエリタイムアウトの既定値は60秒です。

## <a name="cdaoquerydefsetparamvalue"></a><a name="setparamvalue"></a>CDaoQueryDef::SetParamValue

実行時にクエリ定義のパラメーターの値を設定するには、このメンバー関数を呼び出します。

```
virtual void SetParamValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);

virtual void SetParamValue(
    int nIndex,
    const COleVariant& varValue);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
値を設定するパラメーターの名前。

*varValue*<br/>
設定する値。「解説」を参照してください。

*nIndex*<br/>
クエリ定義の Parameters コレクション内のパラメーターの位置を表す序数です。 この値は、 [Getparametercount](#getparametercount)と[getparameterinfo](#getparameterinfo)の呼び出しを使用して取得できます。

### <a name="remarks"></a>解説

パラメーターは、クエリ定義の SQL 文字列の一部として既に設定されている必要があります。 パラメーターには、名前またはコレクション内の序数位置を使用してアクセスできます。

オブジェクトとして設定する値を指定し `COleVariant` ます。 オブジェクトに必要な値と型を設定する方法の詳細については `COleVariant` 、「クラス[COleVariant](../../mfc/reference/colevariant-class.md)」を参照してください。

## <a name="cdaoquerydefsetreturnsrecords"></a><a name="setreturnsrecords"></a>CDaoQueryDef::SetReturnsRecords

SQL パススルークエリを外部データベースに設定するプロセスの一部として、このメンバー関数を呼び出します。

```cpp
void SetReturnsRecords(BOOL bReturnsRecords);
```

### <a name="parameters"></a>パラメーター

*bReturnsRecords*<br/>
外部データベースに対するクエリでレコードが返される場合は TRUE を渡します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このような場合は、他のメンバー関数を使用して、クエリを作成し、そのプロパティを設定する必要があり `CDaoQueryDef` ます。 外部データベースの説明については、「 [Setconnect](#setconnect)」を参照してください。

## <a name="cdaoquerydefsetsql"></a><a name="setsql"></a>CDaoQueryDef::SetSQL

このメンバー関数を呼び出して、クエリ実行によって実行される SQL ステートメントを設定します。

```cpp
void SetSQL(LPCTSTR lpszSQL);
```

### <a name="parameters"></a>パラメーター

*lpszSQL*<br/>
実行に適した完全な SQL ステートメントを含む文字列。 この文字列の構文は、クエリが対象とする DBMS によって異なります。 Microsoft Jet データベースエンジンで使用される構文の詳細については、DAO ヘルプのトピック「コードでの SQL ステートメントの作成」を参照してください。

### <a name="remarks"></a>解説

の一般的な使用方法 `SetSQL` は、SQL パススルークエリで使用するために、querydef オブジェクトを設定することです。 (ターゲット DBMS に対する SQL パススルークエリの構文については、DBMS のドキュメントを参照してください)。

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoTableDef クラス](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoException クラス](../../mfc/reference/cdaoexception-class.md)
