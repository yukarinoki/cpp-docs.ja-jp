---
title: CAtlDllModuleT クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlDllModuleT class
ms.assetid: 351d5767-8257-4878-94be-45a85e31a72d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b1ea8b5922454d32961f0e7d87eda16f55fe52c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364851"
---
# <a name="catldllmodulet-class"></a>CAtlDllModuleT クラス
このクラスは、DLL のモジュールを表します。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class ATL_NO_VTABLE CAtlDllModuleT : public CAtlModuleT<T>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス`CAtlDllModuleT`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlDllModuleT::CAtlDllModuleT](#catldllmodulet)|コンストラクターです。|  
|[CAtlDllModuleT:: ~ CAtlDllModuleT](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlDllModuleT::DllCanUnloadNow](#dllcanunloadnow)|DLL をアンロードできるかどうか。|  
|[CAtlDllModuleT::DllGetClassObject](#dllgetclassobject)|クラス ファクトリを返します。|  
|[CAtlDllModuleT::DllMain](#dllmain)|ダイナミック リンク ライブラリ (DLL) への省略可能なエントリ ポイントです。|  
|[CAtlDllModuleT::DllRegisterServer](#dllregisterserver)|DLL 内のオブジェクトのシステム レジストリにエントリを追加します。|  
|[CAtlDllModuleT::DllUnregisterServer](#dllunregisterserver)|DLL 内のオブジェクトのシステム レジストリのエントリを削除します。|  
|[CAtlDllModuleT::GetClassObject](#getclassobject)|クラス ファクトリを返します。 によって呼び出された[DllGetClassObject](#dllgetclassobject)です。|  
  
## <a name="remarks"></a>コメント  
 `CAtlDllModuleT` ダイナミック リンク ライブラリ (DLL) 用のモジュールを表し、DLL のすべてのプロジェクトで使用される関数を提供します。 この特殊化[CAtlModuleT](../../atl/reference/catlmodulet-class.md)クラスには、登録のサポートが含まれています。  
  
 ATL でモジュールの詳細については、次を参照してください。 [ATL モジュール クラス](../../atl/atl-module-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlDllModuleT`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="catldllmodulet"></a>  CAtlDllModuleT::CAtlDllModuleT  
 コンストラクターです。  
  
```
CAtlDllModuleT() throw();
```  
  
##  <a name="dtor"></a>  CAtlDllModuleT:: ~ CAtlDllModuleT  
 デストラクターです。  
  
```
~CAtlDllModuleT() throw();
```  
  
##  <a name="dllcanunloadnow"></a>  CAtlDllModuleT::DllCanUnloadNow  
 DLL をアンロードできるかどうか。  
  
```
HRESULT DllCanUnloadNow() throw();
```  
  
### <a name="return-value"></a>戻り値  
 できない場合は、DLL が読み込まれた、指定できる場合は s_ok S_FALSE を返します。  
  
##  <a name="dllgetclassobject"></a>  CAtlDllModuleT::DllGetClassObject  
 クラス ファクトリを返します。  
  
```
HRESULT DllGetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `rclsid`  
 作成するオブジェクトの CLSID。  
  
 `riid`  
 要求されたインターフェイスの IID です。  
  
 `ppv`  
 によって識別されるインターフェイス ポインターへのポインター`riid`です。 オブジェクトは、このインターフェイスをサポートしていない場合`ppv`は NULL に設定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="dllmain"></a>  CAtlDllModuleT::DllMain  
 ダイナミック リンク ライブラリ (DLL) への省略可能なエントリ ポイントです。  
  
```
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dwReason`  
 DLL_PROCESS_ATTACH DLL_THREAD_ATTACH、DLL_THREAD_DETACH の通知呼び出しに設定が無効になって 場合。  
  
 *lpReserved*  
 予約済み。  
  
### <a name="return-value"></a>戻り値  
 常に TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 DLL_THREAD_ATTACH を無効にして、DLL_THREAD_DETACH 通知の呼び出しは、多くの Dll があるマルチ スレッド アプリケーションの有効な最適化をすることができますを頻繁に作成スレッド、および削除が Dll では、これらのスレッド レベル通知は必要はありません。添付ファイル/デタッチします。  
  
##  <a name="dllregisterserver"></a>  CAtlDllModuleT::DllRegisterServer  
 DLL 内のオブジェクトのシステム レジストリにエントリを追加します。  
  
```
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `bRegTypeLib`  
 タイプ ライブラリは、登録する場合は TRUE。 既定値は TRUE です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="dllunregisterserver"></a>  CAtlDllModuleT::DllUnregisterServer  
 DLL 内のオブジェクトのシステム レジストリのエントリを削除します。  
  
```
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `bUnRegTypeLib`  
 タイプ ライブラリをレジストリから削除する場合は TRUE。 既定値は TRUE です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="getclassobject"></a>  CAtlDllModuleT::GetClassObject  
 指定された CLSID のオブジェクトを作成します。  
  
```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `rclsid`  
 作成するオブジェクトの CLSID。  
  
 `riid`  
 要求されたインターフェイスの IID です。  
  
 `ppv`  
 によって識別されるインターフェイス ポインターへのポインター`riid`です。 オブジェクトは、このインターフェイスをサポートしていない場合`ppv`は NULL に設定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドによって呼び出されます[CAtlDllModuleT::DllGetClassObject](#dllgetclassobject)と下位互換性のために用意されています。  
  
## <a name="see-also"></a>関連項目  
 [CAtlModuleT クラス](../../atl/reference/catlmodulet-class.md)   
 [CAtlExeModuleT クラス](../../atl/reference/catlexemodulet-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [モジュール クラス](../../atl/atl-module-classes.md)
