---
title: 'TN054: MFC DAO クラス使用中には、直接の DAO の呼び出し |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.dao
dev_langs:
- C++
helpviewer_keywords:
- MFC, DAO and
- passwords [MFC], calling DAO
- security [MFC], DAO
- DAO (Data Access Objects), calling directly
- DAO (Data Access Objects), security
- security [MFC]
- TN054
- DAO (Data Access Objects), and MFC
ms.assetid: f7de7d85-8d6c-4426-aa05-2e617c0da957
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ed0fc9a18278c4e603b9ddae5197f6b5d03ee21
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950948"
---
# <a name="tn054-calling-dao-directly-while-using-mfc-dao-classes"></a>テクニカル ノート 54: MFC DAO クラス使用中の DAO の直接呼び出し
> [!NOTE]
>  Visual C 環境とウィザードは、(ただし、DAO クラスが含まれると、引き続き使用することができます) DAO をサポートしています。 使用することをお勧めします。 [OLE DB テンプレート](../data/oledb/ole-db-templates.md)または[ODBC と MFC](../data/odbc/odbc-and-mfc.md)新しいプロジェクトのです。 DAO は、既存のアプリケーションを保守でのみ使用する必要があります。  
  
 MFC DAO データベース クラスを使用する場合、DAO を直接使用する必要がある場合があります。 通常、これはない場合は、ですが MFC DAO の直接の呼び出しと MFC クラスの使用を組み合わせる場合は、直接 DAO 呼び出す単純なを容易にするヘルパー機構を提供します。 Dao を直接 DAO の MFC マネージ オブジェクトのメソッドの呼び出しは数行のコードのみを必要があります。 作成している DAO オブジェクトを使用する必要があるかどうかは*いない*MFC によって管理されている、次のように実際に呼び出すことで、もう少しの作業を実行する必要がある`Release`オブジェクトにします。 このテクニカル ノートでは、DAO の直接呼び出しする場合、MFC のヘルパーを行える操作に役立つ、および DAO OLE インターフェイスを使用する方法について説明します。 最後に、この注意は、セキュリティ機能によって DAO の直接 DAO を呼び出す方法を示すサンプルの一部の関数を提供します。  
  
## <a name="when-to-make-direct-dao-calls"></a>DAO の直接呼び出しを行うときに  
 MFC によってラップされていない機能を実装する場合または DAO を直接呼び出すを行うための最も一般的な状況がコレクションを更新する必要がある場合に発生します。 MFC によって公開されていない、最も重要な機能は、セキュリティです。 セキュリティ機能を実装する場合は、DAO のユーザーおよびグループ オブジェクトを直接使用する必要があります。 セキュリティ、以外にのみ、いくつか他の DAO 機能は MFC によってサポートされていません。 レコード セットの複製とデータベース レプリケーションの機能だけでなく DAO をいくつか遅延の追加機能が含まれます。  
  
## <a name="a-brief-overview-of-dao-and-mfcs-implementation"></a>DAO と MFC の実装の概要  
 MFC のラップ DAO は、ほとんどについて心配する必要はありませんので、多くの詳細を処理することによって DAO をより簡単に使用します。 これには、OLE の作成と管理、DAO オブジェクト (特に、コレクション オブジェクト)、エラー チェック、および厳密に型指定された、シンプルなインターフェイスを提供するの初期化が含まれます (ありません**バリアント**または`BSTR`引数)。 DAO の直接の呼び出しを作成し、これらの機能も利用できます。 呼び出しは、コードが行う必要がありますすべて`Release`直接 DAO によって作成されたオブジェクトを呼び出し、および*いない*MFC が依存して内部的にインターフェイス ポインターを変更します。 たとえば、変更しないでください、*開か*open のメンバー`CDaoRecordset`オブジェクトの理解していない限り*すべて*内部の問題が発生します。 ただし、使用することで、*開か*フィールド コレクションを取得するには、直接 DAO を呼び出すインターフェイスです。 この場合、*開か*メンバーは変更できません。 だけを呼び出す必要がある`Release`Fields コレクション オブジェクトは、オブジェクトで終了するときにします。  
  
