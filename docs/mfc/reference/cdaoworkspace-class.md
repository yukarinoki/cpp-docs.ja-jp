---
title: CDAOワークスペースクラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 52aaa4970ef483988194691eb6b870cbfe51f494
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377117"
---
# <a name="cdaoworkspace-class"></a>CDAOワークスペースクラス

シングル ユーザーによる名前付きの、パスワードで保護されたデータベース セッションのログインからログオフまでを管理します。 DAO は Office 2013 を通じてサポートされています。 DAO 3.6 は最終バージョンであり、廃止と見なされます。

## <a name="syntax"></a>構文

```
class CDaoWorkspace : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[カオワークスペース::CDaoワークスペース](#cdaoworkspace)|ワークスペース オブジェクトを構築します。 その後、`Create`電話`Open`または .|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コダワークスペース::追加](#append)|新しく作成されたワークスペースをデータベース エンジンの Workspaces コレクションに追加します。|
|[カダワークスペース::開始トランス](#begintrans)|新しいトランザクションを開始します。|
|[カダワークスペース::閉じる](#close)|ワークスペースと、そのワークスペースに含まれるすべてのオブジェクトを閉じます。 保留中のトランザクションはロールバックされます。|
|[コダワークスペース::コミットトランス](#committrans)|現在のトランザクションを完了し、変更を保存します。|
|[コダワークスペース::コンパクトデータベース](#compactdatabase)|データベースを最適化 (または複製) します。|
|[CDAOワークスペース::作成](#create)|新しい DAO ワークスペース オブジェクトを作成します。|
|[スタブログスワークスペース::データベースカウント](#getdatabasecount)|ワークスペースの Databases コレクション内の DAO データベース オブジェクトの数を返します。|
|[スタブログスワークスペース::データベース情報を取得します。](#getdatabaseinfo)|ワークスペースの Databases コレクションで定義されている指定された DAO データベースに関する情報を返します。|
|[コダワークスペース::ゲットイニパス](#getinipath)|Windows レジストリ内の Jet データベース エンジンの初期化設定の場所を返します。|
|[コダワークスペース::取得分離ODBCトランス](#getisolateodbctrans)|同じ ODBC データ ソースに関連する複数のトランザクションが、データ ソースへの強制接続によって分離されているかどうかを示す値を返します。|
|[コダワークスペース::ゲットログインタイムアウト](#getlogintimeout)|ユーザーが ODBC データベースにログインしようとしたときにエラーが発生するまでの秒数を返します。|
|[カオワークスペース::ゲットネーム](#getname)|ワークスペース オブジェクトのユーザー定義名を返します。|
|[カオワークスペース::ゲットユーザー名](#getusername)|ワークスペースの作成時に指定されたユーザー名を返します。 これはワークスペース所有者の名前です。|
|[コダワークスペース::ゲットバージョン](#getversion)|ワークスペースに関連付けられているデータベース エンジンのバージョンを含む文字列を返します。|
|[スオカワークスペース::取得ワークスペースカウント](#getworkspacecount)|データベース エンジンの Workspaces コレクション内の DAO ワークスペース オブジェクトの数を返します。|
|[コダワークスペース::ゲットワークスペース情報](#getworkspaceinfo)|データベース エンジンの Workspaces コレクションで定義されている指定された DAO ワークスペースに関する情報を返します。|
|[カオワークスペース::アイドル](#idle)|データベース エンジンがバックグラウンド タスクを実行できるようにします。|
|[カダワークスペース::IsOpen](#isopen)|ワークスペースが開いている場合は、0 以外を返します。|
|[カダワークスペース::オープン](#open)|DAO の既定のワークスペースに関連付けられたワークスペース オブジェクトを明示的に開きます。|
|[コダワークスペース::修復データベース](#repairdatabase)|破損したデータベースの修復を試みます。|
|[CDaoワークスペース::ロールバック](#rollback)|現在のトランザクションを終了し、変更を保存しません。|
|[スタブアワークスペース::デフォルトパスワードの設定](#setdefaultpassword)|特定のパスワードを使用せずにワークスペース オブジェクトを作成するときにデータベース エンジンが使用するパスワードを設定します。|
|[スタブアワークスペース::デフォルトユーザーの設定](#setdefaultuser)|特定のユーザー名を指定せずにワークスペース オブジェクトを作成するときにデータベース エンジンが使用するユーザー名を設定します。|
|[コダワークスペース::セットイニパス](#setinipath)|Windows レジストリでの Jet データベース エンジンの初期化設定の場所を設定します。|
|[コダワークスペース::セトランスセアプセアプタ](#setisolateodbctrans)|同じ ODBC データ ソースに関連する複数のトランザクションを、データ ソースへの複数の接続を強制することによって分離するかどうかを指定します。|
|[コダワークスペース::セットログインタイムアウト](#setlogintimeout)|ユーザーが ODBC データ ソースにログインしようとしたときにエラーが発生するまでの秒数を設定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[カオワークスペース::m_pDAOWorkspace](#m_pdaoworkspace)|基になる DAO ワークスペース オブジェクトへのポインタ。|

## <a name="remarks"></a>解説

ほとんどの場合、複数のワークスペースは必要ありません。データベースオブジェクトとレコードセットオブジェクトを開くと、DAO のデフォルトのワークスペースが使用されます。 ただし、必要に応じて、追加のワークスペース オブジェクトを作成することで、一度に複数のセッションを実行できます。 各ワークスペース オブジェクトは、独自の Databases コレクションに複数の開いているデータベース オブジェクトを含めることができます。 MFC では、ワークスペースは主にトランザクション マネージャであり、開いているデータベースのセットをすべて同じ "トランザクション領域" に指定します。

> [!NOTE]
> DAO データベース クラスは、オープン データベース接続 (ODBC) に基づく MFC データベース クラスとは異なります。 DAO データベース クラス名には、すべて "CDao" というプレフィックスが付いています。 一般に、DAO に基づく MFC クラスは、ODBC に基づく MFC クラスよりも優れている。 DAO ベースのクラスは、ODBC ドライバを含む Jet データベース エンジンを通じてデータにアクセスします。 また、DAO を直接呼び出すことなく、データベースの作成やクラスを介したテーブルやフィールドの追加などのデータ定義言語 (DDL) 操作もサポートしています。

## <a name="capabilities"></a>機能

クラス`CDaoWorkspace`には、次の機能があります。

- データベース エンジンを初期化することによって作成された既定のワークスペースへの明示的なアクセス。</a0> 通常は、データベースオブジェクトとレコードセットオブジェクトを作成することで、DAO のデフォルトのワークスペースを暗黙的に使用します。

- ワークスペースで開いているすべてのデータベースにトランザクションを適用するトランザクション領域。 別のトランザクションスペースを管理するために追加のワークスペースを作成できます。

- 基になる Microsoft Jet データベース エンジンの多くのプロパティへのインターフェイス (静的メンバー関数を参照)。 ワークスペースを開くか作成するか、または静的メンバー関数を呼び出してから開くか作成すると、データベース エンジンが初期化されます。

- データベース エンジンの Workspaces コレクションへのアクセス。 ワークスペースをコレクションに追加せずに作成し、操作することもできます。

## <a name="security"></a>Security

MFC では、セキュリティ制御に使用される DAO のユーザー コレクションとグループ コレクションは実装されていません。 DAO のこれらの側面が必要な場合は、DAO インターフェイスへの直接呼び出しを使用して、ユーザーがプログラミングする必要があります。 詳細については、[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)を参照してください。

## <a name="usage"></a>使用法

クラス`CDaoWorkspace`を使用して、次のことができます。

- 既定のワークスペースを明示的に開きます。

   通常、既定のワークスペースの使用は暗黙的です - 新しい[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを開くとき。 ただし、データベース エンジンのプロパティや Workspaces コレクションにアクセスする場合など、明示的にアクセスする必要がある場合があります。 以下の「既定のワークスペースの暗黙的使用」を参照してください。

- 新しいワークスペースを作成します。 ワークスペース コレクションに追加する場合は[、Append](#append)を呼び出します。

- ワークスペース コレクションで既存のワークスペースを開きます。

ワークスペース コレクションにまだ存在しない新しいワークスペースの[作成については、Create](#create)メンバー関数で説明します。 ワークスペース オブジェクトは、データバベース エンジン セッション間で保持されません。 アプリケーションが MFC を静的にリンクしている場合、アプリケーションを終了するとデータベース エンジンの初期化が解除されます。 アプリケーションが MFC と動的にリンクしている場合、MFC DLL がアンロードされるときにデータベース エンジンは初期化されません。

既定のワークスペースを明示的に開くか、ワークスペース コレクションで既存のワークスペースを開く[、Open](#open)メンバー関数の下に説明があります。

Close メンバー関数を使用してワークスペースを閉じてワークスペース セッションを[終了](#close)します。 `Close`以前に閉じなかったデータベースを閉じ、コミットされていないトランザクションをロールバックします。

## <a name="transactions"></a>トランザクション

DAO は、ワークスペース レベルでトランザクションを管理します。したがって、開いている複数のデータベースを持つワークスペース上のトランザクションは、すべてのデータベースに適用されます。 たとえば、2 つのデータベースにコミットされていない更新が含まれている場合に[、CommitTrans](#committrans)を呼び出すと、すべての更新がコミットされます。 トランザクションを 1 つのデータベースに制限する場合は、そのデータベースに対して別のワークスペース オブジェクトが必要です。

## <a name="implicit-use-of-the-default-workspace"></a>既定のワークスペースの暗黙的な使用

MFC では、次の状況で DAO の既定のワークスペースが暗黙的に使用されます。

- 新`CDaoDatabase`しいオブジェクトを作成するが、既存`CDaoWorkspace`のオブジェクトを使用しない場合、MFC は DAO の既定のワークスペースに対応する一時的なワークスペース オブジェクトを作成します。 複数のデータベースに対してこの操作を行うと、すべてのデータベース オブジェクトが既定のワークスペースに関連付けられます。 データ メンバーを使用してデータベースのワークスペースに`CDaoDatabase`アクセスできます。

- 同様に、オブジェクトへのポインター`CDaoRecordset`を指定せずに`CDaoDatabase`オブジェクトを作成すると、MFC は一時データベース オブジェクトと、拡張によって一時ワークスペース オブジェクトを作成します。 データ メンバーを使用して、レコードセットのデータベース、および間接的にワークスペースに`CDaoRecordset`アクセスできます。

## <a name="other-operations"></a>その他の操作

破損したデータベースの修復やデータベースの最適化など、その他のデータベース操作も提供されます。

DAO を直接呼び出す方法と DAO セキュリティの詳細については、[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CDaoWorkspace`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="cdaoworkspaceappend"></a><a name="append"></a>コダワークスペース::追加

