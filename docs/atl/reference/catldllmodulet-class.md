---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::DllCanUnloadNow
- ATLBASE/ATL::CAtlDllModuleT::DllGetClassObject
- ATLBASE/ATL::CAtlDllModuleT::DllMain
- ATLBASE/ATL::CAtlDllModuleT::DllRegisterServer
- ATLBASE/ATL::CAtlDllModuleT::DllUnregisterServer
- ATLBASE/ATL::CAtlDllModuleT::GetClassObject
helpviewer_keywords:
- CAtlDllModuleT class
ms.assetid: 351d5767-8257-4878-94be-45a85e31a72d
ms.openlocfilehash: 7a5f8e7e489c8e0d573569ac7c4a8fb63f652732
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319015"
---
# <a name="catldllmodulet-class"></a>クラス

このクラスは、DLL のモジュールを表します。

## <a name="syntax"></a>構文

```
template <class T>
class ATL_NO_VTABLE CAtlDllModuleT : public CAtlModuleT<T>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
クラスから派生`CAtlDllModuleT`したクラス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[をクリックします。](#catldllmodulet)|コンストラクターです。|
|[をクリックします。](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をクリック :Dします。](#dllcanunloadnow)|DLL をアンロードできるかどうかをテストします。|
|[クラスオブジェクトを:D](#dllgetclassobject)|クラス ファクトリを返します。|
|[:Dル・メイン](#dllmain)|ダイナミック リンク ライブラリ (DLL) へのエントリ ポイント (省略可能)。|
|[を:D](#dllregisterserver)|DLL 内のオブジェクトのエントリをシステム レジストリに追加します。|
|[を:Dします。](#dllunregisterserver)|DLL 内のオブジェクトのシステム レジストリのエントリを削除します。|
|[クラスオブジェクト](#getclassobject)|クラス ファクトリを返します。 [によって呼](#dllgetclassobject)び出されます。|

## <a name="remarks"></a>解説

`CAtlDllModuleT`はダイナミック リンク ライブラリ (DLL) のモジュールを表し、すべての DLL プロジェクトで使用される関数を提供します。 この[CAtlModuleT](../../atl/reference/catlmodulet-class.md)クラスの特殊化には、登録のサポートが含まれています。

ATL のモジュールの詳細については[、「ATL モジュール クラス](../../atl/atl-module-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[カトルモジュール](../../atl/reference/catlmodule-class.md)

[カトルモジュール](../../atl/reference/catlmodulet-class.md)

`CAtlDllModuleT`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="catldllmoduletcatldllmodulet"></a><a name="catldllmodulet"></a>をクリックします。

コンストラクターです。

```
CAtlDllModuleT() throw();
```

## <a name="catldllmoduletcatldllmodulet"></a><a name="dtor"></a>をクリックします。

デストラクターです。

```
~CAtlDllModuleT() throw();
```

## <a name="catldllmoduletdllcanunloadnow"></a><a name="dllcanunloadnow"></a>をクリック :Dします。

DLL をアンロードできるかどうかをテストします。

```
HRESULT DllCanUnloadNow() throw();
```

### <a name="return-value"></a>戻り値

DLL をアンロードできる場合はS_OKを返し、アンロードできない場合はS_FALSEを返します。

## <a name="catldllmoduletdllgetclassobject"></a><a name="dllgetclassobject"></a>クラスオブジェクトを:D

クラス ファクトリを返します。

```
HRESULT DllGetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>パラメーター

*rclsid*<br/>
作成するオブジェクトの CLSID。

*riid*<br/>
要求されたインターフェイスの IID。

*Ppv*<br/>
*riid*によって識別されるインターフェイス ポインターへのポインター。 オブジェクトがこのインターフェイスをサポートしていない場合 *、ppv*は NULL に設定されます。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="catldllmoduletdllmain"></a><a name="dllmain"></a>:Dル・メイン

ダイナミック リンク ライブラリ (DLL) へのエントリ ポイント (省略可能)。

```
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```

### <a name="parameters"></a>パラメーター

*dw理由*<br/>
DLL_PROCESS_ATTACHに設定すると、DLL_THREAD_ATTACHとDLL_THREAD_DETACH通知呼び出しは無効になります。

*lp 予約済み*<br/>
予約済み。

### <a name="return-value"></a>戻り値

常に TRUE を返します。

### <a name="remarks"></a>解説

DLL_THREAD_ATTACHとDLL_THREAD_DETACH通知呼び出しを無効にすることは、多くの DLL を持ち、頻繁にスレッドを作成および削除するマルチスレッド アプリケーションで、DLL が添付ファイル/デタッチのスレッド レベルの通知を必要としない場合に役立つ最適化になります。

## <a name="catldllmoduletdllregisterserver"></a><a name="dllregisterserver"></a>を:D

DLL 内のオブジェクトのエントリをシステム レジストリに追加します。

```
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>パラメーター

*を行う*<br/>
タイプ ライブラリを登録する場合は TRUE。 既定値は TRUE です。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="catldllmoduletdllunregisterserver"></a><a name="dllunregisterserver"></a>を:Dします。

DLL 内のオブジェクトのシステム レジストリのエントリを削除します。

```
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
タイプ ライブラリをレジストリから削除する場合は TRUE。 既定値は TRUE です。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="catldllmoduletgetclassobject"></a><a name="getclassobject"></a>クラスオブジェクト

指定した CLSID のオブジェクトを作成します。

```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>パラメーター

*rclsid*<br/>
作成するオブジェクトの CLSID。

*riid*<br/>
要求されたインターフェイスの IID。

*Ppv*<br/>
*riid*によって識別されるインターフェイス ポインターへのポインター。 オブジェクトがこのインターフェイスをサポートしていない場合 *、ppv*は NULL に設定されます。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

このメソッドは[、CAtlDllModuleT によって呼び出されます::DllGetClassObject](#dllgetclassobject)は、下位互換性のために含まれています。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/catlmodulet-class.md)<br/>
[クラス](../../atl/reference/catlexemodulet-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[モジュール クラス](../../atl/atl-module-classes.md)
