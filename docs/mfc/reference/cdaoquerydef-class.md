---
title: CDaoQueryDef クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81e7d3b093da8127887878b2ac5f2af652f549c3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375795"
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
|[CDaoQueryDef::CDaoQueryDef](#cdaoquerydef)|構築、 **CDaoQueryDef**オブジェクト。 次に呼び出す**開く**または**作成**ニーズに応じて、します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoQueryDef::Append](#append)|クエリ定義を保存済みのクエリとして、データベースのクエリ定義のコレクションに追加します。|  
|[CDaoQueryDef::CanUpdate](#canupdate)|クエリは、データベースを更新できる場合は 0 以外を返します。|  
|[CDaoQueryDef::Close](#close)|クエリ定義オブジェクトを閉じます。 これが完了したら、C++ オブジェクトを破棄します。|  
|[CDaoQueryDef::Create](#create)|基になる DAO クエリ定義オブジェクトを作成します。 一時的なクエリ、または呼び出しとクエリ定義を使用する**Append**をデータベースに保存します。|  
|[CDaoQueryDef::Execute](#execute)|クエリ定義オブジェクトによって定義されたクエリを実行します。|  
|[CDaoQueryDef::GetConnect](#getconnect)|クエリ定義に関連付けられている接続文字列を返します。 接続文字列は、データ ソースを識別します。 (SQL のパススルー クエリのみです。 それ以外の場合、空の文字列です。)|  
|[CDaoQueryDef::GetDateCreated](#getdatecreated)|保存済みのクエリが作成された日付を返します。|  
|[CDaoQueryDef::GetDateLastUpdated](#getdatelastupdated)|保存済みのクエリの最終更新日を返します。|  
|[CDaoQueryDef::GetFieldCount](#getfieldcount)|クエリ定義で定義されているフィールドの数を返します。|  
|[CDaoQueryDef::GetFieldInfo](#getfieldinfo)|クエリで定義されている指定フィールドに関する情報を返します。|  
|[CDaoQueryDef::GetName](#getname)|クエリ定義の名前を返します。|  
|[CDaoQueryDef::GetODBCTimeout](#getodbctimeout)|(ODBC クエリ) に対して、ODBC で使用されるタイムアウト値を返すクエリを実行するとします。 これは、時間を決定、クエリの操作が完了するを許可します。|  
|[CDaoQueryDef::GetParameterCount](#getparametercount)|クエリに定義されたパラメーターの数を返します。|  
|[CDaoQueryDef::GetParameterInfo](#getparameterinfo)|クエリに指定されたパラメーターに関する情報を返します。|  
|[CDaoQueryDef::GetParamValue](#getparamvalue)|クエリに指定されたパラメーターの値を返します。|  
|[CDaoQueryDef::GetRecordsAffected](#getrecordsaffected)|アクション クエリによって影響を受けたレコード数を返します。|  
|[CDaoQueryDef::GetReturnsRecords](#getreturnsrecords)|クエリのクエリ定義で定義されているレコードを返す場合は 0 以外を返します。|  
|[CDaoQueryDef::GetSQL](#getsql)|クエリ定義で定義されているクエリを指定する SQL 文字列を返します。|  
|[CDaoQueryDef::GetType](#gettype)|クエリの種類を返します。 削除、更新、追加、テーブルを作成およびなどです。|  
|[CDaoQueryDef::IsOpen](#isopen)|クエリ定義が開いていて、実行できる場合は 0 以外を返します。|  
|[CDaoQueryDef::Open](#open)|データベースのクエリ定義のコレクションに格納されている既存のクエリ定義を開きます。|  
|[CDaoQueryDef::SetConnect](#setconnect)|ODBC データ ソースに対してパススルー クエリの接続文字列を設定します。|  
|[CDaoQueryDef::SetName](#setname)|クエリ定義の作成時に使用されている名を置き換えて、保存済みのクエリの名前を設定します。|  
|[CDaoQueryDef::SetODBCTimeout](#setodbctimeout)|(ODBC クエリ) に対して、ODBC で使用されるタイムアウト値を設定、クエリが実行されるとします。|  
|[CDaoQueryDef::SetParamValue](#setparamvalue)|クエリに指定されたパラメーターの値を設定します。|  
|[CDaoQueryDef::SetReturnsRecords](#setreturnsrecords)|クエリ定義がレコードを返すかどうかを指定します。 この属性を設定する**TRUE** SQL パススルー クエリに対してのみ有効です。|  
|[CDaoQueryDef::SetSQL](#setsql)|クエリ定義で定義されたクエリを指定する SQL 文字列を設定します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoQueryDef::m_pDAOQueryDef](#m_pdaoquerydef)|基になる DAO クエリ定義オブジェクトの OLE インターフェイスへのポインター。|  
|[CDaoQueryDef::m_pDatabase](#m_pdatabase)|ポインター、`CDaoDatabase`クエリ定義が関連付けられているオブジェクト。 クエリ定義は、か、データベースに保存可能性があります。|  
  
## <a name="remarks"></a>コメント  
 クエリ定義は、クエリ、および「作成日」や"ODBC Timeout"など、そのプロパティを説明する SQL ステートメントを含むデータ アクセス オブジェクト 保存せずに、一時的なクエリ定義オブジェクトを作成することもできますが、便利な — とはるかに効率的-一般的を保存する、データベース内のクエリを再利用します。 A [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトは、その保存したクエリ定義を含む QueryDefs コレクションと呼ばれる、コレクションを保持します。  
  
> [!NOTE]
>  DAO データベース クラスは、MFC データベース クラス ODBC Open Database Connectivity () をベースとは異なります。 DAO データベース クラスの名前では、"CDao"プレフィックスがあります。 DAO クラスで ODBC データ ソースのアクセスすることもできます。 一般に、DAO に基づいて MFC クラスは ODBC; に基づいて MFC クラスよりもより高機能ですDAO ベースのクラスは、独自のデータベース エンジンを使用して、ODBC ドライバーを介してなどのデータにアクセスできます。 DAO ベースのクラスには、DAO を直接呼び出すことがなく、クラスを使用してテーブルの追加などのデータ定義言語 (DDL) 操作もサポートします。  
  
## <a name="usage"></a>使用法  
 クエリ定義やオブジェクトを使用するか、保存済みのクエリを使用する新しいクエリまたは一時的なクエリを保存します。  
  
1.  すべてのケースでは構築最初、`CDaoQueryDef`へのポインターを提供するオブジェクト、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)クエリが属しているオブジェクトします。  
  
2.  目的に応じて、次の操作を行います。  
  
    -   保存済みのクエリを使用する呼び出しクエリ定義オブジェクトの[開く](#open)メンバー関数、保存済みのクエリの名前を指定します。  
  
    -   新しい保存したクエリを作成するには、クエリ定義オブジェクトを呼び出す[作成](#create)メンバー関数の場合、クエリの名前を指定します。 呼び出す[Append](#append)データベースのクエリ定義のコレクションに追加して、クエリを保存します。 **作成**クエリ定義では、開いている状態を呼び出した後は**作成**呼び出さないでください**開く**です。  
  
    -   一時的なクエリ定義を作成するには**作成**です。 クエリ名に空の文字列を渡します。 呼び出す必要はありません**Append**です。  
  
 クエリ定義オブジェクトの使用が終了したらを呼び出す、[閉じる](#close)メンバー関数には、クエリ定義オブジェクトを破棄します。  
  
> [!TIP]
>  保存したクエリを作成する最も簡単な方法は、それらを作成し、Microsoft Access を使用して、データベースに保存するのにです。 開き、MFC コードで使用します。  
  
## <a name="purposes"></a>目的  
 次の目的のいずれかのクエリ定義オブジェクトを使用できます。  
  
-   作成する、`CDaoRecordset`オブジェクト  
  
-   オブジェクトの呼び出しに**Execute**を直接操作クエリ、または SQL パススルー クエリを実行するメンバー関数  
  
 任意の種類を選択、アクション、クロス集計、削除、更新プログラムを含めて、クエリのクエリ定義オブジェクトを使用して、追加、テーブルの作成、データ定義、SQL パススルー、共用体、および一括クエリできます。 クエリの種類は、指定した SQL ステートメントの内容によって決まります。 クエリの種類については、次を参照してください。、 **Execute**と[GetType](#gettype)メンバー関数。 レコード セットは行を返すでよく使われるクエリして、通常を使用して、**を選択しています.** キーワード。 **実行**一括操作が最もよく使用されます。 詳細については、次を参照してください。 [Execute](#execute)と[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)です。  
  
## <a name="querydefs-and-recordsets"></a>クエリ定義とレコード セット  
 クエリ定義オブジェクトを使用して作成する、`CDaoRecordset`オブジェクトを一般に作成または前述のように、クエリ定義を開きます。 呼び出すときに、クエリ定義オブジェクトにポインターを渡す、レコード セット オブジェクトを構築[cdaorecordset::open](../../mfc/reference/cdaorecordset-class.md#open)です。 渡すクエリ定義は、開いている状態にする必要があります。 詳細については、クラスを参照してください。 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)です。  
  
 クエリ定義を使用して、開いている状態である場合を除き、(クエリ定義の最も一般的に使用) のレコード セットを作成することはできません。 いずれかを呼び出すことにより、開いている状態にクエリ定義を格納**開く**または**作成**です。  
  
## <a name="external-databases"></a>外部データベース  
 クエリ定義オブジェクトは、外部データベース エンジンのネイティブ SQL 文法を使用することをお勧めします。 たとえば、(Microsoft SQL Server で使用)、TRANSACT-SQL クエリを作成でき、クエリ定義オブジェクトに格納できます。 Microsoft Jet データベース エンジンに基づいていない SQL クエリを使用する必要がある場合は、外部データ ソースを指す接続文字列を指定する必要があります。 有効な接続文字列を持つクエリでは、データベース エンジンをバイパスし、処理用の外部データベース サーバーに直接クエリを渡します。  
  
> [!TIP]
>  Microsoft Jet に関連付けるには、ODBC テーブルを使用することをお勧め (です。MDB) データベース。  
  
 関連情報については、「QueryDef オブジェクト」、"QueryDefs Collection"および「CdbDatabase オブジェクト」DAO SDK のトピックを参照してください。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoQueryDef`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
##  <a name="append"></a>  CDaoQueryDef::Append  
 このメンバー関数を呼び出した後[作成](#create)新しいクエリ定義オブジェクトを作成します。  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>コメント  
 **追加**データベースのクエリ定義のコレクションにオブジェクトを追加することによって、クエリ定義をデータベースに保存します。 一時オブジェクトとして追加することがなくクエリ定義を使用することができますが、それを保持する場合を呼び出す必要があります**Append**です。  
  
 一時的なクエリ定義オブジェクトを追加しようとする場合、MFC に型の例外がスロー [CDaoException](../../mfc/reference/cdaoexception-class.md)です。  
  
##  <a name="canupdate"></a>  CDaoQueryDef::CanUpdate  
 クエリ定義を変更できるかどうかを決定するには、このメンバー関数を呼び出すなどの名前または SQL 文字列の変更などです。  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>戻り値  
 クエリ定義を変更する権限がある場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 場合は、クエリ定義を変更できます。  
  
-   読み取り専用で開かれているデータベースに基づきません。  
  
-   データベースに対する更新アクセス許可があります。  
  
     これは、セキュリティ機能を実装しているかどうかによって異なります。 MFC ではセキュリティのサポートはされていません必要がありますこれを実装する独自の DAO の直接の呼び出しによって、または Microsoft Access を使用しています。 DAO ヘルプの「アクセス許可プロパティ」トピックを参照してください。  
  
##  <a name="cdaoquerydef"></a>  CDaoQueryDef::CDaoQueryDef  
 構築、 **CDaoQueryDef**オブジェクト。  
  
```  
CDaoQueryDef(CDaoDatabase* pDatabase);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDatabase`  
 開いているへのポインター [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクト。  
  
### <a name="remarks"></a>コメント  
 オブジェクトは、データベースのクエリ定義のコレクション、コレクションに格納される新しいクエリまたはしなければならないの一時的なクエリに格納されている既存のクエリ定義を表すことができます。 次の手順は、クエリ定義の種類によって異なります。  
  
-   オブジェクトは、既存のクエリ定義を表している場合は、オブジェクトを呼び出す[開く](#open)メンバー関数を初期化します。  
  
-   オブジェクトは、保存する新しいクエリ定義を表している場合は、オブジェクトを呼び出す[作成](#create)メンバー関数。 これは、データベースのクエリ定義のコレクションにオブジェクトを追加します。 呼び出す`CDaoQueryDef`メンバー関数、オブジェクトの属性を設定します。 最後に、呼び出す[Append](#append)です。  
  
-   オブジェクトを表す場合、一時的なクエリの定義 (データベースに保存しない)、呼び出す**作成**クエリの名前の空の文字列を渡します。 呼び出した後**作成**、直接その属性を設定して、クエリ定義を初期化します。 呼び出す必要はありません**Append**です。  
  
 クエリ定義の属性を設定するには、使用することができます、 [SetName](#setname)、 [SetSQL](#setsql)、 [SetConnect](#setconnect)、[に](#setodbctimeout)、および[SetReturnsRecords](#setreturnsrecords)メンバー関数。  
  
 クエリ定義オブジェクトが完了したら、ときに呼び出すその[閉じる](#close)メンバー関数。 クエリ定義へのポインターがあればを使用して、**削除**C++ オブジェクトを破棄する演算子です。  
  
##  <a name="close"></a>  CDaoQueryDef::Close  
 クエリ定義オブジェクトの使用が終了するときに、このメンバー関数を呼び出します。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>コメント  
 基になる DAO オブジェクトを解放が保存された DAO クエリ定義オブジェクトまたは C++ を破棄しませんクエリ定義を終了`CDaoQueryDef`オブジェクト。 これは同じ[CDaoDatabase::DeleteQueryDef](../../mfc/reference/cdaodatabase-class.md#deletequerydef)DAO (ない場合は一時的なクエリ定義) で、データベースのクエリ定義のコレクションから、クエリ定義を削除します。  
  
##  <a name="create"></a>  CDaoQueryDef::Create  
 新しい保存済みのクエリまたは新しい一時的なクエリを作成するには、このメンバー関数を呼び出します。  
  
```  
virtual void Create(
    LPCTSTR lpszName = NULL,  
    LPCTSTR lpszSQL = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 データベースに保存されたクエリの一意の名前。 詳細については、文字列、DAO ヘルプの「CreateQueryDef メソッド」を参照してください。 既定値、空の文字列を使用する場合は、一時的なクエリ定義が作成されます。 QueryDefs コレクションでは、このようなクエリは保存されません。  
  
 `lpszSQL`  
 クエリを定義する SQL 文字列です。 既定値を受け入れる場合**NULL**、後で呼び出す必要があります[SetSQL](#setsql)文字列を設定します。 それまでは、クエリは、定義されていません。 開くには、レコード セットです。 ただし、未定義のクエリを使用できます。詳細については、「解説」を参照してください。 QueryDefs コレクションにクエリ定義を追加する前に、SQL ステートメントを定義する必要があります。  
  
### <a name="remarks"></a>コメント  
 名前を渡す場合`lpszName`、し、呼び出すことができます[Append](#append)データベースのクエリ定義のコレクションにクエリ定義を保存します。 それ以外の場合、オブジェクトは、一時的なクエリ定義では保存されません。 どちらの場合、開いている状態では、クエリ定義と作成に使用できる、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトまたはクエリ定義の[Execute](#execute)メンバー関数。  
  
 内の SQL ステートメントを指定しない場合`lpszSQL`を使用してクエリを実行することはできません**Execute**がそれを使用して、レコード セットを作成することができます。 その場合は、MFC は、レコード セットの既定の SQL ステートメントを使用します。  
  
##  <a name="execute"></a>  CDaoQueryDef::Execute  
 クエリ定義オブジェクトによって定義されたクエリを実行するには、このメンバー関数を呼び出します。  
  
```  
virtual void Execute(int nOptions = dbFailOnError);
```  
  
### <a name="parameters"></a>パラメーター  
 `nOptions`  
 クエリの特性を決定する整数。 関連情報については、"Execute Method"DAO ヘルプのトピックを参照してください。 ビットごとの OR 演算子を使用することができます ( **&#124;**) をこの引数は、次の定数を結合します。  
  
- **dbDenyWrite**他のユーザーへの書き込み権限を拒否します。  
  
- **組み合わせて**不整合な更新します。  
  
- **指定できます**一貫性のある更新プログラム。  
  
- **dbSQLPassThrough** SQL パススルーします。 処理のための ODBC データベースに渡される SQL ステートメントが発生します。  
  
- **dbFailOnError**既定値です。 更新プログラム エラーが発生した場合と、エラー レポートにロールバック ユーザー。  
  
- **dbSeeChanges**別のユーザーが編集してデータを変更する場合は、実行時エラーを生成します。  
  
> [!NOTE]
>  用語の説明「不整合」と「一貫した、」"Execute Method"DAO ヘルプのトピックを参照してください。  
  
### <a name="remarks"></a>コメント  
 この方法で実行するために使用されるクエリ定義オブジェクトでは、次のクエリの種類のいずれかの表すことができますのみ。  
  
-   アクションのクエリ  
  
-   SQL パススルー クエリ  
  
 **実行**select クエリなどのレコードを返すクエリに対しては機能しません。 **実行**など使用一括操作のクエリでは、よく**更新**、**挿入**、または**SELECT INTO**、またはデータ定義言語 (DDL) 操作です。  
  
> [!TIP]
>  ODBC データ ソースを使用することをお勧め、Microsoft Jet にテーブルをアタッチする (です。MDB) データベース。 詳細については、"にアクセスする外部のデータベースと DAO"DAO ヘルプのトピックを参照してください。  
  
 呼び出す、 [GetRecordsAffected](#getrecordsaffected)最新によって影響を受けたレコードの数を決定するクエリ定義オブジェクトのメンバー関数**Execute**呼び出します。 たとえば、`GetRecordsAffected`削除、更新、またはアクション クエリを実行するときに挿入されるレコードの数に関する情報を返します。 返されるカウントを cascade を更新または削除時の関連テーブルの変更が有効では反映されません。  
  
 両方を含める場合**組み合わせて**と**指定できます**、結果は、既定で含める場合はどちらも、または**組み合わせて**です。  
  
 **実行**はレコード セットを返しません。 使用して**Execute**レコードを選択するクエリで MFC の種類の例外をスローすると、 [CDaoException](../../mfc/reference/cdaoexception-class.md)です。  
  
##  <a name="getconnect"></a>  CDaoQueryDef::GetConnect  
 クエリ定義のデータ ソースに関連付けられた接続文字列を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)クエリ定義の接続文字列を含むです。  
  
### <a name="remarks"></a>コメント  
 この関数は、ODBC データ ソースと特定 ISAM ドライバーでのみ使用されます。 Microsoft Jet では使用されません (です。MDB) データベース。この場合、`GetConnect`空の文字列を返します。 詳細については、次を参照してください。 [SetConnect](#setconnect)です。  
  
> [!TIP]
>  ODBC テーブルを使用することをお勧めは、接続先には、します。MDB データベースです。 詳細については、"にアクセスする外部のデータベースと DAO"DAO ヘルプのトピックを参照してください。  
  
 接続文字列については、"接続 Property"DAO ヘルプのトピックを参照してください。  
  
##  <a name="getdatecreated"></a>  CDaoQueryDef::GetDateCreated  
 クエリ定義オブジェクトが作成された日付を取得するには、このメンバー関数を呼び出します。  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>戻り値  
 A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)クエリ定義が作成された日時を含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 関連情報については、DAO ヘルプのトピックの「作成日時、LastUpdated プロパティ」を参照してください。  
  
##  <a name="getdatelastupdated"></a>  CDaoQueryDef::GetDateLastUpdated  
 クエリ定義オブジェクトの日付を取得するには、このメンバー関数が最後に更新された呼び出し、そのプロパティのいずれかが変更されたとき、名、SQL 文字列、またはその接続文字列など。  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>戻り値  
 A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)クエリ定義が最後に更新された日時を含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 関連情報については、DAO ヘルプのトピックの「作成日時、LastUpdated プロパティ」を参照してください。  
  
##  <a name="getfieldcount"></a>  CDaoQueryDef::GetFieldCount  
 クエリのフィールドの数を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>戻り値  
 クエリで定義されたフィールドの数。  
  
### <a name="remarks"></a>コメント  
 `GetFieldCount` クエリ定義のすべてのフィールドをループに便利です。 そのためを使用して`GetFieldCount`と共に[GetFieldInfo](#getfieldinfo)です。  
  
##  <a name="getfieldinfo"></a>  CDaoQueryDef::GetFieldInfo  
 さまざまな種類のクエリ定義で定義されているフィールドに関する情報を取得するには、このメンバー関数を呼び出します。  
  
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
 `nIndex`  
 インデックスで検索する場合のクエリ定義のフィールド コレクションの目的のフィールドの 0 から始まるインデックス。  
  
 `fieldinfo`  
 参照、`CDaoFieldInfo`要求された情報を表すオブジェクト。  
  
 `dwInfoOptions`  
 取得するフィールドに関する情報を指定するオプション。 使用可能なオプションを返す関数が何もここで表示されます。  
  
- `AFX_DAO_PRIMARY_INFO` (既定値)名前、種類、サイズ、属性  
  
- `AFX_DAO_SECONDARY_INFO` プライマリ情報に加えて: 必要な序数の位置、長さゼロを許可する、ソース フィールド、外部名、ソース テーブル、照合順序  
  
- `AFX_DAO_ALL_INFO` プライマリとセカンダリの情報に加えて: 既定値、入力テキスト、検証規則  
  
 `lpszName`  
 名前で検索する場合、該当するフィールドの名前を含む文字列。 使用することができます、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)です。  
  
### <a name="remarks"></a>コメント  
 返される情報の詳細については`fieldinfo`を参照してください、 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体。 この構造体は、わかりやすい情報に対応するメンバー`dwInfoOptions`上。 1 つのレベルの情報を要求すると、その情報も同様のレベルを取得します。  
  
##  <a name="getname"></a>  CDaoQueryDef::GetName  
 クエリ定義で表されるクエリの名前を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>戻り値  
 クエリ名を返します。  
  
### <a name="remarks"></a>コメント  
 クエリ定義名は一意のユーザー定義の名前です。 クエリ定義名の詳細については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
##  <a name="getodbctimeout"></a>  CDaoQueryDef::GetODBCTimeout  
 ODBC データ ソースへのクエリがタイムアウトする前に、現在の制限時間を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetODBCTimeout();
```  
  
### <a name="return-value"></a>戻り値  
 クエリするまでの秒数がタイムアウトになりました。  
  
### <a name="remarks"></a>コメント  
 この制限時間については、DAO ヘルプの「補足プロパティ」を参照してください。  
  
> [!TIP]
>  Microsoft Jet に関連付けるには、ODBC テーブルを使用することをお勧め (です。MDB) データベース。 詳細については、"にアクセスする外部のデータベースと DAO"DAO ヘルプのトピックを参照してください。  
  
##  <a name="getparametercount"></a>  CDaoQueryDef::GetParameterCount  
 保存済みのクエリのパラメーターの数を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetParameterCount();
```  
  
### <a name="return-value"></a>戻り値  
 クエリで定義されたパラメーターの数。  
  
### <a name="remarks"></a>コメント  
 `GetParameterCount` クエリ定義のすべてのパラメーターをループに便利です。 そのためを使用して`GetParameterCount`と共に[GetParameterInfo](#getparameterinfo)です。  
  
 関連情報については、「オブジェクトがパラメーター」、「パラメーターのコレクション」および"パラメーターの宣言 (SQL)"DAO ヘルプのトピックを参照してください。  
  
##  <a name="getparameterinfo"></a>  CDaoQueryDef::GetParameterInfo  
 クエリ定義で定義されているパラメーターに関する情報を取得するには、このメンバー関数を呼び出します。  
  
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
 `nIndex`  
 インデックスで検索する場合、クエリ定義のパラメーターのコレクションで目的のパラメーターの 0 から始まるインデックス。  
  
 `paraminfo`  
 参照、 [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md)要求された情報を表すオブジェクト。  
  
 `dwInfoOptions`  
 取得するパラメーターに関する情報を指定するオプション。 使用可能なオプションは、その原因は何を返す関数と共に、ここに記載されています。  
  
- `AFX_DAO_PRIMARY_INFO` (既定値)名前、型  
  
 `lpszName`  
 名前で検索する場合、必要なパラメーターの名前を含む文字列。 使用することができます、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)です。  
  
### <a name="remarks"></a>コメント  
 返される情報の詳細については`paraminfo`を参照してください、 [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md)構造体。 この構造体は、わかりやすい情報に対応するメンバー`dwInfoOptions`上。  
  
 関連情報については、"パラメーターの宣言 (SQL)"DAO ヘルプのトピックを参照してください。  
  
##  <a name="getparamvalue"></a>  CDaoQueryDef::GetParamValue  
 クエリ定義のパラメーター コレクションに格納されている指定されたパラメーターの現在の値を取得するには、このメンバー関数を呼び出します。  
  
```  
virtual COleVariant GetParamValue(LPCTSTR lpszName);  
virtual COleVariant GetParamValue(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 パラメーター値を取得する、名前で検索する場合の名前。  
  
 `nIndex`  
 インデックスで検索する場合、クエリ定義のパラメーター コレクション内のパラメーターの 0 から始まるインデックス。 呼び出しでこの値を取得する[GetParameterCount](#getparametercount)と[GetParameterInfo](#getparameterinfo)です。  
  
### <a name="return-value"></a>戻り値  
 クラスのオブジェクト[COleVariant](../../mfc/reference/colevariant-class.md)パラメーターの値を格納します。  
  
### <a name="remarks"></a>コメント  
 名前またはコレクション内の序数位置のいずれかのパラメーターを表示できます。  
  
 関連情報については、"パラメーターの宣言 (SQL)"DAO ヘルプのトピックを参照してください。  
  
##  <a name="getrecordsaffected"></a>  CDaoQueryDef::GetRecordsAffected  
 最後の呼び出しの影響を受けたレコードの数を決定するには、このメンバー関数を呼び出す[Execute](#execute)です。  
  
```  
long GetRecordsAffected();
```  
  
### <a name="return-value"></a>戻り値  
 影響を受けたレコードの数。  
  
### <a name="remarks"></a>コメント  
 返されるカウントを cascade を更新または削除時の関連テーブルの変更が有効では反映されません。  
  
 関連情報については、トピック「DAO ヘルプの「RecordsAffected プロパティ」を参照してください。  
  
##  <a name="getreturnsrecords"></a>  CDaoQueryDef::GetReturnsRecords  
 クエリ定義がレコードを返すクエリに基づくかを決定するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetReturnsRecords();
```  
  
### <a name="return-value"></a>戻り値  
 レコードを返すクエリ定義がクエリに基づいている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、SQL パススルー クエリに対してのみ使用します。 SQL クエリの詳細については、次を参照してください。、 [Execute](#execute)メンバー関数。 SQL パススルー クエリによる作業の詳細については、次を参照してください。、 [SetReturnsRecords](#setreturnsrecords)メンバー関数。  
  
 関連情報については、DAO のヘルプで「レコード表示プロパティ」を参照してください。  
  
##  <a name="getsql"></a>  CDaoQueryDef::GetSQL  
 クエリ定義の基になるクエリを定義する SQL ステートメントを取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetSQL();
```  
  
### <a name="return-value"></a>戻り値  
 クエリ定義の基になるクエリを定義する SQL ステートメント。  
  
### <a name="remarks"></a>コメント  
 キーワード、テーブル名などの文字列を可能性があります解析されます。  
  
 関連情報については、"SQL Property"、"比較の Microsoft Jet データベース エンジン SQL と ANSI SQL"、および「クエリを実行する、データベースと SQL のコード」DAO ヘルプのトピックを参照してください。  
  
##  <a name="gettype"></a>  CDaoQueryDef::GetType  
 クエリ定義のクエリの種類を確認するには、このメンバー関数を呼び出します。  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>戻り値  
 クエリ定義で定義されたクエリの型。 値は、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 クエリの種類はどのような文字列で指定するクエリ定義の SQL クエリ定義を作成するか、既存のクエリ定義の場合で設定[SetSQL](#setsql)メンバー関数。 この関数によって返されたクエリの種類には、次の値のいずれかを指定できます。  
  
- **dbQSelect**選択  
  
- **dbQAction**アクション  
  
- **dbQCrosstab**クロス集計  
  
- **dbQDelete**削除  
  
- **dbQUpdate**更新  
  
- **dbQAppend**追加  
  
- **dbQMakeTable**テーブルの作成  
  
- **dbQDDL**データ定義  
  
- **dbQSQLPassThrough**パススルー  
  
- **dbQSetOperation**共用体  
  
- **dbQSPTBulk**併用**dbQSQLPassThrough**レコードを返さないクエリを指定します。  
  
> [!NOTE]
>  設定しない SQL パススルー クエリを作成する、 **dbSQLPassThrough**定数。 これは自動的に設定 Microsoft Jet データベース エンジンによってクエリ定義オブジェクトを作成し、接続文字列を設定します。  
  
 SQL 文字列については、次を参照してください。 [GetSQL](#getsql)です。 クエリの種類については、次を参照してください。 [Execute](#execute)です。  
  
##  <a name="isopen"></a>  CDaoQueryDef::IsOpen  
 決定するには、このメンバー関数を呼び出すかどうか、`CDaoQueryDef`オブジェクトが現在開いています。  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、`CDaoQueryDef`オブジェクトが現在開いている。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 クエリ定義は、呼び出しに使用する前に、開いている状態である必要があります[Execute](#execute)を作成したり、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクト。 クエリ定義を開いている状態に呼び出すか、[作成](#create)(新しいクエリを定義) のまたは[を開く](#open)(の既存のクエリ定義) です。  
  
##  <a name="m_pdatabase"></a>  CDaoQueryDef::m_pDatabase  
 ポインターが含まれています、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)クエリ定義オブジェクトに関連付けられているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 データベースに直接アクセスする必要がある場合は、このポインターを使用して — たとえば、他のクエリ定義またはレコード セットへのポインターを取得するデータベースのコレクションでオブジェクトします。  
  
##  <a name="m_pdaoquerydef"></a>  CDaoQueryDef::m_pDAOQueryDef  
 基になる DAO クエリ定義オブジェクトの OLE インターフェイスへのポインターが含まれています。  
  
### <a name="remarks"></a>コメント  
 このポインターは完全性と整合性の他のクラスが提供されます。 ただし、MFC には、DAO のクエリ定義ではなく完全にカプセル化するためすることが必要ではありません。 それを使用する場合は注意: 何を行うことがわかっていない限り、ポインターの値を変更して具体的には、します。  
  
##  <a name="open"></a>  CDaoQueryDef::Open  
 開くには、データベースのクエリ定義のコレクションに以前に保存したクエリ定義には、このメンバー関数を呼び出します。  
  
```  
virtual void Open(LPCTSTR lpszName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 開くには保存したクエリ定義の名前を表す文字列。 使用することができます、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)です。  
  
### <a name="remarks"></a>コメント  
 呼び出すことができます、クエリが開いたら、その[Execute](#execute)メンバー関数または作成するクエリ定義を使用して、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクト。  
  
##  <a name="setconnect"></a>  CDaoQueryDef::SetConnect  
 クエリ定義オブジェクトの接続文字列を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetConnect(LPCTSTR lpszConnect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszConnect`  
 関連付けられている接続文字列を含む文字列[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクト。  
  
### <a name="remarks"></a>コメント  
 接続文字列を使用して、ODBC および必要に応じて特定 ISAM ドライバーに追加情報を渡します。 Microsoft Jet 用は使用されません (です。MDB) データベース。  
  
> [!TIP]
>  ODBC テーブルを使用することをお勧めは、接続先には、します。MDB データベースです。  
  
 ODBC データ ソースへの SQL のパススルー クエリを表すクエリを実行する前に設定された接続文字列で`SetConnect`を呼び出すと[SetReturnsRecords](#setreturnsrecords)クエリがレコードを返すかどうかを指定します。  
  
 詳細については、接続文字列の構造と接続文字列コンポーネントの例については、"接続 Property"DAO ヘルプのトピックを参照してください。  
  
##  <a name="setname"></a>  CDaoQueryDef::SetName  
 ない一時的なクエリ定義の名前を変更する場合は、このメンバー関数を呼び出します。  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 関連付けられた nontemporary のクエリの新しい名前を表す文字列[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクト。  
  
### <a name="remarks"></a>コメント  
 クエリ定義名は、ユーザー定義の一意の名前です。 呼び出すことができます`SetName`クエリ定義の前に、オブジェクトが QueryDefs コレクションに追加されます。  
  
##  <a name="setodbctimeout"></a>  CDaoQueryDef::SetODBCTimeout  
 ODBC データ ソースへのクエリがタイムアウトするまでに時間制限を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetODBCTimeout(short nODBCTimeout);
```  
  
### <a name="parameters"></a>パラメーター  
 *nODBCTimeout*  
 クエリするまでの秒数がタイムアウトになりました。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数では、「タイムアウト」接続されているデータ ソースに対する後続の処理までの秒数の既定をオーバーライドできます。 操作は、ネットワーク アクセスの問題、過剰なクエリ処理時間などによりタイムアウト可能性があります。 呼び出す`SetODBCTimeout`クエリのタイムアウト値を変更する場合は、このクエリの定義を持つクエリを実行する前にします。 (ように ODBC には、接続が再利用、タイムアウト値は、同じ接続上のすべてのクライアントの同じ) です。  
  
 クエリのタイムアウトの既定値は、60 秒です。  
  
##  <a name="setparamvalue"></a>  CDaoQueryDef::SetParamValue  
 実行時にクエリ定義でパラメーターの値を設定するには、このメンバー関数を呼び出します。  
  
```  
virtual void SetParamValue(
    LPCTSTR lpszName,  
    const COleVariant& varValue);

 
virtual void SetParamValue(
    int nIndex,  
    const COleVariant& varValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 値を設定するパラメーターの名前。  
  
 `varValue`  
 に設定する値「解説」を参照してください。  
  
 `nIndex`  
 クエリ定義のパラメーター コレクション内のパラメーターの序数位置。 呼び出しでこの値を取得する[GetParameterCount](#getparametercount)と[GetParameterInfo](#getparameterinfo)です。  
  
### <a name="remarks"></a>コメント  
 パラメーター既に、クエリ定義の SQL 文字列の一部として設定されていなければなりません。 名前またはコレクション内の序数位置のいずれかのパラメーターを表示できます。  
  
 として設定する値を指定して、`COleVariant`オブジェクト。 目的の値と型に設定については、`COleVariant`オブジェクト、クラスを参照して[COleVariant](../../mfc/reference/colevariant-class.md)です。  
  
##  <a name="setreturnsrecords"></a>  CDaoQueryDef::SetReturnsRecords  
 外部データベースに SQL パススルー クエリの設定のプロセスの一環として、このメンバー関数を呼び出します。  
  
```  
void SetReturnsRecords(BOOL bReturnsRecords);
```  
  
### <a name="parameters"></a>パラメーター  
 *bReturnsRecords*  
 渡す**TRUE**外部データベースにクエリがレコードを返す場合は、それ以外の場合、 **FALSE**です。  
  
### <a name="remarks"></a>コメント  
 このような場合は、クエリ定義を作成し、使用して他のプロパティを設定する必要があります、`CDaoQueryDef`メンバー関数。 外部データベースの説明は、次を参照してください。 [SetConnect](#setconnect)です。  
  
##  <a name="setsql"></a>  CDaoQueryDef::SetSQL  
 クエリ定義を実行する SQL ステートメントを設定するには、このメンバー関数を呼び出します。  
  
```  
void SetSQL(LPCTSTR lpszSQL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszSQL`  
 実行に適した完全な SQL ステートメントを含む文字列。 この文字列の構文は、DBMS に依存する、クエリのターゲットです。 Microsoft Jet データベース エンジンで使用される構文の詳細については、「ビルド SQL ステートメントでコード」DAO ヘルプのトピックを参照してください。  
  
### <a name="remarks"></a>コメント  
 一般的な使用`SetSQL`パススルーの SQL クエリで使用するためのクエリ定義オブジェクトを設定します。 (対象となる DBMS 上の SQL パススルー クエリの構文、DBMS のマニュアルを参照してください)。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)   
 [どちらのクラス](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoException クラス](../../mfc/reference/cdaoexception-class.md)
