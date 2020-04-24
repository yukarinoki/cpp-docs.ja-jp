---
title: CDaoDatabase クラス
ms.date: 09/17/2019
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
ms.openlocfilehash: 0fbc4ee3f2033f7507a1ed68493fa7e48bc62c51
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754743"
---
# <a name="cdaodatabase-class"></a>CDaoDatabase クラス

データ アクセス オブジェクト (DAO) を使用して Access データベースへの接続を表します。 DAO は Office 2013 を通じてサポートされています。 DAO 3.6 は最終バージョンであり、廃止と見なされます。

## <a name="syntax"></a>構文

```
class CDaoDatabase : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[データベース::データベース](#cdaodatabase)|`CDaoDatabase` オブジェクトを構築します。 オブジェクト`Open`をデータベースに接続するための呼び出し。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[データベース::缶トランスアクト](#cantransact)|データベースがトランザクションをサポートする場合は、0 以外を返します。|
|[データベース::缶更新](#canupdate)|オブジェクトが`CDaoDatabase`更新可能な場合は、0 以外を返します (読み取り専用ではありません)。|
|[CDaoDatabase::Close](#close)|データベース接続を閉じます。|
|[CDaoDatabase::Create](#create)|基になる DAO データベース オブジェクトを作成`CDaoDatabase`し、オブジェクトを初期化します。|
|[データベース::リレーションシップの作成](#createrelation)|データベース内のテーブル間の新しいリレーションシップを定義します。|
|[CDaoDatabase::DeleteQueryDef](#deletequerydef)|データベースの QueryDefs コレクションに保存されているクエリ定義オブジェクトを削除します。|
|[データベース::Dエレットリレーション](#deleterelation)|データベース内のテーブル間の既存のリレーションシップを削除します。|
|[CDaoDatabase::DeleteTableDef](#deletetabledef)|データベース内のテーブルの定義を削除します。 これにより、実際のテーブルとそのすべてのデータが削除されます。|
|[データベース::実行](#execute)|アクション クエリを実行します。 結果`Execute`を返すクエリを呼び出すと、例外がスローされます。|
|[CDaoDatabase::GetConnect](#getconnect)|オブジェクトをデータベースに接続するために使用する`CDaoDatabase`接続文字列を返します。 ODBC に使用されます。|
|[データベース::ゲットネーム](#getname)|現在使用中のデータベースの名前を返します。|
|[データベース::クエリ定義カウント](#getquerydefcount)|データベースに対して定義されているクエリの数を返します。|
|[CDaoDatabase::GetQueryDefInfo](#getquerydefinfo)|データベースで定義された指定されたクエリに関する情報を返します。|
|[データベース::ゲットクエリタイムアウト](#getquerytimeout)|データベース クエリ操作がタイムアウトするまでの秒数を返します。以降の開いている操作、新規操作、更新操作、および編集操作、および ODBC データ ソースに対`Execute`するその他の操作 (呼び出しなど) に影響します。|
|[影響を受けるレコード](#getrecordsaffected)|最後の更新、編集、または追加操作、または の`Execute`呼び出しによって影響を受けるレコードの数を返します。|
|[データベース::取得リレーションシップカウント](#getrelationcount)|データベース内のテーブル間で定義されたリレーションの数を返します。|
|[データベース::取得リレーションシップインフォ](#getrelationinfo)|データベース内のテーブル間で定義された指定されたリレーションシップに関する情報を返します。|
|[データベース::テーブル定義カウント](#gettabledefcount)|データベースで定義されているテーブルの数を返します。|
|[CDaoDatabase::GetTableDefInfo](#gettabledefinfo)|データベース内の指定されたテーブルに関する情報を返します。|
|[データベース::ゲットバージョン](#getversion)|データベースに関連付けられているデータベース エンジンのバージョンを返します。|
|[CDaoDatabase::IsOpen](#isopen)|オブジェクトがデータベースに`CDaoDatabase`現在接続されている場合は、0 以外を返します。|
|[CDaoDatabase::Open](#open)|データベースへの接続を確立します。|
|[データベース::セットクエリタイムアウト](#setquerytimeout)|データベース クエリ操作 (ODBC データ ソースのみ) がタイムアウトするまでの秒数を設定します。以降の開く、新規追加、更新、および削除のすべての操作に影響します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[データベース::m_pDAODatabase](#m_pdaodatabase)|基になる DAO データベース オブジェクトへのポインター。|
|[データベース::m_pWorkspace](#m_pworkspace)|データベースを格納し、そのトランザクション領域を定義する[CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)オブジェクトへのポインター。|

## <a name="remarks"></a>解説

サポートされるデータベース形式については[、GetName](../../mfc/reference/cdaoworkspace-class.md#getname)メンバー関数を参照してください。 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) オブジェクトによって表される特定の "ワークスペース" で一度に1つ以上の`CDaoDatabase`オブジェクトをアクティブにすることができます。 ワークスペースは、Databases コレクションと呼ばれる、開いているデータベース オブジェクトのコレクションを保持します。

## <a name="usage"></a>使用法

レコードセット オブジェクトを作成するときに、データベース オブジェクトを暗黙的に作成できます。 ただし、データベース オブジェクトを明示的に作成することもできます。 既存のデータベースを で`CDaoDatabase`明示的に使用するには、次のいずれかの操作を行います。

- `CDaoDatabase`オブジェクトを構築し、開いている [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) オブジェクトへのポインターを渡します。

- または、ワークスペース`CDaoDatabase`を指定せずにオブジェクトを構築します (MFC は一時ワークスペース オブジェクトを作成します)。

新しいマイクロソフト ジェット (.MDB) データベースを作成`CDaoDatabase`し、オブジェクトを[作成](#create)するメンバー関数を呼び出します。 後*に*`Create`呼`Open`び出さない

既存のデータベースを開くには、オブジェクト`CDaoDatabase`を構築し、[その Open](#open)メンバー関数を呼び出します。

これらの手法はいずれも、DAO データベース オブジェクトをワークスペースの Databases コレクションに追加し、データへの接続を開きます。 接続されたデータベースで操作するための[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) [、CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)、または[CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)オブジェクトを構築する場合は、これらのオブジェクトのコンストラクターを`CDaoDatabase`オブジェクトへのポインターとして渡します。 接続の使用が終了したら[、Close](#close)メンバー関数を呼び出`CDaoDatabase`してオブジェクトを破棄します。 `Close`以前に閉じなかったレコードセットをすべて閉じます。

## <a name="transactions"></a>トランザクション

データベース トランザクション処理は、クラスの[BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans) [、CommitTrans、](../../mfc/reference/cdaoworkspace-class.md#committrans)および[ロールバック](../../mfc/reference/cdaoworkspace-class.md#rollback)のメンバー関数を参照してください`CDaoWorkspace`。

## <a name="odbc-connections"></a>ODBC 接続

ODBC データ ソースを操作する場合は、外部テーブルを Jet にアタッチすることをお勧めします(MDB) データベース。

## <a name="collections"></a>コレクション

各データベースは、テーブル定義、クエリ定義、レコードセット、およびリレーションシップ オブジェクトの独自のコレクションを保持します。 クラス`CDaoDatabase`は、これらのオブジェクトを操作するためのメンバー関数を提供します。

> [!NOTE]
> オブジェクトは、MFC データベース オブジェクトではなく DAO に格納されます。 MFC には、テーブル定義、クエリ定義、およびレコードセット オブジェクトのクラスが用意されていますが、リレーションシップ オブジェクトにはクラスがありません。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CDaoDatabase`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="cdaodatabasecantransact"></a><a name="cantransact"></a>データベース::缶トランスアクト

