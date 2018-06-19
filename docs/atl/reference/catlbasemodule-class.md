---
title: CAtlBaseModule クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::AddResourceInstance
- ATLCORE/ATL::CAtlBaseModule::GetHInstanceAt
- ATLCORE/ATL::CAtlBaseModule::GetModuleInstance
- ATLCORE/ATL::CAtlBaseModule::GetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::RemoveResourceInstance
- ATLCORE/ATL::CAtlBaseModule::SetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::m_bInitFailed
dev_langs:
- C++
helpviewer_keywords:
- CAtlBaseModule class
ms.assetid: 55ade80c-9b0c-4c51-933e-2158436c1096
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 07f1252fe993ff2f2e646528996c1a53d25c5a63
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360320"
---
# <a name="catlbasemodule-class"></a>CAtlBaseModule クラス
このクラスは、すべての ATL プロジェクトでインスタンス化します。  
  
## <a name="syntax"></a>構文  
  
```
class CAtlBaseModule : public _ATL_BASE_MODULE
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlBaseModule::CAtlBaseModule](#catlbasemodule)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlBaseModule::AddResourceInstance](#addresourceinstance)|格納されているハンドルの一覧に、リソースのインスタンスを追加します。|  
|[CAtlBaseModule::GetHInstanceAt](#gethinstanceat)|指定されたリソース インスタンスへのハンドルを返します。|  
|[CAtlBaseModule::GetModuleInstance](#getmoduleinstance)|モジュールのインスタンスを返します、`CAtlBaseModule`オブジェクト。|  
|[CAtlBaseModule::GetResourceInstance](#getresourceinstance)|リソース インスタンスを返します、`CAtlBaseModule`オブジェクト。|  
|[CAtlBaseModule::RemoveResourceInstance](#removeresourceinstance)|格納されているハンドルの一覧から、リソースのインスタンスを削除します。|  
|[CAtlBaseModule::SetResourceInstance](#setresourceinstance)|リソース インスタンスを設定、`CAtlBaseModule`オブジェクト。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlBaseModule::m_bInitFailed](#m_binitfailed)|モジュールの初期化が失敗したかどうかを示す変数です。|  
  
## <a name="remarks"></a>コメント  
 インスタンス`CAtlBaseModule`名前付き _AtlBaseModule がモジュールのインスタンスへのハンドルを含むリソース (既定では、1 つ)、モジュールとプライマリを提供するモジュールへのハンドルの配列へのハンドルを含む、すべての ATL プロジェクト内に存在リソース。 `CAtlBaseModule` 複数のスレッドから安全にアクセスします。  
  
 このクラスは廃止された置換[CComModule](../../atl/reference/ccommodule-class.md) ATL の以前のバージョンで使用されるクラス  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)  
  
 `CAtlBaseModule`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcore.h  
  
##  <a name="addresourceinstance"></a>  CAtlBaseModule::AddResourceInstance  
 格納されているハンドルの一覧に、リソースのインスタンスを追加します。  
  
```
bool AddResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hInst`  
 追加するリソースのインスタンス。  
  
### <a name="return-value"></a>戻り値  
 リソースが正常にした場合は true、追加 false それ以外の場合。  
  
##  <a name="catlbasemodule"></a>  CAtlBaseModule::CAtlBaseModule  
 コンストラクターです。  
  
```
CAtlBaseModule() throw();
```  
  
### <a name="remarks"></a>コメント  
 `CAtlBaseModule` を作成します。  
  
##  <a name="gethinstanceat"></a>  CAtlBaseModule::GetHInstanceAt  
 指定されたリソース インスタンスへのハンドルを返します。  
  
```
HINSTANCE GetHInstanceAt(int i) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *i*  
 リソース インスタンスの数。  
  
### <a name="return-value"></a>戻り値  
 リソースに対応するインスタンスが存在しない場合は、リソースのインスタンス、または NULL にハンドルを返します。  
  
##  <a name="getmoduleinstance"></a>  CAtlBaseModule::GetModuleInstance  
 モジュールのインスタンスを返します、`CAtlBaseModule`オブジェクト。  
  
```
HINSTANCE GetModuleInstance() throw();
```  
  
### <a name="return-value"></a>戻り値  
 モジュールのインスタンスを返します。  
  
##  <a name="getresourceinstance"></a>  CAtlBaseModule::GetResourceInstance  
 リソース インスタンスを返します。  
  
```
HINSTANCE GetResourceInstance() throw();
```  
  
### <a name="return-value"></a>戻り値  
 リソース インスタンスを返します。  
  
##  <a name="m_binitfailed"></a>  CAtlBaseModule::m_bInitFailed  
 モジュールの初期化が失敗したかどうかを示す変数です。  
  
```
static bool m_bInitFailed;
```  
  
### <a name="remarks"></a>コメント  
 True の場合、モジュールが初期化されて、false の初期化に失敗した場合。  
  
##  <a name="removeresourceinstance"></a>  CAtlBaseModule::RemoveResourceInstance  
 格納されているハンドルの一覧から、リソースのインスタンスを削除します。  
  
```
bool RemoveResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hInst`  
 削除するリソースのインスタンス。  
  
### <a name="return-value"></a>戻り値  
 場合、リソースが正常に削除された場合は false それ以外の場合は true を返します。  
  
##  <a name="setresourceinstance"></a>  CAtlBaseModule::SetResourceInstance  
 リソース インスタンスを設定、`CAtlBaseModule`オブジェクト。  
  
```
HINSTANCE SetResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hInst`  
 リソースの新しいインスタンス。  
  
### <a name="return-value"></a>戻り値  
 更新されたリソース インスタンスを返します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [モジュール クラス](../../atl/atl-module-classes.md)
