---
title: データベースのマクロとグローバル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFXDB/AFX_ODBC_CALL
- AFXDB/AFX_SQL_ASYNC
- AFXDB/AFX_SQL_SYNC
- AFXDB/AfxGetHENV
dev_langs:
- C++
helpviewer_keywords:
- global database functions [MFC]
- database macros [MFC]
- database globals [MFC]
- global functions [MFC], database functions
- macros [MFC], MFC database
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb4dbb75dba33fe616fbce95cdec74bd81cc3fe9
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121917"
---
# <a name="database-macros-and-globals"></a>データベース マクロとデータベース グローバル関数
マクロとグローバル変数を以下に示す ODBC ベースのデータベース アプリケーションに適用されます。 DAO ベースのアプリケーションでは使用されません。  
  
 MFC 4.2、マクロの前に`AFX_SQL_ASYNC`と`AFX_SQL_SYNC`他のプロセスに時間を生成する機会を非同期操作に指定します。 MFC 4.2 以降、これらのマクロ、MFC ODBC クラスには同期操作のみが使用されるため、変更の実装で開始します。 マクロ`AFX_ODBC_CALL`MFC 4.2 を初めて有効になりました。  
  
### <a name="database-macros"></a>データベースのマクロ  
  
|||  
|-|-|  
|[AFX_ODBC_CALL](#afx_odbc_call)|返す ODBC API 関数を呼び出す`SQL_STILL_EXECUTING`です。 `AFX_ODBC_CALL` 繰り返し関数を呼び出すまで不要になった返します`SQL_STILL_EXECUTING`です。|  
|[AFX_SQL_ASYNC](#afx_sql_async)|`AFX_ODBC_CALL`.|  
|[AFX_SQL_SYNC](#afx_sql_sync)|返されない ODBC API 関数を呼び出す`SQL_STILL_EXECUTING`です。|  
  
### <a name="database-globals"></a>データベースのグローバル関数  
  
|||  
|-|-| 
|[AfxDbInitModule](#afxdbinitmodule)|MFC と動的にリンクされている標準 MFC DLL をサポートするデータベースを追加します。| 
|[AfxGetHENV](#afxgethenv)|MFC で使用されている ODBC 環境ハンドルを取得します。 このハンドルは、ODBC の直接の呼び出しで使用できます。|  


## <a name="afxdbinitmodule"></a> AfxDbInitModule
MFC データベース (または DAO) は、MFC と動的にリンクされている標準 MFC DLL からサポート、標準 MFC dll のこの関数に対する呼び出しを追加`CWinApp::InitInstance`MFC を初期化する関数を DLL のデータベースです。  
   
### <a name="syntax"></a>構文    
```
void AFXAPI AfxDbInitModule( );    
```  
   
### <a name="remarks"></a>Remarks  
 この呼び出しは、基底クラスを呼び出す前に発生または追加の MFC DLL をデータベースにアクセスするコードを確認してください。 MFC データベース DLL が MFC 拡張 DLL です。MFC 拡張 DLL にワイヤード (有線) を取得するため、`CDynLinkLibrary`チェーンを作成する必要があります、`CDynLinkLibrary`を利用することのすべてのモジュールのコンテキスト内のオブジェクト。 `AfxDbInitModule` 作成、`CDynLinkLibrary`にワイヤード (有線) を取得できるように、正規の MFC DLL のコンテキストでオブジェクト、`CDynLinkLibrary`オブジェクトの標準の MFC DLL のチェーン。  
   
### <a name="requirements"></a>必要条件  
 **ヘッダー:** < afxdll_.h >  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)
 
  

##  <a name="afx_odbc_call"></a>  AFX_ODBC_CALL  
 このマクロが返される任意の ODBC API 関数の呼び出しを使用して`SQL_STILL_EXECUTING`です。  
  
```  
AFX_ODBC_CALL(SQLFunc)  
```  
  
### <a name="parameters"></a>パラメーター  
 *SQLFunc*  
 ODBC API 関数。 ODBC API 関数の詳細については、Windows SDK を参照してください。  
  
### <a name="remarks"></a>Remarks  
 `AFX_ODBC_CALL` 繰り返し関数を呼び出すまで不要になった返します`SQL_STILL_EXECUTING`です。  
  
 呼び出す前に`AFX_ODBC_CALL`、変数を宣言する必要があります`nRetCode`型へのです。  
  
 MFC ODBC クラスのみ同期処理を今すぐ使用のことに注意してください。 非同期操作を実行するのには、ODBC API 関数を呼び出す必要があります`SQLSetConnectOption`です。 詳細については、「を実行する関数に非同期的に」Windows SDK のトピックを参照してください。  

  
### <a name="example"></a>例  
 この例では`AFX_ODBC_CALL`を呼び出して、 `SQLColumns` ODBC API 関数は、によってという名前のテーブルの列の一覧を返します`strTableName`です。 宣言することに注意してください`nRetCode`と関数にパラメーターを渡すレコード セットのデータ メンバーを使用します。 例に示すもの呼び出しの結果を確認`Check`、クラスのメンバー関数`CRecordset`です。 変数`prs`へのポインター、`CRecordset`オブジェクト、他の場所を宣言します。  
  
 [!code-cpp[NVC_MFCDatabase#39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]  

### <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdb.h  

##  <a name="afx_sql_async"></a>  AFX_SQL_ASYNC  
 このマクロを MFC 4.2 で変更の実装です。  
  
```   
AFX_SQL_ASYNC(prs, SQLFunc)   
```  
  
### <a name="parameters"></a>パラメーター  
 *pr*  
 ポインター、`CRecordset`オブジェクトまたは`CDatabase`オブジェクト。 MFC 4.2 以降では、このパラメーター値は無視されます。  
  
 *SQLFunc*  
 ODBC API 関数。 ODBC API 関数の詳細については、Windows SDK を参照してください。  
  
### <a name="remarks"></a>Remarks  
 `AFX_SQL_ASYNC` マクロを呼び出すだけ[AFX_ODBC_CALL](#afx_odbc_call)を無視し、 *pr*パラメーター。 MFC の 4.2、以前のバージョンで`AFX_SQL_ASYNC`返す可能性のある ODBC API 関数の呼び出しに使用された`SQL_STILL_EXECUTING`です。 ODBC API 関数が返さ場合`SQL_STILL_EXECUTING`、し、`AFX_SQL_ASYNC`呼び出して`prs->OnWaitForDataSource`です。  
  
> [!NOTE]
>  MFC ODBC クラスは、唯一の同期処理を使用するようになりました。 非同期操作を実行するのには、ODBC API 関数を呼び出す必要があります`SQLSetConnectOption`です。 詳細については、「を実行する関数に非同期的に」Windows SDK のトピックを参照してください。  
  
### <a name="requirements"></a>必要条件  
  **ヘッダー** afxdb.h  
  
##  <a name="afx_sql_sync"></a>  AFX_SQL_SYNC  
 `AFX_SQL_SYNC`マクロ、関数を呼び出すだけ`SQLFunc`です。  
  
```   
AFX_SQL_SYNC(SQLFunc)   
```  
  
### <a name="parameters"></a>パラメーター  
 *SQLFunc*  
 ODBC API 関数。 これらの関数の詳細については、Windows SDK を参照してください。  
  
### <a name="remarks"></a>Remarks  
 このマクロは返されません ODBC API 関数の呼び出しを使用して`SQL_STILL_EXECUTING`です。  
  
 呼び出しの前に`AFX_SQL_SYNC`、変数を宣言する必要があります`nRetCode`型へのです。 値をチェックする`nRetCode`マクロの呼び出し後にします。  
  
 なおの実装`AFX_SQL_SYNC`MFC 4.2 に変更します。 サーバーの状態をチェックは必要ですが不要になったため`AFX_SQL_SYNC`に値を単に割り当てます`nRetCode`です。 呼び出すのではなく、たとえば、  
  
 [!code-cpp[NVC_MFCDatabase#40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]  
  
 割り当てを行うことができます単に  
  
 [!code-cpp[NVC_MFCDatabase#41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]  
  
### <a name="requirements"></a>必要条件  
  **ヘッダー** afxdb.h  
  
##  <a name="afxgethenv"></a>  AfxGetHENV  
 ODBC の直接の呼び出しで返されるハンドルを使用することができますが、ハンドルを終了またはハンドルが有効であり、使用可能な既存のすべての後にあるとする必要がありますしない`CDatabase`- または`CRecordset`-派生オブジェクトが破棄されました。  
  
```   
HENV AFXAPI AfxGetHENV(); 
```  
  
### <a name="return-value"></a>戻り値  
 MFC で使用されている ODBC 環境ハンドルです。 指定できます`SQL_HENV_NULL`がある場合ありません[CDatabase](../../mfc/reference/cdatabase-class.md)オブジェクトおよびいいえ[CRecordset](../../mfc/reference/crecordset-class.md)使用中のオブジェクト。  
  
### <a name="requirements"></a>必要条件  
  **ヘッダー** afxdb.h  
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