## <a name="description-of-helpers-to-make-dao-calls-easier"></a>呼び出しを簡略化する DAO ヘルパーの説明  
 DAO を簡単に呼び出しを行うために、ヘルパーは、MFC DAO データベース クラスで内部的に使用されるヘルパーと同じです。 予期されるエラーは、を確認し、必要に応じて、適切な例外をスロー、デバッグ出力のログの DAO の直接の呼び出しを行うときに、これらのリターン コードをチェックするこれらのヘルパーが使用されます。 基になる 2 つのヘルパー関数とこれら 2 つのヘルパーのいずれかにマップされる 4 つのマクロがあります。 単に、コードを読み取ることをお勧めします。 参照してください**DAO_CHECK**、 **DAO_CHECK_ERROR**、 **DAO_CHECK_MEM**、および**DAO_TRACE** AFXDAO にします。マクロを表示し、表示 H **AfxDaoCheck**と**AfxDaoTrace** DAOCORE でします。CPP です。  
  
## <a name="using-the-dao-ole-interfaces"></a>DAO OLE インターフェイスを使用します。  
 DAO オブジェクト階層内の各オブジェクトの OLE インターフェイスは、ヘッダー ファイル DBDAOINT で定義されます。H、\Program Files\Microsoft Visual Studio .NET 2003\VC7\include ディレクトリに存在します。 これらのインターフェイスは、全体の DAO の階層を操作できるようにするメソッドを提供します。  
  
 DAO インターフェイスのメソッドの多くを操作する必要があります、`BSTR`オブジェクト (固定長の文字列 OLE オートメーションで使用される)。 `BSTR`オブジェクト通常は内にカプセル化、**バリアント**データ型。 MFC クラス`COleVariant`から継承自体、**バリアント**データ型。 ANSI または Unicode のプロジェクトをビルドするかどうかに応じて、DAO インターフェイスが返されます ANSI または Unicode `BSTR`s。 取得 DAO インターフェイスを保証することの V_BSTR と V_BSTRT、2 つのマクロが便利ですが、`BSTR`予期された型。  
  
 V_BSTR が抽出、 *bstrVal*のメンバー、`COleVariant`です。 このマクロは通常の内容を渡す必要がある場合に使用する`COleVariant`DAO インターフェイスのメソッドにします。 次のコード フラグメントは、宣言と DAO DAOUser インターフェイス V_BSTR マクロを利用する 2 つの方法の実際の使用の両方を示します。  
  
```  
COleVariant varOldName;  
COleVariant varNewName(_T("NewUser"), VT_BSTRT);

 
// Code to assign pUser to a valid value omitted  
DAOUser *pUser = NULL;  
 
// These method declarations were taken from DBDAOINT.H  
// STDMETHOD(get_Name) (THIS_ BSTR FAR* pbstr) PURE;  
// STDMETHOD(put_Name) (THIS_ BSTR bstr) PURE;  
 
DAO_CHECK(pUser->get_Name(&V_BSTR (&varOldName)));

DAO_CHECK(pUser->put_Name(V_BSTR (&varNewName)));
```  
  
 注意してください、`VT_BSTRT`引数で指定された、`COleVariant`上記のコンス トラクターにより、ANSI がある`BSTR`で、 `COleVariant` 、アプリケーションと、Unicode、ANSI バージョンをビルドするかどうかは`BSTR`の Unicode バージョンのアプリケーション。 これは DAO でが必要です。  
  
 その他のマクロ、V_BSTRT は ANSI または Unicode のいずれかを抽出*bstrVal*のメンバー `COleVariant` (ANSI または Unicode) のビルドの種類によって異なります。 次のコードを抽出する方法を示しています、`BSTR`値から、`COleVariant`に、 `CString`:  
  
```  
COleVariant varName(_T("MyName"), VT_BSTRT);

CString str = V_BSTRT(&varName);
```  
  
 格納されているその他の種類を開くには、その他の手法と共に、V_BSTRT マクロ`COleVariant`、DAOVIEW サンプルに示します。 具体的には、この変換で、`CCrack::strVARIANT`メソッドです。 このメソッドに、可能な場合は、値を変換、`COleVariant`のインスタンスに`CString`です。  
  
