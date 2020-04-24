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
ms.openlocfilehash: 6d8bd56c0bfe4f9b35e34d067dd1042ed11066d5
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751656"
---
# <a name="database-macros-and-globals"></a>データベース マクロとデータベース グローバル関数

以下に示すマクロとグローバルは、ODBC ベースのデータベース アプリケーションに適用されます。 DAO ベースのアプリケーションでは使用されません。

MFC 4.2 以前では`AFX_SQL_ASYNC`、`AFX_SQL_SYNC`マクロと非同期操作を他のプロセスに時間を与える機会を与えました。 MFC 4.2 以降、MFC ODBC クラスでは同期操作しか使用されないため、これらのマクロの実装が変更されました。 このマクロ`AFX_ODBC_CALL`は、MFC 4.2 に新しいものでした。

### <a name="database-macros"></a>データベース マクロ

|||
|-|-|
|[AFX_ODBC_CALL](#afx_odbc_call)|を返す ODBC API`SQL_STILL_EXECUTING`関数を呼び出します。 `AFX_ODBC_CALL`は、関数が戻らなくなるまで繰り返`SQL_STILL_EXECUTING`し呼び出します。|
|[AFX_SQL_ASYNC](#afx_sql_async)|`AFX_ODBC_CALL`.|
|[AFX_SQL_SYNC](#afx_sql_sync)|を返さない ODBC API 関数`SQL_STILL_EXECUTING`を呼び出します。|

### <a name="database-globals"></a>データベース・グローバル

|||
|-|-|
|[AfxDbInitModule](#afxdbinitmodule)|MFC に動的にリンクされている通常の MFC DLL のデータベース サポートを追加します。|
|[AfxGetHENV](#afxgethenv)|MFC で現在使用されている ODBC 環境へのハンドルを取得します。 このハンドルは、ODBC 直接呼び出しで使用できます。|

## <a name="afxdbinitmodule"></a><a name="afxdbinitmodule"></a>モジュール

MFC データベース (または DAO) が MFC に動的にリンクされている通常の MFC DLL からサポートされている場合は、MFC`CWinApp::InitInstance`データベース DLL を初期化する通常の MFC DLL 関数にこの関数の呼び出しを追加します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI AfxDbInitModule( );
```

### <a name="remarks"></a>解説

この呼び出しは、基本クラスの呼び出しまたは MFC データベース DLL にアクセスする追加のコードの前に発生することを確認します。 MFC データベース DLL は MFC 拡張 DLL です。MFC 拡張 DLL が`CDynLinkLibrary`チェーンに接続するためには、それを使用するすべてのモジュールのコンテキスト`CDynLinkLibrary`でオブジェクトを作成する必要があります。 `AfxDbInitModule`通常の`CDynLinkLibrary`MFC DLL のコンテキストでオブジェクトを作成し、通常の MFC `CDynLinkLibrary` DLL のオブジェクト チェーンに接続します。

### <a name="requirements"></a>必要条件

**ヘッダー:** \<afxdll_.h>

## <a name="afx_odbc_call"></a><a name="afx_odbc_call"></a>AFX_ODBC_CALL

このマクロを使用して、 を返す可能性のある`SQL_STILL_EXECUTING`ODBC API 関数を呼び出します。

```
AFX_ODBC_CALL(SQLFunc)
```

### <a name="parameters"></a>パラメーター

*を使用する*<br/>
ODBC API 関数。 ODBC API 関数の詳細については、Windows SDK を参照してください。

### <a name="remarks"></a>解説

`AFX_ODBC_CALL`関数が戻らなくなるまで、関数を繰`SQL_STILL_EXECUTING`り返し呼び出します。

を呼び`AFX_ODBC_CALL`出す前に、RETCODE`nRetCode`型の変数を宣言する必要があります。

MFC ODBC クラスでは同期処理のみを使用することに注意してください。 非同期操作を実行するには、ODBC API 関数`SQLSetConnectOption`を呼び出す必要があります。 詳細については、Windows SDK の「関数を非同期に実行する」を参照してください。

### <a name="example"></a>例

この例では`AFX_ODBC_CALL`、ODBC `SQLColumns` API 関数を呼び出すために使用します`strTableName`。 関数にパラメータを`nRetCode`渡すためにレコードセット データ メンバの宣言と使用を確認します。 この例では、 クラスのメンバー関数を使用して`Check`呼び出しの結果`CRecordset`をチェックする方法も示しています。 変数`prs`は、他の場所で`CRecordset`宣言されたオブジェクトへのポインターです。

[!code-cpp[NVC_MFCDatabase#39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="afx_sql_async"></a><a name="afx_sql_async"></a>AFX_SQL_ASYNC

このマクロの実装は MFC 4.2 で変更されました。

```
AFX_SQL_ASYNC(prs, SQLFunc)
```

### <a name="parameters"></a>パラメーター

*Prs*<br/>
`CRecordset`オブジェクトまたは`CDatabase`オブジェクトへのポインター。 MFC 4.2 以降では、このパラメーター値は無視されます。

*を使用する*<br/>
ODBC API 関数。 ODBC API 関数の詳細については、Windows SDK を参照してください。

### <a name="remarks"></a>解説

`AFX_SQL_ASYNC`単にマクロ[をAFX_ODBC_CALL](#afx_odbc_call)呼び出し *、prs*パラメータを無視します。 4.2 より前のバージョンの`AFX_SQL_ASYNC`MFC では、返される`SQL_STILL_EXECUTING`可能性のある ODBC API 関数を呼び出すために使用されていました。 ODBC API 関数が`SQL_STILL_EXECUTING`戻った`AFX_SQL_ASYNC`場合は`prs->OnWaitForDataSource`、 を呼び出します。

> [!NOTE]
> MFC ODBC クラスでは同期処理のみを使用するようになりました。 非同期操作を実行するには、ODBC API 関数`SQLSetConnectOption`を呼び出す必要があります。 詳細については、Windows SDK の「関数を非同期に実行する」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdb.h

## <a name="afx_sql_sync"></a><a name="afx_sql_sync"></a>AFX_SQL_SYNC

マクロ`AFX_SQL_SYNC`は関数`SQLFunc`を呼び出すだけです。

```
AFX_SQL_SYNC(SQLFunc)
```

### <a name="parameters"></a>パラメーター

*を使用する*<br/>
ODBC API 関数。 これらの関数の詳細については、Windows SDK を参照してください。

### <a name="remarks"></a>解説

このマクロを使用して、戻らない ODBC API`SQL_STILL_EXECUTING`関数を呼び出します。

を呼`AFX_SQL_SYNC`び出す前に、RETCODE`nRetCode`型の変数 を宣言する必要があります。 マクロ呼び出し後`nRetCode`の値を確認できます。

MFC 4.2`AFX_SQL_SYNC`での実装変更に注意してください。 サーバーの状態を確認する必要がなくなったため`AFX_SQL_SYNC`、 に値を割`nRetCode`り当てるだけです。 たとえば、呼び出しを行う代わりに

[!code-cpp[NVC_MFCDatabase#40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]

あなたは単に割り当てを行うことができます

[!code-cpp[NVC_MFCDatabase#41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdb.h

## <a name="afxgethenv"></a><a name="afxgethenv"></a>エイプゲゲフ

返されたハンドルは ODBC 直接呼び出しで使用できますが、ハンドルを閉じたり、既存`CDatabase`の派生オブジェクトまたは`CRecordset`派生オブジェクトが破棄された後もハンドルが有効で使用可能であると想定しないでください。

```
HENV AFXAPI AfxGetHENV();
```

### <a name="return-value"></a>戻り値

MFC で現在使用されている ODBC 環境へのハンドル。 `SQL_HENV_NULL` [CDatabase](../../mfc/reference/cdatabase-class.md)オブジェクトがなく[、CRecordset](../../mfc/reference/crecordset-class.md)オブジェクトが使用されていない場合に使用できます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdb.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
