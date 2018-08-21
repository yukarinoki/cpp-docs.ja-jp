---
title: CDaoWorkspace クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoWorkspace
- AFXDAO/CDaoWorkspace
- AFXDAO/CDaoWorkspace::CDaoWorkspace
- AFXDAO/CDaoWorkspace::Append
- AFXDAO/CDaoWorkspace::BeginTrans
- AFXDAO/CDaoWorkspace::Close
- AFXDAO/CDaoWorkspace::CommitTrans
- AFXDAO/CDaoWorkspace::CompactDatabase
- AFXDAO/CDaoWorkspace::Create
- AFXDAO/CDaoWorkspace::GetDatabaseCount
- AFXDAO/CDaoWorkspace::GetDatabaseInfo
- AFXDAO/CDaoWorkspace::GetIniPath
- AFXDAO/CDaoWorkspace::GetIsolateODBCTrans
- AFXDAO/CDaoWorkspace::GetLoginTimeout
- AFXDAO/CDaoWorkspace::GetName
- AFXDAO/CDaoWorkspace::GetUserName
- AFXDAO/CDaoWorkspace::GetVersion
- AFXDAO/CDaoWorkspace::GetWorkspaceCount
- AFXDAO/CDaoWorkspace::GetWorkspaceInfo
- AFXDAO/CDaoWorkspace::Idle
- AFXDAO/CDaoWorkspace::IsOpen
- AFXDAO/CDaoWorkspace::Open
- AFXDAO/CDaoWorkspace::RepairDatabase
- AFXDAO/CDaoWorkspace::Rollback
- AFXDAO/CDaoWorkspace::SetDefaultPassword
- AFXDAO/CDaoWorkspace::SetDefaultUser
- AFXDAO/CDaoWorkspace::SetIniPath
- AFXDAO/CDaoWorkspace::SetIsolateODBCTrans
- AFXDAO/CDaoWorkspace::SetLoginTimeout
- AFXDAO/CDaoWorkspace::m_pDAOWorkspace
dev_langs:
- C++
helpviewer_keywords:
- CDaoWorkspace [MFC], CDaoWorkspace
- CDaoWorkspace [MFC], Append
- CDaoWorkspace [MFC], BeginTrans
- CDaoWorkspace [MFC], Close
- CDaoWorkspace [MFC], CommitTrans
- CDaoWorkspace [MFC], CompactDatabase
- CDaoWorkspace [MFC], Create
- CDaoWorkspace [MFC], GetDatabaseCount
- CDaoWorkspace [MFC], GetDatabaseInfo
- CDaoWorkspace [MFC], GetIniPath
- CDaoWorkspace [MFC], GetIsolateODBCTrans
- CDaoWorkspace [MFC], GetLoginTimeout
- CDaoWorkspace [MFC], GetName
- CDaoWorkspace [MFC], GetUserName
- CDaoWorkspace [MFC], GetVersion
- CDaoWorkspace [MFC], GetWorkspaceCount
- CDaoWorkspace [MFC], GetWorkspaceInfo
- CDaoWorkspace [MFC], Idle
- CDaoWorkspace [MFC], IsOpen
- CDaoWorkspace [MFC], Open
- CDaoWorkspace [MFC], RepairDatabase
- CDaoWorkspace [MFC], Rollback
- CDaoWorkspace [MFC], SetDefaultPassword
- CDaoWorkspace [MFC], SetDefaultUser
- CDaoWorkspace [MFC], SetIniPath
- CDaoWorkspace [MFC], SetIsolateODBCTrans
- CDaoWorkspace [MFC], SetLoginTimeout
- CDaoWorkspace [MFC], m_pDAOWorkspace
ms.assetid: 64f60de6-4df1-4d4a-a65b-c489b5257d52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e6210f8c1b1fd1bd19efb74ca68c7a1bed3f7f1
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2018
ms.locfileid: "39209132"
---
# <a name="cdaoworkspace-class"></a>CDaoWorkspace クラス
シングル ユーザーによる名前付きの、パスワードで保護されたデータベース セッションのログインからログオフまでを管理します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDaoWorkspace : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoWorkspace::CDaoWorkspace](#cdaoworkspace)|ワークスペースのオブジェクトを構築します。 その後、呼び出す`Create`または`Open`します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoWorkspace::Append](#append)|データベース エンジンのワークスペース コレクションに新しく作成したワークスペースを追加します。|  
|[CDaoWorkspace::BeginTrans](#begintrans)|ワークスペースで開いているすべてのデータベースに適用される新しいトランザクションを開始します。|  
|[CDaoWorkspace::Close](#close)|ワークスペースとそのすべての含まれているオブジェクトを閉じます。 保留中のトランザクションがロールバックされます。|  
|[CDaoWorkspace::CommitTrans](#committrans)|現在のトランザクションを完了し、変更を保存します。|  
|[CDaoWorkspace::CompactDatabase](#compactdatabase)|データベースを圧縮 (または重複)。|  
|[CDaoWorkspace::Create](#create)|新しい DAO workspace オブジェクトを作成します。|  
|[CDaoWorkspace::GetDatabaseCount](#getdatabasecount)|ワークスペースのデータベース コレクション内には、DAO データベース オブジェクトの数を返します。|  
|[CDaoWorkspace::GetDatabaseInfo](#getdatabaseinfo)|ワークスペースのデータベース コレクションで定義されている指定された DAO データベースに関する情報を返します。|  
|[CDaoWorkspace::GetIniPath](#getinipath)|Microsoft Jet データベースの場所に、Windows レジストリにエンジンの初期化設定を返します。|  
|[CDaoWorkspace::GetIsolateODBCTrans](#getisolateodbctrans)|データ ソースへの接続を強制する同じ ODBC データ ソースに関連する複数のトランザクションが使用して分離かどうかを示す値を返します。|  
|[CDaoWorkspace::GetLoginTimeout](#getlogintimeout)|ユーザーが、ODBC データベースにログインしようとしたときにエラーが発生するまでの秒数を返します。|  
|[CDaoWorkspace::GetName](#getname)|Workspace オブジェクトのユーザー定義の名前を返します。|  
|[CDaoWorkspace::GetUserName](#getusername)|ワークスペースの作成時にユーザー名が指定されたを返します。 これは、ワークスペースの所有者の名前です。|  
|[CDaoWorkspace::GetVersion](#getversion)|ワークスペースに関連付けられているデータベース エンジンのバージョンを含む文字列を返します。|  
|[CDaoWorkspace::GetWorkspaceCount](#getworkspacecount)|データベース エンジンのワークスペース コレクション内には、ワークスペースの DAO オブジェクトの数を返します。|  
|[CDaoWorkspace::GetWorkspaceInfo](#getworkspaceinfo)|データベース エンジンのワークスペース コレクションで定義されている指定された DAO ワークスペースに関する情報を返します。|  
|[CDaoWorkspace::Idle](#idle)|バック グラウンド タスクを実行するデータベース エンジンを使用します。|  
|[CDaoWorkspace::IsOpen](#isopen)|ワークスペースがある場合、0 以外の値を返しますが開きます。|  
|[ので、使用できません。](#open)|DAO の既定のワークスペースに関連付けられているワークスペース オブジェクトを明示的に開きます。|  
|[CDaoWorkspace::RepairDatabase](#repairdatabase)|破損したデータベースの修復を試みます。|  
|[CDaoWorkspace::Rollback](#rollback)|現在のトランザクションを終了し、変更を保存できません。|  
|[CDaoWorkspace::SetDefaultPassword](#setdefaultpassword)|データベース エンジンがパスワードを指定せずにワークスペースを作成するときに使用するパスワードを設定します。|  
|[CDaoWorkspace::SetDefaultUser](#setdefaultuser)|特定のユーザー名を指定せずにワークスペースを作成するときに、データベース エンジンが使用するユーザー名を設定します。|  
|[CDaoWorkspace::SetIniPath](#setinipath)|Microsoft Jet データベースの場所に、Windows レジストリのエンジンの初期化設定を設定します。|  
|[CDaoWorkspace::SetIsolateODBCTrans](#setisolateodbctrans)|データ ソースへの接続を強制することで、同じ ODBC データ ソースに関連する複数のトランザクションを分離するかどうかを指定します。|  
|[CDaoWorkspace::SetLoginTimeout](#setlogintimeout)|ユーザーが ODBC データ ソースにログインしようとしたときにエラーが発生するまでの秒数を設定します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoWorkspace::m_pDAOWorkspace](#m_pdaoworkspace)|基になる DAO workspace オブジェクトへのポインター。|  
  
## <a name="remarks"></a>Remarks  
 ほとんどの場合、複数のワークスペースを必要はありません。 し、明示的にワークスペース オブジェクトを作成する必要はありません。データベースとレコード セット オブジェクトを開くと、DAO の既定のワークスペースを使用します。 ただし、必要な場合、別のワークスペース オブジェクトを作成して複数のセッション同時に実行できます。 ワークスペースの各オブジェクトは、独自のデータベース コレクション内の複数の開いているデータベース オブジェクトを含めることができます。 Mfc では、ワークスペースとは、主に、トランザクション マネージャー、同じ「トランザクション領域です」すべての開いているデータベースのセットを指定します。  
  
> [!NOTE]
>  DAO データベース クラスは、ベースの開いているデータベースの接続 (ODBC) で MFC データベース クラスとは異なります。 DAO データベース クラスの名前では、"CDao"プレフィックスがあります。 一般に、DAO に基づいて MFC クラスは、ODBC に基づいて、MFC クラスよりもより高機能なは。 DAO ベースのクラスを通じて ODBC ドライバーを含む、Microsoft Jet データベース エンジン データにアクセスします。 データベースの作成と DAO を直接呼び出すことがなくテーブルと、クラスを使用してフィールドを追加するなどのデータ定義言語 (DDL) 操作もサポートします。  
  
## <a name="capabilities"></a>機能  
 クラス`CDaoWorkspace`次を提供します。  
  
-   明示的なアクセス、データベース エンジンを初期化することによって作成された既定のワークスペースに、必要な場合。 通常、使用する DAO の既定のワークスペースに暗黙的にデータベースとレコード セット オブジェクトを作成します。  
  
-   トランザクションがすべてのデータベースに適用されるトランザクション領域は、ワークスペースで開きます。 個別のトランザクションのスペースを管理するその他のワークスペースを作成できます。  
  
-   基になる Microsoft Jet データベース エンジンの多くのプロパティへのインターフェイス (静的メンバー関数を参照してください)。 開くまたは、ワークスペースを作成する前に静的メンバー関数の呼び出しを開くまたは作成、データベース エンジンを初期化します。  
  
-   それに追加されたすべてのアクティブなワークスペースを格納するデータベース エンジンのワークスペース コレクションへのアクセス。 作成し、コレクションに追加せずにワークスペースを使用することもできます。  
  
## <a name="security"></a>セキュリティ  
 MFC dao でのセキュリティ制御に使用されるユーザーとグループのコレクションを実装しません。 DAO の機能を必要がある場合をする必要がありますプログラムに自分で DAO インターフェイスへの直接呼び出しを使用しています。 詳しくは、次を参照してください。[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)します。  
  
## <a name="usage"></a>使用法  
 クラスを使用して`CDaoWorkspace`に。  
  
-   明示的に既定のワークスペースを開きます。  
  
     通常、既定のワークスペースの使用は暗黙的な-新しいが開く[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクト。 明示的にアクセスする必要がありますが、-などに access データベース エンジンのプロパティまたはワークスペースのコレクション。 「既定のワークスペースの暗黙的な使用」を参照してください。  
  
-   新しいワークスペースを作成します。 呼び出す[Append](#append)ワークスペース コレクションに追加する場合。  
  
-   ワークスペース コレクションでは、既存のワークスペースを開きます。  
  
 新しいワークスペースの作成が存在しないコレクションが説明されているワークスペースで、[作成](#create)メンバー関数。 ワークスペースのオブジェクトは、データベース エンジンのセッション間で任意の方法では保持されません。 アプリケーションが MFC を静的にリンクする場合は、データベース エンジン非初期化アプリケーションを終了します。 アプリケーションは、MFC と動的にリンク、する場合、データベース エンジンが MFC DLL がアンロードされるときと初期化されていません。  
  
 説明が明示的に既定のワークスペースを開くか、ワークスペース コレクション内の既存のワークスペースを開く、[オープン](#open)メンバー関数。  
  
 セッションを終了するワークスペースのワークスペースを閉じることで、[閉じる](#close)メンバー関数。 `Close` すべてのデータベースが閉じられていない、コミットされていないトランザクションのロールバックを閉じます。  
  
## <a name="transactions"></a>トランザクション  
 DAO は、ワークスペース レベルでトランザクションを管理します。そのため、複数の開いているデータベース ワークスペースでのトランザクションは、すべてのデータベースに適用されます。 たとえば、2 つのデータベースがある場合がコミットされていない更新プログラムを呼び出す[CommitTrans](#committrans)、すべての更新がコミットされます。 単一のデータベースにトランザクションを制限する場合はその別のワークスペース オブジェクトする必要があります。  
  
## <a name="implicit-use-of-the-default-workspace"></a>既定のワークスペースの暗黙的な使用  
 MFC では、次の状況で暗黙的に DAO の既定のワークスペースを使用します。  
  
-   新規に作成する場合`CDaoDatabase`オブジェクトが、既存をリンクしない`CDaoWorkspace`MFC オブジェクトを作成する一時ワークスペース、DAO の既定のワークスペースに対応するオブジェクトします。 既定のワークスペースに関連付けられているは、複数のデータベースのすべてのデータベース オブジェクトを作成する場合。 を通じて、データベースのワークスペースにアクセスすることができます、`CDaoDatabase`データ メンバー。  
  
-   同様を作成する場合、`CDaoRecordset`オブジェクトへのポインターを指定せず、`CDaoDatabase`オブジェクト、MFC は、一時的なデータベース オブジェクトを作成します。 そしてその延長、一時ワークスペース オブジェクト。 レコード セットのデータベース、および間接的に、そのワークスペースにアクセスできる、`CDaoRecordset`データ メンバー。  
  
## <a name="other-operations"></a>その他の操作  
 他のデータベース操作も提供されます、破損したデータベースの修復やデータベースの最適化など。  
  
 DAO セキュリティと DAO の直接の呼び出しについては、次を参照してください。[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoWorkspace`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdao.h  
  
##  <a name="append"></a>  CDaoWorkspace::Append  
 呼び出した後に、このメンバー関数を呼び出す[作成](#create)です。  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>Remarks  
 `Append` データベース エンジンのワークスペース コレクションに新しく作成されたワークスペース オブジェクトを追加します。 ワークスペースは、データベース エンジンのセッションの間は保持されません。ディスクではなく、メモリ内にのみ格納されます。 ワークスペースを追加する必要はありません。そうでない場合は、引き続き使用できます。  
  
 追加のワークスペースに残りますワークスペース コレクションの アクティブなオープンの状態を呼び出すまで、[閉じる](#close)メンバー関数。  
  
 関連情報については、「DAO ヘルプの「メソッドの追加」」を参照してください。  
  
##  <a name="begintrans"></a>  CDaoWorkspace::BeginTrans  
 トランザクションを開始するには、このメンバー関数を呼び出します。  
  
```  
void BeginTrans();
```  
  
### <a name="remarks"></a>Remarks  
 呼び出した後`BeginTrans`トランザクションをコミットすると、データまたはデータベースの構造に行った更新が有効になります。 ワークスペースは、1 つのトランザクション領域を定義するため、トランザクションは、ワークスペース内のすべての開いているデータベースに適用されます。 トランザクションを完了する 2 つの方法はあります。  
  
-   呼び出す、 [CommitTrans](#committrans)メンバー関数は、トランザクションをコミットし、データ ソースに変更を保存します。  
  
-   または、[ロールバック](#rollback)メンバー関数は、トランザクションを取り消します。  
  
 トランザクションが保留中、workspace オブジェクトまたはデータベース オブジェクトの終了が保留中のすべてのトランザクションにロールバックします。  
  
 1 つの ODBC データ ソースから別の ODBC データ ソース上でのトランザクションを分離する必要がある場合を参照してください、 [SetIsolateODBCTrans](#setisolateodbctrans)メンバー関数。  
  
##  <a name="cdaoworkspace"></a>  CDaoWorkspace::CDaoWorkspace  
 `CDaoWorkspace` オブジェクトを構築します。  
  
```  
CDaoWorkspace();
```  
  
### <a name="remarks"></a>Remarks  
 C++ オブジェクトを構築した後に、2 つのオプションがあります。  
  
-   オブジェクトの[開く](#open)メンバー関数は、既定のワークスペースを開くか、ワークスペース コレクション内の既存のオブジェクトを開きます。  
  
-   オブジェクトのまたは[作成](#create)メンバー関数は新しい DAO ワークスペース オブジェクトを作成します。 使用して参照できる新しいワークスペース セッションが明示的に起動、`CDaoWorkspace`オブジェクト。 呼び出した後`Create`、呼び出すことができます[Append](#append)ワークスペース データベース エンジンのワークスペース コレクションに追加する場合。  
  
 クラスの概要を参照してください。 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)について明示的に作成する必要がある場合は、`CDaoWorkspace`オブジェクト。 開くときに暗黙的に作成されたワークスペースを使用して、通常は、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトを開いたときまたはワークスペースを指定せず、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)データベース オブジェクトを指定せずにオブジェクト。 この方法で作成された MFC DAO オブジェクトは、1 回だけ作成され、再利用される DAO の既定のワークスペースを使用します。  
  
 Workspace オブジェクトを呼び出すと、ワークスペース内にあるオブジェクトを解放する[閉じる](#close)メンバー関数。  
  
##  <a name="close"></a>  CDaoWorkspace::Close  
 ワークスペースのオブジェクトを閉じるには、このメンバー関数を呼び出します。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Remarks  
 ワークスペースを開くオブジェクトを閉じる基になる DAO オブジェクトを解放し、ワークスペースのワークスペース コレクションのメンバーである場合は、コレクションから削除します。 呼び出す`Close`プログラミング手法をお勧めします。  
  
> [!CAUTION]
>  ワークスペース オブジェクトを閉じるには、ワークスペースに開かれているデータベースが閉じられます。 これは、結果、同様に、閉じられているデータベースで、レコード セットを開くと、保留中の編集内容や更新がロールバックされます。 関連情報については、次を参照してください、 [CDaoDatabase::Close](../../mfc/reference/cdaodatabase-class.md#close)、 [CDaoRecordset::Close](../../mfc/reference/cdaorecordset-class.md#close)、 [CDaoTableDef::Close](../../mfc/reference/cdaotabledef-class.md#close)、および[CDaoQueryDef::Close。](../../mfc/reference/cdaoquerydef-class.md#close)メンバー関数。  
  
 ワークスペースのオブジェクトが永続的です。それらへの参照が存在している間にのみ存在します。 これは、こと、データベース エンジンのセッションの終了時に、ワークスペースとそのデータベースのコレクションは無効になることを意味します。 必要がありますの再作成すること、次回のセッション、ワークスペースとデータベースをもう一度開くと、します。  
  
 関連情報については、「Close メソッド」DAO ヘルプのトピックを参照してください。  
  
##  <a name="committrans"></a>  CDaoWorkspace::CommitTrans  
 トランザクションをコミットするには、このメンバー関数を呼び出して、編集と更新プログラムのグループをワークスペースで、1 つまたは複数のデータベースに保存します。  
  
```  
void CommitTrans();
```  
  
### <a name="remarks"></a>Remarks  
 トランザクションでは、一連のデータベースのデータまたは以降の呼び出しでは、その構造の変更の[BeginTrans](#begintrans)します。 いずれかのコミットまたはロールバック、トランザクションを完了すると (変更をキャンセル) と[ロールバック](#rollback)します。 既定では、トランザクションを使用しない更新レコードをすぐにコミットされます。 呼び出す`BeginTrans`を呼び出すまでに遅延するための更新プログラムのコミットメントにより`CommitTrans`します。  
  
> [!CAUTION]
>  1 つのワークスペース内では、トランザクションは、ワークスペースにグローバルが常にされ、データベースまたはレコード セットの 1 つだけに限定されません。 1 つ以上のデータベースまたはレコード セットのワークスペース トランザクション内での操作を実行する場合`CommitTrans`更新、保留中のすべてのコミットと`Rollback`データベースとレコード セットのすべての操作を復元します。  
  
 データベースまたは保留中のトランザクションでワークスペースを閉じると、トランザクションがすべてロールバックされます。  
  
> [!NOTE]
>  これは、2 フェーズ コミットのメカニズムではありません。 1 つの更新は、コミットに失敗した場合、他のユーザーもコミットされます。  
  
##  <a name="compactdatabase"></a>  CDaoWorkspace::CompactDatabase  
 指定した Microsoft Jet を圧縮するには、このメンバー関数を呼び出す (します。MDB) データベース。  
  
```  
static void PASCAL CompactDatabase(
    LPCTSTR lpszSrcName,  
    LPCTSTR lpszDestName,  
    LPCTSTR lpszLocale = dbLangGeneral,  
    int nOptions = 0);

 
static void PASCAL CompactDatabase(
    LPCTSTR lpszSrcName,  
    LPCTSTR lpszDestName,  
    LPCTSTR lpszLocale,  
    int nOptions,  
    LPCTSTR lpszPassword);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszSrcName*  
 既存の名前には、データベースが閉じられます。 できますの完全なパスとファイル名など、"c:\\\MYDB します。MDB"。 ファイル名に拡張子がある場合は、指定する必要があります。 場合は、ネットワークでは、統一された名前付け規則 (UNC) をサポートすることもできます、ネットワーク パスなど"\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB します。MDB"。 (ために、パス文字列に円記号が必要な"\\"は C++ のエスケープ文字です)。  
  
 *lpszDestName*  
 作成する、圧縮されたデータベースの完全パス。 としてネットワーク パスを指定することもできます。 *lpszSrcName*します。 使用することはできません、 *lpszDestName*と同じデータベース ファイルを指定する引数*lpszSrcName*します。  
  
 *lpszPassword*  
 パスワードで保護されたデータベースを縮小する場合に使用されるパスワード。 バージョンを使用する場合`CompactDatabase`パスワードに必要なすべてのパラメーターを指定する必要があります。 また、接続パラメーターであるために要する特殊な書式設定、次のようにします;。PWD = *lpszPassword*します。 例: です。PWD =「満足」。 (先頭にセミコロンが必要です。)  
  
 *lpszLocale*  
 作成するための照合順序を指定するための文字列式*lpszDestName*します。 既定値をそのまま使用して、この引数を省略したかどうかは`dbLangGeneral`(下記参照)、新しいデータベースのロケールは、元のデータベースと同じです。 指定できる値は次のとおりです。  
  
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
  
 *nOptions*  
 ターゲット データベースの 1 つまたは複数のオプションを示す*lpszDestName*します。 既定値をそのまま使用して、この引数を省略した場合、 *lpszDestName*には、同じ暗号化およびと同じバージョンが*lpszSrcName*します。 組み合わせることができます、`dbEncrypt`または`dbDecrypt`ビットごとの OR 演算子を使用するバージョンのオプションのいずれかのオプション。 データベース エンジン バージョンではなく、データベースの形式を指定できる値は次のとおりです。  
  
- `dbEncrypt` データベースの最適化中に暗号化します。  
  
- `dbDecrypt` 最適化中に、データベースの暗号化を解除します。  
  
- `dbVersion10` 最適化中に Microsoft Jet データベース エンジンのバージョン 1.0 を使用するデータベースを作成します。  
  
- `dbVersion11` 最適化中に Microsoft Jet データベース エンジンのバージョン 1.1 を使用するデータベースを作成します。  
  
- `dbVersion20` 最適化中に Microsoft Jet データベース エンジンのバージョン 2.0 を使用するデータベースを作成します。  
  
- `dbVersion30` 最適化中に Microsoft Jet データベース エンジンのバージョン 3.0 を使用するデータベースを作成します。  
  
 使用することができます`dbEncrypt`または`dbDecrypt`で暗号化するように結果は圧縮され、データベースの暗号化を解除するかを指定するオプション引数。 暗号化、定数を省略した場合、または両方を含めた場合`dbDecrypt`と`dbEncrypt`、 *lpszDestName*と同じ暗号化する必要があります*lpszSrcName*します。 バージョンのいずれかの操作は、最適化されたデータベースのデータ形式のバージョンを指定するのにオプションの引数で使用できます。 この定数のデータ形式のバージョンのみに影響を与えます*lpszDestName*します。 1 つだけのバージョンの定数を指定できます。 バージョンの定数を省略した場合*lpszDestName*と同じバージョンが*lpszSrcName*します。 圧縮できる*lpszDestName*が同じバージョンにのみまたはの場合よりも後で*lpszSrcName*。  
  
> [!CAUTION]
>  データベースが暗号化されていないデータベースを構成するバイナリのディスク ファイルを直接読み取るのユーザー/パスワード セキュリティを実装する場合でもことができます。  
  
### <a name="remarks"></a>Remarks  
 データベース内のデータを変更すると、データベース ファイル断片化されて、必要に応じてよりも多くのディスク領域を使用します。 定期的に、データベース ファイルの断片化を解消するデータベースを最適化する必要があります。 最適化されたデータベースは、通常は小さくなります。 照合順序、暗号化、またはデータ形式のバージョンをコピーして、データベースの最適化中に変更することもできます。  
  
> [!CAUTION]
>  `CompactDatabase`メンバー関数は正しく Microsoft Access データベースの全体 1 つのバージョンから別に変換しません。 データ形式だけが変換されます。 フォームやレポートなど、Microsoft へのアクセス定義オブジェクトは変換されません。 ただし、データが正しく変換します。  
  
> [!TIP]
>  使用することも`CompactDatabase`データベース ファイルをコピーします。  
  
 データベース圧縮に関する詳細については、DAO のヘルプで「CompactDatabase メソッド」を参照してください。  
  
##  <a name="create"></a>  CDaoWorkspace::Create  
 新しい DAO ワークスペース オブジェクトを作成し、MFC を関連付けるには、このメンバー関数を呼び出して`CDaoWorkspace`オブジェクト。  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    LPCTSTR lpszUserName,  
    LPCTSTR lpszPassword);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszName*  
 最大 14 文字の文字列で新しいワークスペースのオブジェクトの一意名です。 名前を指定する必要があります。 関連情報については、「Name プロパティ」DAO ヘルプのトピックを参照してください。  
  
 *lpszUserName*  
 ワークスペースの所有者のユーザー名。 要件については、次を参照してください。、 *lpszDefaultUser*パラメーターを、 [SetDefaultUser](#setdefaultuser)メンバー関数。 関連情報については、「UserName プロパティ」DAO ヘルプのトピックを参照してください。  
  
 *lpszPassword*  
 新しい workspace オブジェクトのパスワード。 パスワードは、最大 14 文字し、ASCII 0 (null) を除く任意の文字を含めることができます。 パスワードは大文字小文字が区別されます。 関連情報については、「パスワードのプロパティ」DAO ヘルプのトピックを参照してください。  
  
### <a name="remarks"></a>Remarks  
 全体的な作成手順は次のとおりです。  
  
1.  構築、 [CDaoWorkspace](#cdaoworkspace)オブジェクト。  
  
2.  オブジェクトの`Create`メンバー関数は、基になる DAO ワークスペースを作成します。 ワークスペース名を指定する必要があります。  
  
3.  必要に応じて呼び出す[Append](#append)ワークスペース データベース エンジンのワークスペース コレクションに追加する場合。 追加することがなく、ワークスペースを使用することができます。  
  
 後に、`Create`呼び出し、workspace オブジェクトは、開いている状態で、使用できる状態にします。 呼び出すことはありません`Open`後`Create`します。 呼び出すことはありません`Create`ワークスペース コレクションで、ワークスペースが既に存在する場合。 `Create` アプリケーションのまだ初期化されていない場合は、データベース エンジンを初期化します。  
  
##  <a name="getdatabasecount"></a>  CDaoWorkspace::GetDatabaseCount  
 ワークスペースのデータベース コレクション内の DAO データベース オブジェクトの数を取得するには、このメンバー関数を呼び出す: ワークスペースで開いているデータベースの数。  
  
```  
short GetDatabaseCount();
```  
  
### <a name="return-value"></a>戻り値  
 ワークスペースで開いているデータベースの数。  
  
### <a name="remarks"></a>Remarks  
 `GetDatabaseCount` ワークスペースのデータベース コレクションで定義されているすべてのデータベースをループ処理する必要がある場合に便利です。 コレクション内の特定のデータベースに関する情報を取得するには、次を参照してください。 [GetDatabaseInfo](#getdatabaseinfo)します。 一般的な使用法は`GetDatabaseCount`開かれているデータベースの数、しを使用して、その数ループ インデックスとしてを繰り返し呼び出すの`GetDatabaseInfo`します。  
  
##  <a name="getdatabaseinfo"></a>  CDaoWorkspace::GetDatabaseInfo  
 さまざまな種類については、ワークスペース データベースを開くを取得するには、このメンバー関数を呼び出します。  
  
```  
void GetDatabaseInfo(
    int nIndex,  
    CDaoDatabaseInfo& dbinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetDatabaseInfo(
    LPCTSTR lpszName,  
    CDaoDatabaseInfo& dbinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 インデックスで検索する場合、ワークスペースのデータベース コレクション内のデータベース オブジェクトの 0 から始まるインデックス。  
  
 *dbinfo*  
 参照を[CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md)オブジェクトを要求された情報を返します。  
  
 *dwInfoOptions*  
 取得するデータベースに関する情報を指定するオプションです。 使用可能なオプションを返す関数が何とここは。  
  
- 更新可能トランザクション AFX_DAO_PRIMARY_INFO (既定値) 名  
  
- プライマリ AFX_DAO_SECONDARY_INFO 情報に加えて: バージョンについては、照合順序では、クエリのタイムアウト  
  
- AFX_DAO_ALL_INFO プライマリとセカンダリの情報に加えて: 接続  
  
 *lpszName*  
 名前で検索する場合、データベース オブジェクトの名前。 名前は、新しい workspace オブジェクトの一意名を最大 14 文字の文字列です。  
  
### <a name="remarks"></a>Remarks  
 関数の 1 つのバージョンでは、インデックスを使用してデータベースを検索することができます。 その他のバージョンでは、データベースを名前で検索できます。  
  
 返される情報の説明については*dbinfo*を参照してください、 [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報の項目に対応するは*dwInfoOptions*します。 1 つのレベルの情報を要求するときに、そのレベルもの情報を取得します。  
  
##  <a name="getinipath"></a>  CDaoWorkspace::GetIniPath  
 Microsoft Jet データベースの場所に、Windows レジストリでのエンジンの初期化設定を取得するには、このメンバー関数を呼び出します。  
  
```  
static CString PASCAL GetIniPath();
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)レジストリの場所を格納しています。  
  
### <a name="remarks"></a>Remarks  
 データベース エンジンの設定に関する情報を取得するのに場所を使用することができます。 返される情報は、実際にレジストリのサブキーの名前です。  
  
 関連情報については、「IniPath プロパティ」と"をカスタマイズする Windows レジストリの設定に Data Access"DAO ヘルプのトピックを参照してください。  
  
##  <a name="getisolateodbctrans"></a>  CDaoWorkspace::GetIsolateODBCTrans  
 ワークスペースの DAO IsolateODBCTrans プロパティの現在の値を取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetIsolateODBCTrans();
```  
  
### <a name="return-value"></a>戻り値  
 ODBC のトランザクションが分離されている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 場合によっては、同じ ODBC データベースで保留中の複数の同時トランザクションにする必要があります。 これを行うには、トランザクションごとに別のワークスペースを開く必要があります。 各ワークスペースには、データベースへの独自の ODBC 接続できますが、この速度が低下するシステムのパフォーマンスに留意してください。 トランザクションの分離が通常は必要ないため、同じユーザーによって開かれた複数のワークスペース オブジェクトからの ODBC 接続は、既定で共有されます。  
  
 Microsoft SQL Server など、一部の ODBC サーバーでは、1 つの接続での同時トランザクションは許可されません。 このようなデータベースに対して保留中の時に 1 つ以上のトランザクションが存在する必要がある場合を開くとすぐを TRUE に各ワークスペース IsolateODBCTrans プロパティを設定します。 これにより、各ワークスペースの別の ODBC 接続されます。  
  
 関連情報については、「IsolateODBCTrans プロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="getlogintimeout"></a>  CDaoWorkspace::GetLoginTimeout  
 ワークスペースの DAO LoginTimeout プロパティの現在の値を取得するには、このメンバー関数を呼び出します。  
  
```  
static short PASCAL GetLoginTimeout();
```  
  
### <a name="return-value"></a>戻り値  
 ODBC データベースにログインしようとするとエラーが発生するまでの秒数。  
  
### <a name="remarks"></a>Remarks  
 この値は、ODBC データベースにログインしようとするとエラーが発生するまでの秒数を表します。 LoginTimeout の既定の設定には、20 秒です。 LoginTimeout が 0 に設定されている場合は、タイムアウトが発生せず、データ ソースとの通信が応答を停止する可能性があります。  
  
 ネットワーク エラーの結果として、接続が失敗する、Microsoft SQL Server など、ODBC データベースにログインしようとするか、サーバーが実行されていないためです。 接続に 20 秒を既定の待機ではなく、データベース エンジンがエラーを生成するまで待機する時間を指定できます。 サーバーへのログインは、さまざまな外部サーバーのデータベースに対するクエリの実行などのさまざまなイベントの一部として暗黙的に発生します。  
  
 関連情報については、「LoginTimeout プロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="getname"></a>  CDaoWorkspace::GetName  
 ユーザー定義の名前を基に DAO ワークスペース オブジェクトを取得するには、このメンバー関数を呼び出す、`CDaoWorkspace`オブジェクト。  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) DAO workspace オブジェクトのユーザー定義の名前を格納しています。  
  
### <a name="remarks"></a>Remarks  
 名前は、名前で、データベース エンジンのワークスペース コレクションの DAO のワークスペース オブジェクトにアクセスするために便利です。  
  
 関連情報については、「Name プロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="getusername"></a>  CDaoWorkspace::GetUserName  
 ワークスペースの所有者の名前を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetUserName();
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) workspace オブジェクトの所有者を表します。  
  
### <a name="remarks"></a>Remarks  
 取得またはワークスペースの所有者のアクセス許可を設定のアクセス許可プロパティの設定を確認するには、直接 DAO を呼び出すこれは、どのようなアクセス許可を決定します。 ユーザーが持ちます。 アクセス許可を使用するには、システムが必要です。MDA ファイルです。  
  
 DAO の呼び出し元に関する情報を参照してください、直接[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)します。 関連情報については、「UserName プロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="getversion"></a>  CDaoWorkspace::GetVersion  
 使用中の Microsoft Jet データベース エンジンのバージョンを確認するには、このメンバー関数を呼び出します。  
  
```  
static CString PASCAL GetVersion();
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトに関連付けられているデータベース エンジンのバージョンを示します。  
  
### <a name="remarks"></a>Remarks  
 返される値は"major.minor"; という形式でバージョン番号を表しますたとえば、「3.0」です。 製品のバージョン番号 (たとえば、3.0) は、バージョン番号 (3)、ピリオド、およびリリース番号 (0) で構成されます。  
  
 関連情報については、「バージョンのプロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="getworkspacecount"></a>  CDaoWorkspace::GetWorkspaceCount  
 DAO データベース エンジンのワークスペース コレクション内のオブジェクトのワークスペースの数を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetWorkspaceCount();
```  
  
### <a name="return-value"></a>戻り値  
 ワークスペース コレクション内の開いているワークスペースの数。  
  
### <a name="remarks"></a>Remarks  
 この数は、コレクションに追加されていない、開いているワークスペースには含まれません。 `GetWorkspaceCount` ワークスペース コレクションで定義されているすべてのワークスペースをループ処理する必要がある場合に便利です。 コレクション内の特定のワークスペースに関する情報を取得するには、次を参照してください。 [GetWorkspaceInfo](#getworkspaceinfo)します。 一般的な使用法は`GetWorkspaceCount`の開いているワークスペースの数、しを使用して、その番号ループ インデックスとしてを繰り返し呼び出すの`GetWorkspaceInfo`します。  
  
##  <a name="getworkspaceinfo"></a>  CDaoWorkspace::GetWorkspaceInfo  
 さまざまな種類のセッションで開かれているワークスペースに関する情報を取得するには、このメンバー関数を呼び出します。  
  
```  
void GetWorkspaceInfo(
    int nIndex,  
    CDaoWorkspaceInfo& wkspcinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetWorkspaceInfo(
    LPCTSTR lpszName,  
    CDaoWorkspaceInfo& wkspcinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 インデックスで検索する場合、ワークスペース コレクション内のデータベース オブジェクトの 0 から始まるインデックス。  
  
 *wkspcinfo*  
 参照を[CDaoWorkspaceInfo](../../mfc/reference/cdaoworkspaceinfo-structure.md)オブジェクトを要求された情報を返します。  
  
 *dwInfoOptions*  
 取得するワークスペースに関する情報を指定するオプション。 使用可能なオプションを返す関数が何とここは。  
  
- AFX_DAO_PRIMARY_INFO (既定値) の名前  
  
- プライマリ AFX_DAO_SECONDARY_INFO 情報に加えて: ユーザー名  
  
- AFX_DAO_ALL_INFO プライマリとセカンダリの情報に加えて: ODBCTrans の分離  
  
 *lpszName*  
 名前で検索する場合、workspace オブジェクトの名前。 名前は、新しい workspace オブジェクトの一意名を最大 14 文字の文字列です。  
  
### <a name="remarks"></a>Remarks  
 返される情報の説明については*wkspcinfo*を参照してください、 [CDaoWorkspaceInfo](../../mfc/reference/cdaoworkspaceinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報の項目に対応するは*dwInfoOptions*します。 1 つのレベルの情報を要求するときに、レベルの情報を取得します。  
  
##  <a name="idle"></a>  CDaoWorkspace::Idle  
 呼び出す`Idle`大量のデータ処理のため最新できない可能性があるバック グラウンド タスクを実行する機会に、データベース エンジンを提供します。  
  
```  
static void PASCAL Idle(int nAction = dbFreeLocks);
```  
  
### <a name="parameters"></a>パラメーター  
 *%5%6%7%8.%12%0*  
 アイドル状態の処理中に実行するアクション。 現在、唯一の有効なアクションは`dbFreeLocks`します。  
  
### <a name="remarks"></a>Remarks  
 多くの場合、これは、これがないが現在のレコード セット内のすべてのレコードを保持するための十分なバック グラウンド処理の時間、マルチ ユーザーのマルチタス キングの環境に当てはまります。  
  
> [!NOTE]
>  呼び出す`Idle`Microsoft Jet データベース エンジンのバージョン 3.0 で作成されたデータベースでの必要はありません。 使用`Idle`の以前のバージョンで作成されたデータベースだけです。  
  
 通常、読み取りロックを解除し、ローカル ダイナセット タイプのレコード セット オブジェクト内のデータは他のアクション (マウスの動きを含む) が発生していない場合にのみに更新されます。 定期的に呼び出す場合`Idle`、データベース エンジンの遅れをバック グラウンド タスクを解放することによって処理に時間が不要な読み取りロックを提供します。 指定する、`dbFreeLocks`を引数として定数はすべて読み取りロックが解除されるまでの処理を遅延します。  
  
 このメンバー関数は、アプリケーションの複数のインスタンスが実行されている場合を除き、シングル ユーザー環境では必要ありません。 `Idle`メンバー関数は、ディスク、メモリのロックを解放するデータをフラッシュするデータベース エンジンが強制されるため、マルチ ユーザー環境でパフォーマンスが向上します。 トランザクションの操作を組み込むことで読み取りロックをリリースすることもできます。  
  
 関連情報については、「DAO ヘルプの「メソッドのアイドル状態の」」を参照してください。  
  
##  <a name="isopen"></a>  CDaoWorkspace::IsOpen  
 確認するには、このメンバー関数を呼び出すかどうか、`CDaoWorkspace`オブジェクトが開いて-、かどうか、MFC オブジェクトが初期化されたへの呼び出しで[を開く](#open)への呼び出しまたは[作成](#create)。  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ワークスペースのオブジェクトが開いている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 呼び出すメンバーのオープンの状態にあるワークスペースの機能。  
  
##  <a name="m_pdaoworkspace"></a>  CDaoWorkspace::m_pDAOWorkspace  
 基になる DAO workspace オブジェクトへのポインター。  
  
### <a name="remarks"></a>Remarks  
 基になる DAO オブジェクトへのアクセスを指示する必要がある場合は、このデータ メンバーを使用します。 このポインターを通じて、DAO オブジェクトのインターフェイスを呼び出すことができます。  
  
 DAO オブジェクトに直接アクセスする方法の詳細については、次を参照してください。[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)します。  
  
##  <a name="open"></a>  ので、使用できません。  
 DAO の既定のワークスペースに関連付けられているワークスペース オブジェクトを明示的に開きます。  
  
```  
virtual void Open(LPCTSTR lpszName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszName*  
 オブジェクトの名前、DAO のワークスペースを開く-最大 14 文字の文字列であり、ワークスペースの一意名します。 既定値を明示的に既定のワークスペースを開くの NULL をそのまま使用します。 名前付けに関する要件を参照してください、 *lpszName*パラメーター[作成](#create)です。 関連情報については、「Name プロパティ」DAO ヘルプのトピックを参照してください。  
  
### <a name="remarks"></a>Remarks  
 構築した後、`CDaoWorkspace`オブジェクトを次のいずれかを実行するには、このメンバー関数を呼び出します。  
  
-   明示的に既定のワークスペースを開きます。 NULL を渡す*lpszName*します。  
  
-   既存を開く`CDaoWorkspace`オブジェクト、名前によって、ワークスペース コレクションのメンバー。 既存のワークスペース オブジェクトの有効な名前を渡します。  
  
 `Open` workspace オブジェクトでは、開いている状態をしても、アプリケーションの既に初期化されていない場合、データベース エンジンを初期化します。  
  
 ただし多く`CDaoWorkspace`メンバー関数は、ワークスペースを開いた後にのみ呼び出すことができます、データベース エンジンに対して、次のメンバー関数は使用可能なを呼び出す前に、C++ オブジェクトの構築後`Open`:  
  
||||  
|-|-|-|  
|[作成します。](#create)|[バージョンの取得](#getversion)|[SetDefaultUser](#setdefaultuser)|  
|[GetIniPath](#getinipath)|[アイドル状態します。](#idle)|[SetIniPath](#setinipath)|  
|[GetLoginTimeout](#getlogintimeout)|[SetDefaultPassword](#setdefaultpassword)|[SetLoginTimeout](#setlogintimeout)|  
  
##  <a name="repairdatabase"></a>  CDaoWorkspace::RepairDatabase  
 Microsoft Jet データベース エンジンにアクセスする破損したデータベースを修復しようとする必要がある場合は、このメンバー関数を呼び出します。  
  
```  
static void PASCAL RepairDatabase(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszName*  
 パスとファイル名の既存の Microsoft Jet エンジンはデータベース ファイルです。 パスを省略した場合は、現在のディレクトリのみが検索されます。 システムでは、統一された名前付け規則 (UNC) をサポートする場合も指定できます、ネットワーク パスなど:"\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB します。MDB"。 (ために、パス文字列に円記号が必要な"\\"は C++ のエスケープ文字です)。  
  
### <a name="remarks"></a>Remarks  
 指定されたデータベースを閉じる必要があります*lpszName*修復する前にします。 マルチ ユーザー環境では、他のユーザーが持つことはできません*lpszName*修復して中を開きます。 場合*lpszName*が閉じられていないか使用できません、排他的にエラーが発生します。  
  
 このメンバー関数は、不完全な書き込み操作によって不正であるとマークされたデータベースを修復しようとします。 これは、電源障害やコンピューター ハードウェアの問題のため Microsoft Jet データベース エンジンを使用して、アプリケーションが予期せずに閉じている場合に発生することができます。 操作と呼び出しを完了する場合、[閉じる](../../mfc/reference/cdaodatabase-class.md#close)またはメンバー関数は、通常の方法でアプリケーションを終了、データベース マークされません不正であるとします。  
  
> [!NOTE]
>  データベースを修復した後もを使用して圧縮することをお勧め、 [CompactDatabase](#compactdatabase)メンバー関数は、ファイルの断片化を解消して、ディスク領域を回復します。  
  
 データベースの修復の詳細については、DAO のヘルプで「RepairDatabase メソッド」を参照してください。  
  
##  <a name="rollback"></a>  CDaoWorkspace::Rollback  
 現在のトランザクションを終了し、トランザクションが開始された前に、その条件をワークスペースのすべてのデータベースを復元するには、このメンバー関数を呼び出します。  
  
```  
void Rollback();
```  
  
### <a name="remarks"></a>Remarks  
  
> [!CAUTION]
>  1 つのワークスペース オブジェクト内では、トランザクションは、ワークスペースにグローバルが常にされ、データベースまたはレコード セットの 1 つだけに限定されません。 1 つ以上のデータベースまたはレコード セットのワークスペース トランザクション内での操作を実行する場合`Rollback`すべてのデータベースとレコード セットのすべての操作を復元します。  
  
 ワークスペースのオブジェクトを閉じるには、保存または保留中のトランザクションをロールバックせず、トランザクションは自動的にロールバックします。 呼び出す場合[CommitTrans](#committrans)または`Rollback`最初に呼び出さず[BeginTrans](#begintrans)エラーが発生します。  
  
> [!NOTE]
>  トランザクションを開始するときに、データベース エンジンは、ワークステーションで TEMP 環境変数で指定されたディレクトリに保持されるファイルの操作を記録します。 トランザクション ログ ファイルには、一時ドライブに空き容量が不足場合、データベース エンジンは、MFC をスローする、 `CDaoException` (DAO エラー 2004)。 呼び出す場合、この時点で`CommitTrans`操作の数がコミットされますが、残りの未完了操作は失われ、操作が再起動する必要があります。 呼び出す`Rollback`トランザクション ログを解放し、トランザクションのすべての操作をロールバックします。  
  
##  <a name="setdefaultpassword"></a>  CDaoWorkspace::SetDefaultPassword  
 パスワードを指定せずにワークスペースを作成するときに、データベース エンジンが使用する既定のパスワードを設定するには、このメンバー関数を呼び出します。  
  
```  
static void PASCAL SetDefaultPassword(LPCTSTR lpszPassword);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszPassword*  
 既定のパスワード。 パスワードは、最大 14 文字し、ASCII 0 (null) を除く任意の文字を含めることができます。 パスワードは大文字小文字が区別されます。  
  
### <a name="remarks"></a>Remarks  
 呼び出し後に作成した新しいワークスペースに設定する既定のパスワードが適用されます。 その後、ワークスペースを作成するときにパスワードを指定する必要はありません、[作成](#create)呼び出します。  
  
 このメンバー関数を使用します。  
  
1.  構築、`CDaoWorkspace`オブジェクトしますが、呼び出すのではない`Create`します。  
  
2.  呼び出す`SetDefaultPassword`と、必要に応じて、 [SetDefaultUser](#setdefaultuser)します。  
  
3.  呼び出す`Create`このワークスペース オブジェクトまたはその後のパスワードを指定せずします。  
  
 既定では、デフォルト プロパティは"admin"に設定し、DefaultPassword プロパティが空の文字列 ("")。  
  
 セキュリティの詳細については、「アクセス許可のプロパティ」DAO ヘルプのトピックを参照してください。 関連情報については、「DefaultPassword プロパティ」と「デフォルト プロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="setdefaultuser"></a>  CDaoWorkspace::SetDefaultUser  
 特定のユーザー名を指定せずにワークスペースを作成するときに、データベース エンジンが使用する既定のユーザー名を設定するには、このメンバー関数を呼び出します。  
  
```  
static void PASCAL SetDefaultUser(LPCTSTR lpszDefaultUser);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszDefaultUser*  
 既定のユーザー名。 ユーザー名は 1 ~ 20 文字にして、アルファベット文字、アクセント記号付き文字、数字、スペース、および記号を含める:"(引用符)/(スラッシュ)、\ (円記号)、 \[ \] (角かっこ): (コロン) &#124; (パイプ)、 \< (小さい-不等号)、> (大きい-不等号)、+ (正符号) = (等しく記号)、;(セミコロン) を (コンマ) (疑問符) \* (アスタリスク)、先頭スペース、および制御文字 (ASCII 31 の ASCII 00)。 関連情報については、「UserName プロパティ」DAO ヘルプのトピックを参照してください。  
  
### <a name="remarks"></a>Remarks  
 設定する既定のユーザー名は、呼び出しの後に作成する新規のワークスペースに適用されます。 その後、ワークスペースを作成するときにユーザー名を指定する必要はありません、[作成](#create)呼び出します。  
  
 このメンバー関数を使用します。  
  
1.  構築、`CDaoWorkspace`オブジェクトしますが、呼び出すのではない`Create`します。  
  
2.  呼び出す`SetDefaultUser`と、必要に応じて、 [SetDefaultPassword](#setdefaultpassword)します。  
  
3.  呼び出す`Create`のこのワークスペース オブジェクトまたは以降のユーザー名を指定せずします。  
  
 既定では、デフォルト プロパティは"admin"に設定し、DefaultPassword プロパティが空の文字列 ("")。  
  
 関連情報については、「デフォルト プロパティ」と「DefaultPassword プロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="setinipath"></a>  CDaoWorkspace::SetIniPath  
 Microsoft Jet データベース エンジンの Windows レジストリ設定の場所を指定するには、このメンバー関数を呼び出します。  
  
```  
static void PASCAL SetIniPath(LPCTSTR lpszRegistrySubKey);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszRegistrySubkey*  
 Microsoft Jet データベース エンジンの設定やインストール可能な ISAM データベースに必要なパラメーターの場所を Windows レジストリのサブキーの名前を含む文字列。  
  
### <a name="remarks"></a>Remarks  
 呼び出す`SetIniPath`特別な設定を指定する必要がある場合にのみです。 詳細については、DAO ヘルプの「IniPath プロパティ」を参照してください。  
  
> [!NOTE]
>  呼び出す`SetIniPath`アプリケーションのインストール中にない場合、アプリケーションを実行します。 `SetIniPath` 任意のワークスペース、データベース、またはレコード セットを開く前に呼び出す必要があります。それ以外の場合、MFC は、例外をスローします。  
  
 このメカニズムを使用すると、データベース エンジンのユーザーのレジストリ設定を構成します。 この属性のスコープは、アプリケーションに制限され、アプリケーションを再起動しなくても変更することはできません。  
  
##  <a name="setisolateodbctrans"></a>  CDaoWorkspace::SetIsolateODBCTrans  
 ワークスペースの DAO IsolateODBCTrans プロパティの値を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetIsolateODBCTrans(BOOL bIsolateODBCTrans);
```  
  
### <a name="parameters"></a>パラメーター  
 *bIsolateODBCTrans*  
 ODBC のトランザクションの分離を開始する場合は TRUE を渡します。 ODBC のトランザクションの分離を停止する場合は FALSE を渡します。  
  
### <a name="remarks"></a>Remarks  
 場合によっては、同じ ODBC データベースで保留中の複数の同時トランザクションにする必要があります。 これを行うには、トランザクションごとに別のワークスペースを開く必要があります。 各ワークスペースには、データベースへの独自の ODBC 接続できますが、このシステムのパフォーマンスが低下します。 トランザクションの分離が通常は必要ないため、同じユーザーによって開かれた複数のワークスペース オブジェクトからの ODBC 接続は、既定で共有されます。  
  
 Microsoft SQL Server など、一部の ODBC サーバーでは、1 つの接続での同時トランザクションは許可されません。 このようなデータベースに対して保留中の時に 1 つ以上のトランザクションが存在する必要がある場合を開くとすぐを TRUE に各ワークスペース IsolateODBCTrans プロパティを設定します。 これにより、各ワークスペースの別の ODBC 接続されます。  
  
##  <a name="setlogintimeout"></a>  CDaoWorkspace::SetLoginTimeout  
 ワークスペースの DAO LoginTimeout プロパティの値を設定するには、このメンバー関数を呼び出します。  
  
```  
static void PASCAL SetLoginTimeout(short nSeconds);
```  
  
### <a name="parameters"></a>パラメーター  
 *nSeconds*  
 ODBC データベースにログインしようとするとエラーが発生するまでの秒数。  
  
### <a name="remarks"></a>Remarks  
 この値は、ODBC データベースにログインしようとするとエラーが発生するまでの秒数を表します。 LoginTimeout の既定の設定には、20 秒です。 LoginTimeout が 0 に設定されている場合は、タイムアウトが発生せず、データ ソースとの通信が応答を停止する可能性があります。  
  
 ネットワーク エラーの結果として、接続が失敗する、Microsoft SQL Server など、ODBC データベースにログインしようとするか、サーバーが実行されていないためです。 接続に 20 秒を既定の待機ではなく、データベース エンジンがエラーを生成するまで待機する時間を指定できます。 サーバーへのログオンには、外部サーバーのデータベースに対するクエリの実行などのさまざまなイベントの数値の一部として暗黙的に発生します。 タイムアウト値は LoginTimeout プロパティの現在の設定によって決まります。  
  
 関連情報については、「LoginTimeout プロパティ」DAO ヘルプのトピックを参照してください。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef クラス](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoException クラス](../../mfc/reference/cdaoexception-class.md)