## <a name="simple-example-of-a-direct-call-to-dao"></a>DAO の直接呼び出しの簡単な例  
 場合は、基になる DAO コレクション オブジェクトを更新する必要がある場合に発生する可能性です。 通常、これは必要ありませんが単純なプロシージャである必要がある場合。 コレクションが更新する必要がある場合の例は、マルチ ユーザー環境で動作している複数のユーザーが新しいテーブル定義を作成するときです。 ここでは、テーブル定義のコレクションが古くなる可能性があります。 コレクションを更新するだけで呼び出す必要がある、`Refresh`エラー、特定のコレクションのオブジェクトのチェック方法。  
  
```  
DAO_CHECK(pMyDaoDatabase->  
    m_pDAOTableDefs->Refresh());
```  
  
 現在 DAO コレクション オブジェクトのすべてのインターフェイスがある、MFC DAO データベース クラスのドキュメントに未記載の実装の詳細に注意してください。  
  
## <a name="using-dao-directly-for-dao-security-features"></a>DAO を使用して直接 DAO のセキュリティ機能  
 MFC DAO データベース クラスでは、DAO セキュリティ機能をラップしないでください。 一部の DAO のセキュリティ機能を使用する、DAO インターフェイスのメソッドを呼び出す必要があります。 次の関数は、システム データベースを設定し、ユーザーのパスワードを変更します。 この関数は、3 つの関数を後で定義されているを呼び出します。  
  
```  
void ChangeUserPassword()  
{ *// Specify path to the Microsoft Access *// system database  
    CString strSystemDB = 
    _T("c:\\Program Files\\MSOffice\\access\\System.mdw");

 *// Set system database before MFC initilizes DAO *// NOTE: An MFC module uses only one instance *// of a DAO database engine object. If you have *// called a DAO object in your application prior *// to calling the function below,
    you must call *// AfxDaoTerm to destroy the existing database *// engine object. Otherwise,
    the database engine *// object already in use will be reused,
    and setting *// a system datbase will have no effect. *// *// If you have used a DAO object prior to calling *// this function it is important that DAO be *// terminated with AfxDaoTerm since an MFC *// module only gets one copy of the database engine *// and that engine will be reused if it hasn't been *// terminated. In other words,
    if you do not call *// AfxDaoTerm and there is currently a database *// initialized,
    setting the system database will *// have no affect.  
 
    SetSystemDB(strSystemDB);

 *// User name and password manually added *// by using Microsoft Access  
    CString strUserName = _T("NewUser");

    CString strOldPassword = _T("Password");

    CString strNewPassword = _T("NewPassword");

 *// Set default user so that MFC will be able *// to log in by default using the user name and *// password from the system database  
    SetDefaultUser(strUserName,
    strOldPassword);

 *// Change the password. You should be able to *// call this function from anywhere in your *// MFC application  
    ChangePassword(strUserName,
    strOldPassword,   
    strNewPassword);

 
 .  
 .  
 .  
 
}  
```  
  
 次の 4 つの例を示す方法。  
  
-   システム DAO データベース設定 (です。MDW ファイル) です。  
  
-   既定のユーザーとパスワードを設定します。  
  
-   ユーザーのパスワードを変更します。  
  
-   パスワードを変更します。MDB ファイルです。  
  
### <a name="setting-the-system-database"></a>システム データベースの設定  
 アプリケーションによって使用されるシステム データベースを設定する関数のサンプルを次に示します。 その他の DAO 呼び出しが行われる前に、この関数を呼び出す必要があります。  
  
```  
// Set the system database that the   
// DAO database engine will use  
 
void SetSystemDB(CString& strSystemMDB)  
{  
    COleVariant varSystemDB(strSystemMDB, VT_BSTRT);

 *// Initialize DAO for MFC  
    AfxDaoInit();
DAODBEngine* pDBEngine = AfxDaoGetEngine();

 
    ASSERT(pDBEngine != NULL);

 *// Call put_SystemDB method to set the *// system database for DAO engine  
    DAO_CHECK(pDBEngine->put_SystemDB(varSystemDB.bstrVal));

} 
```  
  