[Create](#create)を呼び出した後、このメンバー関数を呼び出します。

```
virtual void Append();
```

### <a name="remarks"></a>解説

`Append`新しく作成されたワークスペース オブジェクトをデータベース エンジンの Workspaces コレクションに追加します。 ワークスペースは、データベース エンジン セッション間で保持されません。これらは、ディスク上ではなくメモリにのみ格納されます。 ワークスペースを追加する必要はありません。もしそうでなければ、あなたはまだそれを使用することができます。

追加されたワークスペースは[、Close](#close)メンバー関数を呼び出すまで、アクティブなオープン状態の Workspaces コレクションに残ります。

関連情報については、DAO ヘルプの「メソッドの追加」を参照してください。

## <a name="cdaoworkspacebegintrans"></a><a name="begintrans"></a>カダワークスペース::開始トランス

トランザクションを開始するには、このメンバー関数を呼び出します。

```
void BeginTrans();
```

### <a name="remarks"></a>解説

を呼び`BeginTrans`出した後、データまたはデータベース構造に対して行った更新は、トランザクションをコミットしたときに有効になります。 ワークスペースは 1 つのトランザクション領域を定義するため、トランザクションはワークスペース内の開いているすべてのデータベースに適用されます。 トランザクションを完了するには、次の 2 つの方法があります。

- [CommitTrans](#committrans)メンバー関数を呼び出して、トランザクションをコミットし、データ ソースに対する変更を保存します。

- または、[ロールバック](#rollback)メンバー関数を呼び出してトランザクションをキャンセルします。

トランザクションが保留中の間にワークスペース オブジェクトまたはデータベース オブジェクトを閉じても、保留中のすべてのトランザクションがロールバックされます。

ある ODBC データ ソースのトランザクションを別の ODBC データ ソースのトランザクションから分離する必要がある場合は[、SetIsolateODBCTrans](#setisolateodbctrans)メンバー関数を参照してください。

## <a name="cdaoworkspacecdaoworkspace"></a><a name="cdaoworkspace"></a>カオワークスペース::CDaoワークスペース

`CDaoWorkspace` オブジェクトを構築します。

```
CDaoWorkspace();
```

### <a name="remarks"></a>解説

C++ オブジェクトを構築した後、2 つのオプションがあります。

- オブジェクトの[Open](#open)メンバー関数を呼び出して、既定のワークスペースを開くか、Workspaces コレクションの既存のオブジェクトを開きます。

- または、オブジェクトの[Create](#create)メンバー関数を呼び出して、新しい DAO ワークスペース オブジェクトを作成します。 これにより、新しいワークスペース セッションが明示的に開始`CDaoWorkspace`され、オブジェクトを介して参照できます。 呼び`Create`出し後に、データベース エンジンの Workspaces コレクションにワークスペースを追加する場合は[、Append](#append)を呼び出すことができます。

オブジェクトを明示的に作成する必要がある場合の詳細については[、CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)のクラス`CDaoWorkspace`の概要を参照してください。 通常、ワークスペースを指定せずに[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトを開くとき、またはデータベース オブジェクトを指定せずに[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを開くときに、暗黙的に作成されたワークスペースを使用します。 この方法で作成された MFC DAO オブジェクトは、一度作成して再利用する DAO の既定のワークスペースを使用します。

ワークスペースとその含まれているオブジェクトを解放するには、ワークスペース オブジェクトの[Close](#close)メンバー関数を呼び出します。

## <a name="cdaoworkspaceclose"></a><a name="close"></a>カダワークスペース::閉じる

ワークスペース オブジェクトを閉じるには、このメンバー関数を呼び出します。

```
virtual void Close();
```

### <a name="remarks"></a>解説

開いているワークスペース オブジェクトを閉じると、基になる DAO オブジェクトが解放され、ワークスペースが Workspaces コレクションのメンバーである場合は、そのオブジェクトがコレクションから削除されます。 呼`Close`び出しは、プログラミングの良い習慣です。

> [!CAUTION]
> ワークスペース オブジェクトを閉じると、ワークスペース内の開いているデータベースが閉じます。 その結果、データベースで開いているレコードセットも閉じられ、保留中の編集や更新がロールバックされます。 関連情報については、[次](../../mfc/reference/cdaodatabase-class.md#close)を参照してください。 [CDaoRecordset::Close](../../mfc/reference/cdaorecordset-class.md#close) [CDaoTableDef::Close](../../mfc/reference/cdaotabledef-class.md#close) [CDaoQueryDef::Close](../../mfc/reference/cdaoquerydef-class.md#close)

ワークスペース オブジェクトは永続的ではありません。これらのファイルは、参照が存在する間のみ存在します。 つまり、データベース エンジンのセッションが終了しても、ワークスペースとその Databases コレクションは保持されません。 ワークスペースとデータベースを再度開いて、次のセッションに対して再作成する必要があります。

関連情報については、DAO ヘルプの「メソッドを閉じる」を参照してください。

## <a name="cdaoworkspacecommittrans"></a><a name="committrans"></a>コダワークスペース::コミットトランス

このメンバー関数を呼び出してトランザクションをコミットします — ワークスペース内の 1 つ以上のデータベースに対する編集と更新のグループを保存します。

```
void CommitTrans();
```

### <a name="remarks"></a>解説

トランザクションは、データベースのデータまたはその構造に対する一連の変更から成り[、BeginTrans](#begintrans)を呼び出す。 トランザクションを完了したら、Rollback[を使用](#rollback)してトランザクションをコミットするか、ロールバック (変更を取り消す) を行います。 既定では、トランザクションを使用しない場合、レコードの更新は直ちにコミットされます。 呼`BeginTrans`び出しを行うと、 を呼`CommitTrans`び出すまで更新のコミットメントが遅延します。

> [!CAUTION]
> 1 つのワークスペース内では、トランザクションは常にワークスペースに対してグローバルであり、1 つのデータベースまたはレコードセットだけに限定されません。 ワークスペース トランザクション内の複数のデータベースまたはレコードセットに対して操作を`CommitTrans`実行すると、保留中のすべての更新が`Rollback`コミットされ、それらのデータベースおよびレコードセットに対するすべての操作が復元されます。

保留中のトランザクションを含むデータベースまたはワークスペースを閉じると、トランザクションはすべてロールバックされます。

> [!NOTE]
> これは、2 フェーズ コミット メカニズムではありません。 1 つの更新がコミットに失敗した場合、他の更新はコミットされます。

## <a name="cdaoworkspacecompactdatabase"></a><a name="compactdatabase"></a>コダワークスペース::コンパクトデータベース

指定した Jet (.MDB) データベース。

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

*名前*<br/>
閉じている既存のデータベースの名前。 フル パスとファイル名を指定できます("C:\\\MYDB.MDB". ファイル名に拡張子がある場合は、ファイル名を指定する必要があります。 ネットワークが一様な名前付け規則 (UNC) をサポートしている\\\\\\場合は、"\MYSERVER\\\MYSHARE\\\MYDIR \MYDB"\\などのネットワーク パスを指定することもできます。MDB". (パス文字列には "" は\\C++ エスケープ文字であるため、二重円記号が必要です)。

*名前*<br/>
作成する最適化されたデータベースの完全パス。 *lpszSrcName*を使用してネットワーク パスを指定することもできます。 *引数 lpszDestName*を使用して、同じデータベース ファイルを*lpszSrcName*として指定することはできません。

*パスワードを設定します。*<br/>
パスワードで保護されたデータベースを最適化する場合に使用するパスワード。 パスワードを取るバージョンを使用`CompactDatabase`する場合は、すべてのパラメータを指定する必要があります。 また、これは connect パラメーターであるため、次のように特別な書式が必要です。PWD= *lpszPassword*. たとえば、次の例を参照してください。PWD=「ハッピー」。 (先頭のセミコロンが必要です。

*ロケールを指定します。*<br/>
*lpszDestName*を作成するための照合順序を指定するために使用される文字列式。 この引数を省略してデフォルト値を受け入れる`dbLangGeneral`場合 (下記参照)、新しいデータベースのロケールは古いデータベースのロケールと同じです。 次のいずれかの値になります。

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

*nオプション*<br/>
ターゲット データベースの 1 つ以上のオプション*を示します*。 デフォルト値を受け入れてこの引数を省略すると *、lpszDestName*の暗号化は*lpszSrcName*と同じ暗号化と同じになります。 または`dbDecrypt`オプションを`dbEncrypt`、ビットごとの OR 演算子を使用して、バージョン オプションの 1 つと組み合わせることができます。 データベース エンジンのバージョンではなく、データベース形式を指定する値は、次のとおりです。

- `dbEncrypt`最適化中にデータベースを暗号化します。

- `dbDecrypt`最適化中にデータベースを復号化します。

- `dbVersion10`最適化中に Jet データベース エンジン 1.0 を使用するデータベースを作成します。

- `dbVersion11`最適化中に、Jet データベース エンジン 1.1 を使用するデータベースを作成します。

- `dbVersion20`最適化中に Jet データベース エンジン 2.0 を使用するデータベースを作成します。

- `dbVersion30`最適化中に Jet データベース エンジン 3.0 を使用するデータベースを作成します。

または`dbDecrypt`options`dbEncrypt`引数を使用して、最適化時にデータベースを暗号化するか、復号化するかを指定できます。 暗号化定数を省略した場合、または と`dbDecrypt`を`dbEncrypt`両方含める場合*は、 lpszDestName*は*lpszSrcName*と同じ暗号化を持ちます。 オプション引数のバージョン定数のいずれかを使用して、最適化されたデータベースのデータ形式のバージョンを指定できます。 この定数は *、lpszDestName*のデータ形式のバージョンにのみ影響します。 指定できるバージョン定数は 1 つだけです。 バージョン定数を省略すると *、lpszDestName*は*lpszSrcName*と同じバージョンになります。 *lpszDestName は、lpszSrcName*のバージョンと同じか*lpszSrcName*それ以降のバージョンにだけ圧縮できます。

> [!CAUTION]
> データベースが暗号化されていない場合は、ユーザー/パスワード セキュリティを実装していても、データベースを構成するバイナリ ディスク ファイルを直接読み取る可能性があります。

### <a name="remarks"></a>解説

データベース内のデータを変更すると、データベース ファイルが断片化され、必要以上に多くのディスク領域が使用される可能性があります。 データベース ファイルを最適化するには、定期的にデータベースを最適化する必要があります。 最適化されたデータベースは、通常は小さくなります。 また、データベースをコピーして最適化するときに、照合順序、暗号化、またはデータ形式のバージョンを変更することもできます。

> [!CAUTION]
> `CompactDatabase`このメンバー関数は、Access の完全なデータベースをあるバージョンから別のバージョンに正しく変換しません。 変換されるのはデータ形式だけです。 フォームやレポートなどの Access で定義されたオブジェクトは変換されません。 ただし、データは正しく変換されます。

> [!TIP]
> データベース ファイルの`CompactDatabase`コピーにも使用できます。

データベースの最適化の詳細については、DAO ヘルプの「データベースの最適化方法」を参照してください。

## <a name="cdaoworkspacecreate"></a><a name="create"></a>CDAOワークスペース::作成

新しい DAO ワークスペース オブジェクトを作成し、MFC`CDaoWorkspace`オブジェクトに関連付けるには、このメンバー関数を呼び出します。

```
virtual void Create(
    LPCTSTR lpszName,
    LPCTSTR lpszUserName,
    LPCTSTR lpszPassword);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
新しいワークスペース オブジェクトに一意の名前を付ける最大 14 文字の文字列。 名前を指定する必要があります。 関連情報については、DAO ヘルプの「プロパティ名」を参照してください。

*ユーザー名を指定します。*<br/>
ワークスペースの所有者のユーザー名。 要件については、メンバー関数の*lpszDefaultUser* [SetDefaultUser](#setdefaultuser)パラメーターを参照してください。 関連情報については、DAO ヘルプの「ユーザー名プロパティ」を参照してください。

*パスワードを設定します。*<br/>
新しいワークスペース オブジェクトのパスワード。 パスワードは最大 14 文字で、ASCII 0 (null) 以外の任意の文字を使用できます。 パスワードでは大文字と小文字が区別されます。 関連情報については、DAO ヘルプの「パスワード プロパティ」を参照してください。

### <a name="remarks"></a>解説

全体的な作成プロセスは次のとおりです。

1. オブジェクトを構築[します](#cdaoworkspace)。

1. オブジェクトの`Create`メンバー関数を呼び出して、基になる DAO ワークスペースを作成します。 ワークスペース名を指定してください。

1. 必要に応じて、データベース エンジンの Workspaces コレクションにワークスペースを追加する場合は[、Append](#append)を呼び出します。 ワークスペースを追加せずに作業できます。

呼び`Create`出し後、ワークスペース オブジェクトはオープン状態で、使用できる状態になります。 後に`Open``Create`電話をしません。 ワークスペースがワークスペース`Create`コレクションに既に存在する場合は、呼び出しません。 `Create`データベース エンジンがアプリケーション用に初期化されていない場合は、データベース エンジンを初期化します。

## <a name="cdaoworkspacegetdatabasecount"></a><a name="getdatabasecount"></a>スタブログスワークスペース::データベースカウント

ワークスペースの Databases コレクション内の DAO データベース オブジェクトの数 (ワークスペース内で開かれているデータベースの数) を取得します。

```
short GetDatabaseCount();
```

### <a name="return-value"></a>戻り値

ワークスペース内で開いているデータベースの数。

### <a name="remarks"></a>解説

`GetDatabaseCount`ワークスペースの Databases コレクションで定義されているすべてのデータベースをループ処理する必要がある場合に便利です。 コレクション内の特定のデータベースに関する情報を取得するには[、「GetDatabaseInfo](#getdatabaseinfo)」を参照してください。 通常の使用法は`GetDatabaseCount`、開いているデータベースの数を呼び出し、その数を繰り返し`GetDatabaseInfo`呼び出す場合のループ インデックスとして使用することです。

## <a name="cdaoworkspacegetdatabaseinfo"></a><a name="getdatabaseinfo"></a>スタブログスワークスペース::データベース情報を取得します。

ワークスペースで開いているデータベースに関するさまざまな情報を取得します。

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

*nIndex*<br/>
インデックスによる検索用の、ワークスペースの Databases コレクション内のデータベース オブジェクトの 0 から始まるインデックス。

*データベース情報*<br/>
要求された情報を返す[オブジェクト](../../mfc/reference/cdaodatabaseinfo-structure.md)への参照。

*オプション*<br/>
取得するデータベースに関する情報を指定するオプション。 使用可能なオプションは、関数が返す原因と共に次の一覧に示します。

- AFX_DAO_PRIMARY_INFO (デフォルト) 名、更新可能、トランザクション

- AFX_DAO_SECONDARY_INFOプライマリ情報プラス: バージョン、照合順序、クエリ タイムアウト

- プライマリおよびセカンダリの情報と接続をAFX_DAO_ALL_INFOする

*名前を指定します。*<br/>
名前による参照用のデータベース オブジェクトの名前。 名前は、新しいワークスペース オブジェクトに一意の名前を付ける最大 14 文字の文字列です。

### <a name="remarks"></a>解説

関数の 1 つのバージョンでは、インデックスでデータベースを検索できます。 もう 1 つのバージョンでは、データベースを名前で検索できます。

*dbinfo*で返される情報の詳細については[、CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md)構造体を参照してください。 この構造体には *、dwInfoOptions*の説明に記載されている情報の項目に対応するメンバがあります。 あるレベルで情報を要求すると、以前のレベルの情報も取得できます。

## <a name="cdaoworkspacegetinipath"></a><a name="getinipath"></a>コダワークスペース::ゲットイニパス

このメンバー関数を呼び出して、Windows レジストリ内の Jet データベース エンジンの初期化設定の場所を取得します。

```
static CString PASCAL GetIniPath();
```

### <a name="return-value"></a>戻り値

レジストリの場所を含む[CString。](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>解説

この場所を使用して、データベース エンジンの設定に関する情報を取得できます。 実際には、レジストリ サブキーの名前が返されます。

関連情報については、DAO ヘルプの「IniPath プロパティ」および「データ アクセス用の Windows レジストリ設定のカスタマイズ」を参照してください。

## <a name="cdaoworkspacegetisolateodbctrans"></a><a name="getisolateodbctrans"></a>コダワークスペース::取得分離ODBCトランス

ワークスペースの DAO IsolateODBCTrans プロパティの現在の値を取得します。

```
BOOL GetIsolateODBCTrans();
```

### <a name="return-value"></a>戻り値

ODBC トランザクションが分離されている場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

状況によっては、同じ ODBC データベースで複数の同時トランザクションを保留する必要があります。 これを行うには、トランザクションごとに別のワークスペースを開く必要があります。 各ワークスペースはデータベースに対して独自の ODBC 接続を持つことができますが、システムパフォーマンスが低下することに注意してください。 通常、トランザクションの分離は必要ないため、同じユーザーによって開かれた複数のワークスペース オブジェクトからの ODBC 接続は、既定で共有されます。

SQL Server などの一部の ODBC サーバーでは、1 つの接続で同時トランザクションを許可しません。 このようなデータベースに対して保留中のトランザクションを同時に複数持つ必要がある場合は、開くとすぐに各ワークスペースで IsolateODBCTrans プロパティを TRUE に設定します。 これにより、ワークスペースごとに別々の ODBC 接続が強制的に確立されます。

関連情報については、DAO ヘルプのトピック「ODBCTrans プロパティを分離する」を参照してください。

## <a name="cdaoworkspacegetlogintimeout"></a><a name="getlogintimeout"></a>コダワークスペース::ゲットログインタイムアウト

ワークスペースの DAO LoginTimeout プロパティの現在の値を取得します。

```
static short PASCAL GetLoginTimeout();
```

### <a name="return-value"></a>戻り値

ODBC データベースにログインしようとしたときにエラーが発生するまでの秒数。

### <a name="remarks"></a>解説

この値は、ODBC データベースにログインしようとしたときにエラーが発生するまでの秒数を表します。 デフォルトのログインタイムアウト設定は 20 秒です。 LoginTimeout が 0 に設定されている場合、タイムアウトは発生しません。

MICROSOFT SQL Server などの ODBC データベースにログインしようとすると、ネットワーク エラーの結果、またはサーバーが実行されていないために接続が失敗することがあります。 デフォルトの 20 秒の接続を待つよりも、データベース エンジンがエラーを生成するまでの待機時間を指定できます。 サーバーへのログインは、外部サーバー データベースでクエリを実行するなど、さまざまなイベントの一部として暗黙的に実行されます。

関連情報については、DAO ヘルプの「ログイン タイムアウト プロパティ」を参照してください。

## <a name="cdaoworkspacegetname"></a><a name="getname"></a>カオワークスペース::ゲットネーム

`CDaoWorkspace`オブジェクトの基になる DAO ワークスペース オブジェクトのユーザー定義名を取得します。

```
CString GetName();
```

### <a name="return-value"></a>戻り値

DAO ワークスペース オブジェクトのユーザー定義名を含む[CString です](../../atl-mfc-shared/reference/cstringt-class.md)。

### <a name="remarks"></a>解説

この名前は、データベース エンジンの Workspaces コレクション内の DAO ワークスペース オブジェクトに名前でアクセスする場合に便利です。

関連情報については、DAO ヘルプの「プロパティ名」を参照してください。

## <a name="cdaoworkspacegetusername"></a><a name="getusername"></a>カオワークスペース::ゲットユーザー名

ワークスペースの所有者の名前を取得します。

```
CString GetUserName();
```

### <a name="return-value"></a>戻り値

ワークスペース オブジェクトの所有者を表す[CString です](../../atl-mfc-shared/reference/cstringt-class.md)。

### <a name="remarks"></a>解説

ワークスペース所有者のアクセス許可を取得または設定するには、DAO を直接呼び出して Permissions プロパティ設定を確認します。これにより、ユーザーが持つアクセス許可が決まります。 アクセス許可を使用するには、SYSTEM が必要です。MDA ファイル。

DAO を直接呼び出す方法については、[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)を参照してください。 関連情報については、DAO ヘルプの「ユーザー名プロパティ」を参照してください。

## <a name="cdaoworkspacegetversion"></a><a name="getversion"></a>コダワークスペース::ゲットバージョン

このメンバー関数を呼び出して、使用中の Jet データベース エンジンのバージョンを確認します。

```
static CString PASCAL GetVersion();
```

### <a name="return-value"></a>戻り値

オブジェクトに関連付けられているデータベース エンジンのバージョンを示す[CString です](../../atl-mfc-shared/reference/cstringt-class.md)。

### <a name="remarks"></a>解説

返される値は"major.minor"という形式のバージョン番号を表します。たとえば、"3.0" です。 製品バージョン番号 (3.0 など) は、バージョン番号 (3)、期間、およびリリース番号 (0) で構成されます。

関連情報については、DAO ヘルプの「バージョン プロパティ」を参照してください。

## <a name="cdaoworkspacegetworkspacecount"></a><a name="getworkspacecount"></a>スオカワークスペース::取得ワークスペースカウント

データベース エンジンの Workspaces コレクション内の DAO ワークスペース オブジェクトの数を取得します。

```
short GetWorkspaceCount();
```

### <a name="return-value"></a>戻り値

ワークスペース コレクション内の開いているワークスペースの数。

### <a name="remarks"></a>解説

このカウントには、コレクションに追加されていない開いているワークスペースは含まれません。 `GetWorkspaceCount`ワークスペース コレクション内の定義済みワークスペースをすべてループ処理する必要がある場合に便利です。 コレクション内の特定のワークスペースに関する情報を取得するには[、「GetWorkspaceInfo](#getworkspaceinfo)」を参照してください。 一般的な使用法`GetWorkspaceCount`は、開いているワークスペースの数を呼び出し、その数を繰り返し`GetWorkspaceInfo`呼び出す場合のループ インデックスとして使用することです。

## <a name="cdaoworkspacegetworkspaceinfo"></a><a name="getworkspaceinfo"></a>コダワークスペース::ゲットワークスペース情報

セッションで開いているワークスペースに関するさまざまな情報を取得します。

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

*nIndex*<br/>
インデックスによる検索用に、Workspaces コレクション内のデータベース オブジェクトの 0 から始まるインデックス。

*wkspcinfo*<br/>
要求された情報を返す[CDao ワークスペース情報](../../mfc/reference/cdaoworkspaceinfo-structure.md)オブジェクトへの参照。

*オプション*<br/>
取得するワークスペースに関する情報を指定するオプション。 使用可能なオプションは、関数が返す原因と共に次の一覧に示します。

- AFX_DAO_PRIMARY_INFO (デフォルト) 名

- AFX_DAO_SECONDARY_INFOプライマリ情報とユーザー名

- プライマリおよびセカンダリの情報をAFX_DAO_ALL_INFOプラス: ODBCTrans を分離する

*名前を指定します。*<br/>
名前で検索するワークスペース オブジェクトの名前。 名前は、新しいワークスペース オブジェクトに一意の名前を付ける最大 14 文字の文字列です。

### <a name="remarks"></a>解説

*wkspcinfo*で返される情報の説明については、[構造体](../../mfc/reference/cdaoworkspaceinfo-structure.md)を参照してください。 この構造体には *、dwInfoOptions*の説明に記載されている情報の項目に対応するメンバがあります。 あるレベルで情報を要求すると、以前のレベルの情報も取得できます。

## <a name="cdaoworkspaceidle"></a><a name="idle"></a>カオワークスペース::アイドル

データ`Idle`処理が激しいために最新ではない可能性があるバックグラウンド タスクを実行する機会をデータベース エンジンに提供する呼び出し。

```
static void PASCAL Idle(int nAction = dbFreeLocks);
```

### <a name="parameters"></a>パラメーター

*nアクション*<br/>
アイドル処理中に実行するアクション。 現在有効なアクションは`dbFreeLocks`、 だけです。

### <a name="remarks"></a>解説

多くの場合、マルチユーザーのマルチタスク処理環境では、レコードセット内のすべてのレコードを最新の状態に保つために十分なバックグラウンド処理時間がありません。

> [!NOTE]
> 呼`Idle`び出しは、Microsoft Jet データベース エンジンのバージョン 3.0 で作成されたデータベースでは必要ありません。 以前`Idle`のバージョンで作成されたデータベースにのみ使用します。

通常、読み込みロックは解除され、ローカルのダイナセット タイプのレコードセット オブジェクトのデータは、他のアクション (マウスの移動を含む) が発生していない場合にのみ更新されます。 定期的に 呼び`Idle`出す場合は、不要な読み取りロックを解除してバックグラウンド処理タスクを処理する時間をデータベース エンジンに提供します。 定数を`dbFreeLocks`引数として指定すると、すべての読み取りロックが解除されるまで処理が遅れます。

このメンバー関数は、アプリケーションの複数のインスタンスが実行されていない限り、シングルユーザー環境では必要ありません。 `Idle`マルチユーザー環境では、データベース エンジンが強制的にデータをディスクにフラッシュし、メモリのロックを解除するため、メンバー関数のパフォーマンスが向上する場合があります。 操作をトランザクションの一部にすることで、読み取りロックを解除することもできます。

関連情報については、DAO ヘルプの「Idle メソッド」を参照してください。

## <a name="cdaoworkspaceisopen"></a><a name="isopen"></a>カダワークスペース::IsOpen

`CDaoWorkspace`オブジェクトが開いているかどうか、つまり[、MFC](#open)オブジェクトが Open の呼び出しまたは[Create](#create)の呼び出しによって初期化されているかどうかを調べます。

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>戻り値

ワークスペース オブジェクトが開いている場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

開いている状態にあるワークスペースの任意のメンバー関数を呼び出すことができます。

## <a name="cdaoworkspacem_pdaoworkspace"></a><a name="m_pdaoworkspace"></a>カオワークスペース::m_pDAOWorkspace

基になる DAO ワークスペース オブジェクトへのポインター。

### <a name="remarks"></a>解説

基になる DAO オブジェクトに直接アクセスする必要がある場合は、このデータ メンバーを使用します。 このポインターを介して DAO オブジェクトのインターフェイスを呼び出すことができます。

DAO オブジェクトへの直接アクセスについては、テクニカル[ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)を参照してください。

## <a name="cdaoworkspaceopen"></a><a name="open"></a>カダワークスペース::オープン

DAO の既定のワークスペースに関連付けられたワークスペース オブジェクトを明示的に開きます。

```
virtual void Open(LPCTSTR lpszName = NULL);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
開く DAO ワークスペース オブジェクトの名前 — ワークスペースに一意の名前を付ける最大 14 文字の文字列。 既定のワークスペースを明示的に開くには、既定値の NULL を受け入れます。 名前付けの要件については、 [Create](#create)の*lpszName*パラメーターを参照してください。 関連情報については、DAO ヘルプの「プロパティ名」を参照してください。

### <a name="remarks"></a>解説

オブジェクトを構築した`CDaoWorkspace`後、このメンバー関数を呼び出して、次のいずれかの操作を行います。

- 既定のワークスペースを明示的に開きます。 *を渡す NULL を指定します*。

- 既存`CDaoWorkspace`のオブジェクト (Workspaces コレクションのメンバー) を名前で開きます。 既存のワークスペース オブジェクトに有効な名前を渡します。

`Open`ワークスペース オブジェクトをオープン状態にし、アプリケーション用に初期化されていない場合はデータベース エンジンも初期化します。

多くの`CDaoWorkspace`メンバー関数は、ワークスペースを開いた後にのみ呼び出すことができますが、次のメンバー関数は、データベース エンジンを操作しますが、C++ オブジェクトの構築後、呼`Open`び出しの前に使用できます。

||||
|-|-|-|
|[作成](#create)|[Getversion](#getversion)|[デフォルトユーザーの設定](#setdefaultuser)|
|[ゲットイニパス](#getinipath)|[Idle](#idle)|[セットイニパス](#setinipath)|
|[タイムアウトを取得します。](#getlogintimeout)|[デフォルトパスワードを設定します。](#setdefaultpassword)|[タイムアウトを設定します。](#setlogintimeout)|

## <a name="cdaoworkspacerepairdatabase"></a><a name="repairdatabase"></a>コダワークスペース::修復データベース

Microsoft Jet データベース エンジンにアクセスする破損したデータベースを修復する必要がある場合は、このメンバー関数を呼び出します。

```
static void PASCAL RepairDatabase(LPCTSTR lpszName);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
既存の Jet エンジン データベース ファイルのパスとファイル名。 パスを省略すると、現在のディレクトリだけが検索されます。 システムが一様な名前付け規則 (UNC) をサポートしている\\\\\\場合は、ネットワーク\\\\\\パスを指定することもできます。MDB". (パス文字列には "" は\\C++ エスケープ文字であるため、二重円記号が必要です)。

### <a name="remarks"></a>解説

修復する前に *、lpszName*で指定されたデータベースを閉じる必要があります。 マルチユーザー環境では、他のユーザーは*lpszName*を修復中に開くことはできません。 *lpszName*が閉じられていないか、排他的に使用できない場合は、エラーが発生します。

このメンバー関数は、不完全な書き込み操作によって破損している可能性があるデータベースを修復しようとします。 これは、Microsoft Jet データベース エンジンを使用しているアプリケーションが、停電やコンピュータハードウェアの問題のために予期せず終了した場合に発生することがあります。 操作を完了して[Close](../../mfc/reference/cdaodatabase-class.md#close)メンバー関数を呼び出すか、通常の方法でアプリケーションを終了した場合、データベースは破損している可能性があるとしてマークされません。

> [!NOTE]
> データベースを修復した後は[、CompactDatabase](#compactdatabase)メンバー関数を使用して最適化してファイルを最適化し、ディスク領域を回復することもお勧めします。

データベースの修復の詳細については、DAO ヘルプの「データベースの修復方法」を参照してください。

## <a name="cdaoworkspacerollback"></a><a name="rollback"></a>CDaoワークスペース::ロールバック

現在のトランザクションを終了し、トランザクションが開始される前にワークスペース内のすべてのデータベースをその状態に復元するには、このメンバー関数を呼び出します。

```
void Rollback();
```

### <a name="remarks"></a>解説

> [!CAUTION]
> 1 つのワークスペース オブジェクト内では、トランザクションは常にワークスペースに対してグローバルであり、1 つのデータベースまたはレコードセットだけに限定されません。 ワークスペース トランザクション内の複数のデータベースまたはレコードセットに対して操作を`Rollback`実行すると、それらのデータベースとレコードセットすべてに対するすべての操作が復元されます。

保留中のトランザクションを保存またはロールバックせずにワークスペース オブジェクトを閉じると、トランザクションは自動的にロールバックされます。 [最初に BeginTrans](#committrans) `Rollback`を呼び出さずにコミット[Trans](#begintrans)を呼び出すと、エラーが発生します。

> [!NOTE]
> トランザクションを開始すると、データベース エンジンは、ワークステーションの TEMP 環境変数で指定されたディレクトリに保持されているファイルに、その操作を記録します。 トランザクション ログ ファイルが TEMP ドライブ上の使用可能な記憶域を使い果たすと、データベース`CDaoException`エンジンによって MFC がスローされます (DAO エラー 2004)。 この時点で呼び出`CommitTrans`すと、不確定な数の操作がコミットされますが、残りの未完了の操作は失われ、操作を再開する必要があります。 呼`Rollback`び出しはトランザクション ログを解放し、トランザクション内のすべての操作をロールバックします。

## <a name="cdaoworkspacesetdefaultpassword"></a><a name="setdefaultpassword"></a>スタブアワークスペース::デフォルトパスワードの設定

このメンバー関数を呼び出して、特定のパスワードを指定せずにワークスペース オブジェクトを作成するときにデータベース エンジンが使用する既定のパスワードを設定します。

```
static void PASCAL SetDefaultPassword(LPCTSTR lpszPassword);
```

### <a name="parameters"></a>パラメーター

*パスワードを設定します。*<br/>
既定のパスワード。 パスワードは最大 14 文字で、ASCII 0 (null) 以外の任意の文字を使用できます。 パスワードでは大文字と小文字が区別されます。

### <a name="remarks"></a>解説

設定したデフォルトのパスワードは、通話後に作成した新しいワークスペースに適用されます。 後続のワークスペースを作成する場合は[、Create](#create)呼び出しでパスワードを指定する必要はありません。

このメンバー関数を使用するには、次の手順を実行します。

1. オブジェクトを`CDaoWorkspace`構築しますが、呼`Create`び出しません。

1. を`SetDefaultPassword`呼び出し、必要に応じ、[設定既定のユーザー](#setdefaultuser).

1. パスワード`Create`を指定せずに、このワークスペース オブジェクトまたはその後のオブジェクトを呼び出します。

既定では、DefaultUser プロパティは "admin" に設定され、DefaultPassword プロパティは空の文字列 ("" ) に設定されます。

セキュリティの詳細については、DAO ヘルプの「アクセス許可プロパティ」を参照してください。 関連情報については、DAO ヘルプの「DefaultPassword プロパティ」および「既定のユーザー プロパティ」を参照してください。

## <a name="cdaoworkspacesetdefaultuser"></a><a name="setdefaultuser"></a>スタブアワークスペース::デフォルトユーザーの設定

このメンバー関数を呼び出して、特定のユーザー名を指定せずにワークスペース オブジェクトを作成するときにデータベース エンジンが使用する既定のユーザー名を設定します。

```
static void PASCAL SetDefaultUser(LPCTSTR lpszDefaultUser);
```

### <a name="parameters"></a>パラメーター

*デフォルトユーザー*<br/>
既定のユーザー名。 ユーザー名は 1 ~ 20 文字の長さで、アルファベット文字、アクセント付き文字、数字、スペース、および記号を除く記号を含めることができます: "(引用符)、/(スラッシュ)、\(円記号)、(\[\]括\<弧)、(コロン)、&#124;(パイプ)、>(より大きい記号)、+(正符号)、=(等号)、(セミコロン)、カンマ、(疑問符)、\*先頭のスペース、および制御文字(ASCII 00 からASCII 31)。 関連情報については、DAO ヘルプの「ユーザー名プロパティ」を参照してください。

### <a name="remarks"></a>解説

設定したデフォルトのユーザー名は、通話後に作成した新しいワークスペースに適用されます。 後続のワークスペースを作成する場合は[、Create](#create)呼び出しでユーザー名を指定する必要はありません。

このメンバー関数を使用するには、次の手順を実行します。

1. オブジェクトを`CDaoWorkspace`構築しますが、呼`Create`び出しません。

1. 呼`SetDefaultUser`び出し、必要に応じて[、設定既定のパスワード](#setdefaultpassword).

1. ユーザー`Create`名を指定せずに、このワークスペース オブジェクトまたはその後のオブジェクトを呼び出します。

既定では、DefaultUser プロパティは "admin" に設定され、DefaultPassword プロパティは空の文字列 ("" ) に設定されます。

関連情報については、DAO ヘルプの「DefaultUser プロパティ」および「DefaultPassword プロパティ」のトピックを参照してください。

## <a name="cdaoworkspacesetinipath"></a><a name="setinipath"></a>コダワークスペース::セットイニパス

Jet データベース エンジンの Windows レジストリ設定の場所を指定します。

```
static void PASCAL SetIniPath(LPCTSTR lpszRegistrySubKey);
```

### <a name="parameters"></a>パラメーター

*サブキー*<br/>
インストール可能な ISAM データベースに必要な、Jet データベース エンジンの設定またはパラメータの場所に関する Windows レジストリ サブキーの名前を含む文字列。

### <a name="remarks"></a>解説

特別`SetIniPath`な設定を指定する必要がある場合にのみ呼び出します。 詳細については、DAO ヘルプの「IniPath プロパティ」を参照してください。

> [!NOTE]
> アプリケーション`SetIniPath`の実行時ではなく、アプリケーションのインストール中に呼び出します。 `SetIniPath`ワークスペース、データベース、またはレコードセットを開く前に呼び出す必要があります。それ以外の場合、MFC は例外をスローします。

このメカニズムを使用して、ユーザーが指定したレジストリ設定を使用してデータベース エンジンを構成できます。 この属性の有効範囲はアプリケーションに限定され、アプリケーションを再起動しないと変更できません。

## <a name="cdaoworkspacesetisolateodbctrans"></a><a name="setisolateodbctrans"></a>コダワークスペース::セトランスセアプセアプタ

ワークスペースの DAO IsolateODBCTrans プロパティの値を設定するには、このメンバー関数を呼び出します。

```
void SetIsolateODBCTrans(BOOL bIsolateODBCTrans);
```

### <a name="parameters"></a>パラメーター

*を切り離す*<br/>
ODBC トランザクションの分離を開始する場合は TRUE を渡します。 ODBC トランザクションの分離を停止する場合は、FALSE を渡します。

### <a name="remarks"></a>解説

状況によっては、同じ ODBC データベースで複数の同時トランザクションを保留する必要があります。 これを行うには、トランザクションごとに別のワークスペースを開く必要があります。 各ワークスペースはデータベースに対して独自の ODBC 接続を持つことができますが、これによりシステムのパフォーマンスが低下します。 通常、トランザクションの分離は必要ないため、同じユーザーによって開かれた複数のワークスペース オブジェクトからの ODBC 接続は、既定で共有されます。

SQL Server などの一部の ODBC サーバーでは、1 つの接続で同時トランザクションを許可しません。 このようなデータベースに対して保留中のトランザクションを同時に複数持つ必要がある場合は、開くとすぐに各ワークスペースで IsolateODBCTrans プロパティを TRUE に設定します。 これにより、ワークスペースごとに別々の ODBC 接続が強制的に確立されます。

## <a name="cdaoworkspacesetlogintimeout"></a><a name="setlogintimeout"></a>コダワークスペース::セットログインタイムアウト

ワークスペースの DAO LoginTimeout プロパティの値を設定します。

```
static void PASCAL SetLoginTimeout(short nSeconds);
```

### <a name="parameters"></a>パラメーター

*n秒*<br/>
ODBC データベースにログインしようとしたときにエラーが発生するまでの秒数。

### <a name="remarks"></a>解説

この値は、ODBC データベースにログインしようとしたときにエラーが発生するまでの秒数を表します。 デフォルトのログインタイムアウト設定は 20 秒です。 LoginTimeout が 0 に設定されている場合、タイムアウトは発生しません。

MICROSOFT SQL Server などの ODBC データベースにログインしようとすると、ネットワーク エラーの結果、またはサーバーが実行されていないために接続が失敗することがあります。 デフォルトの 20 秒の接続を待つよりも、データベース エンジンがエラーを生成するまでの待機時間を指定できます。 サーバーへのログオンは、外部サーバー データベースでクエリを実行するなど、さまざまなイベントの一部として暗黙的に行われます。 タイムアウト値は、LoginTimeout プロパティの現在の設定によって決まります。

関連情報については、DAO ヘルプの「ログイン タイムアウト プロパティ」を参照してください。

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)<br/>
[クラス](../../mfc/reference/cdaorecordset-class.md)<br/>
[クラス](../../mfc/reference/cdaotabledef-class.md)<br/>
[クラス](../../mfc/reference/cdaoquerydef-class.md)<br/>
[クラスを呼び出す](../../mfc/reference/cdaoexception-class.md)
