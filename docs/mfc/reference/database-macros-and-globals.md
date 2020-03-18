---
title: データベース マクロとデータベース グローバル関数
ms.date: 11/04/2016
f1_keywords:
- AFXDB/AFX_ODBC_CALL
- AFXDB/AFX_SQL_ASYNC
- AFXDB/AFX_SQL_SYNC
- AFXDB/AfxGetHENV
helpviewer_keywords:
- global database functions [MFC]
- database macros [MFC]
- database globals [MFC]
- global functions [MFC], database functions
- macros [MFC], MFC database
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
ms.openlocfilehash: 47a1bb434801c24ab8eee048d9ef8f93793101cc
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79426271"
---
# <a name="database-macros-and-globals"></a>データベース マクロとデータベース グローバル関数

次に示すマクロおよびグローバルは、ODBC ベースのデータベースアプリケーションに適用されます。 DAO ベースのアプリケーションでは使用されません。

MFC 4.2 より前では、マクロ `AFX_SQL_ASYNC` および `AFX_SQL_SYNC`、非同期操作によって他のプロセスに時間をかかる機会を与えました。 Mfc 4.2 以降では、MFC ODBC クラスが同期操作のみを使用しているため、これらのマクロの実装が変更されました。 マクロ `AFX_ODBC_CALL` は、MFC 4.2 の新しいものでした。

### <a name="database-macros"></a>データベースマクロ

