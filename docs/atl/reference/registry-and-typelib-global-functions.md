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
ms.openlocfilehash: 69df927ddd04c19d10703854aa8c8948894309d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326087"
---
# <a name="registry-and-typelib-global-functions"></a>レジストリとタイプ ライブラリに関するグローバル関数

これらの関数は、タイプ ライブラリの読み込みと登録をサポートします。

> [!IMPORTANT]
> 次の表に示す関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

|||
|-|-|
|[AfxRegCreateKey](#afxregcreatekey)|指定したレジストリ キーを作成します。|
|[AfxRegDeleteKey](#afxregdeletekey)|指定したレジストリ キーを削除します。|
|[AfxRegisterPreviewHandler](#afxregisterpreviewhandler)|プレビュー ハンドラを登録するヘルパー。|
|[AfxUnレジスタプレビューハンドラ](#afxunregisterpreviewhandler)| プレビュー ハンドラの登録を解除するヘルパー。 |
|[AtlRegisterTypeLib](#atlregistertypelib)|この関数は、タイプ ライブラリを登録するために呼び出されます。|
|[AtlUnRegisterTypeLib](#atlunregistertypelib)|この関数は、タイプ ライブラリの登録を解除するために呼び出されます。|
|[AfxRegOpenKey](#afxregopenkey)|指定したレジストリ キーを開きます。|
|[AfxRegOpenKeyEx](#afxregopenkeyex)|指定したレジストリ キーを開きます。|
|[AtlLoadTypeLib](#atlloadtypelib)|この関数は、タイプ ライブラリを読み込むために呼び出されます。|
|[AtlUpdateRegistryFromResourceD](#atlupdateregistryfromresourced)|この関数は、提供されたリソースのレジストリを更新するために呼び出されます。|
|[RegistryDataExchange](#registrydataexchange)|システム レジストリのデータの読み取り/書き込みを行います。 [レジストリ データ エクスチェンジ マクロ](../../atl/reference/registry-data-exchange-macros.md)によって呼び出されます。|

これらの関数は、プログラムが情報を格納するために使用するレジストリ内のノードを制御します。

|||
|-|-|
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|アプリケーションがレジストリ へのアクセスを**HKEY_CURRENT_USER** ( **HKCU**) ノードにリダイレクトするかどうかを取得します。|
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|アプリケーションがレジストリへのアクセスを**HKEY_CURRENT_USER** ( **HKCU**) ノードにリダイレクトするかどうかを設定します。|

### <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="atlgetperuserregistration"></a><a name="atlgetperuserregistration"></a>ユーザー登録

この関数を使用して、アプリケーションがレジストリアクセスを**HKEY_CURRENT_USER** (**HKCU**) ノードにリダイレクトするかどうかを決定します。

### <a name="syntax"></a>構文

```
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);
```

### <a name="parameters"></a>パラメーター

*p 有効*<br/>
[アウト]TRUE は、レジストリ情報が**HKCU**ノードに送信されることを示します。FALSE は、アプリケーションがレジストリ情報を既定のノードに書き込むということを示します。 デフォルトのノードは**HKEY_CLASSES_ROOT** (**HKCR**) です。

### <a name="return-value"></a>戻り値

メソッドが成功した場合はS_OKし、エラーが発生した場合は HRESULT エラー コードを返します。

### <a name="remarks"></a>解説

レジストリ リダイレクトは既定では有効になっていません。 このオプションを有効にすると、レジストリへのアクセスは**HKEY_CURRENT_USER\ソフトウェア\クラス**にリダイレクトされます。

リダイレクトはグローバルではありません。 このレジストリ リダイレクトの影響を受けるのは、MFC および ATL フレームワークだけです。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="afxregcreatekey"></a><a name="afxregcreatekey"></a>キーを作成します。

指定したレジストリ キーを作成します。

### <a name="syntax"></a>構文

```
LONG AFXAPI AfxRegCreateKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>パラメーター

*Hkey*<br/>
開いているレジストリ キーへのハンドル。

*サブキー*<br/>
この関数が開くキーまたは作成するキーの名前。

*フク結果*<br/>
開かれたキーまたは作成されたキーへのハンドルを受け取る変数へのポインター。

*Ptm*<br/>
`CAtlTransactionManager`オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値はERROR_SUCCESS。 関数が失敗した場合、戻り値は Winerror.h で定義された 0 以外のエラー コードです。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxpriv.h

## <a name="afxregdeletekey"></a><a name="afxregdeletekey"></a>アックスレグレガネキー

指定したレジストリ キーを削除します。

### <a name="syntax"></a>構文

```
LONG AFXAPI AfxRegDeleteKey(HKEY hKey, LPCTSTR lpSubKey, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>パラメーター

*Hkey*<br/>
開いているレジストリ キーへのハンドル。

*サブキー*<br/>
削除するキーの名前。

*Ptm*<br/>
`CAtlTransactionManager`オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値はERROR_SUCCESS。 関数が失敗した場合、戻り値は Winerror.h で定義された 0 以外のエラー コードです。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxpriv.h

## <a name="afxregisterpreviewhandler"></a>

プレビュー ハンドラを登録するヘルパー。

### <a name="syntax"></a>構文

```
BOOL AFXAPI AfxRegisterPreviewHandler(LPCTSTR lpszCLSID, LPCTSTR lpszShortTypeName, LPCTSTR lpszFilterExt);
```

### <a name="parameters"></a>パラメーター

*を行う*<br/>
ハンドラーの CLSID を指定します。

*名前を指定します。*<br/>
ハンドラーの ProgID を指定します。

*を使用します。*<br/>
このハンドラーに登録されているファイル拡張子を指定します。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="atlregistertypelib"></a><a name="atlregistertypelib"></a>を使用します。

この関数は、タイプ ライブラリを登録するために呼び出されます。

```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
モジュール インスタンスへのハンドル。

*インデックスを使用します。*<br/>
"\N"\\形式の文字列は、N はタイプ ライブラリ リソースの整数インデックスです。 インデックスが不要な場合は NULL を指定できます。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

このヘルパー関数は、[アトルコムモジュールアンレジスタサーバー](server-registration-global-functions.md#atlcommoduleunregisterserver)と[CAtlComModule::レジスタタイプライブラリ](../../atl/reference/catlcommodule-class.md#registertypelib)によって利用されます。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="afxregopenkey"></a><a name="afxregopenkey"></a>キーを開く

指定したレジストリ キーを開きます。

### <a name="syntax"></a>構文

```
LONG AFXAPI AfxRegOpenKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>パラメーター

*Hkey*<br/>
開いているレジストリ キーへのハンドル。

*サブキー*<br/>
この関数が開くキーまたは作成するキーの名前。

*フク結果*<br/>
作成されたキーへのハンドルを受け取る変数へのポインター。

*Ptm*<br/>
`CAtlTransactionManager`オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値はERROR_SUCCESS。 関数が失敗した場合、戻り値は Winerror.h で定義された 0 以外のエラー コードです。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxpriv.h

## <a name="afxregopenkeyex"></a><a name="afxregopenkeyex"></a>キーエックス

指定したレジストリ キーを開きます。

### <a name="syntax"></a>構文

```
LONG AFXAPI AfxRegOpenKeyEx(HKEY hKey, LPCTSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>パラメーター

*Hkey*<br/>
開いているレジストリ キーへのハンドル。

*サブキー*<br/>
この関数が開くキーまたは作成するキーの名前。

*ウルオプション*<br/>
このパラメーターは予約済みで、0 である必要があります。

*サム必要に応じて*<br/>
キーに対する必要なアクセス権を指定するマスク。

*フク結果*<br/>
開いているキーへのハンドルを受け取る変数へのポインター。

*Ptm*<br/>
`CAtlTransactionManager`オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値はERROR_SUCCESS。 関数が失敗した場合、戻り値は Winerror.h で定義された 0 以外のエラー コードです。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxpriv.h

## <a name="afxunregisterpreviewhandler"></a><a name="afxunregisterpreviewhandler"></a>AfxUnレジスタプレビューハンドラ

プレビュー ハンドラの登録を解除するヘルパー。

### <a name="syntax"></a>構文

```
BOOL AFXAPI AfxUnRegisterPreviewHandler(LPCTSTR lpszCLSID);
```

### <a name="parameters"></a>パラメーター

*を行う*<br/>
登録解除するハンドラの CLSID を指定します。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="atlsetperuserregistration"></a><a name="atlsetperuserregistration"></a>ユーザー登録

アプリケーションがレジストリへのアクセスを**HKEY_CURRENT_USER** (**HKCU**) ノードにリダイレクトするかどうかを設定します。

### <a name="syntax"></a>構文

```
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]TRUE は、レジストリ情報が**HKCU**ノードに送信されることを示します。FALSE は、アプリケーションがレジストリ情報を既定のノードに書き込むということを示します。 デフォルトのノードは**HKEY_CLASSES_ROOT** (**HKCR**) です。

### <a name="return-value"></a>戻り値

メソッドが成功した場合はS_OKし、エラーが発生した場合は HRESULT エラー コードを返します。

### <a name="remarks"></a>解説

レジストリ リダイレクトは既定では有効になっていません。 このオプションを有効にすると、レジストリへのアクセスは**HKEY_CURRENT_USER\ソフトウェア\クラス**にリダイレクトされます。

リダイレクトはグローバルではありません。 このレジストリ リダイレクトの影響を受けるのは、MFC および ATL フレームワークだけです。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="atlunregistertypelib"></a><a name="atlunregistertypelib"></a>アトルンレジスタタイプリブ

この関数は、タイプ ライブラリの登録を解除するために呼び出されます。

### <a name="syntax"></a>構文

```
ATLAPI AtlUnRegisterTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
モジュール インスタンスへのハンドル。

*インデックスを使用します。*<br/>
"\N"\\形式の文字列は、N はタイプ ライブラリ リソースの整数インデックスです。 インデックスが不要な場合は NULL を指定できます。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

このヘルパー関数は[、CAtlCom モジュールによって利用されます::アンレジスタタイプリブ](../../atl/reference/catlcommodule-class.md#unregistertypelib)と[アトルコムモジュールアンレジスタサーバー](server-registration-global-functions.md#atlcommoduleunregisterserver).

### <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="atlloadtypelib"></a><a name="atlloadtypelib"></a>を使用します。

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

*を使用します。*<br/>
タイプ ライブラリに関連付けられているモジュールへのハンドル。

*インデックスを使用します。*<br/>
"\N"\\形式の文字列は、N はタイプ ライブラリ リソースの整数インデックスです。 インデックスが不要な場合は NULL を指定できます。

*パス*<br/>
正常に戻った場合は、タイプ ライブラリに関連付けられたモジュールの完全パスを格納します。

*をクリックします。*<br/>
正常に戻った場合は、読み込まれたタイプ ライブラリへのポインターへのポインターを格納します。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

このヘルパー関数は、[アトルレジスタタイプリブ](#atlregistertypelib)と[アトルウンレジスタタイプリブ](#atlunregistertypelib)によって使用されます。

## <a name="atlupdateregistryfromresourced"></a><a name="atlupdateregistryfromresourced"></a>リソースから更新プログラムを作成します。

この関数は Visual Studio 2013 で非推奨とされ、Visual Studio 2015 で削除されます。

```
<removed>
```

## <a name="registrydataexchange"></a><a name="registrydataexchange"></a>レジストリデータエクスチェンジ

システム レジストリのデータの読み取り/書き込みを行います。

### <a name="syntax"></a>構文

```
HRESULT RegistryDataExchange(
    T* pT,
    enum RDXOperations rdxOp,
    void* pItem = NULL);
```

### <a name="parameters"></a>パラメーター

*Pt*<br/>
現在のオブジェクトへのポインター。

*をクリックします。*<br/>
関数が実行する操作を示す列挙値。 許可される値については、「解説」の表を参照してください。

*Pitem*<br/>
レジストリから読み取る、またはレジストリに書き込むデータへのポインター。 データは、レジストリから削除するキーを表すこともできます。 既定値は NULL です。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

マクロ[はBEGIN_RDX_MAP](registry-data-exchange-macros.md#begin_rdx_map)され[、END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map)を呼び出`RegistryDataExchange`す関数に展開されます。

関数が実行する操作を示す列挙値を次の表に示します。

|列挙値|Operation|
|----------------|---------------|
|を読み取る|レジストリからデータを読み取ります。|
|を書き込む|レジストリにデータを書き込みます。|
|を使用します。|レジストリからキーを削除します。|

### <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="see-also"></a>関連項目

[関数](atl-functions.md)<br/>
[レジストリ データエクスチェンジ マクロ](registry-data-exchange-macros.md)
