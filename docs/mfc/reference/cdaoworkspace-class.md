---
title: CDaoWorkspace クラス |Microsoft ドキュメント
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
ms.openlocfilehash: b249f8069ba12772d21d170b67236a5f013290ac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377215"
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
|[CDaoWorkspace::CDaoWorkspace](#cdaoworkspace)|ワークスペース オブジェクトを構築します。 その後、呼び出す**作成**または**開く**です。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoWorkspace::Append](#append)|データベース エンジンのワークスペースのコレクションを新しく作成したワークスペースを追加します。|  
|[CDaoWorkspace::BeginTrans](#begintrans)|ワークスペースで開いているすべてのデータベースに適用される新しいトランザクションを開始します。|  
|[CDaoWorkspace::Close](#close)|ワークスペースとが含まれているオブジェクトのすべてを閉じます。 保留中のトランザクションがロールバックされます。|  
|[CDaoWorkspace::CommitTrans](#committrans)|現在のトランザクションを完了し、変更を保存します。|  
|[CDaoWorkspace::CompactDatabase](#compactdatabase)|データベースを圧縮 (または複製) します。|  
|[CDaoWorkspace::Create](#create)|新しい DAO ワークスペース オブジェクトを作成します。|  
|[CDaoWorkspace::GetDatabaseCount](#getdatabasecount)|ワークスペースのデータベース コレクション内には、DAO データベース オブジェクトの数を返します。|  
|[CDaoWorkspace::GetDatabaseInfo](#getdatabaseinfo)|ワークスペースのデータベース コレクションで定義されている、指定した DAO データベースに関する情報を返します。|  
|[CDaoWorkspace::GetIniPath](#getinipath)|Microsoft Jet データベースの場所に、Windows レジストリにエンジンの初期化の設定を返します。|  
|[CDaoWorkspace::GetIsolateODBCTrans](#getisolateodbctrans)|データ ソースへの接続を適用するかどうかを同じ ODBC データ ソースを含む複数のトランザクションを使用して分離を示す値を返します。|  
|[CDaoWorkspace::GetLoginTimeout](#getlogintimeout)|ユーザーが ODBC データベースにログインしようとしたときにエラーが発生するまでの秒数を返します。|  
|[CDaoWorkspace::GetName](#getname)|ワークスペース オブジェクトのユーザー定義名を返します。|  
|[CDaoWorkspace::GetUserName](#getusername)|ワークスペースの作成時にユーザー名が指定されたを返します。 これは、ワークスペースの所有者の名前です。|  
|[CDaoWorkspace::GetVersion](#getversion)|ワークスペースに関連付けられているデータベース エンジンのバージョンを表す文字列を返します。|  
|[CDaoWorkspace::GetWorkspaceCount](#getworkspacecount)|データベース エンジンのワークスペースのコレクション内には、ワークスペースの DAO オブジェクトの数を返します。|  
|[CDaoWorkspace::GetWorkspaceInfo](#getworkspaceinfo)|データベース エンジンのワークスペースのコレクションで定義されている指定された DAO ワークスペースについての情報を返します。|  
|[CDaoWorkspace::Idle](#idle)|により、データベース エンジンはバック グラウンド タスクを実行します。|  
|[CDaoWorkspace::IsOpen](#isopen)|ワークスペースがある場合は 0 以外を返しますが開きます。|  
|[ので、使用できません。](#open)|DAO の既定のワークスペースに関連付けられているワークスペース オブジェクトを明示的に開きます。|  
|[CDaoWorkspace::RepairDatabase](#repairdatabase)|破損したデータベースの修復を試みます。|  
|[CDaoWorkspace::Rollback](#rollback)|現在のトランザクションを終了し、変更は保存されません。|  
|[CDaoWorkspace::SetDefaultPassword](#setdefaultpassword)|パスワードを指定せずにワークスペースを作成するときに、データベース エンジンが使用するパスワードを設定します。|  
|[CDaoWorkspace::SetDefaultUser](#setdefaultuser)|特定のユーザー名を指定せずにワークスペースを作成するときに、データベース エンジンが使用するユーザー名を設定します。|  
|[CDaoWorkspace::SetIniPath](#setinipath)|Microsoft Jet データベースの場所に、Windows レジストリにエンジンの初期化の設定を設定します。|  
|[CDaoWorkspace::SetIsolateODBCTrans](#setisolateodbctrans)|同じ ODBC データ ソースを含む複数のトランザクションは強制的に複数の接続、データ ソースを別に分離されているかどうかを指定します。|  
|[CDaoWorkspace::SetLoginTimeout](#setlogintimeout)|ユーザーが ODBC データ ソースにログインしようとしたときにエラーが発生するまでの秒数を設定します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoWorkspace::m_pDAOWorkspace](#m_pdaoworkspace)|基になる DAO ワークスペース オブジェクトへのポインター。|  
  
## <a name="remarks"></a>コメント  
 ほとんどの場合、複数のワークスペースにする必要はありません。 し、明示的にワークスペース オブジェクトを作成する必要はありません。データベース オブジェクトと recordset オブジェクトを開くと、DAO の既定のワークスペースを使用します。 ただし、必要な場合、別のワークスペース オブジェクトを作成することで複数のセッション同時に実行できます。 各ワークスペース オブジェクトは、独自のデータベース コレクション内の複数の開いているデータベース オブジェクトを含めることができます。 MFC では、ワークスペースとは、主に、トランザクション マネージャーは、すべて同じ「トランザクション空間」で開かれているデータベースのセットを指定します。  
  
> [!NOTE]
>  DAO データベース クラスは、MFC データベース クラス ODBC Open Database Connectivity () をベースとは異なります。 DAO データベース クラスの名前では、"CDao"プレフィックスがあります。 一般に、DAO に基づいて MFC クラスは、ODBC に基づいて MFC クラスよりもより高機能です。 DAO ベース クラスには、ODBC ドライバーを含む、Microsoft Jet データベース エンジンを通じてデータにアクセスします。 また、データベースの作成や、DAO を直接呼び出すことがなくテーブルと、クラスを使用してフィールドを追加するなどのデータ定義言語 (DDL) 操作をサポートします。  
  
## <a name="capabilities"></a>機能  
 クラス`CDaoWorkspace`次に示します。  
  
-   明示的なアクセス権、データベース エンジンを初期化することによって作成された既定のワークスペースに、必要な場合です。 通常、使用する DAO の既定のワークスペースに暗黙的にデータベースとレコード セット オブジェクトを作成します。  
  
-   トランザクションがすべてのデータベースに適用されるトランザクション領域は、ワークスペースを開きます。 個別のトランザクションのスペースを管理するその他のワークスペースを作成することができます。  
  
-   基になる Microsoft Jet データベース エンジンの多くのプロパティへのインターフェイス (静的メンバー関数を参照してください)。 開くまたは、ワークスペースを作成する前に、静的メンバー関数を呼び出すことは、オープン、作成またはデータベース エンジンを初期化します。  
  
-   追加されたすべてのアクティブなワークスペースを格納するデータベース エンジンのワークスペースのコレクションにアクセスします。 作成し、コレクションに追加せず、ワークスペースを使用することもできます。  
  
## <a name="security"></a>セキュリティ  
 MFC は、DAO では、セキュリティ制御に使用されるユーザーとグループのコレクションを実装しません。 DAO の側面を必要がある場合する必要がありますプログラムに自分で DAO インターフェイスを直接呼び出してです。 詳細については、次を参照してください。[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)です。  
  
## <a name="usage"></a>使用法  
 クラスを使用して`CDaoWorkspace`に。  
  
-   明示的に既定のワークスペースを開きます。  
  
     既定のワークスペースの使用が暗黙の型は通常、新しいが開く[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクト。 明示的にアクセスする必要がありますが、-などを access データベース エンジンのプロパティまたはワークスペースのコレクション。 「既定のワークスペースの暗黙的な使用」を参照してください。  
  
-   新しいワークスペースを作成します。 呼び出す[Append](#append)ワークスペースのコレクションに追加する場合。  
  
-   Workspaces コレクションでは、既存のワークスペースを開きます。  
  
 新しいワークスペースを作成する存在しないコレクションが下に記載されているワークスペースで、[作成](#create)メンバー関数。 を通してエンジン セッション間で任意の方法では、ワークスペースのオブジェクトは保持されません。 場合は、アプリケーションでは、MFC を静的にリンク、によっては、データベース エンジンが非初期化アプリケーションを終了します。 アプリケーションは、MFC と動的にリンクする場合、データベース エンジンは、MFC DLL を読み込むときと初期化できません。  
  
 下に説明が明示的に既定のワークスペースを開くか、Workspaces コレクションで既存のワークスペースを開いて、[開く](#open)メンバー関数。  
  
 セッションを終了するワークスペースのワークスペースを閉じることで、[閉じる](#close)メンバー関数。 **閉じる**閉じますすべてのデータベースが閉じられていない、コミットされていないトランザクションをロールバックしています。  
  
## <a name="transactions"></a>トランザクション  
 DAO は、ワークスペース レベルでトランザクションを管理します。そのため、複数の開いているデータベース ワークスペースでのトランザクションは、すべてのデータベースに適用されます。 たとえば場合は、2 つのデータベースがコミットされていない更新プログラムを呼び出す[CommitTrans](#committrans)、すべての更新はコミットします。 単一のデータベースにトランザクションを制限する場合はその別のワークスペース オブジェクトする必要があります。  
  
## <a name="implicit-use-of-the-default-workspace"></a>既定のワークスペースの暗黙的な使用  
 MFC は、次の状況で暗黙的に DAO の既定のワークスペースを使用します。  
  
-   新規に作成する場合`CDaoDatabase`オブジェクトが、これを既存`CDaoWorkspace`オブジェクト、MFC オブジェクトを作成、一時ワークスペース、DAO の既定のワークスペースに対応します。 これを行う複数のデータベースの場合のすべてのデータベース オブジェクトに割り当てられた既定のワークスペース。 を介して、データベースのワークスペースにアクセスすることができます、`CDaoDatabase`データ メンバーです。  
  
-   同様に、作成する場合、`CDaoRecordset`オブジェクトへのポインターを指定せず、`CDaoDatabase`オブジェクト、MFC は、一時的なデータベース オブジェクトを作成および拡張機能、一時ワークスペース オブジェクトでします。 レコード セットのデータベース、および間接的にそのワークスペースで、使用してアクセスできます、`CDaoRecordset`データ メンバーです。  
  
## <a name="other-operations"></a>その他の操作  
 その他のデータベース操作も提供、データベースの破損を修復またはデータベースを圧縮することなどです。  
  
 DAO の直接の呼び出しと DAO セキュリティについて、次を参照してください。[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoWorkspace`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
##  <a name="append"></a>  CDaoWorkspace::Append  
 このメンバー関数を呼び出した後[作成](#create)です。  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>コメント  
 **追加**新しく作成したワークスペース オブジェクトをデータベース エンジンのワークスペースのコレクションに追加します。 ワークスペースは、データベース エンジンのセッションの間は保持されません。ディスクではなく、メモリ内にのみ格納されます。 ワークスペースを追加する必要はありません。そうしないと場合、は、引き続き使用できます。  
  
 追加されたワークスペースはワークスペースのコレクション、アクティブな内の開いている状態が呼び出されるまでその[閉じる](#close)メンバー関数。  
  
 関連情報については、「DAO ヘルプの「メソッドの追加」」を参照してください。  
  
##  <a name="begintrans"></a>  CDaoWorkspace::BeginTrans  
 トランザクションを開始するには、このメンバー関数を呼び出します。  
  
```  
void BeginTrans();
```  
  
### <a name="remarks"></a>コメント  
 呼び出した後**BeginTrans**トランザクションをコミットすると、データまたはデータベースの構造に行った更新が有効になります。 ワークスペースは、1 つのトランザクション領域を定義するため、トランザクションは、ワークスペース内のすべての開いているデータベースに適用されます。 これには、トランザクションを完了する 2 つの方法があります。  
  
-   呼び出す、 [CommitTrans](#committrans)メンバー関数をトランザクションをコミットし、データ ソースに変更を保存します。  
  
-   呼び出すか、[ロールバック](#rollback)トランザクションをキャンセルするメンバー関数。  
  
 トランザクションが保留中に、ワークスペース オブジェクトまたはデータベース オブジェクトを閉じることは、保留中のすべてのトランザクションではロールバックします。  
  
 1 つの ODBC データ ソースから別の ODBC データ ソース上でのトランザクションを分離する必要がある場合は、次を参照してください。、 [SetIsolateODBCTrans](#setisolateodbctrans)メンバー関数。  
  
##  <a name="cdaoworkspace"></a>  CDaoWorkspace::CDaoWorkspace  
 `CDaoWorkspace` オブジェクトを構築します。  
  
```  
CDaoWorkspace();
```  
  
### <a name="remarks"></a>コメント  
 C++ オブジェクトを構築した後に、次の 2 つのオプションがあります。  
  
-   オブジェクトの[開く](#open)メンバー関数を既定のワークスペースを開くかを開くには、ワークスペースのコレクション内の既存のオブジェクト。  
  
-   オブジェクトのまたは[作成](#create)新しい DAO ワークスペース オブジェクトを作成するメンバー関数。 これは、明示的に新しいワークスペースはセッションを開始を使用して参照することができる`CDaoWorkspace`オブジェクト。 呼び出した後**作成**、呼び出すことができます[Append](#append)ワークスペースをデータベース エンジンのワークスペースのコレクションに追加する場合。  
  
 クラスの概要を参照してください[CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)について明示的に作成する必要がある場合は、`CDaoWorkspace`オブジェクト。 開くときに暗黙的に作成したワークスペースを使用する通常、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)ワークスペースを指定せず、または開くときのオブジェクト、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)せず、データベース オブジェクトを指定するオブジェクト。 この方法で作成された MFC DAO オブジェクトは、1 回作成され、再利用する DAO の既定のワークスペースを使用します。  
  
 ワークスペースとそのコンテナー内のオブジェクトを解放する呼び出しワークスペース オブジェクトの[閉じる](#close)メンバー関数。  
  
##  <a name="close"></a>  CDaoWorkspace::Close  
 ワークスペース オブジェクトをクローズする場合は、このメンバー関数を呼び出します。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>コメント  
 ワークスペースを開くオブジェクトを閉じて基になる DAO オブジェクトを解放し、ワークスペース Workspaces コレクションのメンバーである場合は、コレクションから削除します。 呼び出す**閉じる**お勧めします。  
  
> [!CAUTION]
>  ワークスペース オブジェクトを閉じると、ワークスペースに開かれているデータベースが実行されます。 これは、結果、同様に、閉じられているデータベースで、レコード セットを開くとすべての保留中の編集または更新がロールバックします。 関連情報については、次を参照してください、 [CDaoDatabase::Close](../../mfc/reference/cdaodatabase-class.md#close)、 [CDaoRecordset::Close](../../mfc/reference/cdaorecordset-class.md#close)、 [CDaoTableDef::Close](../../mfc/reference/cdaotabledef-class.md#close)、および[CDaoQueryDef::Close。](../../mfc/reference/cdaoquerydef-class.md#close)メンバー関数。  
  
 ワークスペースのオブジェクトは恒久的です。それらへの参照が存在している間にのみ存在します。 これは、データベース エンジンのセッションの終了時にワークスペースとそのデータベースのコレクションはありませんが永続化することを意味します。 必要があります再作成するには次のセッション ワークスペースとデータベースを再度開くことで。  
  
 関連情報については、「Close メソッド」DAO ヘルプのトピックを参照してください。  
  
##  <a name="committrans"></a>  CDaoWorkspace::CommitTrans  
 トランザクションをコミットするには、このメンバー関数を呼び出す — ワークスペースで、1 つまたは複数のデータベースへの編集と更新プログラムのグループを保存します。  
  
```  
void CommitTrans();
```  
  
### <a name="remarks"></a>コメント  
 トランザクションでは、一連のデータベース内のデータまたはデータへの呼び出しで始まる、構造体への変更の[BeginTrans](#begintrans)です。 いずれかのコミットまたはロールバック、トランザクションを完了したときに (変更をキャンセルで[ロールバック](#rollback)です。 既定では、トランザクションを使用しない更新プログラムのレコードをすぐにコミットされます。 呼び出す**BeginTrans**を呼び出すまで遅延更新プログラムのコミットメントをにより**CommitTrans**です。  
  
> [!CAUTION]
>  1 つのワークスペース内では、トランザクションは、ワークスペースにグローバルが常にされ、データベースまたはレコード セットの 1 つだけに限定されていません。 2 つ以上のデータベースまたはレコード セットのワークスペース トランザクション内で操作を実行する場合**CommitTrans**更新、保留中のすべてのコミットと**ロールバック**それらのデータベースに対するすべての操作を復元し、レコード セット。  
  
 データベースまたは保留中のトランザクションでワークスペースを閉じると、トランザクションはすべてロールバックされます。  
  
> [!NOTE]
>  これは、2 フェーズ コミット メカニズムではありません。 1 つの更新はコミットに失敗した場合、他のユーザーもコミットされます。  
  
##  <a name="compactdatabase"></a>  CDaoWorkspace::CompactDatabase  
 指定した Microsoft Jet を最適化するには、このメンバー関数を呼び出します (です。MDB) データベース。  
  
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
 `lpszSrcName`  
 既存の名前には、データベースが閉じられました。 だということの完全なパスとファイル名など、"c:\\\MYDB です。MDB"です。 ファイル名に拡張子がある場合を指定する必要があります。 ネットワークでは、統一された名前付け規則 (UNC) をサポートする場合、ことができますも指定するネットワーク パスなど"\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB です。MDB"です。 (ために、パス文字列に円記号が必要な"\\"は、C++ のエスケープ文字です)。  
  
 `lpszDestName`  
 作成している最適化されたデータベースの完全パス。 としてネットワーク パスを指定することもできます。`lpszSrcName`です。 使用することはできません、`lpszDestName`と同じデータベース ファイルを指定する引数`lpszSrcName`です。  
  
 `lpszPassword`  
 パスワードで保護されたデータベースを最適化するときに使用されるパスワードです。 バージョンを使用する場合は、`CompactDatabase`パスワードを取得する、すべてのパラメーターを指定する必要があります。 また、これは、接続パラメーターであるため、必要な特殊な書式設定、次のように: です。PWD =`lpszPassword`です。 例: です。PWD =「満足」です。 (先頭のセミコロンが必要です)  
  
 `lpszLocale`  
 作成するための照合順序を指定する文字列式`lpszDestName`です。 既定値を受け入れることにより、この引数を省略したかどうかは**dbLangGeneral** (下記参照)、新しいデータベースのロケールとは、元のデータベースと同じです。 指定できる値は次のとおりです。  
  
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
  
 `nOptions`  
 ターゲット データベースの 1 つまたは複数のオプションを示す`lpszDestName`です。 既定値はそのまま使用してこの引数を省略した場合、`lpszDestName`同じ暗号化と同じバージョンになります`lpszSrcName`です。 組み合わせることができます、 **dbEncrypt**または**dbDecrypt**ビットごとの OR 演算子を使用してバージョンのオプションのいずれかのオプションです。 データベース エンジン バージョンではなく、データベースの形式を指定できる値は次のとおりです。  
  
- **dbEncrypt**最適化中にデータベースを暗号化します。  
  
- **dbDecrypt**最適化中に、データベースの暗号化を解除します。  
  
- **dbVersion10**最適化中に、Microsoft Jet データベース エンジンのバージョン 1.0 を使用するデータベースを作成します。  
  
- **dbVersion11**最適化中に、Microsoft Jet データベース エンジンのバージョン 1.1 を使用するデータベースを作成します。  
  
- **dbVersion20**最適化中に Microsoft Jet データベース エンジンのバージョン 2.0 を使用するデータベースを作成します。  
  
- **dbVersion30**最適化中に Microsoft Jet データベース エンジンのバージョン 3.0 を使用するデータベースを作成します。  
  
 使用することができます**dbEncrypt**または**dbDecrypt**オプションの引数に暗号化するかは圧縮され、それに応じてデータベースの暗号化を解除するかを指定します。 暗号化定数を省略した場合、または両方を指定する**dbDecrypt**と**dbEncrypt**、`lpszDestName`と同じ暗号化が`lpszSrcName`です。 バージョンのいずれかの操作は、最適化されたデータベースのデータ形式のバージョンを指定するのにオプションの引数で使用できます。 この定数のデータの形式のバージョンのみに影響を与える`lpszDestName`です。 バージョン定数は 1 つだけ指定できます。 バージョン定数を省略した場合`lpszDestName`と同じバージョンを持つ`lpszSrcName`します。 圧縮することもできます`lpszDestName`が同じバージョンにのみの場合よりも後で、または`lpszSrcName`です。  
  
> [!CAUTION]
>  データベースが暗号化されていない場合、可能な場合でもある直接ファイルを読み取るバイナリ ディスク、データベースを構成する、ユーザー/パスワードのセキュリティを実装します。  
  
### <a name="remarks"></a>コメント  
 データベース内のデータを変更すると、データベース ファイル断片化されて、必要に応じてより多くのディスク領域を使用します。 定期的に、データベース ファイルの断片化を解消するため、データベースを圧縮する必要があります。 最適化されたデータベースは、通常小さくなります。 コピーし、データベースを圧縮するには、照合順序、暗号化、またはデータ形式のバージョンを変更することもできます。  
  
> [!CAUTION]
>  `CompactDatabase`メンバー関数は正常に変換されません完全な Microsoft Access データベース 1 つのバージョンから別です。 データの形式のみが変換されます。 フォームやレポートなど、Microsoft アクセス定義オブジェクトは変換されません。 ただし、データが正しく変換します。  
  
> [!TIP]
>  使用することも`CompactDatabase`データベース ファイルをコピーします。  
  
 データベース圧縮の詳細については、DAO ヘルプの「CompactDatabase メソッド」を参照してください。  
  
##  <a name="create"></a>  CDaoWorkspace::Create  
 新しい DAO ワークスペース オブジェクトを作成し、MFC に関連付けるには、このメンバー関数を呼び出す`CDaoWorkspace`オブジェクト。  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    LPCTSTR lpszUserName,  
    LPCTSTR lpszPassword);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 新しいワークスペース オブジェクトの一意名を最大 14 文字の文字列。 名前を指定する必要があります。 関連情報については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
 *lpszUserName*  
 ワークスペースの所有者のユーザー名。 要件については、次を参照してください。、`lpszDefaultUser`パラメーターを、 [SetDefaultUser](#setdefaultuser)メンバー関数。 関連情報については、DAO ヘルプの「ユーザー名プロパティ」を参照してください。  
  
 `lpszPassword`  
 新しいワークスペース オブジェクトのパスワード。 パスワードは、長さは最大 14 文字し、ASCII 0 (null) を除く任意の文字を含めることができます。 パスワードは、大文字小文字が区別されます。 関連情報については、DAO ヘルプの「パスワード プロパティ」を参照してください。  
  
### <a name="remarks"></a>コメント  
 全体的な作成手順は次のとおりです。  
  
1.  構築、 [CDaoWorkspace](#cdaoworkspace)オブジェクト。  
  
2.  オブジェクトの**作成**基になる DAO ワークスペースを作成するメンバー関数。 ワークスペース名を指定する必要があります。  
  
3.  必要に応じて呼び出す[Append](#append)ワークスペースをデータベース エンジンのワークスペースのコレクションに追加する場合。 追加することがなく、ワークスペースを使用することができます。  
  
 後に、**作成**呼び出し、ワークスペース オブジェクトは、開いている状態で、使用可能な状態にします。 呼び出すことはありません**開く**後**作成**です。 呼び出すことはありません**作成**場合は、ワークスペースは、ワークスペースのコレクションに既に存在します。 **作成**アプリケーションの既に初期化されていない場合は、データベース エンジンを初期化します。  
  
##  <a name="getdatabasecount"></a>  CDaoWorkspace::GetDatabaseCount  
 ワークスペースのデータベース コレクション内の DAO データベース オブジェクトの数を取得するには、このメンバー関数を呼び出す — ワークスペースで、開いているデータベースの数。  
  
```  
short GetDatabaseCount();
```  
  
### <a name="return-value"></a>戻り値  
 ワークスペースに開かれているデータベースの数。  
  
### <a name="remarks"></a>コメント  
 `GetDatabaseCount` ワークスペースのデータベース コレクションで定義されているすべてのデータベースをループする必要がある場合に役立ちます。 コレクション内の特定のデータベースに関する情報を取得するには、次を参照してください。 [GetDatabaseInfo](#getdatabaseinfo)です。 呼び出すには、一般的な使用`GetDatabaseCount`開かれているデータベースの数、し、その数をループ インデックスとしてを使用を繰り返し呼び出す`GetDatabaseInfo`です。  
  
##  <a name="getdatabaseinfo"></a>  CDaoWorkspace::GetDatabaseInfo  
 さまざまな種類のデータベースを開く ワークスペースで、に関する情報を取得するには、このメンバー関数を呼び出します。  
  
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
 `nIndex`  
 インデックスで検索する場合、ワークスペースのデータベース コレクション内のデータベース オブジェクトの 0 から始まるインデックス。  
  
 `dbinfo`  
 参照、 [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md)要求された情報を表すオブジェクト。  
  
 `dwInfoOptions`  
 取得するデータベースに関する情報を指定するオプション。 使用可能なオプションを返す関数が何もここで表示されます。  
  
- `AFX_DAO_PRIMARY_INFO` (既定値)更新可能な名前、トランザクション  
  
- `AFX_DAO_SECONDARY_INFO` プライマリ情報に加えて: バージョン、照合順序では、クエリのタイムアウト  
  
- `AFX_DAO_ALL_INFO` プライマリとセカンダリの情報に加えて: 接続  
  
 `lpszName`  
 名前で検索する場合、データベース オブジェクトの名前。 名前は、新しいワークスペース オブジェクトの一意名で 14 文字以内の文字列です。  
  
### <a name="remarks"></a>コメント  
 関数の 1 つのバージョンでは、インデックスを使用してデータベースを検索することができます。 その他のバージョンでは、データベースを名前で検索できます。  
  
 返される情報の詳細については`dbinfo`を参照してください、 [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報項目に対応するは`dwInfoOptions`します。 1 つのレベルの情報を要求するときに、同様に、以前のレベルの情報を取得します。  
  
##  <a name="getinipath"></a>  CDaoWorkspace::GetIniPath  
 Microsoft Jet データベースの場所に、Windows レジストリにエンジンの初期化の設定を取得するには、このメンバー関数を呼び出します。  
  
```  
static CString PASCAL GetIniPath();
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)レジストリの場所を含むです。  
  
### <a name="remarks"></a>コメント  
 データベース エンジンの設定に関する情報を取得するのに場所を使用することができます。 返される情報は、実際にはレジストリのサブキーの名前です。  
  
 関連情報については、「IniPath プロパティ」と"をカスタマイズする Windows レジストリ設定のデータ アクセス"DAO ヘルプのトピックを参照してください。  
  
##  <a name="getisolateodbctrans"></a>  CDaoWorkspace::GetIsolateODBCTrans  
 ワークスペースの DAO IsolateODBCTrans プロパティの現在の値を取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetIsolateODBCTrans();
```  
  
### <a name="return-value"></a>戻り値  
 ODBC トランザクションが分離されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 一部の状況では、同じ ODBC データベースで保留中の複数の同時トランザクションに必要があります。 これを行うには、トランザクションごとに独立したワークスペースを開く必要があります。 各ワークスペースには、データベースへの独自の ODBC 接続できますが、この速度が低下するシステムのパフォーマンスに注意してください。 トランザクションの分離が通常必要ないために、同じユーザーによって開かれた複数のワークスペース オブジェクトから ODBC 接続は、既定で共有されます。  
  
 Microsoft SQL Server など、一部の ODBC サーバーでは、単一の接続での同時トランザクションは許可されません。 時に、保留中のようなデータベースに対してトランザクションを 1 つ以上含める必要がある場合は、IsolateODBCTrans プロパティを設定**TRUE**を開くとすぐには、各ワークスペースにします。 これにより、各ワークスペースの別の ODBC 接続されます。  
  
 関連情報については、DAO ヘルプの「IsolateODBCTrans プロパティ」を参照してください。  
  
##  <a name="getlogintimeout"></a>  CDaoWorkspace::GetLoginTimeout  
 ワークスペースの DAO LoginTimeout プロパティの現在の値を取得するには、このメンバー関数を呼び出します。  
  
```  
static short PASCAL GetLoginTimeout();
```  
  
### <a name="return-value"></a>戻り値  
 ODBC データベースにログインしようとするとエラーが発生するまでの秒数。  
  
### <a name="remarks"></a>コメント  
 この値は、ODBC データベースにログインしようとするとエラーが発生するまでの秒数を表します。 LoginTimeout 既定値は 20 秒です。 LoginTimeout が 0 に設定されている場合は、タイムアウトが発生せず、データ ソースとの通信が応答を停止する可能性があります。  
  
 ネットワーク エラーの結果として、接続が失敗する Microsoft SQL Server などの ODBC データベースにログインしようとしているときに、サーバーが実行されていないため、または。 を待機している既定値 20 秒間の接続にではなく、データベース エンジンがエラーを生成するまでに待機する時間を指定することができます。 サーバーへログインは、外部サーバーのデータベースに対するクエリの実行などのさまざまなイベントの数値の一部として暗黙的に実行されます。  
  
 関連情報については、DAO ヘルプの「LoginTimeout プロパティ」を参照してください。  
  
##  <a name="getname"></a>  CDaoWorkspace::GetName  
 このメンバー関数、ユーザー定義の名前を取得、DAO ワークスペース オブジェクトの基になる、`CDaoWorkspace`オブジェクト。  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) DAO ワークスペース オブジェクトのユーザー定義名を格納します。  
  
### <a name="remarks"></a>コメント  
 名前は、名前によって、DAO ワークスペース コレクション内のオブジェクト、データベース エンジンのワークスペースにアクセスするために役立ちます。  
  
 関連情報については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
##  <a name="getusername"></a>  CDaoWorkspace::GetUserName  
 ワークスペースの所有者の名前を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetUserName();
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)ワークスペース オブジェクトの所有者を表すです。  
  
### <a name="remarks"></a>コメント  
 取得またはワークスペースの所有者のアクセス許可を設定、Permissions プロパティの設定を確認するには、直接 DAO を呼び出すどのようなアクセス許可を指定するユーザーがします。 アクセス許可を使用するには、システムが必要です。MDA ファイルです。  
  
 呼び出し元の DAO に関する情報を参照してください、直接[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)です。 関連情報については、DAO ヘルプの「ユーザー名プロパティ」を参照してください。  
  
##  <a name="getversion"></a>  CDaoWorkspace::GetVersion  
 使用中で、Microsoft Jet データベース エンジンのバージョンを確認するには、このメンバー関数を呼び出します。  
  
```  
static CString PASCAL GetVersion();
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトに関連付けられているデータベース エンジンのバージョンを示すです。  
  
### <a name="remarks"></a>コメント  
 返される値は、フォーム"<major.minor"; でバージョン番号を表しますたとえば、「3.0」です。 製品のバージョン番号 (たとえば、3.0) は、バージョン番号 (3)、ピリオド、およびリリース番号 (0) で構成されます。  
  
 関連情報については、DAO ヘルプの「バージョン プロパティ」を参照してください。  
  
##  <a name="getworkspacecount"></a>  CDaoWorkspace::GetWorkspaceCount  
 DAO データベース エンジンのワークスペースのコレクションのオブジェクトのワークスペースの数を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetWorkspaceCount();
```  
  
### <a name="return-value"></a>戻り値  
 Workspaces コレクション内の開いているワークスペースの数。  
  
### <a name="remarks"></a>コメント  
 この数は、コレクションに追加されていないすべての開いているワークスペースには含まれません。 `GetWorkspaceCount` Workspaces コレクションで定義されているすべてのワークスペースをループする必要がある場合に便利ですが。 コレクション内の特定のワークスペースについての情報を取得するには、次を参照してください。 [GetWorkspaceInfo](#getworkspaceinfo)です。 呼び出すには、一般的な使用`GetWorkspaceCount`開いているワークスペースの数、し、その数をループ インデックスとしてを使用を繰り返し呼び出す`GetWorkspaceInfo`です。  
  
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
 `nIndex`  
 インデックスで検索する場合、ワークスペースのコレクション内のデータベース オブジェクトの 0 から始まるインデックス。  
  
 `wkspcinfo`  
 参照、 [CDaoWorkspaceInfo](../../mfc/reference/cdaoworkspaceinfo-structure.md)要求された情報を表すオブジェクト。  
  
 `dwInfoOptions`  
 取得するワークスペースに関する情報を指定するオプション。 使用可能なオプションを返す関数が何もここで表示されます。  
  
- `AFX_DAO_PRIMARY_INFO` (既定値)名  
  
- `AFX_DAO_SECONDARY_INFO` プライマリ情報に加えて: ユーザー名  
  
- `AFX_DAO_ALL_INFO` プライマリとセカンダリの情報に加えて: ODBCTrans の分離  
  
 `lpszName`  
 名前で検索する場合、ワークスペース オブジェクトの名前。 名前は、新しいワークスペース オブジェクトの一意名で 14 文字以内の文字列です。  
  
### <a name="remarks"></a>コメント  
 返される情報の詳細については`wkspcinfo`を参照してください、 [CDaoWorkspaceInfo](../../mfc/reference/cdaoworkspaceinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報項目に対応するは`dwInfoOptions`します。 1 つのレベルの情報を要求するときに、以前のレベルもの情報を取得します。  
  
##  <a name="idle"></a>  CDaoWorkspace::Idle  
 呼び出す**Idle**しない可能性がある最新大量のデータ処理のためのバック グラウンド タスクを実行する機会に、データベース エンジンを提供します。  
  
```  
static void PASCAL Idle(int nAction = dbFreeLocks);
```  
  
### <a name="parameters"></a>パラメーター  
 `nAction`  
 アイドル状態の処理中に実行するアクション。 現在、唯一の有効なアクションは**dbFreeLocks**です。  
  
### <a name="remarks"></a>コメント  
 多くの場合、これは、これがないが現在のレコード セット内のすべてのレコードを保持するための十分なバック グラウンド処理の時間、マルチ ユーザーのマルチタスク環境で当てはまります。  
  
> [!NOTE]
>  呼び出す**Idle** Microsoft Jet データベース エンジンのバージョン 3.0 で作成されたデータベースでの必要はありません。 使用して**Idle**の以前のバージョンで作成されたデータベースだけです。  
  
 通常、読み取りロックを解除し、データをローカル ダイナセットの種類のレコード セット オブジェクトでは、他のアクション (マウスの動きを含む) が実行されていない場合にのみ更新されます。 定期的に呼び出す場合は、 **Idle**時間の遅れを取り戻すにバック グラウンド タスクの解放を使用してデータベース エンジンが不要な読み取りロックを提供します。 指定する、 **dbFreeLocks**を引数として定数は、すべて読み取りロックが解放されるまで、処理を遅延します。  
  
 このメンバー関数は、アプリケーションの複数のインスタンスを実行している場合を除き、シングル ユーザー環境では必要ありません。 **Idle**メンバー関数は、データをディスクにフラッシュ、メモリのロックを解放する、データベース エンジンが強制されるため、マルチ ユーザー環境でパフォーマンスが向上します。 操作をトランザクションの一部にすることにより、読み取りロックをリリースすることもできます。  
  
 関連情報については、"アイドル Method"DAO ヘルプのトピックを参照してください。  
  
##  <a name="isopen"></a>  CDaoWorkspace::IsOpen  
 決定するには、このメンバー関数を呼び出すかどうか、`CDaoWorkspace`オブジェクトが開いている —、かどうか、MFC オブジェクトは初期化されてへの呼び出しによって[開く](#open)またはへの呼び出し[作成](#create)です。  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ワークスペースのオブジェクトが開いている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 関数を呼び出してできますメンバーのいずれかが開いている状態にあるワークスペースのです。  
  
##  <a name="m_pdaoworkspace"></a>  CDaoWorkspace::m_pDAOWorkspace  
 基になる DAO ワークスペース オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 基になる DAO オブジェクトへのアクセスを指示する必要がある場合は、このデータ メンバーを使用します。 このポインターを通じて DAO オブジェクトのインターフェイスを呼び出すことができます。  
  
 DAO オブジェクトに直接アクセスする方法については、次を参照してください。[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)です。  
  
##  <a name="open"></a>  ので、使用できません。  
 DAO の既定のワークスペースに関連付けられているワークスペース オブジェクトを明示的に開きます。  
  
```  
virtual void Open(LPCTSTR lpszName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 オブジェクトの名前、DAO ワークスペースを開くには、ワークスペースの一意名で 14 文字以内の文字列。 既定値を受け入れる**NULL**を明示的に既定のワークスペースを開きます。 名前付けに関する要件を参照してください、`lpszName`パラメーター[作成](#create)です。 関連情報については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
### <a name="remarks"></a>コメント  
 構築した後、`CDaoWorkspace`オブジェクトを次のいずれかを実行するには、このメンバー関数を呼び出します。  
  
-   明示的に既定のワークスペースを開きます。 渡す**NULL**の`lpszName`します。  
  
-   既存の開く`CDaoWorkspace`オブジェクトの名前で、ワークスペースのコレクションのメンバーです。 ワークスペースの既存のオブジェクトの有効な名前を渡します。  
  
 **開く**によってワークスペース オブジェクト、開いている状態になり、アプリケーションの既に初期化されていない場合も、データベース エンジンを初期化します。  
  
 ただし多く`CDaoWorkspace`メンバー関数は、ワークスペースを開いた後にのみ呼び出すことができます、運用データベース エンジンで、次のメンバー関数は使用可能な呼び出しの前に、C++ オブジェクトの構築後**開く**:  
  
||||  
|-|-|-|  
|[作成します。](#create)|[GetVersion](#getversion)|[SetDefaultUser](#setdefaultuser)|  
|[GetIniPath](#getinipath)|[アイドル状態します。](#idle)|[SetIniPath](#setinipath)|  
|[GetLoginTimeout](#getlogintimeout)|[SetDefaultPassword](#setdefaultpassword)|[SetLoginTimeout](#setlogintimeout)|  
  
##  <a name="repairdatabase"></a>  CDaoWorkspace::RepairDatabase  
 Microsoft Jet データベース エンジンにアクセスする破損したデータベースを修復しようとする必要がある場合は、このメンバー関数を呼び出します。  
  
```  
static void PASCAL RepairDatabase(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 パスとファイル名、既存の Microsoft Jet エンジンのデータベースのファイルを実行します。 パスを省略すると、現在のディレクトリのみが検索されます。 システムでは、統一された名前付け規則 (UNC) をサポートする場合、ことができますも指定するネットワーク パスなど:"\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB です。MDB"です。 (ために、パス文字列に円記号が必要な"\\"は、C++ のエスケープ文字です)。  
  
### <a name="remarks"></a>コメント  
 指定されたデータベースを閉じる必要があります`lpszName`修復する前にします。 マルチ ユーザー環境の場合は、他のユーザーが持つことはできません`lpszName`これを修正するときにします。 場合`lpszName`が閉じられていないかが排他的に使用できる、エラーが発生します。  
  
 このメンバー関数は、不完全な書き込み操作によって不正であるとマークされているデータベースを修復しようとします。 これは、電源の停止やコンピューター ハードウェアの問題のため Microsoft Jet データベース エンジンを使用するアプリケーションが予期せず閉じられた場合に発生することができます。 操作と呼び出しが完了した場合、[閉じる](../../mfc/reference/cdaodatabase-class.md#close)メンバー関数またはする通常の方法でアプリケーションを終了するには、データベースがないマーク不正であるとします。  
  
> [!NOTE]
>  データベースを修復するには後もを使用して圧縮することをお勧め、 [CompactDatabase](#compactdatabase)メンバー関数は、ファイルの断片化を解消して、ディスクの空き領域を増やします。  
  
 データベースの修復の詳細については、DAO ヘルプの「RepairDatabase メソッド」を参照してください。  
  
##  <a name="rollback"></a>  CDaoWorkspace::Rollback  
 現在のトランザクションを終了し、トランザクションが開始された前に、その条件に、ワークスペース内のすべてのデータベースを復元するには、このメンバー関数を呼び出します。  
  
```  
void Rollback();
```  
  
### <a name="remarks"></a>コメント  
  
> [!CAUTION]
>  1 つのワークスペース オブジェクト内では、トランザクションは、ワークスペースにグローバルが常にされ、データベースまたはレコード セットの 1 つだけに限定されていません。 1 つ以上のデータベースまたはレコード セットのワークスペース トランザクション内での操作を実行する場合**ロールバック**のすべてのデータベースとレコード セットのすべての操作を復元します。  
  
 ワークスペースを閉じるには、保存したり、保留中のトランザクションをロールバックしたりせず、トランザクションは自動的にロールバックします。 呼び出す場合[CommitTrans](#committrans)または**ロールバック**最初呼び出さず[BeginTrans](#begintrans)エラーが発生します。  
  
> [!NOTE]
>  トランザクションを開始するときに、データベース エンジンは、ワークステーションに、TEMP 環境変数で指定されたディレクトリに置かれるファイルにその操作を記録します。 スローする MFC をデータベース エンジンに発生する場合は、トランザクション ログ ファイルには、一時ドライブに空き容量が不足、 `CDaoException` (DAO エラー 2004)。 この時点で呼び出す場合は、 **CommitTrans**、不特定の数の操作がコミットされますが、残りの未完了の操作は失われの操作を再起動する必要があります。 呼び出す**ロールバック**トランザクション ログを解放し、トランザクション内のすべての操作をロールバックします。  
  
##  <a name="setdefaultpassword"></a>  CDaoWorkspace::SetDefaultPassword  
 パスワードを指定せずにワークスペースを作成するときに、データベース エンジンが使用する既定のパスワードを設定するには、このメンバー関数を呼び出します。  
  
```  
static void PASCAL SetDefaultPassword(LPCTSTR lpszPassword);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszPassword`  
 既定のパスワード。 パスワードは、長さは最大 14 文字し、ASCII 0 (null) を除く任意の文字を含めることができます。 パスワードは、大文字小文字が区別されます。  
  
### <a name="remarks"></a>コメント  
 呼び出し後に作成した新しいワークスペースを設定する既定のパスワードが適用されます。 その後、ワークスペースを作成するときにパスワードを指定する必要はありません、[作成](#create)呼び出します。  
  
 このメンバー関数を使用します。  
  
1.  構築、`CDaoWorkspace`オブジェクトが、呼び出すことはありません**作成**です。  
  
2.  呼び出す`SetDefaultPassword`し、必要に応じて、 [SetDefaultUser](#setdefaultuser)です。  
  
3.  呼び出す**作成**このワークスペース オブジェクトまたは以降の場合、パスワードを指定せずします。  
  
 既定では、デフォルト プロパティが"admin"に設定されてし、DefaultPassword プロパティが空の文字列 ("") です。  
  
 セキュリティの詳細については、「アクセス許可プロパティ」DAO ヘルプのトピックを参照してください。 関連情報については、"DefaultPassword Property"および"デフォルト Property"DAO ヘルプのトピックを参照してください。  
  
##  <a name="setdefaultuser"></a>  CDaoWorkspace::SetDefaultUser  
 特定のユーザー名を指定せずにワークスペースを作成するときに、データベース エンジンが使用する既定のユーザー名を設定するには、このメンバー関数を呼び出します。  
  
```  
static void PASCAL SetDefaultUser(LPCTSTR lpszDefaultUser);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszDefaultUser`  
 既定のユーザー名。 ユーザー名は 1 ~ 20 文字にして、アルファベット文字、アクセント記号付き文字、数字、スペース、および記号を含める:"(引用符)/(スラッシュ)、\ (円記号) \[ \] (かっこ): (コロン)、 &#124; (パイプ)、 \< (小さい-不等号)、> (大きい-不等号)、+ (正符号) = (等しく記号) です。(セミコロン) を (コンマ区切り) (疑問符) * (アスタリスク)、先頭スペース、および制御文字 (ASCII 31 の ASCII 00)。 関連情報については、DAO ヘルプの「ユーザー名プロパティ」を参照してください。  
  
### <a name="remarks"></a>コメント  
 呼び出し後に作成した新しいワークスペースを設定する既定のユーザー名が適用されます。 その後、ワークスペースを作成するときにユーザー名を指定する必要はありません、[作成](#create)呼び出します。  
  
 このメンバー関数を使用します。  
  
1.  構築、`CDaoWorkspace`オブジェクトが、呼び出すことはありません**作成**です。  
  
2.  呼び出す`SetDefaultUser`し、必要に応じて、 [SetDefaultPassword](#setdefaultpassword)です。  
  
3.  呼び出す**作成**このワークスペース オブジェクトまたは以降の場合、ユーザー名を指定せずします。  
  
 既定では、デフォルト プロパティが"admin"に設定されてし、DefaultPassword プロパティが空の文字列 ("") です。  
  
 関連情報については、「デフォルト プロパティ」と"DefaultPassword Property"DAO ヘルプ トピックを参照してください。  
  
##  <a name="setinipath"></a>  CDaoWorkspace::SetIniPath  
 Microsoft Jet データベース エンジンの Windows レジストリ設定の場所を指定するには、このメンバー関数を呼び出します。  
  
```  
static void PASCAL SetIniPath(LPCTSTR lpszRegistrySubKey);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszRegistrySubkey*  
 Microsoft Jet データベース エンジンの設定やインストール可能な ISAM データベースに必要なパラメーターの位置を表す Windows レジストリのサブキーの名前を表す文字列。  
  
### <a name="remarks"></a>コメント  
 呼び出す`SetIniPath`特別な設定を指定する必要がある場合のみです。 詳細については、DAO ヘルプの「IniPath プロパティ」を参照してください。  
  
> [!NOTE]
>  呼び出す`SetIniPath`アプリケーションのインストール中にないときに、アプリケーションを実行します。 `SetIniPath` 任意のワークスペース、データベース、またはレコード セット; を開く前に呼び出す必要があります。それ以外の場合、MFC は、例外をスローします。  
  
 このメカニズムを使用すると、データベース エンジンのユーザー指定のレジストリ設定を構成します。 この属性のスコープは、アプリケーションに制限され、アプリケーションを再起動しなくても変更することはできません。  
  
##  <a name="setisolateodbctrans"></a>  CDaoWorkspace::SetIsolateODBCTrans  
 ワークスペースの DAO IsolateODBCTrans プロパティの値を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetIsolateODBCTrans(BOOL bIsolateODBCTrans);
```  
  
### <a name="parameters"></a>パラメーター  
 *bIsolateODBCTrans*  
 渡す**TRUE** ODBC トランザクションの分離を開始する場合。 渡す**FALSE** ODBC トランザクションの分離を停止する場合。  
  
### <a name="remarks"></a>コメント  
 一部の状況では、同じ ODBC データベースで保留中の複数の同時トランザクションに必要があります。 これを行うには、トランザクションごとに独立したワークスペースを開く必要があります。 各ワークスペースには、データベースへの独自の ODBC 接続できますが、このシステムのパフォーマンスが低下します。 トランザクションの分離が通常必要ないために、同じユーザーによって開かれた複数のワークスペース オブジェクトから ODBC 接続は、既定で共有されます。  
  
 Microsoft SQL Server など、一部の ODBC サーバーでは、単一の接続での同時トランザクションは許可されません。 時に、保留中のようなデータベースに対してトランザクションを 1 つ以上含める必要がある場合は、IsolateODBCTrans プロパティを設定**TRUE**を開くとすぐには、各ワークスペースにします。 これにより、各ワークスペースの別の ODBC 接続されます。  
  
##  <a name="setlogintimeout"></a>  CDaoWorkspace::SetLoginTimeout  
 ワークスペースの DAO LoginTimeout プロパティの値を設定するには、このメンバー関数を呼び出します。  
  
```  
static void PASCAL SetLoginTimeout(short nSeconds);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSeconds`  
 ODBC データベースにログインしようとするとエラーが発生するまでの秒数。  
  
### <a name="remarks"></a>コメント  
 この値は、ODBC データベースにログインしようとするとエラーが発生するまでの秒数を表します。 LoginTimeout 既定値は 20 秒です。 LoginTimeout が 0 に設定されている場合は、タイムアウトが発生せず、データ ソースとの通信が応答を停止する可能性があります。  
  
 ネットワーク エラーの結果として、接続が失敗する Microsoft SQL Server などの ODBC データベースにログインしようとしているときに、サーバーが実行されていないため、または。 を待機している既定値 20 秒間の接続にではなく、データベース エンジンがエラーを生成するまでに待機する時間を指定することができます。 外部サーバーのデータベースに対するクエリの実行などのさまざまなイベントの数値の一部として暗黙的に実行するサーバーにログオンしています。 タイムアウト値は、LoginTimeout プロパティの現在の設定によって決まります。  
  
 関連情報については、DAO ヘルプの「LoginTimeout プロパティ」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)   
 [どちらのクラス](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoException クラス](../../mfc/reference/cdaoexception-class.md)
