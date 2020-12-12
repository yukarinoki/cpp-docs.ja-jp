---
description: 詳細については、「データベースマクロとグローバル」を参照してください。
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
ms.openlocfilehash: 1dd6501c8ea37478a7b75341467e1c77819aa3f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220319"
---
# <a name="database-macros-and-globals"></a>データベース マクロとデータベース グローバル関数

次に示すマクロおよびグローバルは、ODBC ベースのデータベースアプリケーションに適用されます。 DAO ベースのアプリケーションでは使用されません。

MFC 4.2 より前では、マクロは、 `AFX_SQL_ASYNC` `AFX_SQL_SYNC` 他のプロセスに時間をかかる機会を非同期操作に与えました。 Mfc 4.2 以降では、MFC ODBC クラスが同期操作のみを使用しているため、これらのマクロの実装が変更されました。 マクロは `AFX_ODBC_CALL` MFC 4.2 に新しく追加されました。

### <a name="database-macros"></a>データベースマクロ

|名前|説明|
|-|-|
|[AFX_ODBC_CALL](#afx_odbc_call)|を返す ODBC API 関数を呼び出し `SQL_STILL_EXECUTING` ます。 `AFX_ODBC_CALL` は、が返されなくなるまで、関数を繰り返し呼び出し `SQL_STILL_EXECUTING` ます。|
|[AFX_SQL_ASYNC](#afx_sql_async)|`AFX_ODBC_CALL`.|
|[AFX_SQL_SYNC](#afx_sql_sync)|を返さない ODBC API 関数を呼び出し `SQL_STILL_EXECUTING` ます。|

### <a name="database-globals"></a>データベースグローバル

|名前|説明|
|-|-|
|[AfxDbInitModule](#afxdbinitmodule)|MFC に動的にリンクされるレギュラー MFC DLL のデータベースサポートを追加します。|
|[AfxGetHENV](#afxgethenv)|MFC によって現在使用されている ODBC 環境へのハンドルを取得します。 このハンドルは、直接 ODBC 呼び出しで使用できます。|

## <a name="afxdbinitmodule"></a><a name="afxdbinitmodule"></a> AfxDbInitModule

Mfc に動的にリンクされるレギュラー MFC DLL からの MFC データベース (または DAO) のサポートについては、 `CWinApp::InitInstance` mfc データベース dll を初期化するために、通常の MFC dll の関数にこの関数の呼び出しを追加します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI AfxDbInitModule( );
```

### <a name="remarks"></a>解説

この呼び出しは、基本クラスの呼び出しの前、または MFC データベース DLL にアクセスする追加のコードの前に行われていることを確認してください。 MFC データベース DLL は MFC 拡張 DLL です。MFC 拡張 DLL をチェーンに接続するには `CDynLinkLibrary` 、 `CDynLinkLibrary` それを使用するすべてのモジュールのコンテキストでオブジェクトを作成する必要があります。 `AfxDbInitModule` 通常の mfc dll のコンテキストでオブジェクトを作成し、 `CDynLinkLibrary` `CDynLinkLibrary` 通常の mfc dll のオブジェクトチェーンに接続できるようにします。

### <a name="requirements"></a>要件

**ヘッダー:**\<afxdll_.h>

## <a name="afx_odbc_call"></a><a name="afx_odbc_call"></a> AFX_ODBC_CALL

このマクロは、を返す可能性のある ODBC API 関数を呼び出すために使用し `SQL_STILL_EXECUTING` ます。

```
AFX_ODBC_CALL(SQLFunc)
```

### <a name="parameters"></a>パラメーター

*SQLFunc*<br/>
ODBC API 関数。 ODBC API 関数の詳細については、Windows SDK を参照してください。

### <a name="remarks"></a>解説

`AFX_ODBC_CALL` が返されなくなるまで、関数を繰り返し呼び出し `SQL_STILL_EXECUTING` ます。

を呼び出す前に、 `AFX_ODBC_CALL` RETCODE 型の変数を宣言する必要があり `nRetCode` ます。

MFC ODBC クラスでは、同期処理のみが使用されるようになったことに注意してください。 非同期操作を実行するには、ODBC API 関数を呼び出す必要があり `SQLSetConnectOption` ます。 詳細については、Windows SDK の「関数の非同期実行」を参照してください。

### <a name="example"></a>例

この例では、を使用し `AFX_ODBC_CALL` `SQLColumns` て ODBC API 関数を呼び出します。この関数は、によって指定されたテーブル内の列の一覧を返し `strTableName` ます。 の宣言と、 `nRetCode` レコードセットデータメンバーを使用した関数へのパラメーターの引き渡しに注意してください。 また、この例では `Check` 、クラスのメンバー関数であるを使用して、呼び出しの結果を確認する方法も示してい `CRecordset` ます。 変数 `prs` は、 `CRecordset` 他の場所で宣言されたオブジェクトへのポインターです。

[!code-cpp[NVC_MFCDatabase#39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]

### <a name="requirements"></a>要件

**ヘッダー:** afxdb.h

## <a name="afx_sql_async"></a><a name="afx_sql_async"></a> AFX_SQL_ASYNC

MFC 4.2 では、このマクロの実装が変更されました。

```
AFX_SQL_ASYNC(prs, SQLFunc)
```

### <a name="parameters"></a>パラメーター

*prs*<br/>
`CRecordset`オブジェクトまたはオブジェクトへのポインター `CDatabase` 。 MFC 4.2 以降では、このパラメーターの値は無視されます。

*SQLFunc*<br/>
ODBC API 関数。 ODBC API 関数の詳細については、Windows SDK を参照してください。

### <a name="remarks"></a>解説

`AFX_SQL_ASYNC` は単にマクロ [AFX_ODBC_CALL](#afx_odbc_call) を呼び出し、 *pr* パラメーターを無視します。 4.2 より前のバージョンの MFC では、を `AFX_SQL_ASYNC` 返す可能性のある ODBC API 関数を呼び出すためにが使用されていま `SQL_STILL_EXECUTING` した。 ODBC API 関数がを返した場合 `SQL_STILL_EXECUTING` 、 `AFX_SQL_ASYNC` はを呼び出し `prs->OnWaitForDataSource` ます。

> [!NOTE]
> MFC ODBC クラスでは、同期処理のみが使用されるようになりました。 非同期操作を実行するには、ODBC API 関数を呼び出す必要があり `SQLSetConnectOption` ます。 詳細については、Windows SDK の「関数の非同期実行」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdb.h

## <a name="afx_sql_sync"></a><a name="afx_sql_sync"></a> AFX_SQL_SYNC

`AFX_SQL_SYNC`マクロは、単に関数を呼び出し `SQLFunc` ます。

```
AFX_SQL_SYNC(SQLFunc)
```

### <a name="parameters"></a>パラメーター

*SQLFunc*<br/>
ODBC API 関数。 これらの関数の詳細については、「Windows SDK」を参照してください。

### <a name="remarks"></a>解説

このマクロを使用すると、を返さない ODBC API 関数を呼び出すことが `SQL_STILL_EXECUTING` できます。

を呼び出す前に、 `AFX_SQL_SYNC` RETCODE 型の変数を宣言する必要があり `nRetCode` ます。 マクロ呼び出しの後にの値を確認でき `nRetCode` ます。

MFC 4.2 では、の実装が変更されていることに注意 `AFX_SQL_SYNC` してください。 サーバーの状態を確認する必要がなくなったため、は `AFX_SQL_SYNC` 単にに値を割り当て `nRetCode` ます。 たとえば、呼び出しを行うのではなく、

[!code-cpp[NVC_MFCDatabase#40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]

単に割り当てを行うことができます。

[!code-cpp[NVC_MFCDatabase#41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]

### <a name="requirements"></a>要件

  **ヘッダー** afxdb.h

## <a name="afxgethenv"></a><a name="afxgethenv"></a> AfxGetHENV

返されたハンドルは、直接の ODBC 呼び出しで使用できますが、ハンドルを閉じないでください。または、既存 `CDatabase` のまたは `CRecordset` 派生したオブジェクトが破棄された後でもハンドルが有効であり、使用できることを前提としています。

```
HENV AFXAPI AfxGetHENV();
```

### <a name="return-value"></a>戻り値

MFC によって現在使用されている ODBC 環境へのハンドル。 `SQL_HENV_NULL` [CDatabase](../../mfc/reference/cdatabase-class.md)オブジェクトがなく、使用されている[CRecordset](../../mfc/reference/crecordset-class.md)オブジェクトがない場合は、にすることができます。

### <a name="requirements"></a>要件

  **ヘッダー** afxdb.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
