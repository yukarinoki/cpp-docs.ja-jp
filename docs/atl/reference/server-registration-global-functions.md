---
title: サーバー登録に関するグローバル関数 |Microsoft Docs
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
ms.openlocfilehash: a2cc139fa0aa933131e4e19b8efa397e4bddee50
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209229"
---
# <a name="server-registration-global-functions"></a>サーバー登録に関するグローバル関数
これらの関数は、登録とオブジェクト マップ内のサーバー オブジェクトを登録解除のサポートを提供します。  
  
> [!IMPORTANT]
>  Windows ランタイムで実行するアプリケーションでは、次の表に示す関数を使用できません。  
  
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
 *pComModule*  
 COM モジュールへのポインター。  
  
 *bRegTypeLib*  
 TRUE の場合、タイプ ライブラリを登録します。  
  
 *pclsid の値*  
 登録するオブジェクトの CLSID を指します。 NULL の場合、オブジェクトのマップ内のすべてのオブジェクトが登録されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 `AtlComModuleRegisterServer` ATL の自動生成されたオブジェクトのマップおよびマップ内の各オブジェクトを登録します。 場合*と*が null の場合、その後で参照されるオブジェクトのみ*と*が登録されているすべてのオブジェクトが登録されてそれ以外の場合。  
  
 この関数を呼び出して[CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver)します。  
  
##  <a name="atlcommoduleunregisterserver"></a>  AtlComModuleUnregisterServer  
 オブジェクト マップのオブジェクトの登録をすべて解除します。  
  
```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>パラメーター  
 *pComModule*  
 COM モジュールへのポインター。  
  
 *bUnRegTypeLib*  
 TRUE の場合、タイプ ライブラリを登録します。  
  
 *pclsid の値*  
 登録解除するオブジェクトの CLSID を指します。 NULL の場合は、オブジェクト マップ内のすべてのオブジェクトは登録できません。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 `AtlComModuleUnregisterServer` ATL オブジェクト マップおよびマップ内の各オブジェクトの登録を解除します。 場合*と*が null の場合、その後で参照されるオブジェクトのみ*と*登録を解除しました。 それ以外の場合は、登録されているすべてのオブジェクトはありません。  
  
 この関数を呼び出して[CAtlComModule::UnregisterServer](catlcommodule-class.md#unregisterserver)します。  
  
##  <a name="atlcommoduleregisterclassobjects"></a>  AtlComModuleRegisterClassObjects  
 この関数は、クラス オブジェクトを登録するために呼び出されます。  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 *pComModule*  
 COM モジュールへのポインター。  
  
 *dwClsContext*  
 クラスのオブジェクトが実行コンテキストを指定します。 指定できる値は、CLSCTX_INPROC_SERVER や CLSCTX_INPROC_HANDLER、CLSCTX_LOCAL_SERVER は。 参照してください[CLSCTX](https://msdn.microsoft.com/library/windows/desktop/ms693716)の詳細。  
  
 *dwFlags*  
 クラス オブジェクトへの接続の種類を決定します。 指定できる値は、REGCLS_SINGLEUSE、REGCLS_MULTIPLEUSE、または REGCLS_MULTI_SEPARATE は。 参照してください[REGCLS](/windows/desktop/api/combaseapi/ne-combaseapi-tagregcls)の詳細。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 このヘルパー関数が利用[CComModule::RegisterClassObjects](ccommodule-class.md#registerclassobjects) (ATL 7.0 で廃止) と[CAtlExeModuleT::RegisterClassObjects](catlexemodulet-class.md#registerclassobjects)します。  
  
##  <a name="atlcommodulerevokeclassobjects"></a>  AtlComModuleRevokeClassObjects  
 クラス ファクトリをランニング オブジェクト テーブルから削除します。  
  
```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```  
  
### <a name="parameters"></a>パラメーター  
 *pComModule*  
 COM モジュールへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 このヘルパー関数が利用[CComModule::RevokeClassObjects](ccommodule-class.md#revokeclassobjects) (ATL 7.0 で廃止) と[で](catlexemodulet-class.md#revokeclassobjects)します。  
  
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
 *pComModule*  
 COM モジュールへのポインター。  
  
 *rclsid*  
 作成するオブジェクトの CLSID。  
  
 *riid*  
 要求されたインターフェイスの IID。  
  
 *ppv*  
 によって識別されるインターフェイス ポインターへのポインター *riid*します。 オブジェクトは、このインターフェイスをサポートしていない場合*ppv* NULL に設定されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 このヘルパー関数が利用[CComModule::GetClassObject](ccommodule-class.md#getclassobject) (ATL 7.0 で廃止) と[CAtlDllModuleT::GetClassObject](catldllmodulet-class.md#getclassobject)します。  
  
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)
