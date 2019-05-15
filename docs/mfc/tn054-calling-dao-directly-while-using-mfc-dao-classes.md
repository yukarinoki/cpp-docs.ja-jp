---
title: TN054:DAO の MFC DAO クラス使用中に直接呼び出し
ms.date: 06/28/2018
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
ms.openlocfilehash: b6aae8929e2840791e8d629378a0ec2261a2cda9
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65610975"
---
# <a name="tn054-calling-dao-directly-while-using-mfc-dao-classes"></a>TN054:DAO の MFC DAO クラス使用中に直接呼び出し

> [!NOTE]
> Visual C 環境とウィザードは、(DAO クラスが含まれていますし、それらを使用することもできます) が DAO をサポートしています。 使用することをお勧めします。 [OLE DB テンプレート](../data/oledb/ole-db-templates.md)または[ODBC と MFC](../data/odbc/odbc-and-mfc.md)の新しいプロジェクト。 DAO は、既存のアプリケーションを維持するためにのみ使用する必要があります。

MFC DAO データベース クラスを使用して、DAO の直接使用する必要がある状況である可能性があります。 通常、これは、ケースになりませんが MFC DAO の直接呼び出しと MFC クラスの使用を結合するときに、直接 DAO を呼び出す単純なを容易にいくつかのヘルパー メカニズムを提供しました。 Dao を直接 DAO の MFC マネージ オブジェクトのメソッドの呼び出しは、いくつかの行のコードのみを必要があります。 作成して、DAO オブジェクトを使用する必要があるかどうか*いない*MFC によって管理されている、次のように実際に呼び出すことで、もう少し作業を実行する必要がある`Release`オブジェクト。 このテクニカル ノートでは、DAO の直接呼び出しする場合、MFC のヘルパーを実行できる内容に役立つと DAO OLE インターフェイスを使用する方法について説明します。 最後に、この注は、セキュリティ機能の DAO の直接 DAO を呼び出す方法を示すいくつかのサンプル関数を提供します。

## <a name="when-to-make-direct-dao-calls"></a>DAO の直接呼び出しを実行するときに

MFC によってラップされていない機能を実装する場合または DAO を直接呼び出すのための最も一般的な状況がコレクションを更新する必要がある場合に発生します。 MFC では公開されない最も重要な機能にはセキュリティです。 セキュリティ機能を実装する場合は、DAO のユーザーとグループのオブジェクトを直接使用する必要があります。 だけでなく、セキュリティ機能がありますのみ、いくつかその他の DAO MFC でサポートされていません。 DAO に遅延をいくつかの追加だけでなく、レコード セットの複製とデータベースのレプリケーション機能が含まれます。

## <a name="a-brief-overview-of-dao-and-mfcs-implementation"></a>DAO と MFC の実装の概要

MFC のラップ DAO はささいなことについて心配する必要はありませんので、多くの詳細を処理することによって DAO をより簡単に使用します。 OLE の作成と DAO オブジェクト (コレクション オブジェクトでは特に)、エラー チェック、および厳密に型指定された、シンプルなインターフェイスの提供の管理の初期化が含まれます (ありません**バリアント**または`BSTR`引数)。 DAO の直接の呼び出しを行うし、これらの機能も利用できます。 呼び出しはすべて、コードが行う必要があります`Release`直接 DAO によって作成されたオブジェクトの呼び出しと*いない*MFC 可能性がありますに内部的に依存しているインターフェイス ポインターのいずれかを変更します。 たとえば、変更しないでください、*開か*の開いているメンバー`CDaoRecordset`オブジェクトの理解していない限り*すべて*内部の影響。 ただし、使用することができます、*開か*フィールド コレクションを取得するには、直接 DAO を呼び出すインターフェイス。 この場合、*開か*メンバーは変更されません。 だけを呼び出す必要が`Release`フィールド コレクションのオブジェクトがオブジェクトを使い終わったときにします。

## <a name="description-of-helpers-to-make-dao-calls-easier"></a>呼び出しを簡略化する DAO ヘルパーの説明

DAO を簡単に呼び出しを行うために、ヘルパーは、MFC DAO データベース クラスで内部的に使用されるヘルパーと同じです。 これらのヘルパーは、予想されるエラーのチェックと、必要に応じて適切な例外のスロー、デバッグ出力のログ、DAO の直接呼び出しを行うときに、リターン コードを確認に使用されます。 基になる 2 つのヘルパー関数と 2 つのヘルパーはこれらのいずれかにマップされる 4 つのマクロがあります。 コードを読んで理解することをお勧めします。 参照してください**DAO_CHECK**、 **DAO_CHECK_ERROR**、 **DAO_CHECK_MEM**、および**DAO_TRACE** AFXDAO でします。マクロを参照して H **AfxDaoCheck**と**AfxDaoTrace** DAOCORE でします。CPP します。

## <a name="using-the-dao-ole-interfaces"></a>DAO の OLE インターフェイスを使用します。

