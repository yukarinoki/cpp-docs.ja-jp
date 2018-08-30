---
title: IObjectWithSiteImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl::GetSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetChildSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetSite
- ATLCOM/ATL::IObjectWithSiteImpl::m_spUnkSite
dev_langs:
- C++
helpviewer_keywords:
- IObjectWithSiteImpl class
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d4e2b1fe58ab7ea408438b703b9fe803996fa791
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219039"
---
# <a name="iobjectwithsiteimpl-class"></a>IObjectWithSiteImpl クラス
このクラスは、オブジェクトのサイトと通信を可能にするメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```  
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス、`IObjectWithSiteImpl`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IObjectWithSiteImpl::GetSite](#getsite)|インターフェイス ポインターのサイトを照会します。|  
|[IObjectWithSiteImpl::SetChildSite](#setchildsite)|オブジェクトは、サイトの`IUnknown`ポインター。|  
|[IObjectWithSiteImpl::SetSite](#setsite)|オブジェクトは、サイトの`IUnknown`ポインター。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[IObjectWithSiteImpl::m_spUnkSite](#m_spunksite)|サイトの管理`IUnknown`ポインター。|  
  
## <a name="remarks"></a>Remarks  
 [IObjectWithSite](/windows/desktop/api/ocidl/nn-ocidl-iobjectwithsite)インターフェイスにより、サイトと通信するオブジェクト。 クラス`IObjectWithSiteImpl`このインターフェイスの既定の実装を提供し、実装`IUnknown`ダンプ情報を送信することによってデバッグでのデバイスをビルドします。  
  
 `IObjectWithSiteImpl` 2 つの方法を指定します。 クライアントの最初の呼び出し`SetSite`、サイトを渡す`IUnknown`ポインター。 このポインターは、オブジェクト内に保存およびを呼び出すことによって後で取得できる`GetSite`します。  
  
 通常、派生クラスから`IObjectWithSiteImpl`するオブジェクトを作成する場合は、そのコントロールではありません。 コントロールからクラスを派生[IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)サイトのポインターも提供します。 両方のクラスを派生していない`IObjectWithSiteImpl`と`IOleObjectImpl`します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IObjectWithSite`  
  
 `IObjectWithSiteImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="getsite"></a>  IObjectWithSiteImpl::GetSite  
 クエリで識別されるインターフェイスへのポインターのサイト`riid`します。  
  
```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```  
  
### <a name="remarks"></a>Remarks  
 サイトでは、このインターフェイスをサポートする場合を使用して、ポインターが返されます。`ppvSite`します。 それ以外の場合、 `ppvSite` NULL に設定されます。  
  
 参照してください[IObjectWithSite::GetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-getsite) Windows SDK にします。  
  
##  <a name="m_spunksite"></a>  IObjectWithSiteImpl::m_spUnkSite  
 サイトの管理`IUnknown`ポインター。  
  
```
CComPtr<IUnknown> m_spUnkSite;
```  
  
### <a name="remarks"></a>Remarks  
 `m_spUnkSite` このポインターを呼び出すことによってを最初に受信[SetSite](#setsite)します。  
  
##  <a name="setchildsite"></a>  IObjectWithSiteImpl::SetChildSite  
 オブジェクトは、サイトの`IUnknown`ポインター。  
  
```
HRESULT SetChildSite(IUnknown* pUnkSite);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnkSite*  
 [in]ポインター、`IUnknown`このオブジェクトを管理するサイトのインターフェイス ポインター。 NULL の場合、オブジェクトを呼び出す必要があります`IUnknown::Release`既存のサイトがこの時点でオブジェクトいいえを認識できなくなり、サイトにします。  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
##  <a name="setsite"></a>  IObjectWithSiteImpl::SetSite  
 オブジェクトは、サイトの`IUnknown`ポインター。  
  
```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IObjectWithSite::SetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-setsite) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
