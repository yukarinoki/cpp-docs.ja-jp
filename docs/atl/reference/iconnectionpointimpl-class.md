---
title: IConnectionPointImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl::Advise
- ATLCOM/ATL::IConnectionPointImpl::EnumConnections
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionInterface
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionPointContainer
- ATLCOM/ATL::IConnectionPointImpl::Unadvise
- ATLCOM/ATL::IConnectionPointImpl::m_vec
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], implementing
- IConnectionPointImpl class
ms.assetid: 27992115-3b86-45dd-bc9e-54f32876c557
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf1f012067c3a3b85dd5168cf93521e4b2024e00
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884046"
---
# <a name="iconnectionpointimpl-class"></a>IConnectionPointImpl クラス
このクラスは、接続ポイントを実装します。  
  
## <a name="syntax"></a>構文  
  
```
template<class T, const IID* piid, class CDV = CComDynamicUnkArray>  
class ATL_NO_VTABLE IConnectionPointImpl : public _ICPLocator<piid>
```  
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス、`IConnectionPointImpl`します。  
  
 *piid*  
 コネクション ポイント オブジェクトによって表されるインターフェイスの IID へのポインター。  
  
 *CDV*  
 接続を管理するクラスです。 既定値は[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)接続を制限しないことができます。 使用することも[CComUnkArray](../../atl/reference/ccomunkarray-class.md)、固定接続数を指定します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IConnectionPointImpl::Advise](#advise)|接続ポイントとシンクの間の接続を確立します。|  
|[IConnectionPointImpl::EnumConnections](#enumconnections)|コネクション ポイントの接続を反復処理する列挙子を作成します。|  
|[IConnectionPointImpl::GetConnectionInterface](#getconnectioninterface)|接続ポイントによって表されるインターフェイスの IID を取得します。|  
|[IConnectionPointImpl::GetConnectionPointContainer](#getconnectionpointcontainer)|接続可能オブジェクトへのインターフェイス ポインターを取得します。|  
|[IConnectionPointImpl::Unadvise](#unadvise)|以前に確立した接続が終了した`Advise`します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[IConnectionPointImpl::m_vec](#m_vec)|コネクション ポイントの接続を管理します。|  
  
## <a name="remarks"></a>Remarks  
 `IConnectionPointImpl` クライアントへの送信インターフェイスを公開するオブジェクトを使用する接続ポイントを実装します。 クライアントは、シンクと呼ばれるオブジェクトのこのインターフェイスを実装します。  
  
 ATL を使用して[IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)接続可能オブジェクトを実装します。 接続可能オブジェクト内の各接続ポイントで識別される、アウトゴーイング インターフェイスを表す*piid*します。 クラス*CDV*接続ポイントとシンクの間の接続を管理します。 各接続は、「クッキー」によって一意に識別します。  
  
 ATL でのコネクション ポイントの使用に関する詳細については、記事を参照してください。[コネクション ポイント](../../atl/atl-connection-points.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `_ICPLocator`  
  
 `IConnectionPointImpl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcom.h  
  
##  <a name="advise"></a>  IConnectionPointImpl::Advise  
 接続ポイントとシンクの間の接続を確立します。  
  
```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```  
  
### <a name="remarks"></a>Remarks  
 使用[Unadvise](#unadvise)接続呼び出しを終了します。  
  
 参照してください[iconnectionpoint::advise](http://msdn.microsoft.com/library/windows/desktop/ms678815) Windows SDK にします。  
  
##  <a name="enumconnections"></a>  IConnectionPointImpl::EnumConnections  
 コネクション ポイントの接続を反復処理する列挙子を作成します。  
  
```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IConnectionPoint::EnumConnections](http://msdn.microsoft.com/library/windows/desktop/ms680755) Windows SDK にします。  
  
##  <a name="getconnectioninterface"></a>  IConnectionPointImpl::GetConnectionInterface  
 接続ポイントによって表されるインターフェイスの IID を取得します。  
  
```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IConnectionPoint::GetConnectionInterface](http://msdn.microsoft.com/library/windows/desktop/ms693468) Windows SDK にします。  
  
##  <a name="getconnectionpointcontainer"></a>  IConnectionPointImpl::GetConnectionPointContainer  
 接続可能オブジェクトへのインターフェイス ポインターを取得します。  
  
```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IConnectionPoint::GetConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms679669) Windows SDK にします。  
  
##  <a name="m_vec"></a>  IConnectionPointImpl::m_vec  
 コネクション ポイント オブジェクトとシンクの間の接続を管理します。  
  
```
CDV m_vec;
```     
  
### <a name="remarks"></a>Remarks  
 既定では、`m_vec`の種類は[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)します。  
  
##  <a name="unadvise"></a>  IConnectionPointImpl::Unadvise  
 以前に確立した接続が終了した[Advise](#advise)します。  
  
```
STDMETHOD(Unadvise)(DWORD dwCookie);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[:unadvise](http://msdn.microsoft.com/library/windows/desktop/ms686608) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318)   
 [クラスの概要](../../atl/atl-class-overview.md)