DAO オブジェクト階層内の各オブジェクトの OLE インターフェイスは、DBDAOINT ヘッダー ファイルで定義されます。H \Program Files\Microsoft Visual Studio .NET 2003\VC7\include ディレクトリに存在します。 これらのインターフェイスは、DAO、階層全体を操作するためのメソッドを提供します。

DAO インターフェイスのメソッドの多くの場合を操作する必要があります、`BSTR`オブジェクト (固定長の文字列 OLE オートメーションで使用される)。 `BSTR`オブジェクト通常内にカプセル化、**バリアント**データ型。 MFC クラス`COleVariant`自体からは継承、**バリアント**データ型。 ANSI または Unicode ANSI または Unicode のプロジェクトをビルドするかどうかに応じて DAO インターフェイスを返す`BSTR`秒。 V_BSTR と V_BSTRT、2 つのマクロは、DAO のインターフェイスを保証することを取得するのに便利です、`BSTR`想定される型。

V_BSTR が抽出されます、 *bstrVal*のメンバー、`COleVariant`します。 このマクロは通常のコンテンツを渡す必要がある場合に使用する`COleVariant`DAO インターフェイスのメソッドにします。 次のコード フラグメントでは、宣言と DAO DAOUser インターフェイス V_BSTR マクロを利用する 2 つの方法の実際の使用の両方を示します。

```cpp
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

なお、`VT_BSTRT`引数で指定された、`COleVariant`上記のコンス トラクターにより、ANSI がある`BSTR`で、 `COleVariant` 、ANSI バージョンのアプリケーションと、Unicode をビルドするかどうかは`BSTR`の Unicode バージョンのアプリケーション。 これは、DAO が必要です。

ANSI または Unicode のいずれかを抽出は、その他のマクロ、V_BSTRT、 *bstrVal*のメンバー `COleVariant` (ANSI または Unicode) ビルドの種類によって異なります。 次のコードを抽出する方法を示して、`BSTR`から値を`COleVariant`に、 `CString`:

```cpp
COleVariant varName(_T("MyName"), VT_BSTRT);
CString str = V_BSTRT(&varName);
```

格納されているその他の種類を開くには、その他の手法と、V_BSTRT マクロ`COleVariant`、DAOVIEW サンプルで説明します。 具体的には、この変換で、`CCrack::strVARIANT`メソッド。 このメソッドは、可能であれば、変換の値を`COleVariant`のインスタンスに`CString`します。

## <a name="simple-example-of-a-direct-call-to-dao"></a>DAO の直接呼び出しの簡単な例

基になる DAO コレクション オブジェクトを更新する必要がある場合、状況が発生します。 通常、必要に応じてがありますは単純なプロシージャである必要がある場合。 コレクションが更新しなければならない場合がありますの例は、マルチ ユーザー環境で動作している複数のユーザーが新しいテーブルの定義を作成する場合です。 この場合、テーブル定義のコレクションが古くなる可能性があります。 コレクションを更新するには、単に呼び出す必要がある、`Refresh`エラーのチェックと特定のコレクション オブジェクトのメソッド。

```cpp
DAO_CHECK(pMyDaoDatabase->m_pDAOTableDefs->Refresh());
```

現在 DAO コレクション オブジェクトのすべてのインターフェイスが MFC DAO データベース クラスのドキュメントに未記載の実装の詳細に注意してください。

## <a name="using-dao-directly-for-dao-security-features"></a>セキュリティ機能の DAO の直接 DAO を使用します。

MFC DAO データベース クラスでは、DAO のセキュリティ機能をラップしないでください。 一部の DAO のセキュリティ機能を使用して、DAO インターフェイスのメソッドを呼び出す必要があります。 次の関数は、システム データベースを設定し、ユーザーのパスワードを変更します。 この関数は、3 つの関数を後で定義されているを呼び出します。

```cpp
void ChangeUserPassword()
{
    // Specify path to the Microsoft Access *// system database
    CString strSystemDB =
        _T("c:\\Program Files\\MSOffice\\access\\System.mdw");

    // Set system database before MFC initilizes DAO
    // NOTE: An MFC module uses only one instance
    // of a DAO database engine object. If you have
    // called a DAO object in your application prior
    // to calling the function below, you must call
    // AfxDaoTerm to destroy the existing database
    // engine object. Otherwise, the database engine
    // object already in use will be reused, and setting
    // a system datbase will have no effect.
    //
    // If you have used a DAO object prior to calling
    // this function it is important that DAO be
    // terminated with AfxDaoTerm since an MFC
    // module only gets one copy of the database engine
    // and that engine will be reused if it hasn't been
    // terminated. In other words, if you do not call
    // AfxDaoTerm and there is currently a database
    // initialized, setting the system database will
    // have no effect.
    SetSystemDB(strSystemDB);

    // User name and password manually added
    // by using Microsoft Access
    CString strUserName = _T("NewUser");
    CString strOldPassword = _T("Password");
    CString strNewPassword = _T("NewPassword");

    // Set default user so that MFC will be able
    // to log in by default using the user name and
    // password from the system database
    SetDefaultUser(strUserName, strOldPassword);

    // Change the password. You should be able to
    // call this function from anywhere in your
    // MFC application
    ChangePassword(strUserName, strOldPassword, strNewPassword);

    // ...
}
```

次の 4 つの例をする方法。

- システムの DAO データベースの設定 (します。MDW ファイル)。

- 既定のユーザーとパスワードを設定します。

- ユーザーのパスワードを変更します。

- パスワードを変更します。MDB ファイルです。

### <a name="setting-the-system-database"></a>システム データベースの設定

アプリケーションによって使用されるシステム データベースを設定する関数のサンプルを次に示します。 その他の DAO の呼び出しが行われる前に、この関数を呼び出す必要があります。

```cpp
// Set the system database that the
// DAO database engine will use

