---
title: IServiceProviderImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl::QueryService
dev_langs:
- C++
helpviewer_keywords:
- IServiceProviderImpl class
- IServiceProvider interface, ATL implementation
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b1472fe5d952e93b45240128383db9fdec5b093
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363675"
---
# <a name="iserviceproviderimpl-class"></a>IServiceProviderImpl クラス
このクラスの既定の実装を提供する、`IServiceProvider`インターフェイスです。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class ATL_NO_VTABLE IServiceProviderImpl : public IServiceProvider
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IServiceProviderImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IServiceProviderImpl::QueryService](#queryservice)|作成または指定したサービスにアクセスして、サービスの指定したインターフェイスにインターフェイス ポインターを返します。|  
  
## <a name="remarks"></a>コメント  
 `IServiceProvider`インターフェイスは、その GUID で指定されたサービスを検索し、サービスで要求されたインターフェイスのインターフェイス ポインターを返します。 クラス`IServiceProviderImpl`このインターフェイスの既定の実装を提供します。  
  
 **IServiceProviderImpl** 1 つの方法を指定します: [QueryService](#queryservice)、これを作成または、指定したサービスにアクセスし、サービスの指定したインターフェイスにインターフェイス ポインターを返します。  
  
 `IServiceProviderImpl` 以降で、サービス マップを使用して[BEGIN_SERVICE_MAP](service-map-macros.md#begin_service_map)で終わる[END_SERVICE_MAP](service-map-macros.md#end_service_map)です。  
  
 サービス マップには、2 つのエントリが含まれています: [SERVICE_ENTRY](service-map-macros.md#service_entry)、オブジェクトでサポートされている、指定したサービス id (SID) を示すと[SERVICE_ENTRY_CHAIN](service-map-macros.md#service_entry_chain)、どの呼び出し`QueryService`を別のチェーンをオブジェクト。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IServiceProvider`  
  
 `IServiceProviderImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="queryservice"></a>  IServiceProviderImpl::QueryService  
 作成または指定したサービスにアクセスして、サービスの指定したインターフェイスにインターフェイス ポインターを返します。  
  
```
STDMETHOD(QueryService)(
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>パラメーター  
 [IN] `guidService`  
 サービス識別子 (SID) へのポインター。  
  
 [IN] `riid`  
 呼び出し元がアクセスするためをインターフェイスの識別子。  
  
 [出力]. `ppvObj`  
 要求されたインターフェイスへの間接ポインター。  
  
### <a name="return-value"></a>戻り値  
 返された`HRESULT`値は、次のいずれか。  
  
|戻り値|説明|  
|------------------|-------------|  
|S_OK|サービスが正常に作成または取得します。|  
|E_INVALIDARG|1 つ以上の引数が無効です。|  
|E_OUTOFMEMORY|メモリは、サービスを作成するための十分ながありません。|  
|E_UNEXPECTED|不明なエラーが発生しました。|  
|E_NOINTERFACE|要求されたインターフェイスは、このサービスの一部ではないか、サービスが不明です。|  
  
### <a name="remarks"></a>コメント  
 `QueryService` 指定されたサービスで要求されたインターフェイスへの間接ポインターを返します。 呼び出し元が必要でなくなったときにこのポインターを解放するためです。  
  
 呼び出すと`QueryService`、両方のサービス識別子を渡す ( `guidService`) とインターフェイス識別子 ( `riid`)。 `guidService` 、アクセス サービスを指定し、`riid`サービスの一部であるインターフェイスを識別します。 代わりに、インターフェイスへの間接ポインターが表示されます。  
  
 インターフェイスを実装するオブジェクトは、他のサービスの一部であるインターフェイスを実装も可能性があります。 次に例を示します。  
  
-   これらのインターフェイスの一部は、省略可能な可能性があります。 サービスの説明で定義されていないすべてのインターフェイスはサービスのすべての実装、またはすべての返されたオブジェクトで必ずしも存在します。  
  
-   呼び出しとは異なり`QueryInterface`、さまざまなサービス識別子を渡すことが必ずしも別のコンポーネント オブジェクト モデル (COM) オブジェクトが返されることです。  
  
-   返されたオブジェクトは、サービスの定義の一部ではない追加のインターフェイスがあります。  
  
 SID_SMyService SID_SYourService などの 2 つの異なるサービス両方を指定できます、同じインターフェイスの使用、インターフェイスの実装には、2 つのサービス間で共通の何もいる場合でも。 この動作を呼び出す`QueryService`よりも、別のオブジェクトを返すことができます (SID_SMyService、IID_IDispatch) `QueryService` (SID_SYourService、IID_IDispatch)。 オブジェクト id は、さまざまなサービス識別子を指定するときにないと見なされます。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
