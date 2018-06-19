---
title: サーバー登録のグローバル関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlComModuleRegisterServer
- atlbase/ATL::AtlComModuleUnregisterServer
- atlbase/ATL::AtlComModuleRegisterClassObjects
- atlbase/ATL::AtlComModuleRevokeClassObjects
- atlbase/ATL::AtlComModuleGetClassObject
dev_langs:
- C++
ms.assetid: c2f0a35d-857c-4538-a44d-c4ea0db63b06
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08a4141ab5ff27e44f663a4d5f267c2b7d754283
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364706"
---
# <a name="server-registration-global-functions"></a>サーバー登録のグローバル関数
これらの関数は、登録およびオブジェクト マップ内のサーバー オブジェクトの登録を解除するためのサポートを提供します。  
  
> [!IMPORTANT]
>  次の表に示す関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
|||  
|-|-|  
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|オブジェクト マップのオブジェクトをすべて登録します。|  
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|オブジェクト マップのオブジェクトの登録をすべて解除します。|  
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|この関数は、クラス オブジェクトを登録するために呼び出されます。|  
|[AtlComModuleRevokeClassObjects](#atlcommodulerevokeclassobjects)|この関数は COM モジュールからクラス オブジェクトを無効にします。|  
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|この関数は、クラス オブジェクトを取得します。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
   
##  <a name="atlcommoduleregisterserver"></a>  AtlComModuleRegisterServer  
 オブジェクト マップのオブジェクトをすべて登録します。  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>パラメーター  
 `pComModule`  
 COM モジュールへのポインター。  
  
 `bRegTypeLib`  
 タイプ ライブラリは、登録する場合は TRUE。  
  
 `pCLSID`  
 登録するオブジェクトの CLSID を指します。 NULL の場合、オブジェクト マップ内のすべてのオブジェクトが登録されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 `AtlComModuleRegisterServer` ATL の自動生成されたオブジェクトのマップおよびマップ内の各オブジェクトを登録します。 場合`pCLSID`が NULL の場合、によって参照されるオブジェクトのみ`pCLSID`が登録されているすべてのオブジェクトが登録されてそれ以外の場合。  
  
 この関数は[CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver)です。  
  
##  <a name="atlcommoduleunregisterserver"></a>  AtlComModuleUnregisterServer  
 オブジェクト マップのオブジェクトの登録をすべて解除します。  
  
```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>パラメーター  
 `pComModule`  
 COM モジュールへのポインター。  
  
 `bUnRegTypeLib`  
 タイプ ライブラリは、登録する場合は TRUE。  
  
 `pCLSID`  
 登録解除するオブジェクトの CLSID を指します。 NULL の場合は、オブジェクト マップ内のすべてのオブジェクトは登録できません。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 `AtlComModuleUnregisterServer` ATL オブジェクト マップし、マップ内の各オブジェクトの登録を解除します。 場合`pCLSID`が NULL の場合、によって参照されるオブジェクトのみ`pCLSID`未登録です。 それ以外の場合は、すべてのオブジェクトは登録を解除します。  
  
 この関数は[CAtlComModule::UnregisterServer](catlcommodule-class.md#unregisterserver)です。  
  
##  <a name="atlcommoduleregisterclassobjects"></a>  AtlComModuleRegisterClassObjects  
 この関数は、クラス オブジェクトを登録するために呼び出されます。  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `pComModule`  
 COM モジュールへのポインター。  
  
 `dwClsContext`  
 クラスのオブジェクトが実行されるコンテキストを指定します。 使用可能な値は CLSCTX_INPROC_SERVER、CLSCTX_INPROC_HANDLER、または CLSCTX_LOCAL_SERVER です。 参照してください[CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716)詳細についてはします。  
  
 `dwFlags`  
 クラスのオブジェクトへの接続の種類を決定します。 使用可能な値は REGCLS_SINGLEUSE、REGCLS_MULTIPLEUSE、または REGCLS_MULTI_SEPARATE です。 参照してください[REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697)詳細についてはします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このヘルパー関数がによって使用されて[CComModule::RegisterClassObjects](ccommodule-class.md#registerclassobjects) (ATL 7.0 で古い形式) および[CAtlExeModuleT::RegisterClassObjects](catlexemodulet-class.md#registerclassobjects)です。  
  
##  <a name="atlcommodulerevokeclassobjects"></a>  AtlComModuleRevokeClassObjects  
 クラス ファクトリをランニング オブジェクト テーブルから削除します。  
  
```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```  
  
### <a name="parameters"></a>パラメーター  
 `pComModule`  
 COM モジュールへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このヘルパー関数がによって使用されて[CComModule::RevokeClassObjects](ccommodule-class.md#revokeclassobjects) (ATL 7.0 で古い形式) および[で](catlexemodulet-class.md#revokeclassobjects)です。  
  
##  <a name="atlcommodulegetclassobject"></a>  AtlComModuleGetClassObject  
 この関数は、クラス ファクトリを返すために呼び出されます。  
  
```
ATLINLINE ATLAPI AtlComModuleGetClassObject(
    _ATL_COM_MODULE* pComModule,
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv);
```  
  
### <a name="parameters"></a>パラメーター  
 `pComModule`  
 COM モジュールへのポインター。  
  
 `rclsid`  
 作成するオブジェクトの CLSID。  
  
 `riid`  
 要求されたインターフェイスの IID です。  
  
 `ppv`  
 によって識別されるインターフェイス ポインターへのポインター`riid`です。 オブジェクトは、このインターフェイスをサポートしていない場合`ppv`は NULL に設定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このヘルパー関数がによって使用されて[CComModule::GetClassObject](ccommodule-class.md#getclassobject) (ATL 7.0 で古い形式) および[CAtlDllModuleT::GetClassObject](catldllmodulet-class.md#getclassobject)です。  
  
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)
