---
title: クラス
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
ms.openlocfilehash: 133746ff1e4a9453f9563347724a47855a8a3228
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368949"
---
# <a name="cdaoquerydef-class"></a>クラス

クエリ定義、つまり "querydef" を表し、通常はデータベースに保存されています。

## <a name="syntax"></a>構文

```
class CDaoQueryDef : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[クオダクエリデフ::CDaoクエリ定義](#cdaoquerydef)|`CDaoQueryDef` オブジェクトを構築します。 次の`Open`呼`Create`び出しまたは 、 のニーズに応じて。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[次の文字列を使用します。](#append)|保存されたクエリとして、データベースの QueryDefs コレクションにクエリ定義を追加します。|
|[クエリ定義::缶詰](#canupdate)|クエリでデータベースを更新できる場合は、0 以外を返します。|
|[クオダクエリデフ::閉じる](#close)|クエリ定義オブジェクトを閉じます。 C++ オブジェクトを破棄して、終了したら破棄します。|
|[クオダクエリ定義::作成](#create)|基になる DAO クエリ定義オブジェクトを作成します。 クエリ定義を一時クエリとして使用するか、呼`Append`び出してデータベースに保存します。|
|[実行](#execute)|クエリ定義オブジェクトによって定義されたクエリを実行します。|
|[コダクエリデフ::取得接続](#getconnect)|クエリ定義に関連付けられている接続文字列を返します。 接続文字列は、データ ソースを識別します。 (SQL パススルー クエリの場合のみ、それ以外の場合は空の文字列です。|
|[次の文字列を作成しました。](#getdatecreated)|保存されたクエリが作成された日付を返します。|
|[クエリ定義::取得日付最後更新](#getdatelastupdated)|保存されたクエリが最後に更新された日付を返します。|
|[クエリ定義::フィールドカウントを取得します。](#getfieldcount)|クエリ定義で定義されたフィールドの数を返します。|
|[CDaoQueryDef::GetFieldInfo](#getfieldinfo)|クエリで定義された指定されたフィールドに関する情報を返します。|
|[クエリ定義::ゲットネーム](#getname)|クエリ定義の名前を返します。|
|[クエリ定義::取得ODBC タイムアウト](#getodbctimeout)|クエリ定義の実行時に ODBC が使用するタイムアウト値 (ODBC クエリの場合) を返します。 これにより、クエリのアクションが完了するまでの時間が決まります。|
|[を使用します。](#getparametercount)|クエリに定義されているパラメータの数を返します。|
|[を指定します。](#getparameterinfo)|指定したパラメーターに関する情報をクエリに返します。|
|[クエリ定義::ゲットパラム値](#getparamvalue)|指定したパラメーターの値をクエリに返します。|
|[影響を受けるレコードを取得します。](#getrecordsaffected)|アクション クエリによって影響を受けるレコードの数を返します。|
|[レコードを取得します。](#getreturnsrecords)|querydef で定義されたクエリがレコードを返す場合は、0 以外を返します。|
|[クエリ定義::GetSQL](#getsql)|クエリ定義で定義されたクエリを指定する SQL 文字列を返します。|
|[クエリ定義::取得型](#gettype)|クエリの種類 (削除、更新、追加、テーブル作成など) を返します。|
|[カダオクエリデフ::IsOpen](#isopen)|クエリ定義が開いていて実行できる場合は、0 以外を返します。|
|[開く](#open)|データベースの QueryDefs コレクションに格納されている既存のクエリ定義を開きます。|
|[コダクエリデフ::セットコネクト](#setconnect)|ODBC データ ソースに対する SQL パススルー クエリの接続文字列を設定します。|
|[クオダクエリデフ::セット名](#setname)|保存されたクエリの名前を設定し、クエリ定義の作成時に使用されている名前を置き換えます。|
|[クエリ定義::セットODBCタイムアウト](#setodbctimeout)|クエリ定義の実行時に ODBC (ODBC クエリの場合) によって使用されるタイムアウト値を設定します。|
|[クオダクエリデフ::セットパラム値](#setparamvalue)|指定したパラメーターの値をクエリに設定します。|
|[レコードを返します。](#setreturnsrecords)|クエリ定義がレコードを返すかどうかを指定します。 この属性を TRUE に設定することは、SQL パススルー クエリに対してのみ有効です。|
|[クエリ定義::セットSQL](#setsql)|クエリ定義で定義されたクエリを指定する SQL 文字列を設定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[カオダクエリデフ::m_pDAOQueryDef](#m_pdaoquerydef)|基になる DAO クエリ定義オブジェクトの OLE インターフェイスへのポインター。|
|[カオブアクエリデフ::m_pDatabase](#m_pdatabase)|クエリ定義が`CDaoDatabase`関連付けられているオブジェクトへのポインター。 クエリ定義はデータベースに保存される可能性があります。|

## <a name="remarks"></a>解説

クエリ定義は、クエリを記述する SQL ステートメントと、"作成日" や "ODBC タイムアウト" などのプロパティを含むデータ アクセス オブジェクトです。 一時クエリ定義オブジェクトは保存せずに作成することもできますが、データベースで再利用頻度の高いクエリを保存する方が便利で、効率も高くなります。 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトは、保存されたクエリ定義を含むコレクションを保持します。

> [!NOTE]
> DAO データベース クラスは、オープン データベース接続 (ODBC) に基づく MFC データベース クラスとは異なります。 DAO データベースクラス名には、すべて "CDao" というプレフィックスが付いています。 DAO クラスを使用して ODBC データ ソースにアクセスすることはできます。 一般に、DAO に基づく MFC クラスは、ODBC に基づく MFC クラスよりも能力が高くなります。DAO ベースのクラスは、ODBC ドライバを使用して、独自のデータベース エンジンを介してデータにアクセスできます。 DAO ベースのクラスでは、DAO を直接呼び出すことなく、クラスを介してテーブルを追加するなど、データ定義言語 (DDL) 操作もサポートしています。

## <a name="usage"></a>使用法

querydef オブジェクトを使用して、既存の保存済みクエリを操作するか、新しい保存済みクエリまたは一時クエリを作成します。

1. すべての場合において、まず、クエリ`CDaoQueryDef`が属する[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトへのポインタを指定して、オブジェクトを構築します。

1. 次に、必要に応じて次の操作を行います。

   - 既存の保存済みクエリを使用するには、保存されているクエリの名前を指定して、querydef オブジェクトの[Open](#open)メンバー関数を呼び出します。

   - 保存された新しいクエリを作成するには、クエリ定義オブジェクトの[Create](#create)メンバー関数を呼び出して、クエリの名前を指定します。 次に[、クエリ](#append)をデータベースの QueryDefs コレクションに追加して、クエリを保存する Append を呼び出します。 `Create`クエリ定義をオープン状態にするため、呼び出した`Create`後は 呼`Open`び出しません。

   - 一時的なクエリ定義を作成するには`Create`、 を呼び出します。 クエリ名に空の文字列を渡します。 `Append` を呼び出さないでください。

クエリ定義オブジェクトの使用が終了したら[、Close](#close)メンバー関数を呼び出します。その後、クエリ定義オブジェクトを破棄します。

> [!TIP]
> 保存済みクエリを作成する最も簡単な方法は、Access を使用してクエリを作成してデータベースに格納することです。 次に、MFC コードで開いて使用できます。

## <a name="purposes"></a>目的

querydef オブジェクトは、次のいずれかの目的で使用できます。

- オブジェクトを`CDaoRecordset`作成するには

- オブジェクトの`Execute`メンバー関数を呼び出して、アクション クエリまたは SQL パススルー クエリを直接実行するには

選択、アクション、クロス集計、削除、更新、追加、テーブル作成、データ定義、SQL パススルー、ユニオン、および一括クエリなど、あらゆる種類のクエリに対して querydef オブジェクトを使用できます。 クエリの種類は、指定した SQL ステートメントの内容によって決まります。 クエリの種類については、 および`Execute`[GetType](#gettype)メンバー関数を参照してください。 レコードセットは、通常 SELECT を使用する行を返すクエリに使用されます **。キーワードから**。 `Execute`は、一括操作に最もよく使用されます。 詳細については、「[実行](#execute)と[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)」を参照してください。

## <a name="querydefs-and-recordsets"></a>クエリ定義とレコードセット

querydef オブジェクトを使用してオブジェクトを`CDaoRecordset`作成するには、通常、上記の手順でクエリ定義を作成または開きます。 次に、レコードセット オブジェクトを構築し[、CDaoRecordset::Open](../../mfc/reference/cdaorecordset-class.md#open)を呼び出すときにクエリ定義オブジェクトへのポインタを渡します。 渡すクエリ定義は、オープン状態である必要があります。 詳細については、「クラス[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)」を参照してください。

開いている状態でない限り、クエリ定義を使用してレコードセットを作成することはできません (クエリ定義の最も一般的な使用です)。 `Open`クエリ`Create`定義を開いた状態にします。

## <a name="external-databases"></a>外部データベース

Querydef オブジェクトは、外部データベース エンジンのネイティブ SQL 言語を使用する場合に推奨される方法です。 たとえば、(Microsoft SQL Server で使用される) Transact SQL クエリを作成し、クエリ定義オブジェクトに格納できます。 Microsoft Jet データベース エンジンに基づく SQL クエリを使用する必要がある場合は、外部データ ソースを指す接続文字列を指定する必要があります。 有効な接続文字列を持つクエリは、データベース エンジンをバイパスし、外部データベース サーバーに直接クエリを渡して処理します。

> [!TIP]
> ODBC テーブルを操作する場合は、そのテーブルをマイクロソフト ジェット (.MDB) データベース。

関連情報については、DAO SDK の「クエリ定義オブジェクト」、「クエリ定義コレクション」、および「CdbDatabase オブジェクト」のトピックを参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CDaoQueryDef`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="cdaoquerydefappend"></a><a name="append"></a>次の文字列を使用します。

