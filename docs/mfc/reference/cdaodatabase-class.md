---
title: CDaoDatabase クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoDatabase
- AFXDAO/CDaoDatabase
- AFXDAO/CDaoDatabase::CDaoDatabase
- AFXDAO/CDaoDatabase::CanTransact
- AFXDAO/CDaoDatabase::CanUpdate
- AFXDAO/CDaoDatabase::Close
- AFXDAO/CDaoDatabase::Create
- AFXDAO/CDaoDatabase::CreateRelation
- AFXDAO/CDaoDatabase::DeleteQueryDef
- AFXDAO/CDaoDatabase::DeleteRelation
- AFXDAO/CDaoDatabase::DeleteTableDef
- AFXDAO/CDaoDatabase::Execute
- AFXDAO/CDaoDatabase::GetConnect
- AFXDAO/CDaoDatabase::GetName
- AFXDAO/CDaoDatabase::GetQueryDefCount
- AFXDAO/CDaoDatabase::GetQueryDefInfo
- AFXDAO/CDaoDatabase::GetQueryTimeout
- AFXDAO/CDaoDatabase::GetRecordsAffected
- AFXDAO/CDaoDatabase::GetRelationCount
- AFXDAO/CDaoDatabase::GetRelationInfo
- AFXDAO/CDaoDatabase::GetTableDefCount
- AFXDAO/CDaoDatabase::GetTableDefInfo
- AFXDAO/CDaoDatabase::GetVersion
- AFXDAO/CDaoDatabase::IsOpen
- AFXDAO/CDaoDatabase::Open
- AFXDAO/CDaoDatabase::SetQueryTimeout
- AFXDAO/CDaoDatabase::m_pDAODatabase
- AFXDAO/CDaoDatabase::m_pWorkspace
dev_langs:
- C++
helpviewer_keywords:
- CDaoDatabase [MFC], CDaoDatabase
- CDaoDatabase [MFC], CanTransact
- CDaoDatabase [MFC], CanUpdate
- CDaoDatabase [MFC], Close
- CDaoDatabase [MFC], Create
- CDaoDatabase [MFC], CreateRelation
- CDaoDatabase [MFC], DeleteQueryDef
- CDaoDatabase [MFC], DeleteRelation
- CDaoDatabase [MFC], DeleteTableDef
- CDaoDatabase [MFC], Execute
- CDaoDatabase [MFC], GetConnect
- CDaoDatabase [MFC], GetName
- CDaoDatabase [MFC], GetQueryDefCount
- CDaoDatabase [MFC], GetQueryDefInfo
- CDaoDatabase [MFC], GetQueryTimeout
- CDaoDatabase [MFC], GetRecordsAffected
- CDaoDatabase [MFC], GetRelationCount
- CDaoDatabase [MFC], GetRelationInfo
- CDaoDatabase [MFC], GetTableDefCount
- CDaoDatabase [MFC], GetTableDefInfo
- CDaoDatabase [MFC], GetVersion
- CDaoDatabase [MFC], IsOpen
- CDaoDatabase [MFC], Open
- CDaoDatabase [MFC], SetQueryTimeout
- CDaoDatabase [MFC], m_pDAODatabase
- CDaoDatabase [MFC], m_pWorkspace
ms.assetid: 8ff5b342-964d-449d-bef1-d0ff56aadf6d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6cf84b2e5709a4ac31965501005b5260499a3213
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408805"
---
# <a name="cdaodatabase-class"></a>CDaoDatabase クラス

それを通じてデータを操作することのできるデータベースへの接続を表します。

## <a name="syntax"></a>構文

