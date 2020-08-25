---
title: レジストリとタイプ ライブラリに関するグローバル関数
ms.date: 03/27/2019
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
helpviewer_keywords:
- RegistryDataExchange function, global functions
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
ms.openlocfilehash: 0f29f8cac62a7452781e8fde697cdf992db00b8c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834619"
---
# <a name="registry-and-typelib-global-functions"></a>レジストリとタイプ ライブラリに関するグローバル関数

これらの関数は、タイプライブラリの読み込みと登録をサポートしています。

> [!IMPORTANT]
> 次の表に示す関数は、Windows ランタイムで実行するアプリケーションでは使用できません。

|名前|説明|
|-|-|
|[AfxRegCreateKey](#afxregcreatekey)|指定されたレジストリキーを作成します。|
|[AfxRegDeleteKey](#afxregdeletekey)|指定されたレジストリキーを削除します。|
|[AfxRegisterPreviewHandler](#afxregisterpreviewhandler)|プレビューハンドラーを登録するヘルパー。|
|[AfxUnregisterPreviewHandler](#afxunregisterpreviewhandler)| プレビューハンドラーの登録を解除するヘルパー。 |
|[AtlRegisterTypeLib](#atlregistertypelib)|この関数は、タイプ ライブラリを登録するために呼び出されます。|
|[AtlUnRegisterTypeLib](#atlunregistertypelib)|この関数は、タイプライブラリの登録を解除するために呼び出されます。|
|[AfxRegOpenKey](#afxregopenkey)|指定されたレジストリキーを開きます。|
|[AfxRegOpenKeyEx](#afxregopenkeyex)|指定されたレジストリキーを開きます。|
|[AtlLoadTypeLib](#atlloadtypelib)|この関数は、タイプ ライブラリを読み込むために呼び出されます。|
|[AtlUpdateRegistryFromResourceD](#atlupdateregistryfromresourced)|この関数は、提供されたリソースのレジストリを更新するために呼び出されます。|
|[RegistryDataExchange](#registrydataexchange)|システム レジストリのデータの読み取り/書き込みを行います。 [レジストリデータ交換マクロ](../../atl/reference/registry-data-exchange-macros.md)によって呼び出されます。|

これらの関数は、プログラムが情報を格納するために使用するレジストリ内のノードを制御します。

|名前|説明|
|-|-|
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|アプリケーションがレジストリアクセスを **HKEY_CURRENT_USER** ( **HKCU**) ノードにリダイレクトするかどうかを取得します。|
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|アプリケーションがレジストリアクセスを **HKEY_CURRENT_USER** ( **HKCU**) ノードにリダイレクトするかどうかを設定します。|

### <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="atlgetperuserregistration"></a><a name="atlgetperuserregistration"></a> AtlGetPerUserRegistration

アプリケーションがレジストリアクセスを **HKEY_CURRENT_USER** (**HKCU**) ノードにリダイレクトするかどうかを判断するには、この関数を使用します。

### <a name="syntax"></a>構文

```
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);
```

### <a name="parameters"></a>パラメーター

*pEnabled*<br/>
入出力TRUE は、レジストリ情報が **HKCU** ノードに送られることを示します。FALSE は、アプリケーションがレジストリ情報を既定のノードに書き込むことを示します。 既定のノードは **HKEY_CLASSES_ROOT** (**HKCR**) です。

### <a name="return-value"></a>戻り値

メソッドが正常に実行された場合は S_OK。それ以外の場合は、エラーが発生した場合は HRESULT エラーコード。

### <a name="remarks"></a>解説

レジストリリダイレクトは、既定では有効になっていません。 このオプションを有効にすると、レジストリへのアクセスは **HKEY_CURRENT_USER の \ ソフトウェアクラス**にリダイレクトされます。

リダイレクトはグローバルではありません。 このレジストリのリダイレクトによって影響を受けるのは、MFC フレームワークと ATL フレームワークだけです。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="afxregcreatekey"></a><a name="afxregcreatekey"></a> AfxRegCreateKey

指定されたレジストリキーを作成します。

### <a name="syntax"></a>構文

```
LONG AFXAPI AfxRegCreateKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>パラメーター

*hKey*<br/>
開いているレジストリキーを処理するハンドル。

*lpSubKey*<br/>
この関数が開いたり作成したりするキーの名前。

*phkResult*<br/>
開かれたキーまたは作成されたキーへのハンドルを受け取る変数へのポインター。

*pTM*<br/>
オブジェクトへのポインター `CAtlTransactionManager` 。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値は ERROR_SUCCESS になります。 関数が失敗した場合、戻り値は Winerror.h で定義されている0以外のエラーコードになります。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxpriv.h

## <a name="afxregdeletekey"></a><a name="afxregdeletekey"></a> AfxRegDeleteKey

指定されたレジストリキーを削除します。

### <a name="syntax"></a>構文

```
LONG AFXAPI AfxRegDeleteKey(HKEY hKey, LPCTSTR lpSubKey, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>パラメーター

*hKey*<br/>
開いているレジストリキーを処理するハンドル。

*lpSubKey*<br/>
削除するキーの名前。

*pTM*<br/>
オブジェクトへのポインター `CAtlTransactionManager` 。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値は ERROR_SUCCESS になります。 関数が失敗した場合、戻り値は Winerror.h で定義されている0以外のエラーコードになります。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxpriv.h

## <a name="afxregisterpreviewhandler"></a>

プレビューハンドラーを登録するヘルパー。

### <a name="syntax"></a>構文

```
BOOL AFXAPI AfxRegisterPreviewHandler(LPCTSTR lpszCLSID, LPCTSTR lpszShortTypeName, LPCTSTR lpszFilterExt);
```

### <a name="parameters"></a>パラメーター

*lpszCLSID*<br/>
ハンドラーの CLSID を指定します。

*Lpsz短い Typename*<br/>
ハンドラーの ProgID を指定します。

*lpszFilterExt*<br/>
このハンドラーに登録されているファイル拡張子を指定します。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="atlregistertypelib"></a><a name="atlregistertypelib"></a> AtlRegisterTypeLib

この関数は、タイプ ライブラリを登録するために呼び出されます。

```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>パラメーター

*hInstTypeLib*<br/>
モジュールインスタンスへのハンドル。

*lpszIndex*<br/>
"\N" という形式の文字列 \\ 。ここで、N はタイプライブラリリソースの整数インデックスです。 インデックスが不要な場合は NULL を指定できます。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

このヘルパー関数は、 [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver) と [CAtlComModule:: RegisterTypeLib](../../atl/reference/catlcommodule-class.md#registertypelib)によって使用されます。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="afxregopenkey"></a><a name="afxregopenkey"></a> AfxRegOpenKey

指定されたレジストリキーを開きます。

### <a name="syntax"></a>構文

```
LONG AFXAPI AfxRegOpenKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>パラメーター

*hKey*<br/>
開いているレジストリキーを処理するハンドル。

*lpSubKey*<br/>
この関数が開いたり作成したりするキーの名前。

*phkResult*<br/>
作成されたキーへのハンドルを受け取る変数へのポインター。

*pTM*<br/>
オブジェクトへのポインター `CAtlTransactionManager` 。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値は ERROR_SUCCESS になります。 関数が失敗した場合、戻り値は Winerror.h で定義されている0以外のエラーコードになります。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxpriv.h

## <a name="afxregopenkeyex"></a><a name="afxregopenkeyex"></a> AfxRegOpenKeyEx

指定されたレジストリキーを開きます。

### <a name="syntax"></a>構文

```
LONG AFXAPI AfxRegOpenKeyEx(HKEY hKey, LPCTSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>パラメーター

*hKey*<br/>
開いているレジストリキーを処理するハンドル。

*lpSubKey*<br/>
この関数が開いたり作成したりするキーの名前。

*ulOptions*<br/>
このパラメーターは予約されており、ゼロにする必要があります。

*samDesired*<br/>
キーに対する必要なアクセス権を指定するマスク。

*phkResult*<br/>
開かれているキーへのハンドルを受け取る変数へのポインター。

*pTM*<br/>
オブジェクトへのポインター `CAtlTransactionManager` 。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値は ERROR_SUCCESS になります。 関数が失敗した場合、戻り値は Winerror.h で定義されている0以外のエラーコードになります。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxpriv.h

## <a name="afxunregisterpreviewhandler"></a><a name="afxunregisterpreviewhandler"></a> AfxUnregisterPreviewHandler

プレビューハンドラーの登録を解除するヘルパー。

### <a name="syntax"></a>構文

```
BOOL AFXAPI AfxUnRegisterPreviewHandler(LPCTSTR lpszCLSID);
```

### <a name="parameters"></a>パラメーター

*lpszCLSID*<br/>
登録を解除するハンドラーの CLSID を指定します。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="atlsetperuserregistration"></a><a name="atlsetperuserregistration"></a> AtlSetPerUserRegistration

アプリケーションがレジストリアクセスを **HKEY_CURRENT_USER** (**HKCU**) ノードにリダイレクトするかどうかを設定します。

### <a name="syntax"></a>構文

```
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
からTRUE は、レジストリ情報が **HKCU** ノードに送られることを示します。FALSE は、アプリケーションがレジストリ情報を既定のノードに書き込むことを示します。 既定のノードは **HKEY_CLASSES_ROOT** (**HKCR**) です。

### <a name="return-value"></a>戻り値

メソッドが正常に実行された場合は S_OK。それ以外の場合は、エラーが発生した場合は HRESULT エラーコード。

### <a name="remarks"></a>解説

レジストリリダイレクトは、既定では有効になっていません。 このオプションを有効にすると、レジストリへのアクセスは **HKEY_CURRENT_USER の \ ソフトウェアクラス**にリダイレクトされます。

リダイレクトはグローバルではありません。 このレジストリのリダイレクトによって影響を受けるのは、MFC フレームワークと ATL フレームワークだけです。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="atlunregistertypelib"></a><a name="atlunregistertypelib"></a> AtlUnRegisterTypeLib

この関数は、タイプ ライブラリの登録を解除するために呼び出されます。

### <a name="syntax"></a>構文

```
ATLAPI AtlUnRegisterTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>パラメーター

*hInstTypeLib*<br/>
モジュールインスタンスへのハンドル。

*lpszIndex*<br/>
"\N" という形式の文字列 \\ 。ここで、N はタイプライブラリリソースの整数インデックスです。 インデックスが不要な場合は NULL を指定できます。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

このヘルパー関数は、 [CAtlComModule:: UnRegisterTypeLib](../../atl/reference/catlcommodule-class.md#unregistertypelib) と [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver)によって使用されます。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="atlloadtypelib"></a><a name="atlloadtypelib"></a> AtlLoadTypeLib

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

*hInstTypeLib*<br/>
タイプライブラリに関連付けられているモジュールへのハンドル。

*lpszIndex*<br/>
"\N" という形式の文字列 \\ 。ここで、N はタイプライブラリリソースの整数インデックスです。 インデックスが不要な場合は NULL を指定できます。

*pbstrPath*<br/>
正常に返された場合は、タイプライブラリに関連付けられているモジュールの完全パスを格納します。

*ppTypeLib*<br/>
正常に返された場合は、読み込まれたタイプライブラリへのポインターへのポインターを格納します。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

このヘルパー関数は、 [AtlRegisterTypeLib](#atlregistertypelib) と [AtlUnRegisterTypeLib](#atlunregistertypelib)によって使用されます。

## <a name="atlupdateregistryfromresourced"></a><a name="atlupdateregistryfromresourced"></a> AtlUpdateRegistryFromResourceD

この関数は Visual Studio 2013 で非推奨とされ、Visual Studio 2015 で削除されます。

```
<removed>
```

## <a name="registrydataexchange"></a><a name="registrydataexchange"></a> RegistryDataExchange

システム レジストリのデータの読み取り/書き込みを行います。

### <a name="syntax"></a>構文

```
HRESULT RegistryDataExchange(
    T* pT,
    enum RDXOperations rdxOp,
    void* pItem = NULL);
```

### <a name="parameters"></a>パラメーター

*未満*<br/>
現在のオブジェクトへのポインター。

*rdxOp*<br/>
関数が実行する必要がある操作を示す列挙値。 使用できる値については、「解説」の表を参照してください。

*pItem*<br/>
レジストリから読み取られる、またはレジストリに書き込まれるデータへのポインター。 データは、レジストリから削除するキーを表すこともできます。 既定値は NULL です。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

マクロ [BEGIN_RDX_MAP](registry-data-exchange-macros.md#begin_rdx_map) および [END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map) 、を呼び出す関数に展開され `RegistryDataExchange` ます。

関数によって実行される操作を示す列挙値には、次の表を参照してください。

|列挙値|操作|
|----------------|---------------|
|eReadFromReg|レジストリからデータを読み取ります。|
|eWriteToReg|レジストリにデータを書き込みます。|
|eDeleteFromReg|レジストリからキーを削除します。|

### <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="see-also"></a>関連項目

[関数](atl-functions.md)<br/>
[レジストリデータ交換マクロ](registry-data-exchange-macros.md)