データベースでトランザクションが許可されているかどうかを確認します。

```
BOOL CanTransact();
```

### <a name="return-value"></a>戻り値

データベースがトランザクションをサポートする場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

トランザクションは、データベースのワークスペースで管理されます。

## <a name="cdaodatabasecanupdate"></a><a name="canupdate"></a>データベース::缶更新

`CDaoDatabase`オブジェクトが更新を許可するかどうかを確認します。

```
BOOL CanUpdate();
```

### <a name="return-value"></a>戻り値

オブジェクトが更新を`CDaoDatabase`許可する場合は 0 以外。それ以外の場合は 0 で、`CDaoDatabase`オブジェクトを開いたときに true を*bReadOnly*で渡したか、またはデータベース自体が読み取り専用であることを示します。 [Open](#open)メンバー関数を参照してください。

### <a name="remarks"></a>解説

データベースの更新の詳細については、DAO ヘルプの「更新可能なプロパティ」を参照してください。

## <a name="cdaodatabasecdaodatabase"></a><a name="cdaodatabase"></a>データベース::データベース

`CDaoDatabase` オブジェクトを構築します。

```
CDaoDatabase(CDaoWorkspace* pWorkspace = NULL);
```

### <a name="parameters"></a>パラメーター

*ワークスペース*<br/>
新しいデータベース`CDaoWorkspace`オブジェクトを格納するオブジェクトへのポインター。 既定値の NULL を受け入れる場合、コンストラクターは`CDaoWorkspace`既定の DAO ワークスペースを使用する一時オブジェクトを作成します。 ワークスペース オブジェクトへのポインターは[、m_pWorkspace](#m_pworkspace)データ メンバーを介して取得できます。

### <a name="remarks"></a>解説

オブジェクトを構築した後、新しい Microsoft Jet (.MDB) データベースを呼び出す場合は、オブジェクトの[作成](#create)メンバー関数を呼び出します。 既存のデータベースを開いている場合は、オブジェクトの[Open](#open)メンバー関数を呼び出します。

オブジェクトの使用を終了したら[、Close](#close)メンバー関数を呼び出してからオブジェクトを`CDaoDatabase`破棄する必要があります。

ドキュメント クラスにオブジェクトを`CDaoDatabase`埋め込むと便利な場合があります。

> [!NOTE]
> 既存`CDaoDatabase``CDaoDatabase`のオブジェクトへのポインタを渡さずに[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを開いた場合も、オブジェクトは暗黙的に作成されます。 このデータベース オブジェクトは、レコードセット オブジェクトを閉じると閉じられます。

## <a name="cdaodatabaseclose"></a><a name="close"></a>データベース::閉じる

データベースから切断し、開いているレコードセット、テーブル定義、およびデータベースに関連付けられたクエリ定義を閉じます。

```
virtual void Close();
```

### <a name="remarks"></a>解説

このメンバー関数を呼び出す前に、これらのオブジェクトを自分で閉じておくことをお勧めします。 オブジェクトを`CDaoDatabase`閉じると、関連付けられた[ワークスペース](../../mfc/reference/cdaoworkspace-class.md)の Databases コレクションからオブジェクトが削除されます。 オブジェクト`Close`は`CDaoDatabase`破棄されないため、同じデータベースまたは別のデータベースを開いてオブジェクトを再利用できます。

> [!CAUTION]
> データベースを閉じる前に、[開](../../mfc/reference/cdaorecordset-class.md#update)いているすべてのレコードセット オブジェクトに`Close`対して Update メンバー関数 (保留中の編集がある場合) とメンバー関数を呼び出します。 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)または`CDaoDatabase`スタック上のオブジェクトを宣言する関数を終了すると、データベースが閉じられ、保存されていない変更がすべて失われ、保留中のすべてのトランザクションがロールバックされ、保留中のデータの編集は失われます。

> [!CAUTION]
> レコードセット オブジェクトが開いているときにデータベース オブジェクトを閉じようとした場合、または特定のワークスペースに属するデータベース オブジェクトが開いているときにワークスペース オブジェクトを閉じようとすると、それらのレコードセット オブジェクトは閉じられ、保留中の更新や編集はロールバックされます。 ワークスペース オブジェクトに属するデータベース オブジェクトが開いているときにワークスペース オブジェクトを閉じようとすると、その特定のワークスペース オブジェクトに属するすべてのデータベース オブジェクトが閉じられ、その結果、閉じていないレコードセット オブジェクトが閉じられる可能性があります。 データベース オブジェクトを閉じなければ、デバッグ ビルドでアサーション エラーが報告されます。

データベース オブジェクトが関数のスコープ外で定義されている場合、関数を閉じずに関数を終了すると、明示的に閉じられるか、定義されているモジュールがスコープ外になるまで、データベース オブジェクトは開いたままになります。

## <a name="cdaodatabasecreate"></a><a name="create"></a>データベース::作成

新しいマイクロソフト ジェット (.MDB) データベースを作成した後、このメンバー関数`CDaoDatabase`を呼び出します。

```
virtual void Create(
    LPCTSTR lpszName,
    LPCTSTR lpszLocale = dbLangGeneral,
    int dwOptions = 0);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
作成するデータベース ファイルの名前を表す文字列式。 フル パスとファイル名を指定できます("C:\\\MYDB.MDB". 名前を指定する必要があります。 ファイル名拡張子を指定しない場合は、 .MDB が追加されます。 ネットワークが統一命名規則 (UNC)\\\\\\をサポートしている場合は、"\MYSERVER\\\MYSHARE\\\MYDIR \MYDB"\\などのネットワーク パスを指定することもできます。 マイクロソフトジェット(.MDB) データベース ファイルは、このメンバー関数を使用して作成できます。 文字列リテラルでは" " は\\C++ エスケープ文字であるため、二重円記号が必要です。

*ロケールを指定します。*<br/>
データベースを作成するための照合順序を指定するために使用する文字列式。 既定値は `dbLangGeneral` です。 次のいずれかの値になります。

- `dbLangGeneral`英語、ドイツ語、フランス語、ポルトガル語、イタリア語、およびモダンスペイン語

- `dbLangArabic`アラビア語

- `dbLangCyrillic`ロシア語

- `dbLangCzech`チェコ語

- `dbLangDutch`オランダ語

- `dbLangGreek`ギリシャ語

- `dbLangHebrew`ヘブライ語

- `dbLangHungarian`ハンガリー語

- `dbLangIcelandic`アイスランド語

- `dbLangNordic`北欧言語 (Microsoft Jet データベース エンジン バージョン 1.0 のみ)

- `dbLangNorwdan`ノルウェー語とデンマーク語

- `dbLangPolish`ポーランド語

- `dbLangSpanish`伝統的なスペイン語

- `dbLangSwedfin`スウェーデン語とフィンランド語

- `dbLangTurkish`トルコ語

*dw オプション*<br/>
1 つ以上のオプションを示す整数。 次のいずれかの値になります。

- `dbEncrypt`暗号化されたデータベースを作成します。

- `dbVersion10`Jet データベース バージョン 1.0 のデータベースを作成します。

- `dbVersion11`Jet データベース バージョン 1.1 のデータベースを作成します。

- `dbVersion20`Jet データベース バージョン 2.0 のデータベースを作成します。

- `dbVersion30`Jet データベース バージョン 3.0 のデータベースを作成します。

暗号化定数を省略すると、暗号化されていないデータベースが作成されます。 指定できるバージョン定数は 1 つだけです。 バージョン定数を省略すると、Jet データベース バージョン 3.0 を使用するデータベースが作成されます。

> [!CAUTION]
> データベースが暗号化されていない場合は、ユーザー/パスワード セキュリティを実装していても、データベースを構成するバイナリ ディスク ファイルを直接読み取る可能性があります。

### <a name="remarks"></a>解説

`Create`データベース ファイルと基になる DAO データベース オブジェクトを作成し、C++ オブジェクトを初期化します。 オブジェクトは、関連付けられたワークスペースの Databases コレクションに追加されます。 データベース オブジェクトは開いている状態です。後に`Create`呼`Open*`び出さない

> [!NOTE]
> では`Create`、マイクロソフト の Jet (.MDB) データベース。 ISAM データベースまたは ODBC データベースを作成することはできません。

## <a name="cdaodatabasecreaterelation"></a><a name="createrelation"></a>データベース::リレーションシップの作成

データベースのプライマリ テーブルの 1 つ以上のフィールドと、外部テーブル (データベース内の別のテーブル) 内の 1 つ以上のフィールドとの間にリレーションシップを確立します。

```cpp
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

*名前を指定します。*<br/>
リレーション オブジェクトの一意の名前。 名前は、先頭に文字を付ける必要があり、最大 40 文字を使用できます。 数字やアンダースコアの文字を含めることができますが、句読点やスペースを含めることはできません。

*lpszTable*<br/>
リレーションの主テーブルの名前。 テーブルが存在しない場合、MFC は[型 CDaoException](../../mfc/reference/cdaoexception-class.md)の例外をスローします。

*lpszForeignTable*<br/>
リレーションの外部テーブルの名前。 テーブルが存在しない場合、MFC は型の例外をスロー`CDaoException`します。

*l属性*<br/>
リレーションシップの種類に関する情報を含む長い値。 この値を使用して、参照整合性を強制することができます。 ビットごとの OR 演算子 ( **&#124;**) を使用して、次の値のいずれかを組み合わせることができます (組み合わせが意味をなす限り)。

- `dbRelationUnique`関係は一対一です。

- `dbRelationDontEnforce`関係は強制されません (参照整合性はありません)。

- `dbRelationInherited`リレーションシップは、2 つのアタッチされたテーブルを含む現在以外のデータベースに存在します。

- `dbRelationUpdateCascade`更新は連鎖します (カスケードの詳細については、「解説」を参照)。

- `dbRelationDeleteCascade`削除はカスケードされます。

*lpszフィールド*<br/>
プライマリ テーブルのフィールド名を含む NULL で終わる文字列へのポインタです ( *lpszTable*で指定 )。

*lpsz外国フィールド*<br/>
外部テーブルのフィールド名を含む NULL で終わる文字列へのポインター *。*

*レルインフォ*<br/>
作成するリレーションシップに関する情報を含む[CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)オブジェクトへの参照。

### <a name="remarks"></a>解説

リレーションシップに外部データベースのクエリまたはアタッチ テーブルを含めることはできません。

リレーションが 2 つのテーブルのそれぞれで 1 つのフィールドを含む場合は、関数の最初のバージョンを使用します。 リレーションに複数のフィールドが含まれる場合は、2 番目のバージョンを使用します。 1 つのリレーションのフィールドの最大数は 14 です。

このアクションは基になる DAO リレーション オブジェクトを作成しますが、MFC のリレーション オブジェクトのカプセル化はクラス`CDaoDatabase`内に含まれているため、MFC 実装の詳細です。 MFC はリレーションのクラスを提供しません。

リレーション オブジェクトの属性を設定してカスケード操作をアクティブにすると、データベース エンジンは、関連する主キー テーブルを変更したときに、1 つ以上の他のテーブルのレコードを自動的に更新または削除します。

たとえば、顧客テーブルと Orders テーブルの間に連鎖削除リレーションシップを確立するとします。 [得意先] テーブルからレコードを削除すると、その顧客に関連する [受注] テーブルのレコードも削除されます。 また、Orders テーブルと他のテーブルとの間に連鎖削除リレーションシップを確立すると、これらのテーブルのレコードは[得意先] テーブルからレコードを削除したときに自動的に削除されます。

関連情報については、DAO ヘルプの「関連メソッドの作成」を参照してください。

## <a name="cdaodatabasedeletequerydef"></a><a name="deletequerydef"></a>データベース::Dテレテクエリ定義

`CDaoDatabase`オブジェクトの QueryDefs コレクションから指定されたクエリ定義 (保存されたクエリ) を削除します。

```cpp
void DeleteQueryDef(LPCTSTR lpszName);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
削除する保存済みクエリの名前。

### <a name="remarks"></a>解説

その後、そのクエリはデータベースで定義されなくなります。

クエリ定義オブジェクトの作成については、「クラス[CDaoQueryDef」](../../mfc/reference/cdaoquerydef-class.md)を参照してください。 querydef オブジェクトは、オブジェクトを構築`CDaoDatabase`するときに特定の`CDaoQueryDef`オブジェクトに関連付け、データベース オブジェクトへのポインタを渡します。

## <a name="cdaodatabasedeleterelation"></a><a name="deleterelation"></a>データベース::Dエレットリレーション

データベース オブジェクトの Relations コレクションから既存のリレーションシップを削除します。

```cpp
void DeleteRelation(LPCTSTR lpszName);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
削除するリレーションの名前。

### <a name="remarks"></a>解説

その後、関係は存在しなくなります。

関連情報については、DAO ヘルプの「メソッドの削除」を参照してください。

## <a name="cdaodatabasedeletetabledef"></a><a name="deletetabledef"></a>データベースデータベース::Deleteテーブルフフ

オブジェクトの TableDefs コレクションから、指定したテーブルとそのすべてのデータ`CDaoDatabase`を削除します。

```cpp
void DeleteTableDef(LPCTSTR lpszName);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
削除するテーブル定義の名前。

### <a name="remarks"></a>解説

その後、そのテーブルはデータベースで定義されなくなります。

> [!NOTE]
> システム テーブルを削除しないように注意してください。

テーブル定義オブジェクトの作成については、「[クラス CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)」を参照してください。 tabledef オブジェクトは、オブジェクトを構築`CDaoDatabase`するときに特定の`CDaoTableDef`オブジェクトに関連付け、データベース オブジェクトへのポインタを渡します。

関連情報については、DAO ヘルプの「メソッドの削除」を参照してください。

## <a name="cdaodatabaseexecute"></a><a name="execute"></a>データベース::実行

アクション クエリを実行するか、データベースで SQL ステートメントを実行します。

```cpp
void Execute(
    LPCTSTR lpszSQL,
    int nOptions = dbFailOnError);
```

### <a name="parameters"></a>パラメーター

*Lpszsql*<br/>
実行する有効な SQL コマンドを含む NULL で終わる文字列へのポインター。

*nオプション*<br/>
クエリの整合性に関連するオプションを指定する整数。 bitwise-OR 演算子 ( **&#124;**) を使用して、次の定数のいずれかを組み合わせることができます ( たとえば、`dbInconsistent`組み合わせ`dbConsistent`が意味をなす場合 ) 。

- `dbDenyWrite`他のユーザーへの書き込みアクセス許可を拒否します。

- `dbInconsistent`(デフォルト)一貫性のない更新プログラム。

- `dbConsistent`一貫した更新。

- `dbSQLPassThrough`SQL パススルー。 SQL ステートメントを処理のために ODBC データ ソースに渡します。

- `dbFailOnError`エラーが発生した場合は、更新をロールバックします。

- `dbSeeChanges`編集中のデータを別のユーザーが変更している場合に、実行時エラーを生成します。

> [!NOTE]
> 両方`dbInconsistent`が`dbConsistent`含まれているか、どちらも含まれていない場合、結果がデフォルトになります。 これらの定数の詳細については、DAO ヘルプの「メソッドの実行」を参照してください。

### <a name="remarks"></a>解説

`Execute`アクション クエリまたは結果を返さない SQL パススルー クエリに対してのみ機能します。 レコードを返す選択クエリでは機能しません。

アクション クエリの定義と情報については、DAO ヘルプの「アクション クエリ」および「メソッドの実行」を参照してください。

> [!TIP]
> 構文的に正しい SQL ステートメントと適切な権限`Execute`を与えられた場合、メンバー関数は、1 行が変更または削除できなくても失敗しません。 したがって、更新クエリまたは`dbFailOnError`削除クエリを実行`Execute`するメンバー関数を使用する場合は、常にオプションを使用します。 このオプションを使用すると、MFC は[CDaoException](../../mfc/reference/cdaoexception-class.md)型の例外をスローし、影響を受けるレコードのいずれかがロックされ、更新または削除できない場合は、成功したすべての変更をロールバックします。 影響を受けたレコードの`GetRecordsAffected`数をいつでも確認できます。

データベース オブジェクトの[GetRecordsAffected](#getrecordsaffected)メンバー関数を呼び出して、最新`Execute`の呼び出しによって影響を受けるレコードの数を調べます。 たとえば、`GetRecordsAffected`アクション クエリの実行時に削除、更新、または挿入されたレコードの数に関する情報を返します。 カスケード更新または削除が有効な場合、返されるカウントには関連テーブルの変更は反映されません。

`Execute`はレコードセットを返しません。 レコード`Execute`を選択するクエリを使用すると、MFC は型の例外を`CDaoException`スローします。 (に類似した`ExecuteSQL``CDatabase::ExecuteSQL`メンバー関数はありません。

## <a name="cdaodatabasegetconnect"></a><a name="getconnect"></a>データベース::ゲットコネクト

オブジェクトを ODBC または ISAM データベースに接続`CDaoDatabase`するために使用する接続文字列を取得します。

```
CString GetConnect();
```

### <a name="return-value"></a>戻り値

ODBC データ ソースで[Open](#open)が正常に呼び出された場合は接続文字列。それ以外の場合は空の文字列。 マイクロソフトジェット(.MDB) データベースでは`dbSQLPassThrough`[、Execute](#execute)メンバー関数で使用するオプションやレコードセットを開くときに使用するオプションを設定しない限り、文字列は常に空です。

### <a name="remarks"></a>解説

文字列は、オープンなデータベースまたはパススルー クエリで使用されるデータベースのソースに関する情報を提供します。 接続文字列は、データベース型指定子とセミコロンで区切られた 0 個以上のパラメーターで構成されます。

> [!NOTE]
> MFC DAO クラスを使用して ODBC を使用してデータ ソースに接続する方法は、アタッチ テーブルを使用して接続するよりも効率が悪くなります。

> [!NOTE]
> 接続文字列は、必要に応じて ODBC および特定の ISAM ドライバーに追加情報を渡すために使用されます。 には使用されません。MDB データベース。 Microsoft Jet データベースベーステーブルの場合、上記の「戻り値」で説明したように、SQL パススルー クエリに使用する場合を除き、接続文字列は空の文字列 ("") です。

接続文字列の作成方法については[、Open](#open)メンバー関数を参照してください。 `Open`呼び出しで接続文字列を設定した後で、接続文字列を使用して、データベースの種類、パス、ユーザー ID、パスワード、または ODBC データ ソースを確認する設定を確認できます。

## <a name="cdaodatabasegetname"></a><a name="getname"></a>データベース::ゲットネーム

現在開いているデータベースの名前 (既存のデータベース ファイルの名前または登録済みの ODBC データ ソースの名前) を取得します。

```
CString GetName();
```

### <a name="return-value"></a>戻り値

成功した場合は、データベースの完全パスとファイル名。それ以外の場合は、空の[CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>解説

ネットワークが統一命名規則 (UNC) をサポートしている場合は、\\\\\\\\\\\\ネットワーク パスを指定することもできます。MDB". 文字列リテラルでは" " は\\C++ エスケープ文字であるため、二重円記号が必要です。

たとえば、この名前を見出しに表示する場合があります。 名前の取得中にエラーが発生した場合、MFC は[CDaoException](../../mfc/reference/cdaoexception-class.md)型の例外をスローします。

> [!NOTE]
> 外部データベースにアクセスする際のパフォーマンスを向上させるために、外部データベース テーブルを Microsoft Jet データベース ( にアタッチすることをお勧めします。MDB) は、データ ソースに直接接続するのではなく、データ ソースに直接接続する必要があります。

データベースの種類は、パスが指すファイルまたはディレクトリによって次のように示されます。

|パス名が指す。|データベースの種類|
|--------------------------|-------------------|
|.MDB ファイル|ジェット データベース (Access)|
|を含むディレクトリ。DBF ファイル|dBASE データベース|
|を含むディレクトリ。XLSファイル|データベース|
|を含むディレクトリ。PDX ファイル|パラドックスデータベース|
|適切にフォーマットされたテキスト データベース ファイルを含むディレクトリ|テキスト形式データベース|

SQL Server や Oracle などの ODBC データベースの場合、データベースの接続文字列は、ODBC によって登録されているデータ ソース名 (DSN) を識別します。

## <a name="cdaodatabasegetquerydefcount"></a><a name="getquerydefcount"></a>データベース::クエリ定義カウント

データベースの QueryDefs コレクションで定義されているクエリの数を取得します。

```
short GetQueryDefCount();
```

### <a name="return-value"></a>戻り値

データベースで定義されているクエリの数。

### <a name="remarks"></a>解説

`GetQueryDefCount`は、QueryDefs コレクション内のすべてのクエリ定義をループする必要がある場合に便利です。 コレクション内の指定されたクエリに関する情報を取得するには、「 [GetQueryDefInfo](#getquerydefinfo)」を参照してください。

## <a name="cdaodatabasegetquerydefinfo"></a><a name="getquerydefinfo"></a>データベース::クエリ定義情報

データベースで定義されているクエリに関するさまざまな情報を取得します。

```cpp
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
データベースの QueryDefs コレクション内の定義済みクエリのインデックス。

*クエリ定義fo*<br/>
要求された情報を返す[CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md)オブジェクトへの参照。

*オプション*<br/>
取得するレコードセットに関する情報を指定するオプション。 次に、使用可能なオプションと、レコードセットに関して関数が返す内容を示します。

- AFX_DAO_PRIMARY_INFO (デフォルト) 名、タイプ

- AFX_DAO_SECONDARY_INFO主な情報に加えて:作成日、最終更新日、レコードの返却、更新可能

- AFX_DAO_ALL_INFOプライマリおよびセカンダリ情報に加えて、SQL、接続、ODBCTimeout

*名前を指定します。*<br/>
データベースで定義されているクエリの名前を含む文字列。

### <a name="remarks"></a>解説

2 つのバージョンの関数が提供されるため、データベースの QueryDefs コレクション内のインデックスまたはクエリの名前を使用してクエリを選択できます。

*クエリ定義で*返される情報の説明については、[構造体](../../mfc/reference/cdaoquerydefinfo-structure.md)を参照してください。 この構造体には *、dwInfoOptions*の説明に記載されている情報の項目に対応するメンバがあります。 1 つのレベルの情報を要求すると、以前のレベルの情報も取得できます。

## <a name="cdaodatabasegetquerytimeout"></a><a name="getquerytimeout"></a>データベース::ゲットクエリタイムアウト

接続されているデータベースに対する後続の操作がタイムアウトするまでに許容される現在の秒数を取得します。

```
short GetQueryTimeout();
```

### <a name="return-value"></a>戻り値

タイムアウト値を秒単位で格納する短い整数。

### <a name="remarks"></a>解説

ネットワーク アクセスの問題、クエリ処理時間の過剰などにより、操作がタイムアウトすることがあります。 この設定が有効な場合、この`CDaoDatabase`オブジェクトに関連付けられているレコードセットに対して、すべての開いた操作、新しい操作、更新操作、および削除操作に影響します。 現在のタイムアウト設定を変更するには、 [SetQueryTimeout](#setquerytimeout)を呼び出します。 開いた後にレコードセットのクエリ タイムアウト値を変更しても、レコードセットの値は変更されません。 たとえば、後続の[移動](../../mfc/reference/cdaorecordset-class.md#move)操作では新しい値は使用されません。 デフォルト値は、データベース エンジンの初期化時に初期設定されます。

クエリ タイムアウトの既定値は、Windows レジストリから取得されます。 レジストリ設定がない場合、デフォルトは 60 秒です。 すべてのデータベースが、クエリのタイムアウト値を設定する機能をサポートしているわけではありません。 クエリのタイムアウト値を 0 に設定した場合、タイムアウトは発生しません。データベースとの通信が応答を停止する可能性があります。 この動作は、開発中に役立つ場合があります。 呼び出しが失敗した場合、MFC は[型 CDaoException](../../mfc/reference/cdaoexception-class.md)の例外をスローします。

関連情報については、DAO ヘルプの「QueryTimeout プロパティ」を参照してください。

## <a name="cdaodatabasegetrecordsaffected"></a><a name="getrecordsaffected"></a>影響を受けるレコード

[Execute](#execute)メンバー関数の最新の呼び出しによって影響を受けるレコードの数を調べます。

```
long GetRecordsAffected();
```

### <a name="return-value"></a>戻り値

影響を受けるレコードの数を含む長整数。

### <a name="remarks"></a>解説

返される値には、 で実行されるアクション クエリによって削除、更新、または挿入されたレコードの`Execute`数が含まれます。 カスケード更新または削除が有効な場合、返されるカウントには関連テーブルの変更は反映されません。

関連情報については、DAO ヘルプの「レコードに影響を受けるプロパティ」を参照してください。

## <a name="cdaodatabasegetrelationcount"></a><a name="getrelationcount"></a>データベース::取得リレーションシップカウント

データベース内のテーブル間で定義されたリレーションの数を取得します。

```
short GetRelationCount();
```

### <a name="return-value"></a>戻り値

データベース内のテーブル間で定義されたリレーションの数。

### <a name="remarks"></a>解説

`GetRelationCount`は、データベースの Relations コレクションで定義されているすべてのリレーションをループする必要がある場合に便利です。 コレクション内の指定されたリレーションシップに関する情報を取得するには、「 [GetRelationInfo](#getrelationinfo)」を参照してください。

リレーションシップの概念を説明するために、仕入先テーブルと一対多リレーションシップを持つ商品テーブルを考えてみましょう。 この関係では、1 つの供給業者が複数の製品を供給できます。 その他の関係は、一対一と多対多です。

## <a name="cdaodatabasegetrelationinfo"></a><a name="getrelationinfo"></a>データベース::取得リレーションシップインフォ

データベースの Relations コレクション内の指定されたリレーションシップに関する情報を取得します。

```cpp
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
データベースの Relations コレクション内のリレーションシップ オブジェクトのインデックスです。

*レルインフォ*<br/>
要求された情報を返す[オブジェクト](../../mfc/reference/cdaorelationinfo-structure.md)への参照。

*オプション*<br/>
取得するリレーションに関する情報を指定するオプション。 使用可能なオプションは、リレーションに関して関数が返す原因と共に、次の一覧に示します。

- AFX_DAO_PRIMARY_INFO (デフォルト) 名、テーブル、外部テーブル

- 属性AFX_DAO_SECONDARY_INFOフィールド情報

フィールド情報は、そのリレーションに含まれる主テーブルのフィールドを含む[CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md)オブジェクトです。

*名前を指定します。*<br/>
名前による参照用のリレーション オブジェクトの名前を含む文字列。

### <a name="remarks"></a>解説

この関数の 2 つのバージョンは、インデックスまたは名前によるアクセスを提供します。 *relinfo*で返される情報の詳細については、[構造体](../../mfc/reference/cdaorelationinfo-structure.md)を参照してください。 この構造体には *、dwInfoOptions*の説明に記載されている情報の項目に対応するメンバがあります。 あるレベルで情報を要求した場合は、以前の任意のレベルでも情報を取得します。

> [!NOTE]
> リレーション オブジェクトの属性を設定してカスケード操作をアクティブにする`dbRelationUpdateCascades` `dbRelationDeleteCascades`( または ) を設定すると、関連する主キー テーブルが変更されると、Microsoft Jet データベース エンジンによって、1 つ以上のテーブルのレコードが自動的に更新または削除されます。 たとえば、顧客テーブルと Orders テーブルの間に連鎖削除リレーションシップを確立するとします。 [得意先] テーブルからレコードを削除すると、その顧客に関連する [受注] テーブルのレコードも削除されます。 また、Orders テーブルと他のテーブルとの間に連鎖削除リレーションシップを確立すると、これらのテーブルのレコードは[得意先] テーブルからレコードを削除したときに自動的に削除されます。

## <a name="cdaodatabasegettabledefcount"></a><a name="gettabledefcount"></a>データベース::テーブル定義カウント

データベースで定義されているテーブルの数を取得します。

```
short GetTableDefCount();
```

### <a name="return-value"></a>戻り値

データベースで定義されているテーブル定義の数。

### <a name="remarks"></a>解説

`GetTableDefCount`データベースの TableDefs コレクション内のすべてのテーブル定義をループする必要がある場合に便利です。 コレクション内の特定のテーブルに関する情報を取得するには[、「GetTableDefInfo](#gettabledefinfo)」を参照してください。

## <a name="cdaodatabasegettabledefinfo"></a><a name="gettabledefinfo"></a>データベース::テーブル定義情報を取得します。

データベースで定義されているテーブルに関するさまざまな情報を取得します。

```cpp
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
データベースの TableDefs コレクション内のテーブル定義オブジェクトのインデックスです。

*テーブル定義*<br/>
要求された情報を返す[オブジェクト](../../mfc/reference/cdaotabledefinfo-structure.md)への参照。

*オプション*<br/>
取得するテーブルに関する情報を指定するオプション。 使用可能なオプションは、リレーションに関して関数が返す原因と共に、次の一覧に示します。

- AFX_DAO_PRIMARY_INFO (デフォルト) 名、更新可能、属性

- AFX_DAO_SECONDARY_INFO主な情報に加えて: 作成日、最終更新日、ソーステーブル名、接続

- AFX_DAO_ALL_INFOプライマリおよびセカンダリ情報に加えて、検証ルール、検証テキスト、レコード数

*名前を指定します。*<br/>
名前による参照用のテーブル定義オブジェクトの名前。

### <a name="remarks"></a>解説

2 つのバージョンの関数が提供されるため、データベースの TableDefs コレクション内のインデックスまたはテーブルの名前を使用してテーブルを選択できます。

*テーブル定義で*返される情報の説明については、[構造体](../../mfc/reference/cdaotabledefinfo-structure.md)を参照してください。 この構造体には *、dwInfoOptions*の説明に記載されている情報の項目に対応するメンバがあります。 あるレベルで情報を要求すると、以前のレベルの情報も取得できます。

> [!NOTE]
> AFX_DAO_ALL_INFOオプションは、取得が遅くなる可能性のある情報を提供します。 この場合、レコードが多い場合、テーブル内のレコードをカウントすると非常に時間がかかる可能性があります。

## <a name="cdaodatabasegetversion"></a><a name="getversion"></a>データベース::ゲットバージョン

Jet データベース ファイルのバージョンを確認するには、このメンバー関数を呼び出します。

```
CString GetVersion();
```

### <a name="return-value"></a>戻り値

オブジェクトに関連付けられているデータベース ファイルのバージョンを示す[CString です](../../atl-mfc-shared/reference/cstringt-class.md)。

### <a name="remarks"></a>解説

返される値は"major.minor"という形式のバージョン番号を表します。たとえば、"3.0" です。 製品バージョン番号 (3.0 など) は、バージョン番号 (3)、期間、およびリリース番号 (0) で構成されます。 現在までのバージョンは 1.0、1.1、2.0、および 3.0 です。

関連情報については、DAO ヘルプの「バージョン プロパティ」を参照してください。

## <a name="cdaodatabaseisopen"></a><a name="isopen"></a>データベース::IsOpen

オブジェクトがデータベースで`CDaoDatabase`現在開いているかどうかを調べます。

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>戻り値

オブジェクトが`CDaoDatabase`現在開いている場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

## <a name="cdaodatabasem_pdaodatabase"></a><a name="m_pdaodatabase"></a>データベース::m_pDAODatabase

オブジェクトの基になる DAO データベース オブジェクトの OLE`CDaoDatabase`インターフェイスへのポインターを格納します。

### <a name="remarks"></a>解説

DAO インターフェイスに直接アクセスする必要がある場合は、このポインターを使用します。

DAO を直接呼び出す方法については、[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)を参照してください。

## <a name="cdaodatabasem_pworkspace"></a><a name="m_pworkspace"></a>データベース::m_pWorkspace

データベース オブジェクトを含む[CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)オブジェクトへのポインターを格納します。

### <a name="remarks"></a>解説

ワークスペースの Databases コレクション内の他のデータベース オブジェクトへのポインターを取得するなど、ワークスペースに直接アクセスする必要がある場合は、このポインターを使用します。

## <a name="cdaodatabaseopen"></a><a name="open"></a>データベース::オープン

既存のデータベースを表す新しく構築`CDaoDatabase`されたオブジェクトを初期化するには、このメンバー関数を呼び出す必要があります。

```
virtual void Open(
    LPCTSTR lpszName,
    BOOL bExclusive = FALSE,
    BOOL bReadOnly = FALSE,
    LPCTSTR lpszConnect = _T(""));
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
既存の Jet (.MDB) データベース ファイル。 ファイル名に拡張子が付いている場合は、それが必要です。 ネットワークが一様な名前付け規則 (UNC) をサポートしている\\\\\\場合は、"\MYSERVER\\\MYSHARE\\\MYDIR \MYDB"\\などのネットワーク パスを指定することもできます。MDB". 文字列リテラルでは" " は\\C++ エスケープ文字であるため、二重円記号が必要です。

*lpszName*を使用する場合に適用される考慮事項がいくつかあります。 次の場合:

- 別のユーザーが排他アクセス用に既に開いているデータベースを参照し、MFC は[CDaoException](../../mfc/reference/cdaoexception-class.md)型の例外をスローします。 その例外をトラップして、データベースが使用できないことをユーザーに知らせます。

- 空の文字列 ("" ) で *、lpszConnect*は "ODBC;" であり、登録されているすべての ODBC データ ソース名を示すダイアログ ボックスが表示され、ユーザーがデータベースを選択できます。 ODBC データ ソースへの直接接続は避けてください。代わりにアタッチ テーブルを使用してください。

- それ以外の場合は、既存のデータベースまたは有効な ODBC データ ソース名を参照しないため`CDaoException`、MFC は型の例外をスローします。

> [!NOTE]
> DAO エラー コードの詳細については、DAOERR を参照してください。H ファイル。 関連情報については、DAO ヘルプの「トラップ可能なデータ アクセス エラー」を参照してください。

*bエクスクルーシブ*<br/>
データベースを排他 (非共有) アクセス用に開く場合は TRUE、共有アクセス用にデータベースを開く場合は FALSE のブール値。 この引数を省略すると、データベースは共有アクセス用に開かれます。

*読み取り専用*<br/>
データベースを読み取り専用アクセス用に開く場合は TRUE、読み取り/書き込みアクセス用にデータベースを開く場合は FALSE のブール値。 この引数を省略すると、データベースは読み取り/書き込みアクセスで開かれます。 すべての依存レコードセットはこの属性を継承します。

*lpszConnect*<br/>
データベースを開くときに使用する文字列式。 この文字列は、ODBC 接続引数を構成します。 ソース文字列を指定するには、排他引数と読み取り専用引数を指定する必要があります。 データベースが Jet データベース (.MDB)、この文字列は空です("")。 デフォルト値の構文 **(_T**("") ) は、アプリケーションの UNICode ビルドと ANSI ビルドの移植性を提供します。

### <a name="remarks"></a>解説

`Open`データベースを基になる DAO オブジェクトに関連付けます。 データベース オブジェクトを使用して、初期化されるまでレコードセット、テーブル定義、またはクエリ定義オブジェクトを構築することはできません。 `Open`関連付けられたワークスペースの Databases コレクションにデータベース オブジェクトを追加します。

次のようにパラメータを使用します。

- マイクロソフトジェット (.MDB) データベースでは *、lpszName*パラメータを使用し *、lpszConnect*パラメータに空の文字列を渡すか、";データベースがパスワードで保護されている場合は、"PWD=password"を指定します。MDB データベースのみ)。

- ODBC データ ソースを開く場合は、有効な ODBC 接続文字列を*lpszConnect*に渡し、空白の文字列を*lpszName*に渡します。

関連情報については、DAO ヘルプの「データベースを開くメソッド」を参照してください。

> [!NOTE]
> ISAM データベースや ODBC データ ソースなどの外部データベースにアクセスする際のパフォーマンスを向上させるには、Microsoft Jet エンジン データベース ( を使用して外部データベース テーブルをアタッチすることをお勧めします。MDB) は、データ ソースに直接接続するのではなく、データ ソースに直接接続する必要があります。

たとえば、DBMS ホストが使用できない場合などに、接続試行がタイムアウトになる可能性があります。 接続の試行が失敗した`Open`場合は、[型 CDaoException](../../mfc/reference/cdaoexception-class.md)の例外をスローします。

残りの注釈は ODBC データベースにのみ適用されます。

データベースが ODBC データベースであり、`Open`呼び出しのパラメーターに接続を行うための十分な情報が含まれていない場合、ODBC ドライバーはダイアログ ボックスを開き、ユーザーから必要な情報を取得します。 を呼び`Open`出すと、接続文字列*lpszConnect*はプライベートに格納され[、GetConnect](#getconnect)メンバー関数を呼び出して使用できます。

必要に応じて、ユーザーからパスワードなどの情報を取得するために呼`Open`び出す前に独自のダイアログ ボックスを開き、その情報を渡す接続文字列に`Open`追加できます。 また、渡した接続文字列 (Windows レジストリなど) を保存して、次回アプリケーションが`Open``CDaoDatabase`オブジェクトを呼び出す際に再利用できるようにすることもできます。

また、接続文字列を使用して、複数レベルのログイン許可 (それぞれ別`CDaoDatabase`のオブジェクト) を使用したり、データベース固有の他の情報を伝えたりすることもできます。

## <a name="cdaodatabasesetquerytimeout"></a><a name="setquerytimeout"></a>データベース::セットクエリタイムアウト

接続されているデータベースでの後続の操作がタイムアウトするまでに許容される既定の秒数をオーバーライドします。

```cpp
void SetQueryTimeout(short nSeconds);
```

### <a name="parameters"></a>パラメーター

*n秒*<br/>
クエリがタイムアウトするまでの秒数。

### <a name="remarks"></a>解説

ネットワーク アクセスの問題、クエリ処理時間が長すぎるなど、操作がタイムアウトすることがあります。 クエリ`SetQueryTimeout`のタイムアウト値を変更する場合は、レコードセットを開く前、またはレコードセットの[AddNew](../../mfc/reference/cdaorecordset-class.md#addnew) [、Update](../../mfc/reference/cdaorecordset-class.md#update)、または[Delete](../../mfc/reference/cdaorecordset-class.md#delete)のメンバー関数を呼び出す前に呼び出します。 この設定は、このオブジェクトに関連付けられている`Delete`レコードセットに対する、後続のすべての`CDaoDatabase` [Open](../../mfc/reference/cdaorecordset-class.md#open)、、、、`AddNew``Update`および呼び出しに影響します。 開いた後にレコードセットのクエリ タイムアウト値を変更しても、レコードセットの値は変更されません。 たとえば、後続の[移動](../../mfc/reference/cdaorecordset-class.md#move)操作では新しい値は使用されません。

クエリ タイムアウトの既定値は 60 秒です。 すべてのデータベースが、クエリのタイムアウト値を設定する機能をサポートしているわけではありません。 クエリのタイムアウト値を 0 に設定した場合、タイムアウトは発生しません。データベースとの通信が応答を停止する可能性があります。 この動作は、開発中に役立つ場合があります。

関連情報については、DAO ヘルプの「QueryTimeout プロパティ」を参照してください。

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CDAOワークスペースクラス](../../mfc/reference/cdaoworkspace-class.md)<br/>
[クラス](../../mfc/reference/cdaorecordset-class.md)<br/>
[クラス](../../mfc/reference/cdaotabledef-class.md)<br/>
[クラス](../../mfc/reference/cdaoquerydef-class.md)<br/>
[クラス](../../mfc/reference/cdatabase-class.md)<br/>
[クラスを呼び出す](../../mfc/reference/cdaoexception-class.md)