```
class CDaoDatabase : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CDaoDatabase::CDaoDatabase](#cdaodatabase)|`CDaoDatabase` オブジェクトを構築します。 呼び出す`Open`にオブジェクトをデータベースに接続します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDaoDatabase::CanTransact](#cantransact)|データベースがトランザクションをサポートしている場合、0 以外の値を返します。|
|[CDaoDatabase::CanUpdate](#canupdate)|場合は 0 以外の値を返します、`CDaoDatabase`オブジェクトが更新可能な (いない読み取り専用)。|
|[CDaoDatabase::Close](#close)|データベース接続を閉じます。|
|[CDaoDatabase::Create](#create)|基になる DAO データベース オブジェクトを作成し、初期化、`CDaoDatabase`オブジェクト。|
|[CDaoDatabase::CreateRelation](#createrelation)|データベースのテーブル間の新しいリレーションシップを定義します。|
|[CDaoDatabase::DeleteQueryDef](#deletequerydef)|データベースのクエリ定義のコレクションに保存されているクエリ定義オブジェクトを削除します。|
|[CDaoDatabase::DeleteRelation](#deleterelation)|データベースのテーブル間の既存のリレーションシップを削除します。|
|[CDaoDatabase::DeleteTableDef](#deletetabledef)|データベースのテーブルの定義を削除します。 これには、実際のテーブルとそのすべてのデータが削除されます。|
|[CDaoDatabase::Execute](#execute)|アクションのクエリを実行します。 呼び出す`Execute`の結果を返すクエリが例外をスローします。|
|[CDaoDatabase::GetConnect](#getconnect)|接続に使用される接続文字列を返す、`CDaoDatabase`データベースへのオブジェクト。 ODBC を使用します。|
|[CDaoDatabase::GetName](#getname)|現在使用中のデータベースの名前を返します。|
|[CDaoDatabase::GetQueryDefCount](#getquerydefcount)|データベースに対して定義されたクエリの数を返します。|
|[CDaoDatabase::GetQueryDefInfo](#getquerydefinfo)|データベースで定義されている指定されたクエリに関する情報を返します。|
|[CDaoDatabase::GetQueryTimeout](#getquerytimeout)|クエリ操作の後、データベースの秒数を返しますがタイムアウトになります。後続のすべての影響を開く、新規追加、更新、および (のみ) などの操作と ODBC データ ソースの他の操作は編集`Execute`呼び出し。|
|[CDaoDatabase::GetRecordsAffected](#getrecordsaffected)|最後の更新によって影響を受けるレコードの数を返します。 は、編集、または、操作を追加またはへの呼び出しによって`Execute`します。|
|[CDaoDatabase::GetRelationCount](#getrelationcount)|データベース内のテーブル間で定義されている関係の数を返します。|
|[CDaoDatabase::GetRelationInfo](#getrelationinfo)|データベース内のテーブル間で定義されているリレーションシップに関する情報を返します。|
|[CDaoDatabase::GetTableDefCount](#gettabledefcount)|データベースで定義されているテーブルの数を返します。|
|[Cdaodatabase::gettabledefinfo](#gettabledefinfo)|データベースでは、指定されたテーブルに関する情報を返します。|
|[CDaoDatabase::GetVersion](#getversion)|データベースに関連付けられているデータベース エンジンのバージョンを返します。|
|[CDaoDatabase::IsOpen](#isopen)|場合は 0 以外の値を返します、`CDaoDatabase`オブジェクトが現在のデータベースに接続されています。|
|[CDaoDatabase::Open](#open)|データベースへの接続を確立します。|
|[CDaoDatabase::SetQueryTimeout](#setquerytimeout)|データベース秒数 (ODBC データ ソースに対する操作のみ) のクエリ セットがタイムアウトになります。開く新規追加、更新、および削除操作に後続のすべての影響を与えます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CDaoDatabase::m_pDAODatabase](#m_pdaodatabase)|基になる DAO データベース オブジェクトへのポインター。|
|[CDaoDatabase::m_pWorkspace](#m_pworkspace)|ポインター、 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)オブジェクトをデータベースを含み、そのトランザクション領域を定義します。|

## <a name="remarks"></a>Remarks

サポートされているデータベースの形式については、次を参照してください。、 [GetName](../../mfc/reference/cdaoworkspace-class.md#getname)メンバー関数。 1 つまたは複数を持てる`CDaoDatabase`特定の"ワークスペースで、"で表されるオブジェクトを一度にアクティブ、 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)オブジェクト。 ワークスペースは、データベース コレクションと呼ばれる、開いているデータベース オブジェクトのコレクションを保持します。

> [!NOTE]
>  MFC DAO データベース クラスは、ODBC に基づいて MFC データベース クラスとは異なります。 DAO データベース クラスの名前には、"CDao"プレフィックスが付いています。 クラス`CDaoDatabase`の ODBC クラスに似たインターフェイスを提供[CDatabase](../../mfc/reference/cdatabase-class.md)します。 主な違いは`CDatabase`DBMS の Open Database Connectivity (ODBC) と ODBC ドライバーを介して、DBMS にアクセスします。 `CDaoDatabase` Microsoft Jet データベース エンジンに基づくデータ アクセス オブジェクト (DAO) を介してデータにアクセスします。 一般に、DAO に基づいて MFC クラスは ODBC; に基づいて MFC クラスよりもより高機能ですDAO ベースのクラスは、独自のデータベース エンジンを使用して、ODBC ドライバーを含む、データにアクセスできます。 DAO ベースのクラスには、DAO を直接呼び出すことがなく、クラスを使用してテーブルの追加などのデータ定義言語 (DDL) 操作もサポートします。

## <a name="usage"></a>使用法

レコード セット オブジェクトを作成するときに、暗黙的に、データベース オブジェクトを作成できます。 データベース オブジェクトを明示的に作成することもできます。 明示的に既存のデータベースを使用する`CDaoDatabase`次のいずれかを実行します。

- 構築、 `CDaoDatabase` 、オープンにポインターを渡して、オブジェクト[CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)オブジェクト。

- 作成したり、 `CDaoDatabase` (MFC では、一時ワークスペース オブジェクトを作成します)、ワークスペースを指定せずにオブジェクト。

新しい Microsoft Jet を作成する (します。MDB) データベースの場合は、構築、`CDaoDatabase`オブジェクトと呼び出しの[作成](#create)メンバー関数。 *いない*呼び出す`Open`後`Create`します。

既存のデータベースを開くには、構築、`CDaoDatabase`オブジェクトと呼び出しの[を開く](#open)メンバー関数。

これらの手法のいずれかにより、DAO のデータベース オブジェクトをワークスペースのデータベース コレクションに追加し、データへの接続を開きます。 構築する際に[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)、 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)、または[CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)接続されたデータベースに対する操作のためのオブジェクトは、これらのオブジェクトのコンス トラクターを渡す、ポインター、`CDaoDatabase`オブジェクト。 接続を使用してが完了したら、呼び出し、[閉じる](#close)メンバー関数し、破棄、`CDaoDatabase`オブジェクト。 `Close` 閉じられていないすべてのレコード セットを閉じます。

## <a name="transactions"></a>トランザクション

データベース トランザクションの処理がワークスペース レベルで提供されているを参照してください、 [BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans)、 [CommitTrans](../../mfc/reference/cdaoworkspace-class.md#committrans)と[ロールバック](../../mfc/reference/cdaoworkspace-class.md#rollback)クラスのメンバー関数`CDaoWorkspace`.

## <a name="odbc-connections"></a>ODBC 接続

ODBC データ ソースを操作することをお勧めの方法は、Microsoft Jet に外部テーブルをアタッチする (します。MDB) データベース。

## <a name="collections"></a>コレクション

各データベースは、テーブル定義、クエリ定義、レコード セット、およびリレーションシップ オブジェクトの独自のコレクションを保持します。 クラス`CDaoDatabase`これらのオブジェクトを操作するためのメンバー関数を提供します。

> [!NOTE]
>  オブジェクトは、MFC のデータベース オブジェクトではなく、DAO に格納されます。 MFC では、テーブル定義、クエリ定義、およびレコード セット オブジェクトのリレーションシップ オブジェクトではなくクラスを提供します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CDaoDatabase`

## <a name="requirements"></a>要件

**ヘッダー:** afxdao.h

##  <a name="cantransact"></a>  CDaoDatabase::CanTransact

データベースがトランザクションをできるかどうかを判断するには、このメンバー関数を呼び出します。

```
BOOL CanTransact();
```

### <a name="return-value"></a>戻り値

データベースがトランザクションをサポートしている場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

トランザクションは、データベースのワークスペースで管理されます。

##  <a name="canupdate"></a>  CDaoDatabase::CanUpdate

確認するには、このメンバー関数を呼び出すかどうか、`CDaoDatabase`オブジェクトを更新します。

```
BOOL CanUpdate();
```

### <a name="return-value"></a>戻り値