void SetSystemDB(CString& strSystemMDB)
{
    COleVariant varSystemDB(strSystemMDB, VT_BSTRT);

    // Initialize DAO for MFC
    AfxDaoInit();
    DAODBEngine* pDBEngine = AfxDaoGetEngine();

    ASSERT(pDBEngine != NULL);

    // Call put_SystemDB method to set the *// system database for DAO engine
    DAO_CHECK(pDBEngine->put_SystemDB(varSystemDB.bstrVal));
}
```

### <a name="setting-the-default-user-and-password"></a>既定のユーザーとパスワードの設定

既定のユーザーとシステム データベースのパスワードを設定するには、次の関数を使用します。

```cpp
void SetDefaultUser(CString& strUserName,
    CString& strPassword)
{
    COleVariant varUserName(strUserName, VT_BSTRT);
    COleVariant varPassword(strPassword, VT_BSTRT);

    DAODBEngine* pDBEngine = AfxDaoGetEngine();
    ASSERT(pDBEngine != NULL);

    // Set default user:
    DAO_CHECK(pDBEngine->put_DefaultUser(varUserName.bstrVal));

    // Set default password:
    DAO_CHECK(pDBEngine->put_DefaultPassword(varPassword.bstrVal));
}
```

### <a name="changing-a-users-password"></a>ユーザーのパスワードを変更します。

ユーザーのパスワードを変更するには、次の関数を使用します。

```cpp
void ChangePassword(CString &strUserName,
    CString &strOldPassword,
    CString &strNewPassword)
{
    // Create (open) a workspace
    CDaoWorkspace wsp;
    CString strWspName = _T("Temp Workspace");

    wsp.Create(strWspName, strUserName, strOldPassword);
    wsp.Append();

    // Determine how many objects there are *// in the Users collection
    short nUserCount;
    short nCurrentUser;
    DAOUser *pUser = NULL;
    DAOUsers *pUsers = NULL;

    // Side-effect is implicit OLE AddRef()
    // on DAOUser object:
    DAO_CHECK(wsp.m_pDAOWorkspace->get_Users(&pUsers));

    // Side-effect is implicit OLE AddRef()
    // on DAOUsers object
    DAO_CHECK(pUsers->getcount(&nUserCount));

    // Traverse through the list of users
    // and change password for the userid
    // used to create/open the workspace
    for(nCurrentUser = 0; nCurrentUser <nUserCount; nCurrentUser++)
    {
        COleVariant varIndex(nCurrentUser, VT_I2);
        COleVariant varName;

        // Retrieve information for user nCurrentUser
        DAO_CHECK(pUsers->get_Item(varIndex, &pUser));

        // Retrieve name for user nCurrentUser
        DAO_CHECK(pUser->get_Name(&V_BSTR(&varName)));

        CString strTemp = V_BSTRT(&varName);

        // If there is a match, change the password
        if (strTemp == strUserName)
        {
            COleVariant varOldPwd(strOldPassword, VT_BSTRT);
            COleVariant varNewPwd(strNewPassword, VT_BSTRT);

            DAO_CHECK(pUser->NewPassword(V_BSTR(&varOldPwd),
                V_BSTR(&varNewPwd)));

            TRACE("\t Password is changed\n");
        }
    }
    // Clean up: decrement the usage count
    // on the OLE objects
    pUser->Release();
    pUsers->Release();
    wsp.Close();
}
```

### <a name="changing-the-password-of-an-mdb-file"></a>パスワードを変更します。MDB ファイル

パスワードを変更します。MDB ファイルで、次の関数を使用します。

```cpp
void SetDBPassword(LPCTSTR pDB,
    LPCTSTR pszOldPassword,
    LPCTSTR pszNewPassword)
{
    CDaoDatabase db;
    CString strConnect(_T(";pwd="));

    // the database must be opened as exclusive
    // to set a password
    db.Open(pDB, TRUE, FALSE, strConnect + pszOldPassword);

    COleVariant NewPassword(pszNewPassword, VT_BSTRT),
                OldPassword(pszOldPassword, VT_BSTRT);

    DAO_CHECK(db.m_pDAODatabase->NewPassword(V_BSTR(&OldPassword),
        V_BSTR(&NewPassword)));

    db.Close();
}
```

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