### <a name="setting-the-default-user-and-password"></a>既定のユーザーとパスワードの設定  
 既定のユーザーおよびシステム データベースのパスワードを設定するには、次の関数を使用します。  
  
```  
void SetDefaultUser(CString& strUserName,
    CString& strPassword)  
{  
    COleVariant varUserName(strUserName,
    VT_BSTRT);

    COleVariant varPassword(strPassword,
    VT_BSTRT);

 
    DAODBEngine* pDBEngine = AfxDaoGetEngine();
ASSERT(pDBEngine != NULL);

 *// Set default user:  
    DAO_CHECK(pDBEngine->put_DefaultUser(varUserName.bstrVal));

 *// Set default password:  
    DAO_CHECK(pDBEngine->put_DefaultPassword(varPassword.bstrVal));

} 
```  
  
### <a name="changing-a-users-password"></a>ユーザーのパスワードを変更します。  
 ユーザーのパスワードを変更するには、次の関数を使用します。  
  
```  
void ChangePassword(CString &strUserName,   
    CString &strOldPassword,   
    CString &strNewPassword)  
{ *// Create (open) a workspace  
    CDaoWorkspace wsp;  
    CString strWspName = _T("Temp Workspace");

 
    wsp.Create(strWspName, strUserName,  
    strOldPassword);

 wsp.Append();

 *// Determine how many objects there are *// in the Users collection  
    short nUserCount;  
    short nCurrentUser;  
    DAOUser *pUser = NULL;  
    DAOUsers *pUsers = NULL;  
 *// Side-effect is implicit OLE AddRef() *// on DAOUser object:  
    DAO_CHECK(wsp.m_pDAOWorkspace->get_Users(&pUsers));

 *// Side-effect is implicit OLE AddRef() *// on DAOUsers object  
    DAO_CHECK(pUsers->getcount(&nUserCount));

 *// Traverse through the list of users *// and change password for the userid *// used to create/open the workspace  
    for(nCurrentUser = 0; nCurrentUser <nUserCount;  
    nCurrentUser++) 
 {  
    COleVariant varIndex(nCurrentUser, VT_I2);

    COleVariant varName;  
 *// Retrieve information for user nCurrentUser  
    DAO_CHECK(pUsers->get_Item(varIndex, &pUser));

 *// Retrieve name for user nCurrentUser  
    DAO_CHECK(pUser->get_Name(&V_BSTR(&varName)));

 
    CString strTemp = V_BSTRT(&varName);

 *// If there is a match, change the password  
    if(strTemp == strUserName)  
 {  
    COleVariant varOldPwd(strOldPassword,   
    VT_BSTRT);

 COleVariant  varNewPwd(strNewPassword,   
    VT_BSTRT);

 
    DAO_CHECK(pUser->NewPassword(V_BSTR(&varOldPwd), 
    V_BSTR(&varNewPwd)));

 
    TRACE("\t Password is changed\n");

 }  
 }  
 *// Clean up: decrement the usage count *// on the OLE objects  
    pUser->Release();
pUsers->Release();

 
    wsp.Close();

} 
```  
  
### <a name="changing-the-password-of-an-mdb-file"></a>パスワードを変更する、します。MDB ファイル  
 パスワードを変更します。MDB ファイルで、次の関数を使用します。  
  
```  
void SetDBPassword(LPCTSTR pDB,
    LPCTSTR pszOldPassword,
    LPCTSTR pszNewPassword)  
{  
    CDaoDatabase db;  
    CString strConnect(_T(";pwd="));

 *// the database must be opened as exclusive *// to set a password  
    db.Open(pDB,
    TRUE,
    FALSE,   
    strConnect + pszOldPassword);

 
    COleVariant NewPassword(pszNewPassword,
    VT_BSTRT),  
    OldPassword(pszOldPassword,
    VT_BSTRT);

 
    DAO_CHECK(db.m_pDAODatabase->NewPassword(V_BSTR(&OldPassword), 
    V_BSTR(&NewPassword)));

 
    db.Close();

} 
```  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