0 以外の値、`CDaoDatabase`更新プログラムを許可するオブジェクト。 それ以外の場合は 0、いずれかがあるかを示すで渡されます TRUE *bReadOnly*開いたときに、`CDaoDatabase`オブジェクトまたはデータベース自体には読み取り専用です。 参照してください、[オープン](#open)メンバー関数。

### <a name="remarks"></a>Remarks

データベース更新の詳細については、「更新可能なプロパティ」DAO ヘルプのトピックを参照してください。

##  <a name="cdaodatabase"></a>  CDaoDatabase::CDaoDatabase

`CDaoDatabase` オブジェクトを構築します。

```
CDaoDatabase(CDaoWorkspace* pWorkspace = NULL);
```

### <a name="parameters"></a>パラメーター

*pWorkspace*<br/>
ポインター、`CDaoWorkspace`新しいデータベース オブジェクトを格納するオブジェクト。 既定値は NULL に同意する場合、コンス トラクターに一時テーブルが作成`CDaoWorkspace`DAO の既定のワークスペースを使用するオブジェクト。 使用してワークスペース オブジェクトへのポインターを取得することができます、 [m_pWorkspace](#m_pworkspace)データ メンバー。

### <a name="remarks"></a>Remarks

新しい Microsoft Jet を作成する場合、オブジェクトを構築した後 (します。MDB) データベース、オブジェクトの[作成](#create)メンバー関数。 オブジェクトを呼び出し、既存のデータベースを開く場合は、代わりに、[オープン](#open)メンバー関数。

呼び出す必要があります、オブジェクトが完了したら、ときにその[閉じる](#close)メンバー関数を破棄し、`CDaoDatabase`オブジェクト。

埋め込むできると便利な場合があります、`CDaoDatabase`ドキュメント クラス内のオブジェクト。

> [!NOTE]
>  A`CDaoDatabase`を開いた場合、オブジェクトは暗黙的に作成されることも、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)を既存のポインターを渡さずにオブジェクト`CDaoDatabase`オブジェクト。 レコード セット オブジェクトを閉じるときに、このデータベース オブジェクトが閉じられます。

##  <a name="close"></a>  CDaoDatabase::Close

データベースから切断し、開いているレコード セット、テーブル定義、およびデータベースに関連付けられているクエリを閉じるには、このメンバー関数を呼び出します。

```
virtual void Close();
```

### <a name="remarks"></a>Remarks

このメンバー関数を呼び出す前にこれらのオブジェクトを手動で閉じることをお勧めします。 閉じる、`CDaoDatabase`オブジェクトが関連付けられているデータベース コレクションから削除[ワークスペース](../../mfc/reference/cdaoworkspace-class.md)します。 `Close`を破棄しません、`CDaoDatabase`オブジェクト、同じデータベースまたは別のデータベースを開くことによって、オブジェクトを再利用できます。

> [!CAUTION]
>  呼び出す、 [Update](../../mfc/reference/cdaorecordset-class.md#update)メンバー関数 (保留中の編集がある場合)、`Close`データベースを閉じる前に開いているレコード セット オブジェクトのすべてのメンバー関数。 宣言する関数を終了する場合[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)または`CDaoDatabase`スタックで、オブジェクトをデータベースが閉じ、未保存の変更は失われます、保留中のトランザクションはすべてロールバック、およびデータへの保留中の編集に失われます。

> [!CAUTION]
>  データベース オブジェクトを閉じるとすべてのレコード セット オブジェクトが、開いている間にしようとすると、またはその特定のワークスペースに属しているすべてのデータベース オブジェクトが開いている間、workspace オブジェクトを閉じるしようとする場合は、これらのレコード セット オブジェクトが終了し、保留中の更新または編集になりますロールバックされます。 それに属するすべてのデータベース オブジェクトが開いている間、workspace オブジェクトを終了しようとすると、この操作は閉じられていないレコード セット オブジェクトが閉じられている可能性があります、その特定のワークスペース オブジェクトに属するすべてのデータベース オブジェクトを閉じます。 データベース オブジェクトを終了していない場合、MFC は、デバッグ ビルドでは、アサーション エラーを報告します。

データベース オブジェクトが、関数のスコープ外に定義されている終了せず、関数を終了する場合は、データベース オブジェクトに明示的に閉じられるまで開いたままになります。 またはが定義されているモジュールは対象外です。

##  <a name="create"></a>  CDaoDatabase::Create

新しい Microsoft Jet を作成する (します。MDB) データベースを構築した後、このメンバー関数を呼び出し、`CDaoDatabase`オブジェクト。

```
virtual void Create(
    LPCTSTR lpszName,
    LPCTSTR lpszLocale = dbLangGeneral,
    int dwOptions = 0);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
作成するデータベース ファイルの名前を指定する文字列式。 できます、完全なパスとファイル名など、"c:\\\MYDB します。MDB"。 名前を指定する必要があります。 場合は、ファイル名拡張子を指定しません。MDB が追加されます。 場合は、ネットワークでは、統一された名前付け規則 (UNC) をサポートすることもできます、ネットワーク パスなど"\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB"。 Microsoft Jet のみ (します。MDB) データベース ファイルは、このメンバー関数を使用して作成できます。 (二重の円記号が文字列リテラルで必要なため、"\\"は C++ のエスケープ文字)。

*lpszLocale*<br/>
データベースを作成するための照合順序を指定するために使用する文字列式。 既定値は `dbLangGeneral` です。 指定できる値は次のとおりです。

- `dbLangGeneral` 英語、ドイツ語、フランス語、ポルトガル語、イタリア語、および最新のスペイン語

- `dbLangArabic` アラビア語

- `dbLangCyrillic` ロシア語

- `dbLangCzech` チェコ語

- `dbLangDutch` オランダ語

- `dbLangGreek` ギリシャ語

- `dbLangHebrew` ヘブライ語

- `dbLangHungarian` ハンガリー語

- `dbLangIcelandic` アイスランド語

- `dbLangNordic` スカンジナビア語 (Microsoft Jet データベース エンジンのバージョン 1.0 のみ)

- `dbLangNorwdan` ノルウェー語、デンマーク語

- `dbLangPolish` ポーランド語

- `dbLangSpanish` 従来のスペイン語

- `dbLangSwedfin` スウェーデン語、フィンランド語

- `dbLangTurkish` トルコ語

*dwOptions*<br/>
1 つまたは複数のオプションを示す整数。 指定できる値は次のとおりです。

- `dbEncrypt` 暗号化されたデータベースを作成します。

- `dbVersion10` Microsoft Jet データベースのバージョン 1.0 とデータベースを作成します。

- `dbVersion11` Microsoft Jet データベースのバージョン 1.1 とデータベースを作成します。

- `dbVersion20` Microsoft Jet データベース バージョン 2.0 では、データベースを作成します。

- `dbVersion30` Microsoft Jet データベースのバージョン 3.0 とデータベースを作成します。

暗号化の定数を省略した場合、暗号化されていないデータベースが作成されます。 1 つだけのバージョンの定数を指定できます。 バージョンの定数を省略した場合は、Microsoft Jet データベースのバージョン 3.0 を使用するデータベースが作成されます。

> [!CAUTION]
>  データベースが暗号化されていないデータベースを構成するバイナリのディスク ファイルを直接読み取るのユーザー/パスワード セキュリティを実装する場合でもことができます。

### <a name="remarks"></a>Remarks

`Create` データベース ファイルと基になる DAO データベース オブジェクトを作成し、C++ オブジェクトを初期化します。 オブジェクトが関連付けられているワークスペースのデータベース コレクションに追加されます。 データベース オブジェクトは、開いている状態です。呼び出さない`Open*`後`Create`します。

> [!NOTE]
>  `Create`、Microsoft Jet のみを作成することができます (します。MDB) データベース。 ISAM データベースまたは ODBC データベースを作成することはできません。

##  <a name="createrelation"></a>  CDaoDatabase::CreateRelation

プライマリ データベースのテーブルに 1 つまたは複数のフィールドと外部テーブル (データベース内の別のテーブル) 内の 1 つまたは複数のフィールド間の関係を確立するには、このメンバー関数を呼び出します。

```
void CreateRelation(
    LPCTSTR lpszName,
    LPCTSTR lpszTable,
    LPCTSTR lpszForeignTable,
    long lAttributes,
    LPCTSTR lpszField,
    LPCTSTR lpszForeignField);

void CreateRelation(CDaoRelationInfo& relinfo);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
リレーションシップ オブジェクトの一意の名前。 名前は文字で始める必要があり、最大 40 文字を含めることができます。 数字を含めることができ、アンダー スコア文字しますが、区切り記号やスペースを含めることはできません。

*lpszTable*<br/>
リレーションシップの主テーブルの名前。 テーブルが存在しない場合、MFC は、型の例外をスローします[CDaoException](../../mfc/reference/cdaoexception-class.md)します。

*lpszForeignTable*<br/>
リレーションシップで外部テーブルの名前。 テーブルが存在しない場合、MFC は、型の例外をスローします`CDaoException`します。

*lAttributes*<br/>
リレーションシップの種類に関する情報を含む long 値。 この値を使用すると、特に、参照整合性を適用します。 ビットごとの OR 演算子を使用することができます ( **&#124;**) である限り、組み合わせの意味)、次の値のいずれかを結合します。

- `dbRelationUnique` リレーションシップは一対一です。

- `dbRelationDontEnforce` リレーションシップがない (参照整合性がありません) が適用されます。

- `dbRelationInherited` アタッチされた 2 つのテーブルを含む固定データベース内にリレーションシップが存在します。

- `dbRelationUpdateCascade` 更新プログラムが伝播する (詳細連鎖は、「解説」を参照してください)。

- `dbRelationDeleteCascade` 削除が重ねて表示します。

*lpszField*<br/>
主テーブル内のフィールドの名前を含む null で終わる文字列へのポインター (付けた*lpszTable*)。

*lpszForeignField*<br/>
外部テーブル内のフィールドの名前を含む null で終わる文字列へのポインター (付けた*lpszForeignTable*)。

*relinfo*<br/>
参照を[CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)を作成する関係に関する情報を含むオブジェクト。

### <a name="remarks"></a>Remarks

リレーションシップには、クエリ、またはアタッチを外部データベースからテーブルを含めることはできません。

リレーションシップには 2 つのテーブルの 1 つのフィールドが含まれている場合は、関数の最初のバージョンを使用します。 リレーションシップに複数のフィールドが含まれている場合は、2 番目のバージョンを使用します。 リレーションシップ内のフィールドの最大数には 14 です。

この操作には、基になる DAO 関係オブジェクトが作成されますが、クラス内でリレーションシップ オブジェクトの MFC のカプセル化が含まれているので、MFC 実装の詳細は`CDaoDatabase`します。 MFC では、関係クラスを提供していません。

連鎖操作をアクティブ化するオブジェクトの属性リレーションシップを設定すると、データベース エンジンは自動的に更新または関連する主キー テーブルに変更されたときに、他の 1 つまたは複数のテーブル内のレコードを削除します。

たとえば、Customers テーブルと Orders テーブルの間で連鎖削除のリレーションシップを確立するとします。 Customers テーブルからレコードを削除するときにその顧客に関連する Orders テーブル内のレコードも削除されます。 さらに、他のテーブルと Orders テーブルの間で連鎖削除のリレーションシップを確立する場合、それらのテーブルからレコードの Customers テーブルからレコードを削除すると削除に自動的にされます。

関連情報については、DAO のヘルプで「CreateRelation メソッド」を参照してください。

##  <a name="deletequerydef"></a>  CDaoDatabase::DeleteQueryDef

指定したクエリ定義を削除するには、このメンバー関数を呼び出す: 保存したクエリ: から、`CDaoDatabase`オブジェクトのクエリ定義のコレクション。

```
void DeleteQueryDef(LPCTSTR lpszName);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
削除する保存されたクエリの名前。

### <a name="remarks"></a>Remarks

その後、そのクエリでは、データベースで定義されます不要になった。

クエリ定義のオブジェクトを作成する方法の詳細については、クラスを参照してください。 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)します。 クエリ定義のオブジェクトに関連付けられると、特定`CDaoDatabase`オブジェクトを構築するとき、`CDaoQueryDef`オブジェクト、データベース オブジェクトへのポインターを渡します。

##  <a name="deleterelation"></a>  CDaoDatabase::DeleteRelation

データベース オブジェクトの関係のコレクションから既存のリレーションシップを削除するには、このメンバー関数を呼び出します。

```
void DeleteRelation(LPCTSTR lpszName);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
削除するリレーションシップの名前。

### <a name="remarks"></a>Remarks

その後、不要になったリレーションが存在します。

関連情報については、DAO のヘルプで「メソッドの削除」を参照してください。

##  <a name="deletetabledef"></a>  CDaoDatabase::DeleteTableDef

指定したテーブルとのデータをすべて削除するには、このメンバー関数を呼び出し、`CDaoDatabase`オブジェクトのテーブル定義のコレクション。

```
void DeleteTableDef(LPCTSTR lpszName);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
削除するテーブル定義の名前。

### <a name="remarks"></a>Remarks

その後、そのテーブルは不要になった、データベースで定義します。

> [!NOTE]
>  非常にしないように注意するシステム テーブルを削除します。

テーブル定義のオブジェクトを作成する方法の詳細については、クラスを参照してください。 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)します。 テーブル定義のオブジェクトに関連付けられると、特定`CDaoDatabase`オブジェクトを構築するとき、`CDaoTableDef`オブジェクト、データベース オブジェクトへのポインターを渡します。

関連情報については、DAO のヘルプで「メソッドの削除」を参照してください。

##  <a name="execute"></a>  CDaoDatabase::Execute

アクションのクエリを実行またはデータベースで SQL ステートメントを実行するには、このメンバー関数を呼び出します。

```
void Execute(
    LPCTSTR lpszSQL,
    int nOptions = dbFailOnError);
```

### <a name="parameters"></a>パラメーター

*lpszSQL*<br/>
実行する有効な SQL コマンドを含む null で終わる文字列へのポインター。

*nOptions*<br/>
クエリの整合性に関連するオプションを指定する整数。 ビットごとの OR 演算子を使用することができます ( **&#124;**) 定数は、次のいずれかを結合する (意味が指定 — たとえば、組み合わせることができません`dbInconsistent`で`dbConsistent`)。

- `dbDenyWrite` 他のユーザーに書き込みアクセス許可を拒否します。

- `dbInconsistent` (既定値)更新プログラムの一貫性がありません。

- `dbConsistent` 一貫性のある更新します。

- `dbSQLPassThrough` SQL パススルーします。 処理のための ODBC データ ソースに渡される SQL ステートメントをによりします。

- `dbFailOnError` ロールバックは、エラーが発生した場合に更新します。

- `dbSeeChanges` 別のユーザーが編集してデータを変更する場合は、実行時エラーを生成します。

> [!NOTE]
>  両方`dbInconsistent`と`dbConsistent`が含まれていますか、結果が、既定でどちらが含まれる場合。 これらの定数の詳細については、DAO のヘルプで「メソッドの実行」を参照してください。

### <a name="remarks"></a>Remarks

`Execute` アクションのクエリ、または結果を返さない SQL パススルー クエリに対してのみ機能します。 レコードを返す select クエリの場合は機能しません。

定義とアクションのクエリについては、「アクションのクエリ」および DAO ヘルプの「メソッドの実行」トピックを参照してください。

> [!TIP]
>  正しい構文の SQL ステートメントと、適切なアクセス許可を与え、`Execute`メンバー関数はでも失敗しませんいない場合、1 つの行を変更または削除できます。 そのため、常に使用して、`dbFailOnError`オプションを使用する場合、`Execute`更新プログラムを実行またはクエリを削除するメンバー関数。 このオプションは、型の例外をスローする MFC [CDaoException](../../mfc/reference/cdaoexception-class.md)し場合、影響を受けたレコードのいずれかがロックされているとできませんを更新または削除に成功したすべての変更をロールバックします。 いつでも呼び出すことに注意してください`GetRecordsAffected`に影響を受けたレコードの数を参照してください。

呼び出す、 [GetRecordsAffected](#getrecordsaffected)最新によって影響を受けたレコードの数を決定するデータベース オブジェクトのメンバー関数`Execute`呼び出します。 たとえば、`GetRecordsAffected`削除、更新、またはアクションのクエリを実行するときに挿入されるレコードの数に関する情報を返します。 返されるカウントが cascade を更新または削除時に、関連テーブルの変更が有効では反映されません。

`Execute` レコード セットは返されません。 使用して`Execute`レコードを選択するクエリに MFC の種類の例外をスローすると、`CDaoException`します。 (があるない`ExecuteSQL`メンバー関数に似ています`CDatabase::ExecuteSQL`)。

##  <a name="getconnect"></a>  CDaoDatabase::GetConnect

接続に使用される接続文字列を取得するには、このメンバー関数を呼び出す、 `CDaoDatabase` ODBC または ISAM データベースへのオブジェクト。

```
CString GetConnect();
```

### <a name="return-value"></a>戻り値

接続文字列の場合は[オープン](#open)ODBC データ ソースで正常に呼び出される。 それ以外の場合、空の文字列。 For Microsoft Jet (します。MDB) データベースの場合は、文字列は常に空で使用するために設定していない場合、`dbSQLPassThrough`オプション併用、 [Execute](#execute)メンバー関数、またはレコード セットを開くときに使用します。

### <a name="remarks"></a>Remarks

文字列は、開いているデータベースまたはパススルー クエリで使用されるデータベースのソースに関する情報を提供します。 接続文字列は、データベースの型指定子は、セミコロンで区切られた 0 個以上のパラメーターで構成されます。

> [!NOTE]
>  MFC DAO クラスを使用して ODBC 経由でデータ ソースに接続することは、接続されているテーブルを使用して接続するより非効率です。

> [!NOTE]
>  接続文字列は、ODBC および必要に応じて、特定の ISAM ドライバーに追加情報を渡す使用されます。 を使用されません。MDB データベース。 Microsoft Jet データベースのベース テーブルでは、接続文字列は空の文字列 ("") 使用する場合を除き、SQL パススルー クエリの戻り値を上記で説明されているとします。

参照してください、[オープン](#open)接続文字列を作成する方法の説明については、メンバー関数。 接続文字列が設定されていると、`Open`呼び出し、後で使用できますの種類、パス、データベースのユーザー ID、パスワード、または ODBC データ ソースを決定する設定を確認します。

##  <a name="getname"></a>  CDaoDatabase::GetName

これは既存のデータベース ファイルの名前、現在開いているデータベースの名前または登録済みの ODBC データ ソースの名前を取得するには、このメンバー関数を呼び出します。

```
CString GetName();
```

### <a name="return-value"></a>戻り値

成功した場合は、データベースのファイル名と完全なパスそれ以外の場合、空[CString](../../atl-mfc-shared/reference/cstringt-class.md)します。

### <a name="remarks"></a>Remarks

ネットワーク パスを指定できますも、ネットワークでは、統一された名前付け規則 (UNC) をサポートする場合、たとえば、"\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB します。MDB"。 (二重の円記号が文字列リテラルで必要なため、"\\"は C++ のエスケープ文字)。

たとえば、見出しにこの名前を表示することができます。 名前の取得中にエラーが発生した場合、MFC は、型の例外をスローします[CDaoException](../../mfc/reference/cdaoexception-class.md)します。

> [!NOTE]
>  パフォーマンスを向上させる外部データベースにアクセスするときにお勧めします外部データベース テーブルは、Microsoft Jet データベースに接続する (します。MDB) データ ソースに直接接続するのではなく。

データベースの種類はファイルまたはディレクトリに、次のように、パスがポイントするによって示されます。

|ポインターをパス名.|データベースの種類|
|--------------------------|-------------------|
|.MDB ファイル|Microsoft Jet データベース (Microsoft Access)|
|格納するディレクトリ。DBF ファイル|dBASE データベース|
|格納するディレクトリ。XLS ファイル|Microsoft Excel データベース|
|格納するディレクトリ。PDX ファイル|Paradox データベース|
|データベース ファイルを適切に書式設定されたテキストを含むディレクトリ|テキスト形式のデータベース|

ODBC データベース SQL Server や Oracle などの場合は、データベースの接続文字列は、ODBC によって登録されているデータ ソース名 (DSN) を識別します。

##  <a name="getquerydefcount"></a>  CDaoDatabase::GetQueryDefCount

データベースのクエリ定義のコレクションで定義されているクエリの数を取得するには、このメンバー関数を呼び出します。

```
short GetQueryDefCount();
```

### <a name="return-value"></a>戻り値

データベースで定義されているクエリの数。

### <a name="remarks"></a>Remarks

`GetQueryDefCount` QueryDefs コレクション内のすべてのクエリ定義をループ処理する必要がある場合に便利です。 コレクション内の指定されたクエリに関する情報を取得するには、次を参照してください。 [GetQueryDefInfo](#getquerydefinfo)します。

##  <a name="getquerydefinfo"></a>  CDaoDatabase::GetQueryDefInfo

さまざまな種類のデータベースで定義されたクエリに関する情報を取得するには、このメンバー関数を呼び出します。

```
void GetQueryDefInfo(
    int nIndex,
    CDaoQueryDefInfo& querydefinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);


void GetQueryDefInfo(
    LPCTSTR lpszName,
    CDaoQueryDefInfo& querydefinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
インデックスで検索する場合、データベースのクエリ定義のコレクションで定義済みのクエリのインデックス。

*querydefinfo*<br/>
参照を[CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md)オブジェクトを要求された情報を返します。

*dwInfoOptions*<br/>
取得するレコード セットに関する情報を指定するオプション。 使用可能なオプションにに関する、レコード セットを返す関数がどのようなと共に示します。

- AFX_DAO_PRIMARY_INFO (既定値) の名前、型

- プライマリ AFX_DAO_SECONDARY_INFO 情報に加えて: 作成された日付、最終更新日付、レコードを返す、更新可能

- AFX_DAO_ALL_INFO プライマリとセカンダリの情報に加えて: SQL、Connect、補足

*lpszName*<br/>
名前で検索する場合、データベースで定義されているクエリの名前を含む文字列。

### <a name="remarks"></a>Remarks

データベースのクエリ定義のコレクション内のインデックスまたはクエリの名前のいずれかにクエリを選択できるように、関数の 2 つのバージョンが提供されます。

返される情報の説明については*querydefinfo*を参照してください、 [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報の項目に対応するは*dwInfoOptions*します。 1 つのレベルの情報を要求すると、その情報も同様のレベルを取得します。

##  <a name="getquerytimeout"></a>  CDaoDatabase::GetQueryTimeout

現在接続されているデータベースに対する後続の処理がタイムアウトするまで許可する秒数を取得するには、このメンバー関数を呼び出します。

```
short GetQueryTimeout();
```

### <a name="return-value"></a>戻り値

秒のタイムアウト値を持つ短整数。

### <a name="remarks"></a>Remarks

操作は、ネットワーク アクセスの問題や、過剰なクエリ処理時間のためタイムアウト可能性があります。 開いているすべてに影響を与える設定が有効になっているときに、新規追加、更新、およびこれに関連付けられているすべてのレコード セットでの delete 操作`CDaoDatabase`オブジェクト。 現在のタイムアウト設定を変更するには呼び出すことによって[SetQueryTimeout](#setquerytimeout)します。 開いた後、レコード セットのクエリ タイムアウト値を変更しても、レコード セットの値は変わりません。 たとえば、後続[移動](../../mfc/reference/cdaorecordset-class.md#move)操作では、新しい値を使用しないでください。 データベース エンジンが初期化されるときに、既定値が設定されます。

クエリ タイムアウトの既定値は、Windows レジストリから取得されます。 レジストリ設定がない場合は、既定値は 60 秒です。 すべてのデータベースでは、クエリのタイムアウト値を設定する機能をサポートします。 クエリのタイムアウト値は 0 を設定した場合のタイムアウトは行われません。データベースとの通信が応答を停止する可能性があります。 この動作は、開発時に役立ちます。 型の例外がスローされます、呼び出しが失敗した場合、 [CDaoException](../../mfc/reference/cdaoexception-class.md)します。

関連情報については、「QueryTimeout プロパティ」DAO ヘルプのトピックを参照してください。

##  <a name="getrecordsaffected"></a>  CDaoDatabase::GetRecordsAffected

最新の呼び出しによって影響を受けたレコードの数を決定するには、このメンバー関数を呼び出す、 [Execute](#execute)メンバー関数。

```
long GetRecordsAffected();
```

### <a name="return-value"></a>戻り値

影響を受けたレコードの数を表す長整数。

### <a name="remarks"></a>Remarks

返される値には、削除、更新、またはアクション クエリを実行で挿入されたレコードの数が含まれています。`Execute`します。 返されるカウントが cascade を更新または削除時に、関連テーブルの変更が有効では反映されません。

関連情報については、「RecordsAffected プロパティ」DAO ヘルプのトピックを参照してください。

##  <a name="getrelationcount"></a>  CDaoDatabase::GetRelationCount

データベース内のテーブル間で定義されている関係の数を取得するには、このメンバー関数を呼び出します。

```
short GetRelationCount();
```

### <a name="return-value"></a>戻り値

データベース内のテーブル間で定義されている関係の数。

### <a name="remarks"></a>Remarks

`GetRelationCount` データベースの関係のコレクションで定義されているすべての関係をループ処理する必要がある場合に便利です。 コレクション内の特定の関係に関する情報を取得するには、次を参照してください。 [GetRelationInfo](#getrelationinfo)します。

リレーションシップの概念を説明するために、Suppliers テーブルと一対多のリレーションシップがあります製品のテーブルを検討してください。 このリレーションシップでは、1 つの仕入先は 1 つ以上の製品を指定できます。 その他の関係は、一対一および多対多です。

##  <a name="getrelationinfo"></a>  CDaoDatabase::GetRelationInfo

データベースの関係のコレクションに指定されたリレーションシップに関する情報を取得するには、このメンバー関数を呼び出します。

```
void GetRelationInfo(
    int nIndex,
    CDaoRelationInfo& relinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);


void GetRelationInfo(
    LPCTSTR lpszName,
    CDaoRelationInfo& relinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
インデックスで検索する場合、データベースの関係コレクションでのリレーションシップ オブジェクトのインデックス。

*relinfo*<br/>
参照を[CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)オブジェクトを要求された情報を返します。

*dwInfoOptions*<br/>
取得する関係に関する情報を指定するオプションです。 使用可能なオプションにリレーションシップに関するを返す関数がどのようなと共に示します。

- AFX_DAO_PRIMARY_INFO (既定値) の名前、テーブル、外部テーブル

- AFX_DAO_SECONDARY_INFO 属性、フィールドの情報

フィールドの情報は、 [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md)リレーションシップに関連する主テーブルからフィールドを含むオブジェクト。

*lpszName*<br/>
名前で検索する場合、リレーションシップ オブジェクトの名前を含む文字列。

### <a name="remarks"></a>Remarks

この関数の 2 つのバージョンは、インデックスまたは名前のいずれかのアクセスを提供します。 返される情報の説明については*relinfo*を参照してください、 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報の項目に対応するは*dwInfoOptions*します。 1 つのレベルの情報を要求する場合も同様、以前のレベルで情報を取得します。

> [!NOTE]
>  リレーションシップの連鎖操作をアクティブ化するオブジェクトの属性を設定した場合 (`dbRelationUpdateCascades`または`dbRelationDeleteCascades`) に変更されたときに、複数の他のテーブルに関連する主キー、または Microsoft Jet データベース エンジンを自動的に更新または 1 つのレコードの削除テーブル。 たとえば、Customers テーブルと Orders テーブルの間で連鎖削除のリレーションシップを確立するとします。 Customers テーブルからレコードを削除するときにその顧客に関連する Orders テーブル内のレコードも削除されます。 さらに、他のテーブルと Orders テーブルの間で連鎖削除のリレーションシップを確立する場合、それらのテーブルからレコードの Customers テーブルからレコードを削除すると削除に自動的にされます。

##  <a name="gettabledefcount"></a>  CDaoDatabase::GetTableDefCount

データベースで定義されているテーブルの数を取得するには、このメンバー関数を呼び出します。

```
short GetTableDefCount();
```

### <a name="return-value"></a>戻り値

データベースで定義されているテーブルの定義の数。

### <a name="remarks"></a>Remarks

`GetTableDefCount` データベースのテーブル定義のコレクション内のすべてのテーブルをループ処理する必要がある場合に便利です。 コレクション内の特定のテーブルに関する情報を取得するには、次を参照してください。[プライマリ](#gettabledefinfo)します。

##  <a name="gettabledefinfo"></a>  Cdaodatabase::gettabledefinfo

さまざまな種類のデータベースで定義されているテーブルに関する情報を取得するには、このメンバー関数を呼び出します。

```
void GetTableDefInfo(
    int nIndex,
    CDaoTableDefInfo& tabledefinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);


void GetTableDefInfo(
    LPCTSTR lpszName,
    CDaoTableDefInfo& tabledefinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
インデックスで検索する場合、データベースのテーブル定義のコレクション内のテーブル定義オブジェクトのインデックス。

*tabledefinfo*<br/>
参照を[CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md)オブジェクトを要求された情報を返します。

*dwInfoOptions*<br/>
取得するテーブルに関する情報を指定するオプションです。 使用可能なオプションにリレーションシップに関するを返す関数がどのようなと共に示します。

- 更新可能な AFX_DAO_PRIMARY_INFO (既定値) の名前の属性します。

- プライマリ AFX_DAO_SECONDARY_INFO 情報に加えて: 作成された日付を最終更新日付、ソース テーブル名、接続

- AFX_DAO_ALL_INFO プライマリとセカンダリの情報に加えて: 検証規則、検証のテキスト レコードの数

*lpszName*<br/>
名前で検索する場合、テーブル定義オブジェクトの名前。

### <a name="remarks"></a>Remarks

関数の 2 つのバージョンは、テーブルを選択するには、データベースのテーブル定義のコレクション内のインデックスまたはテーブルの名前のいずれかのように提供されます。

返される情報の説明については*tabledefinfo*を参照してください、 [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報の項目に対応するは*dwInfoOptions*します。 1 つのレベルの情報を要求する場合は、そのレベルもの情報を取得します。

> [!NOTE]
>  AFX_DAO_ALL_INFO オプションは、取得に時間がかかる可能性のある情報を提供します。 この場合、カウント テーブルのレコードが非常に時間がかかる場合は、多くのレコードがある可能性があります。

##  <a name="getversion"></a>  CDaoDatabase::GetVersion

Microsoft Jet データベース ファイルのバージョンを確認するには、このメンバー関数を呼び出します。

```
CString GetVersion();
```

### <a name="return-value"></a>戻り値

A [CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトに関連付けられているデータベース ファイルのバージョンを示します。

### <a name="remarks"></a>Remarks

返される値は"major.minor"; という形式でバージョン番号を表しますたとえば、「3.0」です。 製品のバージョン番号 (たとえば、3.0) は、バージョン番号 (3)、ピリオド、およびリリース番号 (0) で構成されます。 バージョンは、1.0、1.1、2.0 および 3.0 です。

関連情報については、「バージョンのプロパティ」DAO ヘルプのトピックを参照してください。

##  <a name="isopen"></a>  CDaoDatabase::IsOpen

確認するには、このメンバー関数を呼び出すかどうか、`CDaoDatabase`オブジェクトが現在開いているデータベースでします。

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>戻り値

0 以外の値、`CDaoDatabase`オブジェクトが現在開いている場合は 0 それ以外の場合。

### <a name="remarks"></a>Remarks

##  <a name="m_pdaodatabase"></a>  CDaoDatabase::m_pDAODatabase

基に DAO データベース オブジェクトの OLE インターフェイスへのポインターが含まれています、`CDaoDatabase`オブジェクト。

### <a name="remarks"></a>Remarks

DAO インターフェイスに直接アクセスする必要がある場合は、このポインターを使用します。

DAO の呼び出し元に関する情報を参照してください、直接[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)します。

##  <a name="m_pworkspace"></a>  CDaoDatabase::m_pWorkspace

ポインターが含まれています、 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)データベース オブジェクトを格納しているオブジェクト。

### <a name="remarks"></a>Remarks

ワークスペースに直接アクセスする必要がある場合は、このポインターを使用して、たとえば、ワークスペースのデータベース コレクション内の他のデータベース オブジェクトへのポインターを取得します。

##  <a name="open"></a>  CDaoDatabase::Open

新しく構築された初期化するためにこのメンバー関数を呼び出す必要があります`CDaoDatabase`既存のデータベースを表すオブジェクト。

```
virtual void Open(
    LPCTSTR lpszName,
    BOOL bExclusive = FALSE,
    BOOL bReadOnly = FALSE,
    LPCTSTR lpszConnect = _T(""));
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
既存の Microsoft Jet の名前を指定する文字列式 (します。MDB) データベース ファイル。 ファイル名に拡張子がある場合が必要です。 場合は、ネットワークでは、統一された名前付け規則 (UNC) をサポートすることもできます、ネットワーク パスなど"\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB します。MDB"。 (二重の円記号が文字列リテラルで必要なため、"\\"は C++ のエスケープ文字)。

使用するときにいくつかの考慮事項が適用*lpszName*します。 場合に。

- 既に別のユーザーの種類の例外をスロー MFC によって排他的に開かれているデータベースを指す[CDaoException](../../mfc/reference/cdaoexception-class.md)します。 例外をトラップすることで、ユーザー、データベースが使用できないことを確認します。

- 空の文字列 ("") と*lpszConnect*は"ODBC;"、ユーザーがデータベースを選択できるように、登録されているすべての ODBC データ ソース名を一覧表示する ダイアログ ボックスが表示されます。 ODBC データ ソースへの直接接続を避ける必要があります。代わりに、接続されているテーブルを使用します。

- それ以外の場合、既存のデータベースまたは有効な ODBC データ ソース名、型の例外をスロー MFC を参照しない`CDaoException`します。

> [!NOTE]
>  詳細については、DAO のエラー コードは、DAOERR を参照してください。H ファイルです。 関連情報については、「トラップ可能なデータ アクセス エラー」DAO ヘルプのトピックを参照してください。

*bExclusive*<br/>
ブール値、データベースがデータベースの共有アクセス用に開かれる場合 (非共有) の排他アクセスと FALSE 用に開く場合は TRUE です。 この引数を省略すると、共有アクセス用にデータベースが開きます。

*bReadOnly*<br/>
ブール値、データベースが読み取り専用アクセスと FALSE の場合、データベースは読み取り/書き込みアクセス用に開かれる開く場合は TRUE です。 この引数を省略すると、データベースが読み取り/書き込みアクセスを開きます。 依存するすべてのレコード セットは、この属性を継承します。

*lpszConnect*<br/>
データベースを開くに使用する文字列式。 この文字列の構成、ODBC 接続の引数。 ソース文字列を指定して排他的読み取り専用の引数を指定する必要があります。 場合は、データベースは、Microsoft Jet データベース (します。MDB)、この文字列が空 ("")。 既定値の構文: **_T**(""): Unicode と ANSI の移植性は、アプリケーションのビルドを提供します。

### <a name="remarks"></a>Remarks

`Open` データベースを基になる DAO オブジェクトに関連付けます。 データベース オブジェクトを使用して初期化されるまでに、レコード セット、テーブル定義、またはクエリ定義のオブジェクトを構築することはできません。 `Open` 関連付けられているワークスペースのデータベース コレクションには、データベース オブジェクトを追加します。

ようパラメーターを使用します。

- Microsoft Jet を開いている場合 (します。MDB) データベースを使用して、 *lpszName*パラメーターを渡しますが、空の文字列の*lpszConnect*パラメーターまたはパスの形式のパスワード文字列";PWD = パスワード"データベースがパスワードで保護されている場合 (します。MDB データベースの場合のみ)。

- ODBC データ ソースを開く場合に有効な ODBC 接続文字列を渡す*lpszConnect*と空の文字列に*lpszName*します。

関連情報については、DAO のヘルプで「OpenDatabase メソッド」を参照してください。

> [!NOTE]
>  外部データベース、ISAM データベースなど、ODBC データ ソースにアクセスするときのパフォーマンス向上のためお勧め外部データベース テーブルは、Microsoft Jet エンジン データベースに接続する (します。MDB) データ ソースに直接接続するのではなく。

これは、方法は、たとえば、DBMS ホストが使用できない場合は、接続の試行がタイムアウトする可能性があります。 接続の試行が失敗した場合、`Open`型の例外をスローします[CDaoException](../../mfc/reference/cdaoexception-class.md)します。

残りの「解説」は、ODBC データベースのみに適用されます。

かどうか、データベースは、ODBC データベースとでは、パラメーター、`Open`呼び出しには、接続を作成するのに十分な情報が含まれていない、ODBC ドライバーは、ユーザーから必要な情報を取得するダイアログ ボックスを開きます。 呼び出すと`Open`、接続文字列、 *lpszConnect*は個別に格納され、呼び出すことによっては、 [GetConnect](#getconnect)メンバー関数。

呼び出す前に、独自のダイアログ ボックスを開く場合は、`Open`パスワードなど、ユーザーから情報を取得するに渡す接続文字列にし、その情報を追加`Open`します。 時間、アプリケーション呼び出しのため、再利用できますが、[次へ] (おそらく、Windows レジストリ) に渡す接続文字列を保存することも`Open`上、`CDaoDatabase`オブジェクト。

複数レベルのログイン認証の接続文字列を使用することもできます (それぞれ、別の`CDaoDatabase`オブジェクト) またはその他のデータベースに固有の情報を伝達するためにします。

##  <a name="setquerytimeout"></a>  CDaoDatabase::SetQueryTimeout

接続されているデータベースのタイムアウトで後続の操作の前に、秒の既定の数を上書きするには、このメンバー関数を呼び出します。

```
void SetQueryTimeout(short nSeconds);
```

### <a name="parameters"></a>パラメーター

*nSeconds*<br/>
クエリ試行する前に許可する秒数がタイムアウトになりました。

### <a name="remarks"></a>Remarks

操作は、ネットワーク アクセスの問題や、過剰なクエリ処理時間のためタイムアウト可能性があります。 呼び出す`SetQueryTimeout`またはレコード セットの前に、レコード セットを開く前に[AddNew](../../mfc/reference/cdaorecordset-class.md#addnew)、 [Update](../../mfc/reference/cdaorecordset-class.md#update)、または[削除](../../mfc/reference/cdaorecordset-class.md#delete)メンバー関数の場合は、クエリを変更します。タイムアウト値。 この設定は、後続のすべての適用[オープン](../../mfc/reference/cdaorecordset-class.md#open)、 `AddNew`、`Update`と`Delete`これに関連付けられているすべてのレコード セットへの呼び出し`CDaoDatabase`オブジェクト。 開いた後、レコード セットのクエリ タイムアウト値を変更しても、レコード セットの値は変わりません。 たとえば、後続[移動](../../mfc/reference/cdaorecordset-class.md#move)操作では、新しい値を使用しないでください。

クエリ タイムアウトの既定値は、60 秒です。 すべてのデータベースでは、クエリのタイムアウト値を設定する機能をサポートします。 クエリのタイムアウト値は 0 を設定した場合のタイムアウトは行われません。データベースとの通信が応答を停止します。 この動作は、開発時に役立ちます。

関連情報については、「QueryTimeout プロパティ」DAO ヘルプのトピックを参照してください。

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CDaoWorkspace クラス](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoTableDef クラス](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDatabase クラス](../../mfc/reference/cdatabase-class.md)<br/>
[CDaoException クラス](../../mfc/reference/cdaoexception-class.md)
