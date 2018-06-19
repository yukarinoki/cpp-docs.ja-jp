---
title: CAtlComModule クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlComModule
- ATLBASE/ATL::CAtlComModule
- ATLBASE/ATL::CAtlComModule::CAtlComModule
- ATLBASE/ATL::CAtlComModule::RegisterServer
- ATLBASE/ATL::CAtlComModule::RegisterTypeLib
- ATLBASE/ATL::CAtlComModule::UnregisterServer
- ATLBASE/ATL::CAtlComModule::UnRegisterTypeLib
dev_langs:
- C++
helpviewer_keywords:
- CAtlComModule class
ms.assetid: af5dd71a-a0d1-4a2e-9a24-154a03381c75
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 47e85f3aab75f8fafb76977847ce36d37808af60
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364793"
---
# <a name="catlcommodule-class"></a>CAtlComModule クラス
このクラスは、COM サーバー モジュールを実装します。  
  
## <a name="syntax"></a>構文  
  
```
class CAtlComModule : public _ATL_COM_MODULE
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlComModule::CAtlComModule](#catlcommodule)|コンストラクターです。|  
|[CAtlComModule:: ~ CAtlComModule](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlComModule::RegisterServer](#registerserver)|オブジェクト マップ内の各オブジェクトのシステム レジストリを更新するには、このメソッドを呼び出します。|  
|[CAtlComModule::RegisterTypeLib](#registertypelib)|タイプ ライブラリを登録するには、このメソッドを呼び出します。|  
|[CAtlComModule::UnregisterServer](#unregisterserver)|オブジェクト マップ内の各オブジェクトの登録を解除するには、このメソッドを呼び出します。|  
|[CAtlComModule::UnRegisterTypeLib](#unregistertypelib)|タイプ ライブラリの登録を解除するには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
 `CAtlComModule` クライアントが、モジュールのコンポーネントにアクセスできるよう、COM サーバー モジュールを実装します。  
  
 このクラスは廃止された置換[CComModule](../../atl/reference/ccommodule-class.md) ATL の以前のバージョンで使用されるクラス 参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)  
  
 `CAtlComModule`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="catlcommodule"></a>  CAtlComModule::CAtlComModule  
 コンストラクターです。  
  
```
CAtlComModule() throw();
```  
  
### <a name="remarks"></a>コメント  
 モジュールを初期化します。  
  
##  <a name="dtor"></a>  CAtlComModule:: ~ CAtlComModule  
 デストラクターです。  
  
```
~CAtlComModule();
```  
  
### <a name="remarks"></a>コメント  
 すべてのクラス ファクトリを解放します。  
  
##  <a name="registerserver"></a>  CAtlComModule::RegisterServer  
 オブジェクト マップ内の各オブジェクトのシステム レジストリを更新するには、このメソッドを呼び出します。  
  
```
HRESULT RegisterServer(BOOL bRegTypeLib = FALSE, const CLSID* pCLSID = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `bRegTypeLib`  
 タイプ ライブラリは、登録する場合は TRUE。 既定値は FALSE です。  
  
 `pCLSID`  
 登録するオブジェクトの CLSID を指します。 NULL (既定値) の場合は、オブジェクト マップ内のすべてのオブジェクトを登録するかどうか。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 グローバル関数を呼び出す[AtlComModuleRegisterServer](server-registration-global-functions.md#atlcommoduleregisterserver)です。  
  
##  <a name="registertypelib"></a>  CAtlComModule::RegisterTypeLib  
 タイプ ライブラリを登録するには、このメソッドを呼び出します。  
  
```
HRESULT RegisterTypeLib(LPCTSTR lpszIndex);
HRESULT RegisterTypeLib();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszIndex`  
 形式で文字列"\\\N"、N はタイプ ライブラリのリソースの整数のインデックス。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 タイプ ライブラリに関する情報をシステム レジストリに追加します。 モジュールのインスタンスに複数のタイプ ライブラリが含まれている場合は、このメソッドの最初のバージョンを使用して、どのタイプ ライブラリを使用する必要がありますを指定します。  
  
##  <a name="unregisterserver"></a>  CAtlComModule::UnregisterServer  
 オブジェクト マップ内の各オブジェクトの登録を解除するには、このメソッドを呼び出します。  
  
```
HRESULT UnregisterServer(
  BOOL bRegTypeLib = FALSE,  
  const CLSID* pCLSID = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `bRegTypeLib`  
 タイプ ライブラリの登録解除する場合は TRUE。 既定値は FALSE です。  
  
 `pCLSID`  
 登録解除するオブジェクトの CLSID を指します。 場合は NULL (既定値) の場合は、オブジェクト マップ内のすべてのオブジェクトの登録が解除されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 グローバル関数を呼び出す[AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver)です。  
  
##  <a name="unregistertypelib"></a>  CAtlComModule::UnRegisterTypeLib  
 タイプ ライブラリの登録を解除するには、このメソッドを呼び出します。  
  
```
HRESULT UnRegisterTypeLib(LPCTSTR lpszIndex);
HRESULT UnRegisterTypeLib();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszIndex`  
 形式で文字列"\\\N"、N はタイプ ライブラリのリソースの整数のインデックス。  
  
### <a name="remarks"></a>コメント  
 システム レジストリからタイプ ライブラリに関する情報を削除します。 モジュールのインスタンスに複数のタイプ ライブラリが含まれている場合は、このメソッドの最初のバージョンを使用して、どのタイプ ライブラリを使用する必要がありますを指定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
## <a name="see-also"></a>関連項目  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)   
 [クラスの概要](../../atl/atl-class-overview.md)
