---
title: サービス マップ マクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_SERVICE_MAP
- atlcom/ATL::END_SERVICE_MAP
- atlcom/ATL::SERVICE_ENTRY
- atlcom/ATL::SERVICE_ENTRY_CHAIN
dev_langs:
- C++
ms.assetid: ca02a125-454a-4cf6-aac2-1c5585025ed4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2d2fa313c574951a8f8ba7c85d5b405707ec220
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364155"
---
# <a name="service-map-macros"></a>サービス マップ マクロ
これらのマクロは、サービス マップとエントリを定義します。  
  
|||  
|-|-|  
|[BEGIN_SERVICE_MAP](#begin_service_map)|ATL サービス マップの先頭をマークします。|  
|[END_SERVICE_MAP](#end_service_map)|ATL サービス マップの最後をマークします。|  
|[SERVICE_ENTRY](#service_entry)|オブジェクトが特定のサービス ID をサポートしていることを示します。|  
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|指示[IServiceProviderImpl::QueryService](#queryservice)を指定したオブジェクトのチェーン。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
   
##  <a name="begin_service_map"></a>  BEGIN_SERVICE_MAP  
 サービス マップの開始位置をマークします。  
  
```
BEGIN_SERVICE_MAP(theClass)
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 [in]サービス マップを含むクラスを指定します。  
  
### <a name="remarks"></a>コメント  
 サービス マップを使用して、COM オブジェクトにサービス プロバイダーの機能を実装します。 クラスを派生させる必要があります最初に、 [IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md)です。 エントリの 2 つの種類があります。  
  
- [SERVICE_ENTRY](#service_entry)指定したサービス ID (SID) のサポートを示します。  
  
- [SERVICE_ENTRY_CHAIN](#service_entry_chain)ように指示[IServiceProviderImpl::QueryService](#queryservice)チェーンして、指定した別のオブジェクトにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#57](../../atl/codesnippet/cpp/service-map-macros_1.h)]  
  
##  <a name="end_service_map"></a>  END_SERVICE_MAP  
 サービス マップの最後をマークします。  
  
```
END_SERVICE_MAP()
```  
  
### <a name="example"></a>例  
 例を参照して[BEGIN_SERVICE_MAP](#begin_service_map)です。  
  
##  <a name="service_entry"></a>  SERVICE_ENTRY  
 オブジェクトで指定したサービス id をサポートしていることを示します*SID*です。  
  
```
SERVICE_ENTRY( SID )
```  
  
### <a name="parameters"></a>パラメーター  
 *SID*  
 サービス id。  
  
### <a name="example"></a>例  
 例を参照して[BEGIN_SERVICE_MAP](#begin_service_map)です。  
  
##  <a name="service_entry_chain"></a>  SERVICE_ENTRY_CHAIN  
 指示[IServiceProviderImpl::QueryService](#queryservice)で指定されたオブジェクトへのチェーンを`punk`です。  
  
```
SERVICE_ENTRY_CHAIN( punk )
```  
  
### <a name="parameters"></a>パラメーター  
 `punk`  
 ポインター、 **IUnknown**をチェーンするインターフェイスです。  
  
### <a name="example"></a>例  
 例を参照して[BEGIN_SERVICE_MAP](#begin_service_map)です。  
  
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
 [[マクロ]](../../atl/reference/atl-macros.md)