[Create](#create)を呼び出して新しいクエリ定義オブジェクトを作成した後、このメンバー関数を呼び出します。

```
virtual void Append();
```

### <a name="remarks"></a>解説

`Append`オブジェクトをデータベースの QueryDefs コレクションに追加して、データベースにクエリ定義を保存します。 クエリ定義を追加せずに一時オブジェクトとして使用できますが、永続化する場合は を呼び出す`Append`必要があります。

一時的なクエリ定義オブジェクトを追加しようとすると、MFC は[CDaoException](../../mfc/reference/cdaoexception-class.md)型の例外をスローします。

## <a name="cdaoquerydefcanupdate"></a><a name="canupdate"></a>クエリ定義::缶詰

名前や SQL 文字列の変更など、クエリ定義を変更できるかどうかを調べます。

```
BOOL CanUpdate();
```

### <a name="return-value"></a>戻り値

クエリ定義の変更が許可されている場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

次の場合にクエリ定義を変更できます。

- 読み取り専用で開いているデータベースに基づいていません。

- データベースの更新権限があります。

   これは、セキュリティ機能を実装しているかどうかによって異なります。 MFC ではセキュリティはサポートされません。これを実装するには、直接呼び出すか、Access を使用して実装する必要があります。 DAO ヘルプの「アクセス許可プロパティ」を参照してください。

## <a name="cdaoquerydefcdaoquerydef"></a><a name="cdaoquerydef"></a>クオダクエリデフ::CDaoクエリ定義

`CDaoQueryDef` オブジェクトを構築します。

```
CDaoQueryDef(CDaoDatabase* pDatabase);
```

### <a name="parameters"></a>パラメーター

*データベース*<br/>
開いている[CDao データベース](../../mfc/reference/cdaodatabase-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

オブジェクトは、データベースの QueryDefs コレクションに格納されている既存のクエリ定義、コレクションに格納される新しいクエリ、または格納されない一時的なクエリを表すことができます。 次のステップは、クエリ定義のタイプによって異なります。

- オブジェクトが既存のクエリ定義を表す場合は、オブジェクトの[Open](#open)メンバー関数を呼び出して初期化します。

- 保存する新しいクエリ定義を表すオブジェクトの場合は、そのオブジェクトの[Create](#create)メンバー関数を呼び出します。 これにより、オブジェクトがデータベースの QueryDefs コレクションに追加されます。 次に`CDaoQueryDef`、メンバー関数を呼び出して、オブジェクトの属性を設定します。 最後に[、Append](#append)を呼び出します。

- オブジェクトが一時的なクエリ定義を表す場合 (データベースに保存しない場合`Create`)、クエリ名に空の文字列を渡します。 を呼`Create`び出した後、属性を直接設定してクエリ定義を初期化します。 `Append` を呼び出さないでください。

クエリ定義の属性を設定するには、[メンバー](#setname)関数を使用します。 [SetSQL](#setsql) [SetConnect](#setconnect) [SetODBCTimeout](#setodbctimeout) [SetReturnsRecords](#setreturnsrecords)

クエリ定義オブジェクトの処理が終了したら、その[Close](#close)メンバー関数を呼び出します。 クエリ定義へのポインターがある場合は **、delete**演算子を使用して C++ オブジェクトを破棄します。

## <a name="cdaoquerydefclose"></a><a name="close"></a>クオダクエリデフ::閉じる

クエリ定義オブジェクトの使用が終了したら、このメンバー関数を呼び出します。

```
virtual void Close();
```

### <a name="remarks"></a>解説

クエリ定義を閉じると、基になる DAO オブジェクトは解放されますが、保存されている DAO クエリ`CDaoQueryDef`定義オブジェクトや C++ オブジェクトは破棄されません。 これは、一時的なクエリ定義でない場合に、DAO のデータベースの QueryDefs コレクションからクエリ定義を削除する[CDaoDatabase::DeleteQueryDef](../../mfc/reference/cdaodatabase-class.md#deletequerydef)とは異なります。

## <a name="cdaoquerydefcreate"></a><a name="create"></a>クオダクエリ定義::作成

保存された新しいクエリまたは新しい一時クエリを作成します。

```
virtual void Create(
    LPCTSTR lpszName = NULL,
    LPCTSTR lpszSQL = NULL);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
データベースに保存されたクエリの一意の名前。 文字列の詳細については、DAO ヘルプのトピック「クエリ定義メソッドの作成」を参照してください。 既定値を受け入れる場合は、空の文字列、一時クエリ定義が作成されます。 このようなクエリは、QueryDefs コレクションには保存されません。

*Lpszsql*<br/>
クエリを定義する SQL 文字列。 既定値の NULL を受け入れる場合は、後で[SetSQL](#setsql)を呼び出して文字列を設定する必要があります。 それまでは、クエリは未定義です。 ただし、未定義のクエリを使用してレコードセットを開くことができます。詳細については、「解説」を参照してください。 クエリ定義を QueryDefs コレクションに追加するには、SQL ステートメントを事前に定義しておく必要があります。

### <a name="remarks"></a>解説

*lpszName*で名前を渡すと[、Append](#append)を呼び出して、データベースの QueryDefs コレクションにクエリ定義を保存できます。 それ以外の場合、オブジェクトは一時的なクエリ定義であり、保存されません。 どちらの場合も、クエリ定義は開いた状態にあり、これを使用して[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを作成するか、クエリ定義の[Execute](#execute)メンバー関数を呼び出すことができます。

*lpszSQL*で SQL ステートメントを指定しない場合は、クエリを実行できません`Execute`が、それを使用してレコードセットを作成できます。 その場合、MFC はレコードセットの既定の SQL ステートメントを使用します。

## <a name="cdaoquerydefexecute"></a><a name="execute"></a>実行

querydef オブジェクトによって定義されたクエリを実行します。

```
virtual void Execute(int nOptions = dbFailOnError);
```

### <a name="parameters"></a>パラメーター

*nオプション*<br/>
クエリの特性を決定する整数。 関連情報については、DAO ヘルプの「メソッドの実行」を参照してください。 ビットごとの OR 演算子 ( **&#124;**) を使用して、この引数に対して次の定数を組み合わせることができます。

- `dbDenyWrite`他のユーザーへの書き込みアクセス許可を拒否します。

- `dbInconsistent`一貫性のない更新プログラム。

- `dbConsistent`一貫した更新。

- `dbSQLPassThrough`SQL パススルー。 SQL ステートメントを処理のために ODBC データベースに渡します。

- `dbFailOnError`既定値。 エラーが発生した場合に更新をロールバックし、エラーをユーザーに報告します。

- `dbSeeChanges`編集中のデータを別のユーザーが変更している場合に、実行時エラーを生成します。

> [!NOTE]
> "不整合" および "一貫性のある" という用語の説明については、DAO ヘルプの「メソッドの実行」を参照してください。

### <a name="remarks"></a>解説

この方法で実行するために使用される Querydef オブジェクトは、次のクエリの種類のいずれかを表すことができます。

- アクション クエリ

- SQL パススルー クエリ

`Execute`は、選択クエリなどのレコードを返すクエリでは機能しません。 `Execute`は、一括操作クエリ (**たとえば、更新**、**挿入**、**または SELECT INTO**など ) や、データ定義言語 (DDL) 操作に使用されます。

> [!TIP]
> ODBC データ ソースを操作する場合は、テーブルを Jet にアタッチする方法 (.MDB) データベース。 詳細については、DAO ヘルプの「DAO を使用した外部データベースへのアクセス」を参照してください。

クエリ定義オブジェクトの[GetRecordsAffected](#getrecordsaffected)メンバー関数を呼び出して、最新`Execute`の呼び出しによって影響を受けるレコードの数を調べます。 たとえば、`GetRecordsAffected`アクション クエリの実行時に削除、更新、または挿入されたレコードの数に関する情報を返します。 カスケード更新または削除が有効な場合、返されるカウントには関連テーブルの変更は反映されません。

両方`dbInconsistent`を含める場合`dbConsistent`、または両方を含めずに含めなければ、`dbInconsistent`結果はデフォルトの.

`Execute`はレコードセットを返しません。 レコード`Execute`を選択するクエリを使用すると、MFC は[型 CDaoException](../../mfc/reference/cdaoexception-class.md)の例外をスローします。

## <a name="cdaoquerydefgetconnect"></a><a name="getconnect"></a>コダクエリデフ::取得接続

クエリ定義のデータ ソースに関連付けられている接続文字列を取得します。

```
CString GetConnect();
```

### <a name="return-value"></a>戻り値

クエリ定義の接続文字列を含む[CString](../../atl-mfc-shared/reference/cstringt-class.md)です。

### <a name="remarks"></a>解説

この関数は、ODBC データ ソースと特定の ISAM ドライバでのみ使用されます。 マイクロソフトジェット (.MDB) データベース;この場合、`GetConnect`空の文字列を返します。 詳細については、「 [SetConnect](#setconnect)」を参照してください。

> [!TIP]
> ODBC テーブルを使用する場合は、ODBC テーブルを にアタッチする方法を使用する方法を使用する方法を使用してください。MDB データベース。 詳細については、DAO ヘルプの「DAO を使用した外部データベースへのアクセス」を参照してください。

接続文字列の詳細については、DAO ヘルプの「プロパティの接続」を参照してください。

## <a name="cdaoquerydefgetdatecreated"></a><a name="getdatecreated"></a>次の文字列を作成しました。

クエリ定義オブジェクトが作成された日付を取得します。

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>戻り値

クエリ定義が作成された日付と時刻を含む[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクト。

### <a name="remarks"></a>解説

関連情報については、DAO ヘルプの「日付作成、最後に更新されたプロパティ」を参照してください。

## <a name="cdaoquerydefgetdatelastupdated"></a><a name="getdatelastupdated"></a>クエリ定義::取得日付最後更新

名前、SQL 文字列、接続文字列など、プロパティが変更されたときに、querydef オブジェクトが最後に更新された日付を取得します。

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>戻り値

クエリ定義が最後に更新された日付と時刻を含む[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクト。

### <a name="remarks"></a>解説

関連情報については、DAO ヘルプの「日付作成、最後に更新されたプロパティ」を参照してください。

## <a name="cdaoquerydefgetfieldcount"></a><a name="getfieldcount"></a>クエリ定義::フィールドカウントを取得します。

クエリ内のフィールドの数を取得します。

```
short GetFieldCount();
```

### <a name="return-value"></a>戻り値

クエリで定義されたフィールドの数。

### <a name="remarks"></a>解説

`GetFieldCount`は、クエリ定義のすべてのフィールドをループ処理するのに便利です。 そのためには`GetFieldCount`[、GetFieldInfo](#getfieldinfo)と組み合わせて使用します。

## <a name="cdaoquerydefgetfieldinfo"></a><a name="getfieldinfo"></a>次の項目を取得します。

クエリ定義で定義されているフィールドに関するさまざまな情報を取得します。

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
インデックスによる検索用に、クエリ定義の Fields コレクション内の目的のフィールドの 0 から始まるインデックス。

*Fieldinfo*<br/>
要求された情報を`CDaoFieldInfo`返すオブジェクトへの参照。

*オプション*<br/>
取得するフィールドに関する情報を指定するオプション。 使用可能なオプションは、関数が返す原因と共に次の一覧に示します。

- AFX_DAO_PRIMARY_INFO (デフォルト) の名前、種類、サイズ、属性

- AFX_DAO_SECONDARY_INFOプライマリ情報プラス: 序数位置、必須、許容長ゼロ、ソース フィールド、外部名、ソース テーブル、照合順序

- プライマリおよびセカンダリの情報に加えて、AFX_DAO_ALL_INFO:デフォルト値、検証テキスト、検証ルール

*名前を指定します。*<br/>
名前で検索する目的のフィールドの名前を含む文字列。 [CString](../../atl-mfc-shared/reference/cstringt-class.md)を使用できます。

### <a name="remarks"></a>解説

*fieldinfo*で返される情報の詳細については[、CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体を参照してください。 この構造体には、上記*の dwInfoOptions*の説明情報に対応するメンバーがあります。 1 つのレベルの情報を要求すると、以前のレベルの情報も取得できます。

## <a name="cdaoquerydefgetname"></a><a name="getname"></a>クエリ定義::ゲットネーム

クエリ定義で表されるクエリの名前を取得します。

```
CString GetName();
```

### <a name="return-value"></a>戻り値

クエリ名を返します。

### <a name="remarks"></a>解説

クエリ定義名は、一意のユーザー定義名です。 クエリ定義名の詳細については、DAO ヘルプの「プロパティ名」を参照してください。

## <a name="cdaoquerydefgetodbctimeout"></a><a name="getodbctimeout"></a>クエリ定義::取得ODBC タイムアウト

ODBC データ ソースへのクエリがタイムアウトするまでの現在の時間制限を取得します。

```
short GetODBCTimeout();
```

### <a name="return-value"></a>戻り値

クエリがタイムアウトするまでの秒数。

### <a name="remarks"></a>解説

この制限時間については、DAO ヘルプの「ODBC タイムアウト プロパティ」を参照してください。

> [!TIP]
> ODBC テーブルを操作する場合は、そのテーブルをマイクロソフト ジェット (.MDB) データベース。 詳細については、DAO ヘルプの「DAO を使用した外部データベースへのアクセス」を参照してください。

## <a name="cdaoquerydefgetparametercount"></a><a name="getparametercount"></a>を使用します。

保存されたクエリのパラメーター数を取得します。

```
short GetParameterCount();
```

### <a name="return-value"></a>戻り値

クエリで定義されたパラメーターの数。

### <a name="remarks"></a>解説

`GetParameterCount`は、クエリ定義内のすべてのパラメータをループ処理するのに便利です。 そのためには`GetParameterCount`[、GetParameterInfo](#getparameterinfo)と組み合わせて使用します。

関連情報については、DAO ヘルプの「パラメータ オブジェクト」、「パラメータ コレクション」、「パラメータ宣言 (SQL)」のトピックを参照してください。

## <a name="cdaoquerydefgetparameterinfo"></a><a name="getparameterinfo"></a>を指定します。

クエリ定義で定義されているパラメーターに関する情報を取得します。

```
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
インデックスによる検索用のクエリ定義の Parameters コレクション内の目的のパラメーターの 0 から始まるインデックス。

*パラインフォ*<br/>
要求された情報を返す[オブジェクト](../../mfc/reference/cdaoparameterinfo-structure.md)への参照。

*オプション*<br/>
取得するパラメーターに関する情報を指定するオプション。 使用可能なオプションは、関数が返す原因と共に次のリストに表示されます。

- AFX_DAO_PRIMARY_INFO (デフォルト) 名、タイプ

*名前を指定します。*<br/>
名前で検索する目的のパラメーターの名前を含む文字列。 [CString](../../atl-mfc-shared/reference/cstringt-class.md)を使用できます。

### <a name="remarks"></a>解説

*パラムインフォ*で返される情報の説明については、[構造体](../../mfc/reference/cdaoparameterinfo-structure.md)を参照してください。 この構造体には、上記*の dwInfoOptions*の説明情報に対応するメンバーがあります。

関連情報については、DAO ヘルプの「PARAMETERS 宣言 (SQL)」を参照してください。

## <a name="cdaoquerydefgetparamvalue"></a><a name="getparamvalue"></a>クエリ定義::ゲットパラム値

クエリ定義の Parameters コレクションに格納されている指定したパラメーターの現在の値を取得します。

```
virtual COleVariant GetParamValue(LPCTSTR lpszName);
virtual COleVariant GetParamValue(int nIndex);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
名前で検索する値を持つパラメーターの名前。

*nIndex*<br/>
インデックスによる検索用のクエリ定義の Parameters コレクション内のパラメーターの 0 から始まるインデックス。 この値は[、呼](#getparametercount)び[出しを](#getparameterinfo)使用して取得できます。

### <a name="return-value"></a>戻り値

パラメーターの値を格納するクラス[のオブジェクト](../../mfc/reference/colevariant-class.md)。

### <a name="remarks"></a>解説

パラメーターには、名前またはコレクション内の序数の位置を使用してアクセスできます。

関連情報については、DAO ヘルプの「PARAMETERS 宣言 (SQL)」を参照してください。

## <a name="cdaoquerydefgetrecordsaffected"></a><a name="getrecordsaffected"></a>影響を受けるレコードを取得します。

[Execute](#execute)の最後の呼び出しによって影響を受けたレコードの数を調べます。

```
long GetRecordsAffected();
```

### <a name="return-value"></a>戻り値

影響を受けたレコード数です。

### <a name="remarks"></a>解説

カスケード更新または削除が有効な場合、返されるカウントには関連テーブルの変更は反映されません。

関連情報については、DAO ヘルプの「レコードに影響を受けるプロパティ」を参照してください。

## <a name="cdaoquerydefgetreturnsrecords"></a><a name="getreturnsrecords"></a>レコードを取得します。

クエリ定義がレコードを返すクエリに基づいているかどうかを確認します。

```
BOOL GetReturnsRecords();
```

### <a name="return-value"></a>戻り値

クエリ定義がレコードを返すクエリに基づく場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメンバー関数は、SQL パススルー クエリにのみ使用されます。 SQL クエリの詳細については、「[実行](#execute)」のメンバー関数を参照してください。 SQL パススルー クエリの操作の詳細については、[メンバー](#setreturnsrecords)関数を参照してください。

関連情報については、DAO ヘルプの「レコードプロパティの返す」を参照してください。

## <a name="cdaoquerydefgetsql"></a><a name="getsql"></a>クエリ定義::GetSQL

クエリ定義の基になるクエリを定義する SQL ステートメントを取得します。

```
CString GetSQL();
```

### <a name="return-value"></a>戻り値

クエリ定義の基になるクエリを定義する SQL ステートメント。

### <a name="remarks"></a>解説

キーワードやテーブル名など、文字列を解析する可能性があります。

関連情報については、DAO ヘルプのトピック「SQL プロパティ」、「Microsoft Jet データベース エンジン SQL と ANSI SQL の比較」、および「コード内の SQL を使用したデータベースのクエリ」を参照してください。

## <a name="cdaoquerydefgettype"></a><a name="gettype"></a>クエリ定義::取得型

クエリ定義のクエリの種類を確認します。

```
short GetType();
```

### <a name="return-value"></a>戻り値

クエリ定義によって定義されるクエリの型。 値については、「解説」を参照してください。

### <a name="remarks"></a>解説

クエリの種類は、クエリ定義を作成するとき、または既存のクエリ定義の[SetSQL](#setsql)メンバー関数を呼び出すときに、クエリ定義の SQL 文字列で指定した内容によって設定されます。 この関数によって返されるクエリの種類は、次のいずれかの値です。

- `dbQSelect`選択

- `dbQAction` 動作

- `dbQCrosstab`クロス 集計

- `dbQDelete`削除

- `dbQUpdate` Update

- `dbQAppend`追加

- `dbQMakeTable`メイクテーブル

- `dbQDDL`データ定義

- `dbQSQLPassThrough`パススルー

- `dbQSetOperation`連合

- `dbQSPTBulk`レコードを`dbQSQLPassThrough`返さないクエリを指定するために使用します。

> [!NOTE]
> SQL パススルー クエリを作成するには、定数を`dbSQLPassThrough`設定しないでください。 これは、Querydef オブジェクトを作成して接続文字列を設定するときに、Jet データベース エンジンによって自動的に設定されます。

SQL 文字列の詳細については、 [GetSQL](#getsql)を参照してください。 クエリの種類については、「[実行](#execute)」を参照してください。

## <a name="cdaoquerydefisopen"></a><a name="isopen"></a>カダオクエリデフ::IsOpen

`CDaoQueryDef`オブジェクトが現在開いているかどうかを調べます。

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>戻り値

オブジェクトが`CDaoQueryDef`現在開いている場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

クエリ定義を[呼び出](#execute)す前に、クエリ定義を開いている状態にする必要があります[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)。 クエリ定義をオープン状態にする場合は、[作成](#create)(新しいクエリ定義の場合) または[Open](#open) (既存のクエリ定義の場合) を呼び出します。

## <a name="cdaoquerydefm_pdatabase"></a><a name="m_pdatabase"></a>カオブアクエリデフ::m_pDatabase

クエリ定義オブジェクトに関連付けられている[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトへのポインターを格納します。

### <a name="remarks"></a>解説

データベースのコレクション内の他のクエリ定義オブジェクトまたはレコードセット オブジェクトへのポインタを取得する場合など、データベースに直接アクセスする必要がある場合に、このポインタを使用します。

## <a name="cdaoquerydefm_pdaoquerydef"></a><a name="m_pdaoquerydef"></a>カオダクエリデフ::m_pDAOQueryDef

基になる DAO クエリ定義オブジェクトの OLE インターフェイスへのポインターを格納します。

### <a name="remarks"></a>解説

このポインターは、他のクラスとの完全性と一貫性を保つためです。 ただし、MFC は DAO クエリ定義を完全にカプセル化しているため、必要になることはほとんどありません。 使用する場合は、注意して行います - 特に、あなたが何をしているのか分からない限り、ポインタの値を変更しないでください。

## <a name="cdaoquerydefopen"></a><a name="open"></a>開く

このメンバー関数を呼び出して、データベースの QueryDefs コレクションに以前保存されているクエリ定義を開きます。

```
virtual void Open(LPCTSTR lpszName = NULL);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
開く保存済みクエリ定義の名前を含む文字列。 [CString](../../atl-mfc-shared/reference/cstringt-class.md)を使用できます。

### <a name="remarks"></a>解説

クエリ定義が開いたら、[その実行](#execute)メンバー関数を呼び出すか、クエリ定義を使用して[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを作成できます。

## <a name="cdaoquerydefsetconnect"></a><a name="setconnect"></a>コダクエリデフ::セットコネクト

クエリ定義オブジェクトの接続文字列を設定します。

```
void SetConnect(LPCTSTR lpszConnect);
```

### <a name="parameters"></a>パラメーター

*lpszConnect*<br/>
関連付けられた[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトの接続文字列を含む文字列。

### <a name="remarks"></a>解説

接続文字列は、必要に応じて ODBC および特定の ISAM ドライバーに追加情報を渡すために使用されます。 マイクロソフトジェット (.MDB) データベース。

> [!TIP]
> ODBC テーブルを使用する場合は、ODBC テーブルを にアタッチする方法を使用する方法を使用する方法を使用してください。MDB データベース。

ODBC データ ソースに対する SQL パススルー クエリを表すクエリ定義を実行する前に、`SetConnect`接続文字列を[設定し、SetReturnsRecords](#setreturnsrecords)を呼び出して、クエリがレコードを返すかどうかを指定します。

接続文字列の構造と接続文字列コンポーネントの例の詳細については、DAO ヘルプの「プロパティの接続」を参照してください。

## <a name="cdaoquerydefsetname"></a><a name="setname"></a>クオダクエリデフ::セット名

一時的でないクエリ定義の名前を変更する場合は、このメンバー関数を呼び出します。

```
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
関連付けられた[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクト内の一時的でないクエリの新しい名前を含む文字列。

### <a name="remarks"></a>解説

クエリ定義名は、一意のユーザー定義名です。 クエリ定義オブジェクト`SetName`が QueryDefs コレクションに追加される前に呼び出すことができます。

## <a name="cdaoquerydefsetodbctimeout"></a><a name="setodbctimeout"></a>クエリ定義::セットODBCタイムアウト

クエリが ODBC データ ソースにタイムアウトするまでの時間制限を設定します。

```
void SetODBCTimeout(short nODBCTimeout);
```

### <a name="parameters"></a>パラメーター

*タイムアウト*<br/>
クエリがタイムアウトするまでの秒数。

### <a name="remarks"></a>解説

このメンバー関数を使用すると、接続されているデータ ソースに対する後続の操作が "タイムアウト" されるまでの既定の秒数を上書きできます。 ネットワーク アクセスの問題、クエリ処理時間の過剰などにより、操作がタイムアウトすることがあります。 クエリ`SetODBCTimeout`のタイムアウト値を変更する場合は、このクエリ定義を使用してクエリを実行する前に呼び出します。 ODBC が接続を再利用するため、同じ接続のすべてのクライアントでタイムアウト値が同じになります。

クエリ タイムアウトの既定値は 60 秒です。

## <a name="cdaoquerydefsetparamvalue"></a><a name="setparamvalue"></a>クオダクエリデフ::セットパラム値

実行時にクエリ定義のパラメーターの値を設定します。

```
virtual void SetParamValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);

virtual void SetParamValue(
    int nIndex,
    const COleVariant& varValue);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
値を設定するパラメータの名前。

*値*<br/>
設定する値。「解説」を参照してください。

*nIndex*<br/>
クエリ定義の Parameters コレクション内のパラメーターの序数位置。 この値は[、呼](#getparametercount)び[出しを](#getparameterinfo)使用して取得できます。

### <a name="remarks"></a>解説

パラメータは、クエリ定義の SQL 文字列の一部として既に設定されている必要があります。 パラメーターには、名前またはコレクション内の序数の位置を使用してアクセスできます。

オブジェクトとして設定する値を`COleVariant`指定します。 `COleVariant`オブジェクト内の目的の値と型の設定については、「クラス[COleVariant](../../mfc/reference/colevariant-class.md)」を参照してください。

## <a name="cdaoquerydefsetreturnsrecords"></a><a name="setreturnsrecords"></a>レコードを返します。

外部データベースへの SQL パススルー クエリを設定するプロセスの一環として、このメンバー関数を呼び出します。

```
void SetReturnsRecords(BOOL bReturnsRecords);
```

### <a name="parameters"></a>パラメーター

*レコード*<br/>
外部データベースのクエリがレコードを返す場合は TRUE を渡します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このような場合は、querydef を作成し、そのプロパティを他`CDaoQueryDef`のメンバー関数を使用して設定する必要があります。 外部データベースの詳細については、 [SetConnect](#setconnect)を参照してください。

## <a name="cdaoquerydefsetsql"></a><a name="setsql"></a>クエリ定義::セットSQL

クエリ定義が実行する SQL ステートメントを設定します。

```
void SetSQL(LPCTSTR lpszSQL);
```

### <a name="parameters"></a>パラメーター

*Lpszsql*<br/>
実行に適した完全な SQL ステートメントを含む文字列。 この文字列の構文は、クエリが対象とする DBMS によって異なります。 Jet データベース エンジンで使用される構文の詳細については、DAO ヘルプの「コード内の SQL ステートメントの作成」を参照してください。

### <a name="remarks"></a>解説

一般的な使用方法`SetSQL`は、SQL パススルー クエリで使用するクエリ定義オブジェクトを設定することです。 (ターゲット DBMS での SQL パススルー クエリの構文については、DBMS のマニュアルを参照してください。

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)<br/>
[クラス](../../mfc/reference/cdaotabledef-class.md)<br/>
[クラスを呼び出す](../../mfc/reference/cdaoexception-class.md)
