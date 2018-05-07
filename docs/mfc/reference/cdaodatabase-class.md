---
title: CDaoDatabase クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 8b5ae20f06cee55a13327d5bbe7ad058047b53c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
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
|[CDaoDatabase::CDaoDatabase](#cdaodatabase)|`CDaoDatabase` オブジェクトを構築します。 呼び出す**開く**にオブジェクトをデータベースに接続します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoDatabase::CanTransact](#cantransact)|データベース トランザクションをサポートする場合は 0 以外を返します。|  
|[CDaoDatabase::CanUpdate](#canupdate)|場合は 0 以外を返します、`CDaoDatabase`オブジェクトが更新可能な (いない読み取り専用)。|  
|[CDaoDatabase::Close](#close)|データベース接続を閉じます。|  
|[CDaoDatabase::Create](#create)|基になる DAO データベース オブジェクトを作成し、初期化、`CDaoDatabase`オブジェクト。|  
|[CDaoDatabase::CreateRelation](#createrelation)|データベースのテーブル間の新しいリレーションシップを定義します。|  
|[CDaoDatabase::DeleteQueryDef](#deletequerydef)|データベースのクエリ定義のコレクションに保存されているクエリ定義オブジェクトを削除します。|  
|[CDaoDatabase::DeleteRelation](#deleterelation)|データベースのテーブル間の既存のリレーションシップを削除します。|  
|[CDaoDatabase::DeleteTableDef](#deletetabledef)|データベース内のテーブルの定義を削除します。 これは、実際のテーブルとそのすべてのデータを削除します。|  
|[CDaoDatabase::Execute](#execute)|アクション クエリを実行します。 呼び出す**Execute**の結果を返すクエリが例外をスローします。|  
|[CDaoDatabase::GetConnect](#getconnect)|接続に使用される接続文字列を返します、`CDaoDatabase`データベースへのオブジェクト。 ODBC を使用します。|  
|[CDaoDatabase::GetName](#getname)|現在使用中、データベースの名前を返します。|  
|[CDaoDatabase::GetQueryDefCount](#getquerydefcount)|データベースに対して定義されているクエリの数を返します。|  
|[CDaoDatabase::GetQueryDefInfo](#getquerydefinfo)|データベースで定義されている、指定されたクエリに関する情報を返します。|  
|[CDaoDatabase::GetQueryTimeout](#getquerytimeout)|クエリ操作をどのデータベース後の秒数を返しますが、タイムアウトします。後続のすべての影響を開く、新しく追加、更新、および (のみ) などの操作と ODBC データ ソースの他の操作は編集**Execute**呼び出しです。|  
|[CDaoDatabase::GetRecordsAffected](#getrecordsaffected)|前回の更新によって影響を受けるレコードの数を返しますの編集、または追加操作またはへの呼び出しによって**Execute**です。|  
|[CDaoDatabase::GetRelationCount](#getrelationcount)|データベース内のテーブル間で定義されているリレーションシップの数を返します。|  
|[CDaoDatabase::GetRelationInfo](#getrelationinfo)|データベース内のテーブル間で定義されているリレーションシップに関する情報を返します。|  
|[:Gettabledefcount](#gettabledefcount)|データベースで定義されているテーブルの数を返します。|  
|[Cdaodatabase::gettabledefinfo](#gettabledefinfo)|データベース内の指定されたテーブルに関する情報を返します。|  
|[CDaoDatabase::GetVersion](#getversion)|データベースに関連付けられているデータベース エンジンのバージョンを返します。|  
|[CDaoDatabase::IsOpen](#isopen)|場合は 0 以外を返します、`CDaoDatabase`オブジェクトが現在のデータベースに接続されています。|  
|[CDaoDatabase::Open](#open)|データベースへの接続を確立します。|  
|[CDaoDatabase::SetQueryTimeout](#setquerytimeout)|セットがどのデータベース後の秒数クエリ操作 (ODBC データ ソースのみ) はタイムアウトします。開く新規追加、更新、および削除操作に後続のすべての影響を与えます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoDatabase::m_pDAODatabase](#m_pdaodatabase)|基になる DAO データベース オブジェクトへのポインター。|  
|[CDaoDatabase::m_pWorkspace](#m_pworkspace)|ポインター、 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)データベースが含まれており、そのトランザクション領域を定義するオブジェクト。|  
  
## <a name="remarks"></a>コメント  
 サポートされているデータベースの形式については、次を参照してください。、 [GetName](../../mfc/reference/cdaoworkspace-class.md#getname)メンバー関数。 1 つ以上を持つことができます`CDaoDatabase`与えられた"ワークスペースで、"で表されるオブジェクトを一度にアクティブ、 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)オブジェクト。 ワークスペースは、データベース コレクションと呼ばれる、開いているデータベース オブジェクトのコレクションを保持します。  
  
> [!NOTE]
>  MFC DAO データベース クラスは、ODBC に基づいて MFC データベース クラスとは異なります。 DAO データベース クラスの名前では、"CDao"プレフィックスがあります。 クラス`CDaoDatabase`の ODBC クラスに似たインターフェイスを提供[CDatabase](../../mfc/reference/cdatabase-class.md)です。 その主な違いは`CDatabase`DBMS のオープン データベース コネクティビティ (ODBC) と ODBC ドライバーを介して、DBMS にアクセスします。 `CDaoDatabase` Microsoft Jet データベース エンジンに基づくデータ アクセス オブジェクト (DAO) を介してデータにアクセスします。 一般に、DAO に基づいて MFC クラスは ODBC; に基づいて MFC クラスよりもより高機能ですDAO ベースのクラスは、独自のデータベース エンジンを使用して、ODBC ドライバーを介してなどのデータにアクセスできます。 DAO ベースのクラスには、DAO を直接呼び出すことがなく、クラスを使用してテーブルの追加などのデータ定義言語 (DDL) 操作もサポートします。  
  
## <a name="usage"></a>使用法  
 レコード セット オブジェクトを作成するときに、暗黙的に、データベース オブジェクトを作成できます。 明示的にデータベース オブジェクトを作成することもできます。 使用して明示的に既存のデータベースを使用する`CDaoDatabase`次のいずれかの操作します。  
  
-   構築、`CDaoDatabase`オブジェクト、開いているにポインターを渡す[CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)オブジェクト。  
  
-   作成したり、 `CDaoDatabase` (MFC では、一時ワークスペース オブジェクトを作成します)、ワークスペースを指定しないでオブジェクト。  
  
 新しい Microsoft Jet を作成する (です。MDB) データベースの場合は、構築、`CDaoDatabase`オブジェクトと呼び出しの[作成](#create)メンバー関数。 操作を行います*いない*呼び出し**開く**後**作成**です。  
  
 既存のデータベースを開くには、構築、`CDaoDatabase`オブジェクトと呼び出しその[開く](#open)メンバー関数。  
  
 これらの手法のいずれかにより、DAO データベース オブジェクトをワークスペースのデータベース コレクションに追加し、データへの接続を開きます。 構築する際に[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)、[どちら](../../mfc/reference/cdaotabledef-class.md)、または[CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)接続されているデータベースに対する操作のためのオブジェクトは、これらのオブジェクトのコンス トラクターを渡す、ポインター、`CDaoDatabase`オブジェクト。 接続を使用して完了したらを呼び出す、[閉じる](#close)メンバー関数し、破棄、`CDaoDatabase`オブジェクト。 **閉じる**閉じられていないすべてのレコード セットを閉じます。  
  
## <a name="transactions"></a>トランザクション  
 データベース トランザクションの処理は、ワークスペースのレベルに指定するを参照してください、 [BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans)、 [CommitTrans](../../mfc/reference/cdaoworkspace-class.md#committrans)と[ロールバック](../../mfc/reference/cdaoworkspace-class.md#rollback)クラスのメンバー関数`CDaoWorkspace`.  
  
## <a name="odbc-connections"></a>ODBC 接続  
 ODBC データ ソースを使用するための推奨方法は、Microsoft Jet に外部テーブルをアタッチする (です。MDB) データベース。  
  
## <a name="collections"></a>コレクション  
 各データベースでは、テーブル定義、クエリ定義、レコード セット、およびリレーションシップ オブジェクトのコレクションを保持します。 クラス`CDaoDatabase`これらのオブジェクトを操作するためのメンバー関数を提供します。  
  
> [!NOTE]
>  オブジェクトは、MFC データベース オブジェクトではなく、DAO に格納されます。 MFC は、tabledef、クエリ定義、およびレコード セット オブジェクトですが、リレーションシップ オブジェクトではなくクラスを提供します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoDatabase`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
##  <a name="cantransact"></a>  CDaoDatabase::CanTransact  
 データベースがトランザクションを許可するかどうかを決定するには、このメンバー関数を呼び出します。  
  
```  
BOOL CanTransact();
```  
  
### <a name="return-value"></a>戻り値  
 データベース トランザクションをサポートする場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 トランザクションは、データベースのワークスペースで管理されます。  
  
##  <a name="canupdate"></a>  CDaoDatabase::CanUpdate  
 決定するには、このメンバー関数を呼び出すかどうか、`CDaoDatabase`オブジェクトの更新が許可されます。  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、`CDaoDatabase`オブジェクトにより、更新は、渡される 0 それ以外の場合、いずれかがあるかを示す**TRUE**で`bReadOnly`開いたときに、`CDaoDatabase`オブジェクトまたはデータベース自体が読み取り専用です。 参照してください、[開く](#open)メンバー関数。  
  
### <a name="remarks"></a>コメント  
 データベースの更新方法については、DAO ヘルプの「更新可能なプロパティ」を参照してください。  
  
##  <a name="cdaodatabase"></a>  CDaoDatabase::CDaoDatabase  
 `CDaoDatabase` オブジェクトを構築します。  
  
```  
CDaoDatabase(CDaoWorkspace* pWorkspace = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWorkspace*  
 ポインター、`CDaoWorkspace`新しいデータベース オブジェクトを格納するオブジェクト。 既定値を受け入れる場合**NULL**、コンス トラクターを作成、一時的な`CDaoWorkspace`既定 DAO のワークスペースを使用するオブジェクト。 使用してワークスペース オブジェクトへのポインターを取得できます、 [m_pWorkspace](#m_pworkspace)データ メンバーです。  
  
### <a name="remarks"></a>コメント  
 新しい Microsoft Jet を作成する場合は、オブジェクトを構築した後 (です。MDB) データベース、オブジェクトの[作成](#create)メンバー関数。 オブジェクトを呼び出して、既存のデータベースを開く場合は、代わりに、[開く](#open)メンバー関数。  
  
 オブジェクトが完了したらを呼び出す必要があります、[閉じる](#close)メンバーに機能し、破棄、`CDaoDatabase`オブジェクト。  
  
 埋め込みにできると便利な場合があります、`CDaoDatabase`ドキュメント クラスのオブジェクト。  
  
> [!NOTE]
>  A`CDaoDatabase`を開いた場合、オブジェクトは暗黙的に作成されるも、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを既存のポインターを渡さずに`CDaoDatabase`オブジェクト。 レコード セット オブジェクトを閉じると、このデータベース オブジェクトは閉じられます。  
  
##  <a name="close"></a>  CDaoDatabase::Close  
 このメンバー関数をデータベースから切断し、開いているレコード セット、テーブル定義、およびデータベースに関連付けられているクエリ定義を閉じてを呼び出します。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を呼び出す前にこれらのオブジェクトを手動で閉じることをお勧めします。 閉じる、`CDaoDatabase`オブジェクトを関連するデータベース コレクションから削除[ワークスペース](../../mfc/reference/cdaoworkspace-class.md)です。 **閉じる**を破棄しません、`CDaoDatabase`オブジェクト、同じデータベースまたは別のデータベースを開くことによって、オブジェクトを再利用できます。  
  
> [!CAUTION]
>  呼び出す、[更新](../../mfc/reference/cdaorecordset-class.md#update)メンバー関数 (保留中の編集がある場合) および**閉じる**データベースを終了する前に開いているレコード セット オブジェクトのすべてのメンバー関数。 宣言する関数を終了する場合[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)または`CDaoDatabase`スタックで、オブジェクトをデータベースが閉じ、未保存の変更は失われる、すべて保留中のトランザクションはロールバック、および、保留中の編集、データは失われます。  
  
> [!CAUTION]
>  レコード セット オブジェクトが、開いているときに、データベース オブジェクトを閉じるしようとする場合、またはその特定のワークスペースに属しているすべてのデータベース オブジェクトが開いている間に、ワークスペース オブジェクトを閉じるしようとする場合は、これらのレコード セット オブジェクトが閉じられ、保留中の更新または編集されます。ロールバックされます。 それに属するすべてのデータベース オブジェクトが開いている間は、ワークスペース オブジェクトを終了しようとすると、操作は閉じられていないレコード セット オブジェクトで発生する可能性があります、その特定のワークスペース オブジェクトに属するすべてのデータベース オブジェクトを閉じます。 データベース オブジェクトを終了しない場合、MFC は、デバッグ ビルドで、アサーションの失敗を報告します。  
  
 データベース オブジェクトが、関数のスコープ外に定義されている終了せず、関数を終了する場合は、データベース オブジェクトを明示的に閉じられるまで開いたままになりかが定義されているモジュールがスコープ外です。  
  
##  <a name="create"></a>  CDaoDatabase::Create  
 新しい Microsoft Jet を作成する (です。MDB) データベースを構築した後にこのメンバー関数を呼び出して、`CDaoDatabase`オブジェクト。  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    LPCTSTR lpszLocale = dbLangGeneral,  
    int dwOptions = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 作成しているデータベース ファイルの名前を指定する文字列式です。 だということの完全なパスとファイル名など、"c:\\\MYDB です。MDB"です。 名前を指定する必要があります。 場合は、ファイル名拡張子を指定しません。MDB が追加されます。 ネットワークでは、統一された名前付け規則 (UNC) をサポートする場合、ことができますも指定するネットワーク パスなど"\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB"です。 Microsoft Jet のみ (です。MDB) データベース ファイルは、このメンバー関数を使用して作成できます。 (二重の円記号がリテラル文字列で必要なため"\\"は、C++ のエスケープ文字です)。  
  
 `lpszLocale`  
 データベースを作成するための照合順序を指定するために使用する文字列式です。 既定値は**dbLangGeneral**です。 指定できる値は次のとおりです。  
  
- **dbLangGeneral**英語、ドイツ語、フランス語、ポルトガル語、イタリア語、および最新のスペイン語  
  
- **dbLangArabic**アラビア語  
  
- **dbLangCyrillic**ロシア語  
  
- **dbLangCzech**チェコ語  
  
- **dbLangDutch**オランダ語  
  
- **dbLangGreek**ギリシャ語  
  
- **dbLangHebrew**ヘブライ語  
  
- **dbLangHungarian**ハンガリー語  
  
- **dbLangIcelandic**アイスランド語  
  
- **dbLangNordic**スカンジナビア語 (Microsoft Jet データベース エンジンのバージョン 1.0 のみ)  
  
- **dbLangNorwdan**ノルウェー語、デンマーク語  
  
- **dbLangPolish**ポーランド語  
  
- **dbLangSpanish**従来のスペイン語  
  
- **dbLangSwedfin**スウェーデン語、フィンランド語  
  
- **dbLangTurkish**トルコ語  
  
 `dwOptions`  
 1 つまたは複数のオプションを示す整数。 指定できる値は次のとおりです。  
  
- **dbEncrypt**暗号化されたデータベースを作成します。  
  
- **dbVersion10** Microsoft Jet データベースのバージョン 1.0 でデータベースを作成します。  
  
- **dbVersion11** Microsoft Jet データベースのバージョン 1.1 でデータベースを作成します。  
  
- **dbVersion20** Microsoft Jet データベースのバージョン 2.0 でデータベースを作成します。  
  
- **dbVersion30** Microsoft Jet データベースのバージョン 3.0 とデータベースを作成します。  
  
 暗号化の定数を省略すると、暗号化されていないデータベースが作成されます。 バージョン定数は 1 つだけ指定できます。 バージョンの定数を省略すると、Microsoft Jet データベースのバージョン 3.0 を使用するデータベースが作成されます。  
  
> [!CAUTION]
>  データベースが暗号化されていない場合、可能な場合でもある直接ファイルを読み取るバイナリ ディスク、データベースを構成する、ユーザー/パスワードのセキュリティを実装します。  
  
### <a name="remarks"></a>コメント  
 **作成**データベース ファイルと基になる DAO データベース オブジェクトを作成し、C++ オブジェクトを初期化します。 オブジェクトは、関連付けられているワークスペースのデータベース コレクションに追加されます。 データベース オブジェクトは、開いている状態です。呼び出す必要はありません**開く**後**作成**です。  
  
> [!NOTE]
>  **作成**、Microsoft Jet のみを作成することができます (です。MDB) データベース。 ISAM データベースまたは ODBC データベースを作成することはできません。  
  
##  <a name="createrelation"></a>  CDaoDatabase::CreateRelation  
 データベースの主テーブル内の 1 つ以上のフィールドと外部テーブル (データベース内の別のテーブル) 内の 1 つ以上のフィールド間の関係を確立するためにこのメンバー関数を呼び出します。  
  
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
 `lpszName`  
 リレーションシップ オブジェクトの一意の名前。 名前は文字で始める必要があり、最大 40 文字を含めることができます。 数字を含めることができ、アンダー スコア文字ですが、区切り記号やスペースを含めることはできません。  
  
 `lpszTable`  
 リレーションシップの主テーブルの名前。 テーブルが存在しない場合、MFC に型の例外がスロー [CDaoException](../../mfc/reference/cdaoexception-class.md)です。  
  
 `lpszForeignTable`  
 リレーションシップの外部テーブルの名前。 テーブルが存在しない場合、MFC に型の例外がスロー`CDaoException`です。  
  
 `lAttributes`  
 リレーションシップの種類に関する情報を含む long 値です。 この値を使用すると、その他の処理の間の参照整合性を適用します。 ビットごとの OR 演算子を使用することができます ( **&#124;**) である限り、組み合わせの意味)、次の値のいずれかを結合します。  
  
- **dbRelationUnique**リレーションシップは一対一です。  
  
- **dbRelationDontEnforce**関係はありません (参照整合性がありません) を適用します。  
  
- **dbRelationInherited**リレーションシップが 2 つの接続されているテーブルを含む固定データベースに存在します。  
  
- **これら**が連鎖的に更新プログラム (連鎖については、「解説」を参照してください)。  
  
- **dbRelationDeleteCascade**が連鎖的に削除します。  
  
 *lpszField*  
 主テーブル内のフィールドの名前を表す null で終わる文字列へのポインター (付けた`lpszTable`)。  
  
 *lpszForeignField*  
 外部テーブルのフィールドの名前を表す null で終わる文字列へのポインター (付けた`lpszForeignTable`)。  
  
 *relinfo*  
 参照、 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)を作成する関係に関する情報を含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 リレーションシップには、クエリ、またはアタッチ外部データベースからテーブルを含めることはできません。  
  
 リレーションには 2 つのテーブルの 1 つのフィールドが含まれている場合は、関数の最初のバージョンを使用します。 リレーションシップに複数のフィールドが含まれている場合は、2 番目のバージョンを使用します。 リレーションシップ内のフィールドの最大数は 14 です。  
  
 この操作は、基になる DAO リレーションシップ オブジェクトを作成が、これは、MFC 実装の詳細関係オブジェクトの MFC のカプセル化は、クラス内に含まれるため`CDaoDatabase`です。 MFC では、リレーションのクラスを提供していません。  
  
 リレーションシップを cascade 操作をアクティブ化するオブジェクトの属性を設定すると、データベース エンジンは自動的に更新または関連の主キー テーブルに変更が加えられたその他の 1 つまたは複数のテーブル内のレコードを削除します。  
  
 たとえば、Customers テーブルと Orders テーブルの間で連鎖削除のリレーションシップを確立するとします。 Customers テーブルからレコードを削除すると、その顧客に関連する受注テーブル内のレコードも削除されます。 さらに、他のテーブルと Orders テーブルの間で連鎖削除のリレーションシップを確立すると、それらのテーブルからレコードを自動的に削除、Customers テーブルからレコードを削除するとします。  
  
 関連情報については、DAO ヘルプの「CreateRelation メソッド」を参照してください。  
  
##  <a name="deletequerydef"></a>  CDaoDatabase::DeleteQueryDef  
 指定したクエリ定義を削除するには、このメンバー関数を呼び出す: クエリを保存 — から、`CDaoDatabase`オブジェクトのクエリ定義のコレクション。  
  
```  
void DeleteQueryDef(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 削除する保存済みのクエリの名前。  
  
### <a name="remarks"></a>コメント  
 その後、そのクエリがで定義されていないデータベース。  
  
 クエリ定義オブジェクトを作成する方法の詳細については、クラスを参照してください。 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)です。 クエリ定義オブジェクトが特定の関連付けられる`CDaoDatabase`オブジェクトを構築するとき、`CDaoQueryDef`オブジェクト、データベース オブジェクトへのポインターを渡します。  
  
##  <a name="deleterelation"></a>  CDaoDatabase::DeleteRelation  
 データベース オブジェクトの関係のコレクションから既存のリレーションシップを削除するには、このメンバー関数を呼び出します。  
  
```  
void DeleteRelation(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 削除するリレーションシップの名前。  
  
### <a name="remarks"></a>コメント  
 その後、不要になったリレーションが存在します。  
  
 関連情報については、「Delete メソッド」DAO ヘルプのトピックを参照してください。  
  
##  <a name="deletetabledef"></a>  CDaoDatabase::DeleteTableDef  
 指定したテーブルとそのすべてのデータからを削除するには、このメンバー関数を呼び出す、`CDaoDatabase`オブジェクトのテーブル定義のコレクション。  
  
```  
void DeleteTableDef(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 削除するテーブル定義の名前。  
  
### <a name="remarks"></a>コメント  
 その後、そのテーブルは、不要になったデータベースに定義されます。  
  
> [!NOTE]
>  システム テーブルを削除しないことに注意します。  
  
 テーブル定義のオブジェクトを作成する方法の詳細については、クラスを参照してください。[どちら](../../mfc/reference/cdaotabledef-class.md)です。 テーブル定義オブジェクトが特定の関連付けられる`CDaoDatabase`オブジェクトを構築するとき、`CDaoTableDef`オブジェクト、データベース オブジェクトへのポインターを渡します。  
  
 関連情報については、「Delete メソッド」DAO ヘルプのトピックを参照してください。  
  
##  <a name="execute"></a>  CDaoDatabase::Execute  
 アクション クエリを実行するか、データベースで SQL ステートメントを実行するには、このメンバー関数を呼び出します。  
  
```  
void Execute(
    LPCTSTR lpszSQL,  
    int nOptions = dbFailOnError);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszSQL`  
 実行する有効な SQL コマンドを含む null で終わる文字列へのポインター。  
  
 `nOptions`  
 クエリの整合性に関連するオプションを指定する整数。 ビットごとの OR 演算子を使用することができます ( **&#124;**) 定数は、次のいずれかを結合する (組み合わせ意味をなさなく指定 — などを組み合わせて**組み合わせて**で**指定できます**)。  
  
- **dbDenyWrite**他のユーザーへの書き込み権限を拒否します。  
  
- **組み合わせて**(既定) の一貫性のない更新します。  
  
- **指定できます**一貫性のある更新プログラム。  
  
- **dbSQLPassThrough** SQL パススルーします。 処理のために、ODBC データ ソースに渡される SQL ステートメントが発生します。  
  
- **dbFailOnError**エラーが発生した場合は、更新をロールバックします。  
  
- **dbSeeChanges**別のユーザーが編集してデータを変更する場合は、実行時エラーを生成します。  
  
> [!NOTE]
>  両方**組み合わせて**と**指定できます**が含まれるか、結果に既定値がどちらもが含まれる場合は、します。 これらの定数の詳細については、"Execute Method"DAO ヘルプのトピックを参照してください。  
  
### <a name="remarks"></a>コメント  
 **実行**アクション クエリ、または結果を返さない SQL パススルー クエリに対してのみ機能します。 レコードを返す select クエリでは機能しません。  
  
 定義とアクションのクエリについては、「アクション クエリ」と"Execute Method"DAO ヘルプのトピックを参照してください。  
  
> [!TIP]
>  構文的に正しい SQL ステートメントと、適切なアクセス許可を与え、 **Execute**メンバー関数はも失敗しませんしない場合、1 行を変更または削除します。 そのため、常に使用して、 **dbFailOnError**オプションを使用する場合、 **Execute**更新プログラムを実行またはクエリを削除するメンバー関数。 このオプションは、型の例外をスローする MFC [CDaoException](../../mfc/reference/cdaoexception-class.md)し影響を受けたレコードのいずれかがロックされているとできませんを更新または削除の場合は、すべての正常な変更をロールバックします。 常に呼び出すことのできる注`GetRecordsAffected`に影響を受けたレコードの数を参照してください。  
  
 呼び出す、 [GetRecordsAffected](#getrecordsaffected)最新によって影響を受けたレコードの数を決定するデータベース オブジェクトのメンバー関数**Execute**呼び出します。 たとえば、`GetRecordsAffected`削除、更新、またはアクション クエリを実行するときに挿入されるレコードの数に関する情報を返します。 返されるカウントを cascade を更新または削除時の関連テーブルの変更が有効では反映されません。  
  
 **実行**はレコード セットを返しません。 使用して**Execute**レコードを選択するクエリで MFC の種類の例外をスローすると、`CDaoException`です。 (がない`ExecuteSQL`メンバー関数に似ています`CDatabase::ExecuteSQL`)。  
  
##  <a name="getconnect"></a>  CDaoDatabase::GetConnect  
 接続に使用する接続文字列を取得するには、このメンバー関数を呼び出す、 `CDaoDatabase` ODBC または ISAM データベースへのオブジェクト。  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>戻り値  
 接続文字列の場合は[開く](#open)ODBC データ ソースで正常に呼び出される、それ以外のされましたが、空の文字列。 Microsoft Jet 用 (です。MDB) データベースの場合は、文字列は常に空で使用するために設定していない場合、 **dbSQLPassThrough**オプションと共に使用、 [Execute](#execute)メンバー関数、またはレコード セットを開くときに使用します。  
  
### <a name="remarks"></a>コメント  
 文字列は、開いているデータベースまたはパススルー クエリで使用されるデータベースのソースに関する情報を提供します。 接続文字列は、データベースの型指定子は、セミコロンで区切られた 0 個以上のパラメーターで構成されます。  
  
> [!NOTE]
>  MFC DAO クラスを使用して ODBC 経由でデータ ソースに接続は、接続されているテーブルを使用して接続するより非効率です。  
  
> [!NOTE]
>  接続文字列を使用して、ODBC および必要に応じて特定 ISAM ドライバーに追加情報を渡します。 を使用されません。MDB データベース。 Microsoft Jet データベースのベース テーブルでは、接続文字列は、空の文字列 ("") 使用する場合を除き、SQL のパススルー クエリの戻り値を上記で説明されているとします。  
  
 参照してください、[開く](#open)接続文字列を作成する方法の詳細については、メンバー関数。 接続文字列が設定されると、**開く**呼び出し、後で使用できます、種類、パス、データベースのユーザー ID、パスワード、または ODBC データ ソースを決定する設定を確認します。  
  
##  <a name="getname"></a>  CDaoDatabase::GetName  
 既存のデータベース ファイルの名前を現在開いているデータベースの名前または登録された ODBC データ ソースの名前を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、データベースのファイル名と完全パスそれ以外の場合、空[CString](../../atl-mfc-shared/reference/cstringt-class.md)です。  
  
### <a name="remarks"></a>コメント  
 ネットワーク パスを指定できますも、ネットワークでは、統一された名前付け規則 (UNC) をサポートする場合、たとえば、"\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB です。MDB"です。 (二重の円記号がリテラル文字列で必要なため"\\"は、C++ のエスケープ文字です)。  
  
 たとえば、見出しにこの名前を表示する可能性があります、します。 名前を取得中にエラーが発生する場合、MFC に型の例外がスロー [CDaoException](../../mfc/reference/cdaoexception-class.md)です。  
  
> [!NOTE]
>  パフォーマンス向上のため、外部データベースにアクセスしているときにことをお勧め外部データベース テーブルは、Microsoft Jet データベースに接続する (です。MDB)、データ ソースに直接接続するのではなくです。  
  
 データベースの種類は、ファイルまたはディレクトリに、次のようにパスが指すで示されます。  
  
|パス名が指す.|データベースの種類|  
|--------------------------|-------------------|  
|.MDB ファイル|Microsoft Jet データベース (Access)|  
|格納するディレクトリ。DBF ファイル|dBASE データベース|  
|格納するディレクトリ。XLS ファイル|Microsoft Excel データベース|  
|格納するディレクトリ。PDX ファイル|Paradox データベース|  
|データベース ファイルを適切に書式付きテキストを含むディレクトリ|テキスト形式のデータベース|  
  
 SQL Server、Oracle などの ODBC データベース、データベースの接続文字列は、ODBC によって登録されているデータ ソース名 (DSN) を識別します。  
  
##  <a name="getquerydefcount"></a>  CDaoDatabase::GetQueryDefCount  
 データベースのクエリ定義のコレクションで定義されているクエリの数を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetQueryDefCount();
```  
  
### <a name="return-value"></a>戻り値  
 データベースで定義されているクエリの数。  
  
### <a name="remarks"></a>コメント  
 `GetQueryDefCount` QueryDefs コレクション内のすべてのクエリ定義をループする必要がある場合に便利ですが。 コレクション内の指定されたクエリに関する情報を取得するには、次を参照してください。 [GetQueryDefInfo](#getquerydefinfo)です。  
  
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
 `nIndex`  
 インデックスで検索する場合、データベースのクエリ定義のコレクションで定義済みのクエリのインデックス。  
  
 *querydefinfo*  
 参照、 [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md)要求された情報を表すオブジェクト。  
  
 `dwInfoOptions`  
 取得するレコード セットに関する情報を指定するオプション。 使用可能なオプションは、関数は、レコード セットを返しますもここで表示されます。  
  
- `AFX_DAO_PRIMARY_INFO` (既定値)名前、型  
  
- `AFX_DAO_SECONDARY_INFO` プライマリ情報に加えて: 作成日付、前回の更新の日付をレコードを返す、更新可能  
  
- `AFX_DAO_ALL_INFO` プライマリとセカンダリの情報に加えて: SQL では、接続、補足  
  
 `lpszName`  
 名前で検索する場合、データベースで定義されたクエリの名前を含む文字列。  
  
### <a name="remarks"></a>コメント  
 データベースのクエリ定義のコレクション内のインデックスまたはクエリの名前のいずれかにクエリを選択できるように、関数の 2 つのバージョンが提供されます。  
  
 返される情報の詳細については*querydefinfo*を参照してください、 [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報項目に対応するは`dwInfoOptions`します。 1 つのレベルの情報を要求すると、その情報も同様のレベルを取得します。  
  
##  <a name="getquerytimeout"></a>  CDaoDatabase::GetQueryTimeout  
 現在接続されているデータベースの後続の処理がタイムアウトするまで許可する秒数を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetQueryTimeout();
```  
  
### <a name="return-value"></a>戻り値  
 秒のタイムアウト値を含む短整数です。  
  
### <a name="remarks"></a>コメント  
 操作は、ネットワーク アクセスの問題、過剰なクエリ処理時間などによりタイムアウト可能性があります。 すべてのオープン状態に影響を与える設定が有効になっているときに、新しく追加、更新、およびこれに関連付けられているすべてのレコード セットでの delete 操作`CDaoDatabase`オブジェクト。 現在のタイムアウト設定を変更するには呼び出すことによって[SetQueryTimeout](#setquerytimeout)です。 かっこの後、レコード セットのクエリ タイムアウト値を変更しても、レコード セットの値は変わりません。 例については、後続[移動](../../mfc/reference/cdaorecordset-class.md#move)操作は、新しい値を使用しないでください。 データベース エンジンが初期化されたときに既定値は初期設定されます。  
  
 クエリのタイムアウトの既定値は、Windows レジストリから取得されます。 レジストリ設定がない場合は、既定値は 60 秒にします。 すべてのデータベースでは、クエリのタイムアウト値を設定する機能をサポートします。 0 の場合のクエリ タイムアウト値を設定すると、タイムアウトが発生しなかった場合およびデータベースとの通信が応答を停止します。 この動作は、開発時に役立ちます。 MFC が型の例外をスローする場合は、呼び出しが失敗すると、 [CDaoException](../../mfc/reference/cdaoexception-class.md)です。  
  
 関連情報については、DAO ヘルプの「QueryTimeout プロパティ」を参照してください。  
  
##  <a name="getrecordsaffected"></a>  CDaoDatabase::GetRecordsAffected  
 最新の呼び出しによって影響を受けたレコードの数を決定するには、このメンバー関数を呼び出す、 [Execute](#execute)メンバー関数。  
  
```  
long GetRecordsAffected();
```  
  
### <a name="return-value"></a>戻り値  
 影響を受けたレコードの数を表す長整数。  
  
### <a name="remarks"></a>コメント  
 返される値には、削除、更新、またはを使用して実行アクション クエリによって挿入されたレコードの数が含まれています。 **Execute**です。 返されるカウントを cascade を更新または削除時の関連テーブルの変更が有効では反映されません。  
  
 関連情報については、DAO ヘルプの「RecordsAffected プロパティ」を参照してください。  
  
##  <a name="getrelationcount"></a>  CDaoDatabase::GetRelationCount  
 データベース内のテーブル間で定義されているリレーションシップの数を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetRelationCount();
```  
  
### <a name="return-value"></a>戻り値  
 データベース内のテーブル間で定義されているリレーションシップの数。  
  
### <a name="remarks"></a>コメント  
 **GetRelationCount**はデータベースの Relations コレクションで定義されているすべての関係をループする必要がある場合に便利です。 コレクション内の特定の関係に関する情報を取得するには、次を参照してください。 [GetRelationInfo](#getrelationinfo)です。  
  
 リレーションシップの概念を示すためには、Suppliers テーブルと一対多のリレーションシップを持つ可能性があります製品のテーブルを検討してください。 このリレーションシップでは、1 つの仕入先は 1 つ以上の製品を提供できます。 その他の関係は、一対一および多対多です。  
  
##  <a name="getrelationinfo"></a>  CDaoDatabase::GetRelationInfo  
 データベースの Relations コレクションで指定されたリレーションシップに関する情報を取得するには、このメンバー関数を呼び出します。  
  
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
 `nIndex`  
 インデックスで検索する場合、データベースの Relations コレクションでのリレーションシップ オブジェクトのインデックス。  
  
 *relinfo*  
 参照、 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)要求された情報を表すオブジェクト。  
  
 `dwInfoOptions`  
 取得する関係に関する情報を指定するオプションです。 使用可能なオプションは、関数が返す関連情報が何もここで表示されます。  
  
- `AFX_DAO_PRIMARY_INFO` (既定値)名前、テーブル、外部テーブル  
  
- `AFX_DAO_SECONDARY_INFO` 属性、フィールドの情報  
  
 フィールドの情報は、 [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md)リレーションシップに関係する主テーブルからフィールドを含むオブジェクト。  
  
 `lpszName`  
 名前で検索する場合、リレーションシップ オブジェクトの名前を含む文字列。  
  
### <a name="remarks"></a>コメント  
 この関数の 2 つのバージョンは、インデックスまたは名前のいずれかのアクセスを提供します。 返される情報の詳細については*relinfo*を参照してください、 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報項目に対応するは`dwInfoOptions`します。 1 つのレベルの情報を要求する場合も以前レベルにある情報を取得します。  
  
> [!NOTE]
>  連鎖操作をアクティブ化するオブジェクトの属性リレーションシップを設定した場合 ( **dbRelationUpdateCascades**または**dbRelationDeleteCascades**)、Microsoft Jet データベース エンジンを自動的に更新または関連の主キー テーブルを変更するときは、その他の 1 つまたは複数のテーブル内のレコードを削除します。 たとえば、Customers テーブルと Orders テーブルの間で連鎖削除のリレーションシップを確立するとします。 Customers テーブルからレコードを削除すると、その顧客に関連する受注テーブル内のレコードも削除されます。 さらに、他のテーブルと Orders テーブルの間で連鎖削除のリレーションシップを確立すると、それらのテーブルからレコードを自動的に削除、Customers テーブルからレコードを削除するとします。  
  
##  <a name="gettabledefcount"></a>  :Gettabledefcount  
 データベースで定義されているテーブルの数を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetTableDefCount();
```  
  
### <a name="return-value"></a>戻り値  
 データベースで定義されているテーブルの数。  
  
### <a name="remarks"></a>コメント  
 `GetTableDefCount` データベースのテーブル定義のコレクション内のすべてのテーブル定義をループする必要がある場合に役立ちます。 コレクションの指定されたテーブルに関する情報を取得するには、次を参照してください。[プライマリ](#gettabledefinfo)です。  
  
##  <a name="gettabledefinfo"></a>  Cdaodatabase::gettabledefinfo  
 各種のデータベースで定義されているテーブルに関する情報を取得するには、このメンバー関数を呼び出します。  
  
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
 `nIndex`  
 インデックスで検索する場合、データベースのテーブル定義のコレクション内のテーブル定義オブジェクトのインデックス。  
  
 `tabledefinfo`  
 参照、 [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md)要求された情報を表すオブジェクト。  
  
 `dwInfoOptions`  
 取得するテーブルに関する情報を指定するオプション。 使用可能なオプションは、関数が返す関連情報が何もここで表示されます。  
  
- `AFX_DAO_PRIMARY_INFO` (既定値)更新可能な名前、属性  
  
- `AFX_DAO_SECONDARY_INFO` プライマリ情報に加えて: 日付 Created、最終更新日、ソース テーブル名、接続  
  
- `AFX_DAO_ALL_INFO` プライマリとセカンダリの情報に加えて: 検証規則、検証のテキストのレコードの数  
  
 `lpszName`  
 名前で検索する場合、テーブル定義オブジェクトの名前。  
  
### <a name="remarks"></a>コメント  
 関数の 2 つのバージョンは、テーブルを選択するには、データベースのテーブル定義のコレクション内のインデックスまたはテーブルの名前のいずれかのように提供されます。  
  
 返される情報の詳細については`tabledefinfo`を参照してください、 [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報項目に対応するは`dwInfoOptions`します。 1 つのレベルの情報を要求すると、そのレベルを同様の情報を取得します。  
  
> [!NOTE]
>  `AFX_DAO_ALL_INFO`オプションは、取得に時間がかかることができる情報を提供します。 この場合、テーブル内のレコードのカウントが非常に時間がかかる場合は、多数のレコードがある可能性があります。  
  
##  <a name="getversion"></a>  CDaoDatabase::GetVersion  
 Microsoft Jet データベース ファイルのバージョンを確認するには、このメンバー関数を呼び出します。  
  
```  
CString GetVersion();
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトに関連付けられているデータベース ファイルのバージョンを示すです。  
  
### <a name="remarks"></a>コメント  
 返される値は、フォーム"<major.minor"; でバージョン番号を表しますたとえば、「3.0」です。 製品のバージョン番号 (たとえば、3.0) は、バージョン番号 (3)、ピリオド、およびリリース番号 (0) で構成されます。 日付のバージョンは 1.0、1.1、2.0 および 3.0 です。  
  
 関連情報については、DAO ヘルプの「バージョン プロパティ」を参照してください。  
  
##  <a name="isopen"></a>  CDaoDatabase::IsOpen  
 決定するには、このメンバー関数を呼び出すかどうか、`CDaoDatabase`オブジェクトがデータベースで現在開かれています。  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、`CDaoDatabase`オブジェクトが現在開いている。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_pdaodatabase"></a>  CDaoDatabase::m_pDAODatabase  
 DAO データベース オブジェクトの基になる OLE インターフェイスへのポインターが含まれています、`CDaoDatabase`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 DAO インターフェイスに直接アクセスする必要がある場合は、このポインターを使用します。  
  
 呼び出し元の DAO に関する情報を参照してください、直接[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)です。  
  
##  <a name="m_pworkspace"></a>  CDaoDatabase::m_pWorkspace  
 ポインターが含まれています、 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)データベース オブジェクトを含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 ワークスペースに直接アクセスする必要がある場合は、このポインターを使用して、たとえば、ワークスペースのデータベース コレクション内の他のデータベース オブジェクトへのポインターを取得するためです。  
  
##  <a name="open"></a>  CDaoDatabase::Open  
 新しく構築された初期化するためにこのメンバー関数を呼び出す必要があります`CDaoDatabase`を既存のデータベースを表すオブジェクト。  
  
```  
virtual void Open(
    LPCTSTR lpszName,  
    BOOL bExclusive = FALSE,  
    BOOL bReadOnly = FALSE,  
    LPCTSTR lpszConnect = _T(""));
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 既存の Microsoft Jet の名前を指定する文字列式 (です。MDB) データベース ファイルです。 ファイル名に拡張子がある場合が必要です。 ネットワークでは、統一された名前付け規則 (UNC) をサポートする場合、ことができますも指定するネットワーク パスなど"\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB です。MDB"です。 (二重の円記号がリテラル文字列で必要なため"\\"は、C++ のエスケープ文字です)。  
  
 使用する場合に、いくつかの考慮事項が適用`lpszName`です。 場合に。  
  
-   既に別のユーザーの種類の例外がスロー MFC によって排他的に開かれているデータベースを指す[CDaoException](../../mfc/reference/cdaoexception-class.md)です。 例外をトラップすることで、ユーザー データベースが使用できないことを確認します。  
  
-   空の文字列 ("") と*lpszConnect*は"ODBC;"、ユーザーがデータベースを選択できるように、登録されているすべての ODBC データ ソース名を一覧表示するダイアログ ボックスが表示されます。 ODBC データ ソースへの直接接続を避ける必要があります。接続されているテーブルを使用します。  
  
-   それ以外の場合を示さない既存のデータベースまたは有効な ODBC データ ソース名、型の例外がスロー MFC`CDaoException`です。  
  
> [!NOTE]
>  DAO のエラー コードの詳細については、DAOERR を参照してください。H ファイルです。 関連情報については、「トラップできるデータ アクセス エラー」DAO ヘルプのトピックを参照してください。  
  
 `bExclusive`  
 ブール値が**TRUE**かどうか、データベースは (共有) の排他アクセス用に開かれると**FALSE**データベースが共有アクセス用に開かれる場合。 この引数を省略した場合、データベースが共有アクセス用に開きます。  
  
 `bReadOnly`  
 ブール値である**TRUE**かどうか、データベースは読み取り専用アクセス用に開かれると**FALSE**データベースが読み取り/書き込みアクセス用に開かれる場合。 この引数を省略した場合、データベースは読み取り/書き込みアクセスで開かです。 依存するすべてのレコード セットは、この属性を継承します。  
  
 `lpszConnect`  
 データベースを開くに使用する文字列式です。 この文字列の構成、ODBC 接続の引数。 ソース文字列を指定および排他的読み取り専用の引数を指定する必要があります。 場合は、データベースは、Microsoft Jet データベース (です。MDB)、この文字列が空 ("") です。 既定値の構文: **_T**(""): Unicode と ANSI の移植性がアプリケーションのビルドを提供します。  
  
### <a name="remarks"></a>コメント  
 **開いている**を基になる DAO オブジェクト、データベースに関連付けます。 初期化されるまで、レコード セット、テーブル定義、またはクエリ定義オブジェクトを構築するために、データベース オブジェクトを使用することはできません。 **開いている**データベース オブジェクトに関連付けられているワークスペースのデータベース コレクションに追加します。  
  
 次のように、パラメーターを使用します。  
  
-   Microsoft Jet 開こうとしている場合 (です。MDB) データベースを使用して、`lpszName`パラメーターと、空の文字列のパス、`lpszConnect`パラメーターまたはパスの形式のパスワード文字列";PWD = パスワード"データベースがパスワードで保護されている場合 (です。MDB データベースの場合のみ)。  
  
-   ODBC データ ソース、開いている場合に有効な ODBC 接続文字列を渡す`lpszConnect`と空の文字列で`lpszName`です。  
  
 関連情報については、DAO ヘルプの「OpenDatabase メソッド」を参照してください。  
  
> [!NOTE]
>  外部データベース、ISAM データベースなど、ODBC データ ソースにアクセスするときにパフォーマンスを向上させることをお勧め外部データベース テーブルは、Microsoft Jet エンジン データベースに接続する (です。MDB)、データ ソースに直接接続するのではなくです。  
  
 たとえば、DBMS ホストが使用できない場合は、接続試行がタイムアウトする可能性はします。 接続の試行が失敗した場合、**開く**型の例外をスロー [CDaoException](../../mfc/reference/cdaoexception-class.md)です。  
  
 ODBC データベースのみに解説が適用されます。  
  
 かどうか、データベースは、ODBC データベースとでは、パラメーター、**開く**呼び出しは、接続を作成するための十分な情報を含まない、ODBC ドライバーは、ユーザーから、必要な情報を取得するダイアログ ボックスを開きます。 呼び出すと**開く**、接続文字列`lpszConnect`非公開で格納されている、使用可能なを呼び出して、 [GetConnect](#getconnect)メンバー関数。  
  
 呼び出す前に、独自のダイアログ ボックスを開くことができる場合は、**開く**パスワードなど、ユーザーから情報を取得し、その情報、接続文字列を追加に渡す**開く**です。 または、接続文字列を渡す (おそらく、Windows レジストリ) できる再利用できるように、次の時間をアプリケーション呼び出しすることができます**開く**上、`CDaoDatabase`オブジェクト。  
  
 複数レベルのログインの権限の接続文字列を使用することもできます (それぞれ異なるを`CDaoDatabase`オブジェクト) またはその他のデータベースに固有の情報を伝達します。  
  
##  <a name="setquerytimeout"></a>  CDaoDatabase::SetQueryTimeout  
 既定の接続されているデータベースのタイムアウトの後続の処理になるまでの秒数をオーバーライドする場合は、このメンバー関数を呼び出します。  
  
```  
void SetQueryTimeout(short nSeconds);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSeconds`  
 クエリ試行するまでに許可する秒数がタイムアウトになりました。  
  
### <a name="remarks"></a>コメント  
 操作は、ネットワーク アクセスの問題や、過剰なクエリの処理時間のためタイムアウト可能性があります。 呼び出す`SetQueryTimeout`またはレコード セットの前に、レコード セットを開く前に[AddNew](../../mfc/reference/cdaorecordset-class.md#addnew)、[更新](../../mfc/reference/cdaorecordset-class.md#update)、または[削除](../../mfc/reference/cdaorecordset-class.md#delete)メンバー関数の場合は、クエリを変更します。タイムアウト値。 後続のすべての設定に影響[開く](../../mfc/reference/cdaorecordset-class.md#open)、 `AddNew`、**更新**、および**削除**これに関連付けられているすべてのレコード セットへの呼び出し`CDaoDatabase`オブジェクト。 かっこの後、レコード セットのクエリ タイムアウト値を変更しても、レコード セットの値は変わりません。 例については、後続[移動](../../mfc/reference/cdaorecordset-class.md#move)操作は、新しい値を使用しないでください。  
  
 クエリのタイムアウトの既定値は、60 秒です。 すべてのデータベースでは、クエリのタイムアウト値を設定する機能をサポートします。 0 の場合のクエリ タイムアウト値を設定すると、タイムアウトが発生しなかった場合データベースとの通信が応答を停止します。 この動作は、開発時に役立ちます。  
  
 関連情報については、DAO ヘルプの「QueryTimeout プロパティ」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoWorkspace クラス](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)   
 [どちらのクラス](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)   
 [CDatabase クラス](../../mfc/reference/cdatabase-class.md)   
 [CDaoException クラス](../../mfc/reference/cdaoexception-class.md)
