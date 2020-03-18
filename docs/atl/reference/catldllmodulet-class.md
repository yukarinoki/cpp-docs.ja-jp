---
title: CAtlDllModuleT クラス
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
ms.openlocfilehash: be42915c6c2e941bc5fc1de78c5c7ac26ccca6e2
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423442"
---
# <a name="catldllmodulet-class"></a>CAtlDllModuleT クラス

このクラスは、DLL のモジュールを表します。

## <a name="syntax"></a>構文

```
template <class T>
class ATL_NO_VTABLE CAtlDllModuleT : public CAtlModuleT<T>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
`CAtlDllModuleT`から派生したクラス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|Description|
|----------|-----------------|
|[CAtlDllModuleT:: CAtlDllModuleT](#catldllmodulet)|コンストラクターです。|
|[CAtlDllModuleT:: ~ CAtlDllModuleT](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[CAtlDllModuleT::D llCanUnloadNow](#dllcanunloadnow)|DLL をアンロードできるかどうかをテストします。|
|[CAtlDllModuleT::D llGetClassObject](#dllgetclassobject)|クラスファクトリを返します。|
|[CAtlDllModuleT::D llMain](#dllmain)|ダイナミックリンクライブラリ (DLL) への省略可能なエントリポイント。|
|[CAtlDllModuleT::D llRegisterServer](#dllregisterserver)|DLL 内のオブジェクトのエントリをシステムレジストリに追加します。|
|[CAtlDllModuleT::D llUnregisterServer](#dllunregisterserver)|DLL 内のオブジェクトのシステムレジストリのエントリを削除します。|
|[CAtlDllModuleT:: GetClassObject](#getclassobject)|クラスファクトリを返します。 [DllGetClassObject](#dllgetclassobject)によって呼び出されます。|

## <a name="remarks"></a>解説

`CAtlDllModuleT` は、ダイナミックリンクライブラリ (DLL) 用のモジュールを表し、すべての DLL プロジェクトで使用される関数を提供します。 この[CAtlModuleT](../../atl/reference/catlmodulet-class.md)クラスの特殊化には、登録のサポートが含まれています。

ATL のモジュールの詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CAtlDllModuleT`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

##  <a name="catldllmodulet"></a>CAtlDllModuleT:: CAtlDllModuleT

コンストラクターです。

```
CAtlDllModuleT() throw();
```

##  <a name="dtor"></a>CAtlDllModuleT:: ~ CAtlDllModuleT

デストラクターです。

```
~CAtlDllModuleT() throw();
```

##  <a name="dllcanunloadnow"></a>CAtlDllModuleT::D llCanUnloadNow

DLL をアンロードできるかどうかをテストします。

```
HRESULT DllCanUnloadNow() throw();
```

### <a name="return-value"></a>戻り値

DLL をアンロードできる場合は S_OK を返し、できない場合は S_FALSE を返します。

##  <a name="dllgetclassobject"></a>CAtlDllModuleT::D llGetClassObject

クラスファクトリを返します。

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

*ppv*<br/>
*Riid*によって識別されるインターフェイスポインターへのポインター。 オブジェクトがこのインターフェイスをサポートしていない場合、 *ppv*は NULL に設定されます。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

##  <a name="dllmain"></a>CAtlDllModuleT::D llMain

ダイナミックリンクライブラリ (DLL) への省略可能なエントリポイント。

```
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```

### <a name="parameters"></a>パラメーター

*dwReason*<br/>
DLL_PROCESS_ATTACH に設定すると、DLL_THREAD_ATTACH と DLL_THREAD_DETACH 通知の呼び出しが無効になります。

*Lpreserved 使う*<br/>
予約済み。

### <a name="return-value"></a>戻り値

常に TRUE を返します。

### <a name="remarks"></a>解説

DLL_THREAD_ATTACH と DLL_THREAD_DETACH の通知呼び出しを無効にすると、多数の Dll を持つマルチスレッドアプリケーションで、スレッドを頻繁に作成して削除する可能性があり、その Dll が attachment/デタッチのスレッドレベルの通知を必要としない場合に便利です。

##  <a name="dllregisterserver"></a>CAtlDllModuleT::D llRegisterServer

DLL 内のオブジェクトのエントリをシステムレジストリに追加します。

```
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>パラメーター

*bRegTypeLib*<br/>
タイプライブラリを登録する場合は TRUE。 既定値は TRUE です。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

##  <a name="dllunregisterserver"></a>CAtlDllModuleT::D llUnregisterServer

DLL 内のオブジェクトのシステムレジストリのエントリを削除します。

```
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>パラメーター

*bUnRegTypeLib*<br/>
タイプライブラリをレジストリから削除する場合は TRUE。 既定値は TRUE です。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

##  <a name="getclassobject"></a>CAtlDllModuleT:: GetClassObject

指定された CLSID のオブジェクトを作成します。

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

*ppv*<br/>
*Riid*によって識別されるインターフェイスポインターへのポインター。 オブジェクトがこのインターフェイスをサポートしていない場合、 *ppv*は NULL に設定されます。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

このメソッドは、 [Catldllmodulet::D llgetclassobject](#dllgetclassobject)によって呼び出され、旧バージョンとの互換性のために用意されています。

## <a name="see-also"></a>参照

[CAtlModuleT クラス](../../atl/reference/catlmodulet-class.md)<br/>
[CAtlExeModuleT クラス](../../atl/reference/catlexemodulet-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[モジュールクラス](../../atl/atl-module-classes.md)
