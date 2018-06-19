---
title: レジストリとタイプ ライブラリのグローバル関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlGetPerUserRegistration
- afxpriv/ATL::AfxRegCreateKey
- afxpriv/ATL::AfxRegDeleteKey
- atlbase/ATL::AtlRegisterTypeLib
- afxpriv/ATL::AfxRegOpenKey
- afxpriv/ATL::AfxRegOpenKeyEx
- afxdisp/ATL::AfxUnregisterPreviewHandler
- atlbase/ATL::AtlSetPerUserRegistration
- atlbase/ATL::AtlUnRegisterTypeLib
- atlbase/ATL::AtlLoadTypeLib
- atlbase/ATL::AtlUpdateRegistryFromResourceD
- atlbase/ATL::RegistryDataExchange
dev_langs:
- C++
helpviewer_keywords:
- RegistryDataExchange function, global functions
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb0a89ecf8bb81e515703abe819bb1edfbf80d59
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365508"
---
# <a name="registry-and-typelib-global-functions"></a>レジストリとタイプ ライブラリに関するグローバル関数
これらの関数は、読み込みと登録、タイプ ライブラリのサポートを提供します。  
  
> [!IMPORTANT]
>  次の表に示す関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
|||  
|-|-|  
|[AfxRegCreateKey](#afxrefcreatekey)|指定されたレジストリ キーを作成します。|
|[AfxRegDeleteKey](#afxrefdeletekey)|指定されたレジストリ キーを削除します。|
|[AfxRegisterPreviewHandler](#afxregisterpreviewhandler)|プレビュー ハンドラーを登録するためのヘルパー。|
|[AfxUnregisterPreviewHandler](#afxunregisterpreviewhandler)| プレビュー ハンドラーの登録を解除するためのヘルパー。 |
|[AtlRegisterTypeLib](#atlregistertypelib)|この関数は、タイプ ライブラリを登録するために呼び出されます。|  
|[この代替](#atlunregistertypelib)|この関数は、タイプ ライブラリの登録を解除するには|  
|[AfxRegOpenKey](#afxregopenkey)|指定されたレジストリ キーを開きます。|
|[AfxRegOpenKeyEx](#afxregopenkeyex)|指定されたレジストリ キーを開きます。|
|[AtlLoadTypeLib](#atlloadtypelib)|この関数は、タイプ ライブラリを読み込むために呼び出されます。|  
|[AtlUpdateRegistryFromResourceD](#atlupdateregistryfromresourced)|この関数は、提供されたリソースのレジストリを更新するために呼び出されます。|  
|[RegistryDataExchange](#registrydataexchange)|システム レジストリのデータの読み取り/書き込みを行います。 によって呼び出される、[レジストリ データ交換マクロ](../../atl/reference/registry-data-exchange-macros.md)です。|  
  
 これらの関数は、情報を格納するプログラムを使用して、レジストリ内のどのノードを制御します。  
  
|||  
|-|-|  
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|アプリケーションがレジストリ アクセスをリダイレクトするかどうかを取得、 **HKEY_CURRENT_USER** ( **HKCU**) ノード。|  
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|アプリケーションがレジストリ アクセスをリダイレクトするかどうかを設定、 **HKEY_CURRENT_USER** ( **HKCU**) ノード。|  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h

## <a name="atlgetperuserregistration"></a> AtlGetPerUserRegistration
この関数を使用して、アプリケーションがレジストリ アクセスをリダイレクトするかどうかを判断、 **HKEY_CURRENT_USER** (**HKCU**) ノード。  
  
### <a name="syntax"></a>構文  
  
```  
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `pEnabled`  
 `TRUE` レジストリ情報に送られることを示す、 **HKCU**ノードです。`FALSE`アプリケーションが既定のノードにレジストリ情報を書き出すことを示します。 既定のノードは**HKEY_CLASSES_ROOT** (**HKCR**)。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` メソッドが成功すると、それ以外の場合、`HRESULT`エラーが発生した場合はエラー コード。  
  
### <a name="remarks"></a>コメント  
 レジストリのリダイレクトは、既定では無効です。 このオプションを有効にすると、レジストリへのアクセスにリダイレクト**する**です。  
  
 リダイレクトはグローバルではありません。 MFC と ATL のフレームワークは、このレジストリのリダイレクトの影響を受けます。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  

 ## <a name="afxregcreatekey"></a> AfxRegCreateKey
 指定されたレジストリ キーを作成します。  
  
### <a name="syntax"></a>構文  
  
```  
LONG AFXAPI AfxRegCreateKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);  
```  
  
### <a name="parameters"></a>パラメーター  
 `hKey`  
 開いているレジストリ キーへのハンドル。  
  
 `lpSubKey`  
 この関数を開くか作成するキーの名前。  
  
 `phkResult`  
 開くか作成されたキーへのハンドルを受け取る変数へのポインター。  
  
 `pTM`  
 ポインター、`CAtlTransactionManager`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 関数が成功すると、戻り値は、error_success を返します。 関数が失敗した場合、戻り値は、Winerror.h で定義されている 0 以外のエラー コードです。  

### <a name="requirements"></a>要件  
 **ヘッダー:** afxpriv.h  

## <a name="afxregdeletekey"></a> AfxRegDeleteKey
指定されたレジストリ キーを削除します。  
  
### <a name="syntax"></a>構文  
  
```  
LONG AFXAPI AfxRegDeleteKey(HKEY hKey, LPCTSTR lpSubKey, CAtlTransactionManager* pTM = NULL);  
```  
  
### <a name="parameters"></a>パラメーター  
 `hKey`  
 開いているレジストリ キーへのハンドル。  
  
 `lpSubKey`  
 削除するキーの名前。  
  
 `pTM`  
 ポインター、`CAtlTransactionManager`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 関数が成功すると、戻り値は、error_success を返します。 関数が失敗した場合、戻り値は、Winerror.h で定義されている 0 以外のエラー コードです。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxpriv.h  

## <a name="afxregisterpreviewhandler"></a>
プレビュー ハンドラーを登録するためのヘルパー。  
  
### <a name="syntax"></a>構文  
  
```  
BOOL AFXAPI AfxRegisterPreviewHandler(LPCTSTR lpszCLSID, LPCTSTR lpszShortTypeName, LPCTSTR lpszFilterExt);  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszCLSID`  
 ハンドラーの CLSID を指定します。  
  
 `lpszShortTypeName`  
 ハンドラーの ProgID を指定します。  
  
 `lpszFilterExt`  
 このハンドラーに登録されているファイルの拡張子を指定します。  
  
### <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h   

##  <a name="atlregistertypelib"></a>  AtlRegisterTypeLib  
 この関数は、タイプ ライブラリを登録するために呼び出されます。  
  
  
```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstTypeLib`  
 モジュールのインスタンスへのハンドル。  
  
 `lpszIndex`  
 形式で文字列"\\\N"、N はタイプ ライブラリのリソースの整数のインデックス。 インデックスが必要ない場合、NULL を指定できます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このヘルパー関数がによって使用されて[AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver)と[CAtlComModule::RegisterTypeLib](../../atl/reference/catlcommodule-class.md#registertypelib)です。  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h

 ## <a name="afxregopenkey"></a> AfxRegOpenKey
 指定されたレジストリ キーを開きます。  
  
### <a name="syntax"></a>構文  
  
```  
LONG AFXAPI AfxRegOpenKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);  
```  
  
### <a name="parameters"></a>パラメーター  
 `hKey`  
 開いているレジストリ キーへのハンドル。  
  
 `lpSubKey`  
 この関数を開くか作成するキーの名前。  
  
 `phkResult`  
 作成されたキーへのハンドルを受け取る変数へのポインター。  
  
 `pTM`  
 ポインター、`CAtlTransactionManager`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 関数が成功すると、戻り値は、error_success を返します。 関数が失敗した場合、戻り値は、Winerror.h で定義されている 0 以外のエラー コードです。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxpriv.h  

## <a name="afxregopenkeyex"></a>  AfxRegOpenKeyEx
指定されたレジストリ キーを開きます。 

### <a name="syntax"></a>構文  
  
```  
LONG AFXAPI AfxRegOpenKeyEx(HKEY hKey, LPCTSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);  
```  
  
### <a name="parameters"></a>パラメーター  
 `hKey`  
 開いているレジストリ キーへのハンドル。  
  
 `lpSubKey`  
 この関数を開くか作成するキーの名前。  
  
 `ulOptions`  
 このパラメーターは予約されており、0 にする必要があります。  
  
 `samDesired`  
 キーに必要なアクセス権を指定するマスクです。  
  
 `phkResult`  
 開いているキーへのハンドルを受け取る変数へのポインター。  
  
 `pTM`  
 ポインター、`CAtlTransactionManager`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 関数が成功すると、戻り値は、error_success を返します。 関数が失敗した場合、戻り値は、Winerror.h で定義されている 0 以外のエラー コードです。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxpriv.h  

 ## <a name="afxunregisterpreviewhandler"></a> AfxUnregisterPreviewHandler
 プレビュー ハンドラーの登録を解除するためのヘルパー。  
  
### <a name="syntax"></a>構文  
  
```  
BOOL AFXAPI AfxUnRegisterPreviewHandler(LPCTSTR lpszCLSID);  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszCLSID`  
 登録解除するハンドラーの CLSID を指定します。  
  
### <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  

## <a name="atlsetperuserregistration"></a> AtlSetPerUserRegistration
アプリケーションがレジストリ アクセスをリダイレクトするかどうかを設定、 **HKEY_CURRENT_USER** (**HKCU**) ノード。  
  
### <a name="syntax"></a>構文  
  
```  
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE` レジストリ情報に送られることを示す、 **HKCU**ノードです。`FALSE`アプリケーションが既定のノードにレジストリ情報を書き出すことを示します。 既定のノードは**HKEY_CLASSES_ROOT** (**HKCR**)。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` メソッドが成功すると、それ以外の場合、`HRESULT`エラーが発生した場合はエラー コード。  
  
### <a name="remarks"></a>コメント  
 レジストリのリダイレクトは、既定では無効です。 このオプションを有効にすると、レジストリへのアクセスにリダイレクト**する**です。  
  
 リダイレクトはグローバルではありません。 MFC と ATL のフレームワークは、このレジストリのリダイレクトの影響を受けます。  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  

##  <a name="atlunregistertypelib"></a>  この代替  
 この関数は、タイプ ライブラリの登録を解除するために呼び出されます。  
  
### <a name="syntax"></a>構文  
```
ATLAPI AtlUnRegisterTypeLib(
    HINSTANCE hInstTypeLib, 
    LPCOLESTR lpszIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstTypeLib`  
 モジュールのインスタンスへのハンドル。  
  
 `lpszIndex`  
 形式で文字列"\\\N"、N はタイプ ライブラリのリソースの整数のインデックス。 インデックスが必要ない場合、NULL を指定できます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このヘルパー関数がによって使用されて[CAtlComModule::UnRegisterTypeLib](../../atl/reference/catlcommodule-class.md#unregistertypelib)と[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)です。  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h

##  <a name="atlloadtypelib"></a>  AtlLoadTypeLib  
 この関数は、タイプ ライブラリを読み込むために呼び出されます。  
  
### <a name="syntax"></a>構文  
```
ATLINLINE ATLAPI AtlLoadTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex,
    BSTR* pbstrPath,
    ITypeLib** ppTypeLib);
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstTypeLib`  
 タイプ ライブラリに関連付けられているモジュールへのハンドルします。  
  
 `lpszIndex`  
 形式で文字列"\\\N"、N はタイプ ライブラリのリソースの整数のインデックス。 インデックスが必要ない場合、NULL を指定できます。  
  
 *pbstrPath*  
 正常に返された場合は、タイプ ライブラリに関連付けられているモジュールの完全なパスが含まれています。  
  
 `ppTypeLib`  
 正常に返された場合は、読み込まれたタイプ ライブラリへのポインターへのポインターを格納します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このヘルパー関数がによって使用されて[AtlRegisterTypeLib](#atlregistertypelib)と[この代替](#atlunregistertypelib)です。  
  
##  <a name="atlupdateregistryfromresourced"></a>  AtlUpdateRegistryFromResourceD  
 この関数は Visual Studio 2013 で非推奨とされ、Visual Studio 2015 で削除されます。  
  
```
<removed>
```  
  

  
##  <a name="registrydataexchange"></a>  RegistryDataExchange  
 システム レジストリのデータの読み取り/書き込みを行います。  

### <a name="syntax"></a>構文  
```
HRESULT RegistryDataExchange(
    T* pT,
    enum RDXOperations rdxOp,
    void* pItem = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pT*  
 現在のオブジェクトへのポインター。  
  
 *rdxOp*  
 どの操作を示す列挙値関数を実行する必要があります。 有効な値の「解説」セクションの表を参照してください。  
  
 `pItem`  
 データの読み取りまたはレジストリに書き込まれるデータへのポインター。 データは、レジストリから削除するキーを表すこともできます。 既定値は NULL です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 マクロ[BEGIN_RDX_MAP](registry-data-exchange-macros.md#begin_rdx_map)と[END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map)展開してを呼び出す関数を`RegistryDataExchange`です。  
  
 関数は、操作を実行する必要がありますかを示す列挙値は、次の表に示します。  
  
|列挙値|操作|  
|----------------|---------------|  
|eReadFromReg|レジストリからデータを読み取ります。|  
|eWriteToReg|データをレジストリに書き込みます。|  
|eDeleteFromReg|キーがレジストリから削除します。|  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h

## <a name="see-also"></a>関連項目  
 [関数](atl-functions.md)[レジストリ データ交換マクロ](registry-data-exchange-macros.md)