|||
|-|-|
|[AFX_ODBC_CALL](#afx_odbc_call)|`SQL_STILL_EXECUTING`を返す ODBC API 関数を呼び出します。 `AFX_ODBC_CALL` は、`SQL_STILL_EXECUTING`が返されなくなるまで、関数を繰り返し呼び出します。|
|[AFX_SQL_ASYNC](#afx_sql_async)|`AFX_ODBC_CALL` を呼び出します。|
|[AFX_SQL_SYNC](#afx_sql_sync)|`SQL_STILL_EXECUTING`を返さない ODBC API 関数を呼び出します。|

### <a name="database-globals"></a>データベースグローバル

|||
|-|-|
|[AfxDbInitModule](#afxdbinitmodule)|MFC に動的にリンクされるレギュラー MFC DLL のデータベースサポートを追加します。|
|[AfxGetHENV](#afxgethenv)|MFC によって現在使用されている ODBC 環境へのハンドルを取得します。 このハンドルは、直接 ODBC 呼び出しで使用できます。|

## <a name="afxdbinitmodule"></a>AfxDbInitModule

Mfc に動的にリンクされるレギュラー MFC DLL からの MFC データベース (または DAO) のサポートについては、MFC データベース DLL を初期化するために、通常の MFC DLL の `CWinApp::InitInstance` 関数でこの関数の呼び出しを追加します。

### <a name="syntax"></a>構文

```
void AFXAPI AfxDbInitModule( );
```

### <a name="remarks"></a>解説

この呼び出しは、基本クラスの呼び出しの前、または MFC データベース DLL にアクセスする追加のコードの前に行われていることを確認してください。 MFC データベース DLL は MFC 拡張 DLL です。MFC 拡張 DLL を `CDynLinkLibrary` チェーンに接続するには、それを使用するすべてのモジュールのコンテキストで `CDynLinkLibrary` オブジェクトを作成する必要があります。 `AfxDbInitModule` は、標準の mfc dll のコンテキストで `CDynLinkLibrary` オブジェクトを作成し、通常の MFC DLL の `CDynLinkLibrary` オブジェクトチェーンに接続できるようにします。

### <a name="requirements"></a>必要条件

**ヘッダー:** \<afxdll_ >

##  <a name="afx_odbc_call"></a>AFX_ODBC_CALL

このマクロを使用して、`SQL_STILL_EXECUTING`を返す可能性のある ODBC API 関数を呼び出します。

```
AFX_ODBC_CALL(SQLFunc)
```

### <a name="parameters"></a>パラメーター

*SQLFunc*<br/>
ODBC API 関数。 ODBC API 関数の詳細については、Windows SDK を参照してください。

### <a name="remarks"></a>解説

`AFX_ODBC_CALL` は、`SQL_STILL_EXECUTING`が返されなくなるまで、関数を繰り返し呼び出します。

`AFX_ODBC_CALL`を呼び出す前に、型 RETCODE の変数 `nRetCode`を宣言する必要があります。

MFC ODBC クラスでは、同期処理のみが使用されるようになったことに注意してください。 非同期操作を実行するには、`SQLSetConnectOption`ODBC API 関数を呼び出す必要があります。 詳細については、Windows SDK の「関数の非同期実行」を参照してください。

### <a name="example"></a>例

この例では、`AFX_ODBC_CALL` を使用して、`strTableName`によって指定されたテーブル内の列の一覧を返す、`SQLColumns` ODBC API 関数を呼び出します。 `nRetCode` の宣言と、レコードセットデータメンバーを使用した関数へのパラメーターの引き渡しに注意してください。 また、この例では、`CRecordset`クラスのメンバー関数 `Check`を使用して呼び出しの結果を確認する方法も示しています。 変数 `prs` は `CRecordset` オブジェクトへのポインターであり、他の場所で宣言されています。

[!code-cpp[NVC_MFCDatabase#39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

##  <a name="afx_sql_async"></a>AFX_SQL_ASYNC

MFC 4.2 では、このマクロの実装が変更されました。

```
AFX_SQL_ASYNC(prs, SQLFunc)
```

### <a name="parameters"></a>パラメーター

*pr*<br/>
`CRecordset` オブジェクトまたは `CDatabase` オブジェクトへのポインター。 MFC 4.2 以降では、このパラメーターの値は無視されます。

*SQLFunc*<br/>
ODBC API 関数。 ODBC API 関数の詳細については、Windows SDK を参照してください。

### <a name="remarks"></a>解説

`AFX_SQL_ASYNC` は単にマクロ[AFX_ODBC_CALL](#afx_odbc_call)を呼び出し、 *pr*パラメーターを無視します。 4\.2 より前のバージョンの MFC では、`SQL_STILL_EXECUTING`を返す可能性のある ODBC API 関数を呼び出すために `AFX_SQL_ASYNC` が使用されていました。 ODBC API 関数が `SQL_STILL_EXECUTING`を返した場合、`AFX_SQL_ASYNC` は `prs->OnWaitForDataSource`を呼び出します。

> [!NOTE]
>  MFC ODBC クラスでは、同期処理のみが使用されるようになりました。 非同期操作を実行するには、`SQLSetConnectOption`ODBC API 関数を呼び出す必要があります。 詳細については、Windows SDK の「関数の非同期実行」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdb.h

##  <a name="afx_sql_sync"></a>AFX_SQL_SYNC

`AFX_SQL_SYNC` マクロは、単に関数 `SQLFunc`を呼び出します。

```
AFX_SQL_SYNC(SQLFunc)
```

### <a name="parameters"></a>パラメーター

*SQLFunc*<br/>
ODBC API 関数。 これらの関数の詳細については、「Windows SDK」を参照してください。

### <a name="remarks"></a>解説

このマクロを使用すると、`SQL_STILL_EXECUTING`を返さない ODBC API 関数を呼び出すことができます。

`AFX_SQL_SYNC`を呼び出す前に、RETCODE 型の変数 `nRetCode`を宣言する必要があります。 マクロ呼び出しの後に `nRetCode` の値を確認できます。

MFC 4.2 では `AFX_SQL_SYNC` の実装が変更されていることに注意してください。 サーバーの状態を確認する必要がなくなったため、`AFX_SQL_SYNC` は単に `nRetCode`に値を割り当てます。 たとえば、呼び出しを行うのではなく、

[!code-cpp[NVC_MFCDatabase#40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]

単に割り当てを行うことができます。

[!code-cpp[NVC_MFCDatabase#41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdb.h

##  <a name="afxgethenv"></a>AfxGetHENV

返されたハンドルを直接の ODBC 呼び出しで使用できますが、ハンドルを閉じないでください。または、既存の `CDatabase`または `CRecordset`派生したオブジェクトが破棄された後でもハンドルが有効であり、使用できることを前提としています。

```
HENV AFXAPI AfxGetHENV();
```

### <a name="return-value"></a>戻り値

MFC によって現在使用されている ODBC 環境へのハンドル。 [CDatabase](../../mfc/reference/cdatabase-class.md)オブジェクトがなく、使用されている[CRecordset](../../mfc/reference/crecordset-class.md)オブジェクトがない場合は、`SQL_HENV_NULL` できます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdb.h

## <a name="see-also"></a>参照

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
